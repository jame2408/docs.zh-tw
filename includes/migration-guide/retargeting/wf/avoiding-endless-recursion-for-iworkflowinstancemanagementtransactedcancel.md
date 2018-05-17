### <a name="avoiding-endless-recursion-for-iworkflowinstancemanagementtransactedcancel-and-iworkflowinstancemanagementtransactedterminate"></a><span data-ttu-id="eeb1a-101">避免 IWorkflowInstanceManagement.TransactedCancel 與 IWorkflowInstanceManagement.TransactedTerminate 的無止盡遞迴</span><span class="sxs-lookup"><span data-stu-id="eeb1a-101">Avoiding endless recursion for IWorkflowInstanceManagement.TransactedCancel and IWorkflowInstanceManagement.TransactedTerminate</span></span>

|   |   |
|---|---|
|<span data-ttu-id="eeb1a-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="eeb1a-102">Details</span></span>|<span data-ttu-id="eeb1a-103">在某些情況下，若使用 <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedCancel%2A?displayProperty=nameWithType> 或 <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedTerminate%2A?displayProperty=nameWithType> API 取消或終止工作流程服務執行個體，當 <code>Workflow</code> 執行階段因為處理要求的過程，而嘗試保有該服務執行個體時，工作流程執行個體可能會出現因為無止盡遞迴而發生堆疊溢位。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-103">Under some circumstances when using <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedCancel%2A?displayProperty=nameWithType> or <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedTerminate%2A?displayProperty=nameWithType> APIs to cancel or terminate a worklow service instance, the workflow instance may encounter a stack overflow due to endless recursion when the <code>Workflow</code> runtime attempts to persist the service instance as part of processing the request.</span></span> <span data-ttu-id="eeb1a-104">若工作流程執行個體的狀態是正在等待某些其他未完成的 WCF 要求進入至另一個服務才能完成，就會發生此問題。作業 <code>TransactedCancel</code> 和 <code>TransactedTerminate</code> 會為該工作流程服務執行個體，建立已排入佇列的工作項目。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-104">The problem occurs if the workflow instance is in a state where it is waiting for some other outstanding WCF request to another service to complete.The <code>TransactedCancel</code> and <code>TransactedTerminate</code> operations create work items that are queued for the workflow service instance.</span></span> <span data-ttu-id="eeb1a-105">處理 <code>TransactedCancel/TransactedTerminate</code> 要求的過程中，不會執行這些工作項目。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-105">These work items are not executed as part of the processing of the <code>TransactedCancel/TransactedTerminate</code> request.</span></span> <span data-ttu-id="eeb1a-106">因為工作流程服務執行個體正忙於等候其他未完成的 WCF 要求完成，所以建立的工作項目會維持在佇列中。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-106">Because the workflow service instance is busy waiting for the other outstanding WCF request to complete, the work item created remains queued.</span></span> <span data-ttu-id="eeb1a-107"><code>TransactedCancel/TransactedTerminate</code> 作業已完成，且控制權已回到用戶端。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-107">The <code>TransactedCancel/TransactedTerminate</code> operation completes and control is returned back to the client.</span></span> <span data-ttu-id="eeb1a-108">當交易與嘗試認可的 <code>TransactedCancel/TransactedTerminate</code> 作業相關聯時，它需要保有該工作流程服務執行個體的狀態。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-108">When the transaction associated with the <code>TransactedCancel/TransactedTerminate</code> operation attempts to commit, it needs to persist the workflow serivce instance state.</span></span> <span data-ttu-id="eeb1a-109">但因為執行個體仍有未完成的 <code>WCF</code>要求，所以工作流程執行階段無法保有該工作流程服務執行個體，因而發生無止盡的遞迴迴圈而導致堆疊溢位。因為 <code>TransactedCancel</code> 與 <code>TransactedTerminate</code> 只會在記憶體中建立工作項目，所以交易存在的事實並沒有任何影響。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-109">But because there is an outstanding <code>WCF</code> request for the instance, the Workflow runtime cannot persist the workflow service instance, and an endless recursion loop leads to the stack overflow.Because <code>TransactedCancel</code> and <code>TransactedTerminate</code> only create a work item in memory, the fact that a transaction exists doesn't have any effect.</span></span> <span data-ttu-id="eeb1a-110">復原交易並不會捨棄該工作項目。為解決此問題，從 .NET Framework 4.7.2 起已引進了 <code>AppSetting</code>，其可新增至工作流程服務的 <code>web.config/app.config</code>，告知它可忽略 <code>TransactedCancel</code> 與 <code>TransactedTerminate</code> 的交易。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-110">A rollback of the transaction does not discard the work item.To address this issue, starting in .NET Framework 4.7.2, we have introduced an <code>AppSetting</code> that can be added to the <code>web.config/app.config</code> of the workflow service that tells it to ignore transactions for <code>TransactedCancel</code> and <code>TransactedTerminate</code>.</span></span> <span data-ttu-id="eeb1a-111">如此即可讓交易在無須等待要保有工作流程執行個體的情況下進行認可。此功能的 AppSetting 名稱為 <code>microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate</code>。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-111">This allows the transaction to commit without waiting for the workflow instance to persist.The AppSetting for this feature is named <code>microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate</code>.</span></span> <span data-ttu-id="eeb1a-112">值 <code>true</code> 表示應忽略該交易，以避免堆疊溢位。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-112">A value of <code>true</code> indicates that the transaction should be ignored, thus avoiding the stack overflow.</span></span> <span data-ttu-id="eeb1a-113">此 AppSetting 的預設值為 <code>false</code>，因此不會影響現有的工作流程服務執行個體。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-113">The default value of this AppSetting is <code>false</code>, so existing workflow service instances are not affected.</span></span>|
|<span data-ttu-id="eeb1a-114">建議</span><span class="sxs-lookup"><span data-stu-id="eeb1a-114">Suggestion</span></span>|<span data-ttu-id="eeb1a-115">若目前使用 AppFabric 或另一個 <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> 用戶端，且在嘗試取消或終止工作流程執行個體時，在工作流程服務執行個體中發生了堆疊溢位，您可以將下列內容加入工作流程服務的 web.config/app.config 檔案之 <code>&lt;appSettings&gt;</code> 區段中：</span><span class="sxs-lookup"><span data-stu-id="eeb1a-115">If you are using AppFabric or another <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> client and are encountering a stack overflow in the workflow serivce instance when trying to cancel or terminate a workflow instance, you can add the following to the <code>&lt;appSettings&gt;</code> section of the web.config/app.config file for the workflow service:</span></span><pre><code class="lang-xml">&lt;add key=&quot;microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate&quot; value=&quot;true&quot;/&gt;&#13;&#10;</code></pre><span data-ttu-id="eeb1a-116">若未遇到問題，則不需要執行這項動作。</span><span class="sxs-lookup"><span data-stu-id="eeb1a-116">If you are not encountering the problem, you do not need to do this.</span></span>|
|<span data-ttu-id="eeb1a-117">範圍</span><span class="sxs-lookup"><span data-stu-id="eeb1a-117">Scope</span></span>|<span data-ttu-id="eeb1a-118">Edge</span><span class="sxs-lookup"><span data-stu-id="eeb1a-118">Edge</span></span>|
|<span data-ttu-id="eeb1a-119">版本</span><span class="sxs-lookup"><span data-stu-id="eeb1a-119">Version</span></span>|<span data-ttu-id="eeb1a-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="eeb1a-120">4.7.2</span></span>|
|<span data-ttu-id="eeb1a-121">類型</span><span class="sxs-lookup"><span data-stu-id="eeb1a-121">Type</span></span>|<span data-ttu-id="eeb1a-122">正在重定目標</span><span class="sxs-lookup"><span data-stu-id="eeb1a-122">Retargeting</span></span>|

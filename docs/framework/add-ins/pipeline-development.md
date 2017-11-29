---
title: "管線開發"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4991fc65a48d620d30d09c44f1a30c2d1839071e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="pipeline-development"></a><span data-ttu-id="aa7a2-102">管線開發</span><span class="sxs-lookup"><span data-stu-id="aa7a2-102">Pipeline Development</span></span>
<span data-ttu-id="aa7a2-103">增益集管線是主應用程式和增益集必須用來與對方進行通訊管線區段的路徑。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-103">The add-in pipeline is the path of pipeline segments that the host application and its add-in must use to communicate with each other.</span></span>  
  
 <span data-ttu-id="aa7a2-104">下圖顯示的通訊管線及其區段。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-104">The following illustration shows the communication pipeline and its segments.</span></span>  
  
 <span data-ttu-id="aa7a2-105">![新增 &#45; 管線模型中。] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span><span class="sxs-lookup"><span data-stu-id="aa7a2-105">![Add&#45;in pipeline model.](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span></span>  
<span data-ttu-id="aa7a2-106">增益集管線</span><span class="sxs-lookup"><span data-stu-id="aa7a2-106">Add-in pipeline</span></span>  
  
 <span data-ttu-id="aa7a2-107">主機應用程式管線的一端與增益集的另一端。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-107">The host application is at one end of the pipeline and the add-in is at the other end.</span></span> <span data-ttu-id="aa7a2-108">從每一個結尾開始，而且移動中間，主應用程式和增益集已定義檢視的物件模型，它們都共用的抽象基底類別。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-108">Starting from each end and moving toward the middle, both the host application and the add-in have an abstract base class that defines a view of the object model that they both share.</span></span> <span data-ttu-id="aa7a2-109">這些型別 （類別） 會構成檢視增益集管線區段和增益集管線區段的 [主機] 檢視。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-109">These types (classes) make up the add-in view pipeline segment and the host view of the add-in pipeline segment.</span></span> <span data-ttu-id="aa7a2-110">檢視增益集管線區段通常會包含一個以上的抽象類別，但是加入在繼承自的類別就所謂的增益集基底。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-110">The add-in view pipeline segment often contains more than one abstract class but the class that the add-in inherits from is known as the add-in base.</span></span>  
  
 <span data-ttu-id="aa7a2-111">增益集端配接器管線區段，主應用程式端配接器管線區段轉換類型，其檢視管線區段與合約管線區段之間的流量。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-111">The add-in-side adapter pipeline segment and the host-side adapter pipeline segment convert the flow of types between their view pipeline segments and the contract pipeline segment.</span></span> <span data-ttu-id="aa7a2-112">管線的中央區段是衍生自合約<xref:System.AddIn.Contract.IContract>介面。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-112">The central segment of the pipeline is a contract that is derived from the <xref:System.AddIn.Contract.IContract> interface.</span></span> <span data-ttu-id="aa7a2-113">這個合約會定義主應用程式和其增益集將會同時使用的方法。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-113">This contract defines the methods that the host application and its add-in will both use.</span></span>  
  
 <span data-ttu-id="aa7a2-114">如果成個別的應用程式定義域中載入主機和增益集，您必須隔離界限分隔主應用程式範圍從增益集的範圍。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-114">If you load the host and the add-in into separate application domains, you have an isolation boundary that separates the scope of the host application from the scope of the add-in.</span></span> <span data-ttu-id="aa7a2-115">合約是只有主機和增益集應用程式定義域中載入的組件。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-115">The contract is the only assembly that is loaded in both the host and add-in application domains.</span></span> <span data-ttu-id="aa7a2-116">主機和中的每個參考其檢視的合約方法。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-116">The host and the add-in each refer only to their view of the contract methods.</span></span> <span data-ttu-id="aa7a2-117">因此，它們被分隔的從合約的抽象層。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-117">Therefore, they are separated by a layer of abstraction from the contract.</span></span>  
  
 <span data-ttu-id="aa7a2-118">若要開發管線區段，您必須建立包含它們的目錄結構。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-118">To develop pipeline segments, you must create a directory structure that will contain them.</span></span> <span data-ttu-id="aa7a2-119">如需開發需求與範圍的指導方針的詳細資訊，請參閱[管線開發需求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-119">For more information about development requirements and scope guidelines, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
 <span data-ttu-id="aa7a2-120">下圖顯示管線區段所組成的類型。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-120">The following illustration shows the types that make up the pipeline segments.</span></span> <span data-ttu-id="aa7a2-121">在圖例中顯示的型別名稱是任意的但主機和主機以外的所有類型都檢視的增益集需要屬性，所以建構資訊存放區的方法可以找到它們。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-121">The names of the types shown in the illustration are arbitrary, but all types except for the host and the host view of the add-in require attributes so they can be discovered by methods that construct an information store.</span></span>  
  
 <span data-ttu-id="aa7a2-122">![新增 &#45; 所需屬性的型別與模型中。] (../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")</span><span class="sxs-lookup"><span data-stu-id="aa7a2-122">![Add&#45;in model with required attributes on types.](../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")</span></span>  
<span data-ttu-id="aa7a2-123">具有類型的增益集管線</span><span class="sxs-lookup"><span data-stu-id="aa7a2-123">Add-in pipeline with types</span></span>  
  
 <span data-ttu-id="aa7a2-124">下表描述用於啟用增益集管線區段。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-124">The following table describes the pipeline segments for activating an add-in.</span></span> <span data-ttu-id="aa7a2-125">如需有關這些區段的詳細資訊，請參閱[合約、 檢視和配接器](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-125">For more information about these segments, see [Contracts, Views, and Adapters](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c).</span></span>  
  
|<span data-ttu-id="aa7a2-126">管線區段</span><span class="sxs-lookup"><span data-stu-id="aa7a2-126">Pipeline segment</span></span>|<span data-ttu-id="aa7a2-127">描述</span><span class="sxs-lookup"><span data-stu-id="aa7a2-127">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="aa7a2-128">主機</span><span class="sxs-lookup"><span data-stu-id="aa7a2-128">Host</span></span>|<span data-ttu-id="aa7a2-129">建立增益集的執行個體應用程式組件。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-129">The application assembly that creates an instance of an add-in.</span></span>|  
|<span data-ttu-id="aa7a2-130">增益集的 [主機] 檢視</span><span class="sxs-lookup"><span data-stu-id="aa7a2-130">Host view of the add-in</span></span>|<span data-ttu-id="aa7a2-131">代表主應用程式檢視的物件類型和用來與增益集通訊的方法。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-131">Represents the host application's view of the object types and methods used to communicate with the add-in.</span></span> <span data-ttu-id="aa7a2-132">[主機] 檢視是一個抽象基底類別或介面。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-132">The host view is an abstract base class or interface.</span></span>|  
|<span data-ttu-id="aa7a2-133">主機端配接器</span><span class="sxs-lookup"><span data-stu-id="aa7a2-133">Host-side adapter</span></span>|<span data-ttu-id="aa7a2-134">會調整方法與合約具有一或多個類別的組件。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-134">An assembly with one or more classes that adapts methods to and from the contract.</span></span><br /><br /> <span data-ttu-id="aa7a2-135">這個管線區段由使用<xref:System.AddIn.Pipeline.HostAdapterAttribute>屬性。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-135">This pipeline segment is identified by using the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute.</span></span><br /><br /> <span data-ttu-id="aa7a2-136">不支援多模組組件。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-136">Multi-module assemblies are not supported.</span></span>|  
|<span data-ttu-id="aa7a2-137">合約</span><span class="sxs-lookup"><span data-stu-id="aa7a2-137">Contract</span></span>|<span data-ttu-id="aa7a2-138">衍生自介面<xref:System.AddIn.Contract.IContract>介面以及定義通訊類型主機和其增益集之間的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-138">An interface that is derived from the <xref:System.AddIn.Contract.IContract> interface and that defines the protocol for communicating types between the host and its add-in.</span></span><br /><br /> <span data-ttu-id="aa7a2-139">這個管線區段由設定<xref:System.AddIn.Pipeline.AddInContractAttribute>屬性。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-139">This pipeline segment is identified by setting the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>|  
|<span data-ttu-id="aa7a2-140">增益集端配接器</span><span class="sxs-lookup"><span data-stu-id="aa7a2-140">Add-in-side adapter</span></span>|<span data-ttu-id="aa7a2-141">會調整方法與合約具有一或多個類別的組件。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-141">An assembly with one or more classes that adapts methods to and from the contract.</span></span><br /><br /> <span data-ttu-id="aa7a2-142">這個管線區段由使用<xref:System.AddIn.Pipeline.AddInAdapterAttribute>屬性。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-142">This pipeline segment is identified by using the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute.</span></span><br /><br /> <span data-ttu-id="aa7a2-143">包含具有類型的增益集端配接器目錄中的每個組件<xref:System.AddIn.Pipeline.AddInAdapterAttribute>屬性載入增益集應用程式定義域。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-143">Each assembly in the add-in-side adapter directory that contains a type that has an <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute is loaded into the add-in's application domain.</span></span><br /><br /> <span data-ttu-id="aa7a2-144">新增在端的目錄中的每個組件會在它自己的應用程式定義域中載入。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-144">Each assembly in the add-in-side directory is loaded in its own application domain.</span></span><br /><br /> <span data-ttu-id="aa7a2-145">不支援多模組組件</span><span class="sxs-lookup"><span data-stu-id="aa7a2-145">Multi-module assemblies are not supported</span></span>|  
|<span data-ttu-id="aa7a2-146">增益集的檢視</span><span class="sxs-lookup"><span data-stu-id="aa7a2-146">Add-in view</span></span>|<span data-ttu-id="aa7a2-147">組件，表示增益集的檢視物件型別和方法，可用來與主機通訊。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-147">An assembly that represents the add-in's view of the object types and methods that are used to communicate with the host.</span></span> <span data-ttu-id="aa7a2-148">增益集檢視是一個抽象基底類別或介面。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-148">The add-in view is an abstract base class or interface.</span></span><br /><br /> <span data-ttu-id="aa7a2-149">這個管線區段由使用<xref:System.AddIn.Pipeline.AddInBaseAttribute>屬性。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-149">This pipeline segment is identified by using the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span><br /><br /> <span data-ttu-id="aa7a2-150">每個組件中包含具有類型的 AddInViews 目錄<xref:System.AddIn.Pipeline.AddInBaseAttribute>屬性載入增益集應用程式定義域。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-150">Each assembly in the AddInViews directory that contains a type that has an <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute is loaded into the add-in's application domain.</span></span>|  
|<span data-ttu-id="aa7a2-151">增益集</span><span class="sxs-lookup"><span data-stu-id="aa7a2-151">Add-in</span></span>|<span data-ttu-id="aa7a2-152">會執行服務，主應用程式具現化的類型。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-152">An instantiated type that performs a service for the host.</span></span>|  
  
## <a name="pipeline-activation-path"></a><span data-ttu-id="aa7a2-153">管線啟動路徑</span><span class="sxs-lookup"><span data-stu-id="aa7a2-153">Pipeline Activation Path</span></span>  
 <span data-ttu-id="aa7a2-154">下圖顯示類型的啟動時啟動增益集。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-154">The following illustration shows the activation of types when an add-in is activated.</span></span> <span data-ttu-id="aa7a2-155">它也會顯示物件的傳遞至主機，例如計算或物件的集合的結果。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-155">It also shows the passing of objects to the host, such as the results of a calculation or a collection of objects.</span></span> <span data-ttu-id="aa7a2-156">這是最常見的案例。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-156">This is the most typical scenario.</span></span>  
  
 <span data-ttu-id="aa7a2-157">![新增 &#45; 具有啟動路徑的模型中。] (../../../docs/framework/add-ins/media/addin6.png "AddIn6")</span><span class="sxs-lookup"><span data-stu-id="aa7a2-157">![Add&#45;in model with activation path.](../../../docs/framework/add-ins/media/addin6.png "AddIn6")</span></span>  
<span data-ttu-id="aa7a2-158">從增益集的啟動路徑至主機</span><span class="sxs-lookup"><span data-stu-id="aa7a2-158">Activation path from the add-in to the host</span></span>  
  
 <span data-ttu-id="aa7a2-159">管線的啟動路徑，就會發生，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa7a2-159">The activation path of the pipeline occurs as follows:</span></span>  
  
1.  <span data-ttu-id="aa7a2-160">主應用程式會啟動增益集與<xref:System.AddIn.Hosting.AddInToken.Activate%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-160">The host application activates the add-in with the <xref:System.AddIn.Hosting.AddInToken.Activate%2A> method.</span></span>  
  
2.  <span data-ttu-id="aa7a2-161">增益集，增益集的檢視、 新增在端配接器和合約組件會載入增益集應用程式定義域。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-161">The add-in, add-in view, add-in-side adapter, and the contract assemblies are loaded into the add-in's application domain.</span></span>  
  
3.  <span data-ttu-id="aa7a2-162">使用 [增益集] 檢視來建立增益集端配接器執行個體 (所識別的類別與<xref:System.AddIn.Pipeline.AddInBaseAttribute>屬性) 當做其建構函式。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-162">An instance of the add-in-side adapter is created using the add-in view (with the class identified by the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute) as its constructor.</span></span> <span data-ttu-id="aa7a2-163">增益集端配接器，繼承自該合約。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-163">The add-in-side adapter inherits from the contract.</span></span>  
  
4.  <span data-ttu-id="aa7a2-164">增益集端配接器，其為合約型別 （選擇性） 隔離界限之間傳遞至主應用程式端配接器的建構函式。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-164">The add-in-side adapter, which is typed as the contract, is passed across the (optional) isolation boundary to the host-side adapter's constructor.</span></span>  
  
5.  <span data-ttu-id="aa7a2-165">主機的應用程式定義域載入增益集，主應用程式端配接器，以及合約組件的 [主機] 檢視。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-165">The host view of the add-in, host-side adapter, and the contract assemblies are loaded into the host's application domain.</span></span>  
  
6.  <span data-ttu-id="aa7a2-166">建立主應用程式端配接器執行個體當做其建構函式中使用合約。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-166">An instance of the host-side adapter is created using the contract as its constructor.</span></span> <span data-ttu-id="aa7a2-167">主機端配接器會繼承自增益集的 [主機] 檢視。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-167">The host-side adapter inherits from the host view of the add-in.</span></span>  
  
7.  <span data-ttu-id="aa7a2-168">主機具有增益集，其中型別為主機檢視的增益集，而且可以繼續呼叫其方法。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-168">The host has the add-in, which is typed as the host view of the add-in, and can continue calling its methods.</span></span>  
  
## <a name="walkthroughs"></a><span data-ttu-id="aa7a2-169">逐步解說</span><span class="sxs-lookup"><span data-stu-id="aa7a2-169">Walkthroughs</span></span>  
 <span data-ttu-id="aa7a2-170">有三個逐步解說主題描述如何建立管線使用 Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="aa7a2-170">There are three walkthrough topics that describe how to create pipelines using Visual Studio:</span></span>  
  
-   [<span data-ttu-id="aa7a2-171">逐步解說： 建立可延伸應用程式</span><span class="sxs-lookup"><span data-stu-id="aa7a2-171">Walkthrough: Creating an Extensible Application</span></span>](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     <span data-ttu-id="aa7a2-172">描述主控件執行加法、 減法、 乘法和除法計算的計算機增益集。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-172">Describes a calculator add-in that performs addition, subtraction, multiplication, and divsion calculations for the host.</span></span>  
  
-   [<span data-ttu-id="aa7a2-173">逐步解說： 啟用主機變更為回溯相容性</span><span class="sxs-lookup"><span data-stu-id="aa7a2-173">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     <span data-ttu-id="aa7a2-174">說明 [小算盤] 增益集與計算增強的功能，以及如何維護與第一個計算機增益集的相容性。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-174">Describes a calculator add-in with enhanced calculation capabilities, and how to maintain compatibility with the first calculator add-in.</span></span>  
  
-   [<span data-ttu-id="aa7a2-175">主控件與增益集之間的逐步解說： 傳遞集合</span><span class="sxs-lookup"><span data-stu-id="aa7a2-175">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     <span data-ttu-id="aa7a2-176">描述如何通過管線使用案例的資料集合。</span><span class="sxs-lookup"><span data-stu-id="aa7a2-176">Describes how to pass data collections over the pipeline using a book store scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa7a2-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aa7a2-177">See Also</span></span>  
 [<span data-ttu-id="aa7a2-178">增益集管線案例</span><span class="sxs-lookup"><span data-stu-id="aa7a2-178">Add-in Pipeline Scenarios</span></span>](http://msdn.microsoft.com/en-us/feb70e0b-8734-494c-aeaf-b567f014043e)  
 [<span data-ttu-id="aa7a2-179">增益集和擴充性</span><span class="sxs-lookup"><span data-stu-id="aa7a2-179">Add-ins and Extensibility</span></span>](../../../docs/framework/add-ins/index.md)
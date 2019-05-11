---
title: ポートの種類を操作する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, port types
- port types, deleting
- port types, Web
- port types, request-response
- orchestrations, ports
- port types, modifier
- port types
- ports, port types
- port types, one-way
ms.assetid: 78ac731e-c330-4888-a9ee-10523fef8ed0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace5ba21f0e7615e2db9ecc192e696b229a0f3ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332881"
---
# <a name="how-to-work-with-port-types"></a><span data-ttu-id="47d41-102">ポートの種類を操作する方法</span><span class="sxs-lookup"><span data-stu-id="47d41-102">How to Work with Port Types</span></span>
<span data-ttu-id="47d41-103">ポートの種類は、通信方式、一連の操作 (要求または応答)、およびこれらの操作のメッセージの種類で構成されます。</span><span class="sxs-lookup"><span data-stu-id="47d41-103">A port type consists of a communication pattern, a set of operations (requests or responses), and the message types that those operations can work on.</span></span> <span data-ttu-id="47d41-104">パターンは、いずれか一方向または要求-応答 (双方向)、およびそのポートの種類で定義されているすべての操作は、同じパターンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47d41-104">The pattern can be either one-way or request-response (two-way), and all operations defined on that port type must use the same pattern.</span></span> <span data-ttu-id="47d41-105">ポートの種類は、方向に依存しない: 個々 のポートの方向を指定します。</span><span class="sxs-lookup"><span data-stu-id="47d41-105">Note that port types are direction-agnostic: direction is specified on individual ports.</span></span>  
  
 <span data-ttu-id="47d41-106">ポートの種類のスコープがによって定義されている、**型修飾子**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="47d41-106">The scope of a port type is defined by the **Type Modifier** property.</span></span> <span data-ttu-id="47d41-107">ポートの種類は、パブリック、プライベート、または内部にあります。</span><span class="sxs-lookup"><span data-stu-id="47d41-107">A port type can be public, private, or internal.</span></span> <span data-ttu-id="47d41-108">パブリックの場合は、オーケストレーションと対話するすべてのユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="47d41-108">If it is public, it is visible to anyone interacting with the orchestration.</span></span> <span data-ttu-id="47d41-109">プライベートの場合は、同じプロジェクトおよび名前空間内の他のオーケストレーションに表示します。</span><span class="sxs-lookup"><span data-stu-id="47d41-109">If it is private, it is visible to other orchestrations within the same project and namespace.</span></span> <span data-ttu-id="47d41-110">内部ポートの種類が、プロジェクト内でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="47d41-110">If it is internal, the port type is visible only within the project.</span></span> <span data-ttu-id="47d41-111">ポートの種類の定義には、メッセージの種類が含まれているために、メッセージの種類のスコープはそれを使用するポートの種類の包含する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47d41-111">Since a port type definition includes message types, the scope of the message type must encompass that of any port type that uses it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47d41-112">ポートの種類は、任意の数のポートに適用できます。</span><span class="sxs-lookup"><span data-stu-id="47d41-112">A port type can be applied to any number of ports.</span></span> <span data-ttu-id="47d41-113">ポート、ポートの種類のインスタンスとして考えることができます。</span><span class="sxs-lookup"><span data-stu-id="47d41-113">You can think of a port as an instance of a port type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47d41-114">ポートの種類は本質的に通信方向; がありません。個々 のポートでは、方向を設定します。</span><span class="sxs-lookup"><span data-stu-id="47d41-114">A port type does not inherently have a communication direction; you set direction on individual ports.</span></span>  
  
### <a name="to-add-a-request-response-port-type"></a><span data-ttu-id="47d41-115">要求-応答ポートの種類を追加するには</span><span class="sxs-lookup"><span data-stu-id="47d41-115">To add a request-response port type</span></span>  
  
1.  <span data-ttu-id="47d41-116">オーケストレーションの種類 ウィンドウで、右クリック**ポートの種類** をクリックし、**新しい要求-応答ポートの種類**します。</span><span class="sxs-lookup"><span data-stu-id="47d41-116">In the Orchestration View window, right-click **Port Types** and then click **New Request-response Port Type**.</span></span>  
  
     <span data-ttu-id="47d41-117">**ポートの種類**が折りたたまれている場合、ノードを展開し、1 つの既定の操作と共に新しい要求-応答ポートの種類が追加されます。</span><span class="sxs-lookup"><span data-stu-id="47d41-117">The **Port Types** node expands, if collapsed, and a new request-response port type is added with one default operation.</span></span>  
  
2.  <span data-ttu-id="47d41-118">ポートの種類の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="47d41-118">Specify a name for the port type.</span></span>  
  
3.  <span data-ttu-id="47d41-119">1 つまたは複数のポート操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="47d41-119">Define one or more port operations.</span></span>  
  
     <span data-ttu-id="47d41-120">ポートの操作で、名前を指定できますが、「要求」と「応答します」としてのみ表示されますと、別のプロジェクトから、それらを選択するとは、</span><span class="sxs-lookup"><span data-stu-id="47d41-120">You can name your port operations, but when you are selecting them from another project, you will see them only as "Request" and "Response."</span></span> <span data-ttu-id="47d41-121">別のプロジェクトからポート操作を選択する場合は、正しいメッセージ型を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="47d41-121">If you select a port operation from another project, verify that it has the correct message type.</span></span>  
  
### <a name="to-add-a-one-way-port-type"></a><span data-ttu-id="47d41-122">一方向のポートの種類を追加するには</span><span class="sxs-lookup"><span data-stu-id="47d41-122">To add a one-way port type</span></span>  
  
1.  <span data-ttu-id="47d41-123">オーケストレーションの種類 ウィンドウで、右クリック**ポートの種類**し**新しい一方向ポートの種類**します。</span><span class="sxs-lookup"><span data-stu-id="47d41-123">In the Orchestration View window, right-click **Port Types** and then click **New One-way Port Type**.</span></span>  
  
     <span data-ttu-id="47d41-124">**ポートの種類**が折りたたまれている場合、ノードを展開し、1 つの既定の操作と共に新しい一方向のポートの種類が追加されます。</span><span class="sxs-lookup"><span data-stu-id="47d41-124">The **Port Types** node expands, if collapsed, and a new one-way port type is added with one default operation.</span></span>  
  
2.  <span data-ttu-id="47d41-125">ポートの種類の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="47d41-125">Specify a name for the port type.</span></span>  
  
3.  <span data-ttu-id="47d41-126">1 つまたは複数のポート操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="47d41-126">Define one or more port operations.</span></span>  
  
### <a name="to-add-a-web-port-type"></a><span data-ttu-id="47d41-127">Web ポートの種類を追加するには</span><span class="sxs-lookup"><span data-stu-id="47d41-127">To add a Web port type</span></span>  
  
-   <span data-ttu-id="47d41-128">Web サービスのプロキシ クラスを含むアセンブリへの参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="47d41-128">Add a project reference to an assembly containing a proxy class for a Web service.</span></span> <span data-ttu-id="47d41-129">詳細については、次を参照してください。 [Web ポートの作成](../core/creating-web-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="47d41-129">For more information, see [Creating Web Ports](../core/creating-web-ports.md).</span></span>  
  
### <a name="to-remove-a-port-type"></a><span data-ttu-id="47d41-130">ポートの種類を削除するには</span><span class="sxs-lookup"><span data-stu-id="47d41-130">To remove a port type</span></span>  
  
-   <span data-ttu-id="47d41-131">オーケストレーションの種類 ウィンドウでクリックして、削除するポートの種類を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="47d41-131">In the Orchestration View window, right-click the port type to delete, and then click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47d41-132">ポートの種類が使用中の場合は、削除すると、それを使用して構成されているポートの構成は影響します。</span><span class="sxs-lookup"><span data-stu-id="47d41-132">If the port type is in use, deleting it will impact the configuration of any ports that are configured to use it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47d41-133">読み取り専用として表示される項目は、別のオーケストレーションで定義されています。</span><span class="sxs-lookup"><span data-stu-id="47d41-133">Items that appear as read-only are defined in another orchestration.</span></span>  
  
### <a name="to-set-the-type-modifier-for-a-port-type"></a><span data-ttu-id="47d41-134">ポートの種類の型修飾子を設定するには</span><span class="sxs-lookup"><span data-stu-id="47d41-134">To set the type modifier for a port type</span></span>  
  
-   <span data-ttu-id="47d41-135">[プロパティ] ウィンドウでは、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="47d41-135">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="47d41-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="47d41-136">Property</span></span>|<span data-ttu-id="47d41-137">説明</span><span class="sxs-lookup"><span data-stu-id="47d41-137">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="47d41-138">型修飾子</span><span class="sxs-lookup"><span data-stu-id="47d41-138">Type Modifier</span></span>|<span data-ttu-id="47d41-139">ポートの種類のスコープを決定します。</span><span class="sxs-lookup"><span data-stu-id="47d41-139">Determines the scope of the port type:</span></span><br /><br /> <span data-ttu-id="47d41-140">プライベート-このポートの種類へのアクセスが含まれているモジュールに制限されています。</span><span class="sxs-lookup"><span data-stu-id="47d41-140">Private—Access to this port type is limited to the containing module.</span></span><br /><br /> <span data-ttu-id="47d41-141">公開-このポートの種類へのアクセスが制限されています。</span><span class="sxs-lookup"><span data-stu-id="47d41-141">Public—Access to this port type is not limited.</span></span><br /><br /> <span data-ttu-id="47d41-142">内部-このポートの種類へのアクセスは、同じプロジェクト内のモジュールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="47d41-142">Internal—Access to this port type is limited to modules within the same project.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47d41-143">参照</span><span class="sxs-lookup"><span data-stu-id="47d41-143">See Also</span></span>  
 <span data-ttu-id="47d41-144">[通信方式](../core/communication-pattern.md) </span><span class="sxs-lookup"><span data-stu-id="47d41-144">[Communication Pattern](../core/communication-pattern.md) </span></span>  
 <span data-ttu-id="47d41-145">[ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="47d41-145">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="47d41-146">オーケストレーションでのポートの使用</span><span class="sxs-lookup"><span data-stu-id="47d41-146">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)
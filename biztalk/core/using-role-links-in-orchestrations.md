---
title: オーケストレーションでロール リンクの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- role links
- roles, links
- roles
- roles, about roles
- role links, about role links
- role links, properties
- role links, initializing
ms.assetid: 0cf85544-12c9-4541-8925-61a6e946cce0
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e3c4e4a4c3a99fb6e1962299d440717eaa8d51b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288466"
---
# <a name="using-role-links-in-orchestrations"></a><span data-ttu-id="fbd2d-102">オーケストレーションでのロール リンクの使用</span><span class="sxs-lookup"><span data-stu-id="fbd2d-102">Using Role Links in Orchestrations</span></span>
<span data-ttu-id="fbd2d-103">ロール リンクは、オーケストレーションと取引先間の対話処理を抽象化したものです。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-103">Role links are a form of abstraction for the interactions between your orchestration and your trading partners.</span></span> <span data-ttu-id="fbd2d-104">ロール リンクを使用すると、ビジネス プロセス全体を維持したまま、取引先の解決、メッセージの内容、またはデータベースの検索結果に基づいて取引先を動的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-104">Role links enable you to dynamically choose which trading partner to interact with based on trading partner resolution, message content, or the results of a database lookup while maintaining your overall business process intact.</span></span>  
  
 <span data-ttu-id="fbd2d-105">たとえば、企業間取引のシナリオでは、複数の購入者、1 つの供給業者、および供給業者の商品を配送する複数の出荷業者が存在します。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-105">For example, in a business-to-business scenario, there are multiple buyers, a single supplier, and multiple shipping agencies for the supplier.</span></span> <span data-ttu-id="fbd2d-106">購入者が注文書を送信した場合、供給業者は、パーティの解決を通じてその購入者を特定し、適切な割引率を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-106">When a buyer sends a purchase order to the supplier, the supplier knows through party resolution which buyer is sending the purchase order and can apply the appropriate discount.</span></span> <span data-ttu-id="fbd2d-107">さらに、商品の配送を担当する出荷業者を、注文された商品に基づいて実行時に決定できます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-107">Moreover, based on the goods ordered, the supplier determines at run time which shipping agency will be in charge of the delivery.</span></span> <span data-ttu-id="fbd2d-108">各出荷業者は独自のトランスポート プロトコルを使用している可能性がありますが、供給業者は、実行時に同一のビジネス プロセスを使用してすべての出荷業者を処理し、どの出荷業者に配送を依頼するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-108">Although each shipping agency may have its own transport protocol, the supplier can use the same business process at run time to handle all the shipping agencies and determine which agency to interact with.</span></span> <span data-ttu-id="fbd2d-109">出荷業者は、トランスポート プロトコルを更新する場合、後の段階で、たとえば、FTP から HTTP へ — 供給業者がのみを BizTalk エクスプ ローラーまたは BizTalk Server 管理コンソールを使用して、その特定の出荷業者に関連付けられている送信ポートを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-109">At a later stage, if a shipping agency updates its transport protocol—for example, from FTP to HTTP—the supplier only needs to use BizTalk Explorer or the BizTalk Server Administration console to update the send port associated with that particular shipping agency.</span></span> <span data-ttu-id="fbd2d-110">オーケストレーションに格納されているビジネス プロセスを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-110">The supplier does not need to change its business process, which resides in the orchestration.</span></span>  
  
## <a name="roles"></a><span data-ttu-id="fbd2d-111">ロール</span><span class="sxs-lookup"><span data-stu-id="fbd2d-111">Roles</span></span>  
 <span data-ttu-id="fbd2d-112">オーケストレーションには次の 2 つのロールがあります。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-112">There are two roles in an orchestration:</span></span>  
  
-   <span data-ttu-id="fbd2d-113">メッセージを受信および処理する "実装" ロール。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-113">An "implements" role to receive and process messages.</span></span> <span data-ttu-id="fbd2d-114">このロールはプロバイダーとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-114">This role is also known as the provider.</span></span>  
  
-   <span data-ttu-id="fbd2d-115">メッセージを送信する "使用" ロール。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-115">A "uses" role to send messages.</span></span> <span data-ttu-id="fbd2d-116">このロールはコンシューマーとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-116">This role is also known as the consumer.</span></span>  
  
## <a name="role-links"></a><span data-ttu-id="fbd2d-117">ロール リンク</span><span class="sxs-lookup"><span data-stu-id="fbd2d-117">Role Links</span></span>  
 <span data-ttu-id="fbd2d-118">ロール リンクには、コンシューマー ロールとプロバイダー ロールのいずれか、またはその両方を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-118">A role link can include either a consumer or a provider role, or one of each.</span></span> <span data-ttu-id="fbd2d-119">コンシューマー ロールは、プロバイダー ロールによって提供されるサービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-119">A consumer role consumes the services provided by the provider role.</span></span> <span data-ttu-id="fbd2d-120">これらのロールのいずれかまたは両方を使用するロール リンクを定義する場合は、リンクしているパートナーによって補完ロールが適切に定義されていることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-120">When you define a role link with one or both of these roles, it is assumed that the complementary role is being fulfilled by the partner with whom you are linking.</span></span>  
  
 <span data-ttu-id="fbd2d-121">ロール リンクには、 **SourceParty** 、プロパティ、 **DestinationParty**プロパティ、およびイニシャライズ ロール。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-121">A role link has a **SourceParty** property, a **DestinationParty** property, and an initiating role.</span></span> <span data-ttu-id="fbd2d-122">イニシャライズ ロールは最初の通信が発生して、ロール リンクの値を設定して開始する、ロール、 **DestinationParty**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-122">An initiating role is the role on which the first communication occurs, and which therefore initiates the role link by setting the value of the **DestinationParty** property.</span></span>  
  
 <span data-ttu-id="fbd2d-123">イニシャライズ ロールが場合、コンシューマーのメッセージを送信するため、明示的に設定する、 **DestinationParty**オーケストレーションでのプロパティ (1 回、1 回だけ)。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-123">If the initiating role is a consumer for sending messages, you explicitly set the **DestinationParty** property (once and only once) in your orchestration.</span></span> <span data-ttu-id="fbd2d-124">値を設定するためには、 **DestinationParty**で、**式**ConfirmOrder がロール リンクの名前、PartnerName と OrganizationName が、次の例のように、図形パーティのパラメーター:</span><span class="sxs-lookup"><span data-stu-id="fbd2d-124">To do so, you set the value of the **DestinationParty** in the **Expression** shape, as in the following example, where ConfirmOrder is the name of a role link, and PartnerName and OrganizationName are parameters of a party:</span></span>  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 <span data-ttu-id="fbd2d-125">イニシャライズ ロールがプロバイダーの場合、メッセージの受信、 **DestinationParty**プロパティは、受信側によって自動的に初期化します。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-125">If the initiating role is a provider for receiving messages, the **DestinationParty** property is initialized automatically by the receiver.</span></span> <span data-ttu-id="fbd2d-126">**DestinationParty**プロバイダー自体に設定されています。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-126">The **DestinationParty** is set to the provider itself.</span></span> <span data-ttu-id="fbd2d-127">**SourceParty**プロパティは読み取り専用、およびセキュリティ識別子 (SID) 送信者のまたはパーティに関連付けられている証明書に基づいてパーティ名を解決するのには信頼されているパイプライン コンポーネントを通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-127">The **SourceParty** property is read-only, and is supplied through a trusted pipeline component to resolve the party name based on the security identifier (SID) of the sender or on a certificate associated with the party.</span></span> <span data-ttu-id="fbd2d-128">パイプライン コンポーネントを実行しているホストとしてマークする必要があります**信頼されている認証**です。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-128">The host running the pipeline component must be marked as **Authentication Trusted**.</span></span> <span data-ttu-id="fbd2d-129">値を取得することができます、 **SourceParty**で、**式**次のサンプル コードを使用して図形。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-129">You can get the value of the **SourceParty** in the **Expression** shape by using the following sample code:</span></span>  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a><span data-ttu-id="fbd2d-130">ロール リンクの種類</span><span class="sxs-lookup"><span data-stu-id="fbd2d-130">Role Link Types</span></span>  
 <span data-ttu-id="fbd2d-131">ロール リンクは、ロール リンクの種類のインスタンスであり、単一のロールまたは 2 つのロールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-131">A role link is an instance of a role link type, which consists of either one or two roles.</span></span> <span data-ttu-id="fbd2d-132">ロール リンクの種類を使用する場合は、次の点を考慮します。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-132">When working with a role link type, consider the following:</span></span>  
  
-   <span data-ttu-id="fbd2d-133">単一のロールで構成されるロール リンクでは、指定したポートの種類を参照できるのは、一度だけです。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-133">You can refer only once to any given port type within a single role link type.</span></span>  
  
-   <span data-ttu-id="fbd2d-134">ロール リンクの種類の定義にポートの種類が含まれるので、ポートの種類のスコープは、関連するロール リンクの種類のスコープを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-134">Because a role link type definition includes port types, the scope of a port type must encompass that of any role link type that uses it.</span></span>  
  
-   <span data-ttu-id="fbd2d-135">ビジネス アクティビティ サービス (BAS) を使用する場合は、構造化パラメーター スキーマとそれに関連付けるロール リンクの種類を、同一の BizTalk アセンブリ内で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-135">When working with Business Activity Services (BAS), the structured parameter schema must be defined in the same BizTalk assembly as the role link type it is associated with.</span></span> <span data-ttu-id="fbd2d-136">構造化パラメーター スキーマは、ロール リンクの種類を構成する個々のロールではなく、ロール リンクの種類に関連付けられます。したがって、役割の異なる 2 つのパーティがロール リンクの種類を含むアセンブリを共有する場合は、同じ構造化パラメーター スキーマが両方のパーティに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-136">Because the schema is associated with the role link type and not with the individual roles that make up that role link type, if the parties that play the different roles share the assembly containing the role link type, both parties will see the same structured parameter schemas.</span></span> <span data-ttu-id="fbd2d-137">同じロール リンクの種類を使用する 2 つのパーティが異なるパラメーター スキーマを必要とする場合は、各パーティに対して別々のアセンブリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-137">If the two parties use the same role link type but must have different parameter schemas, a different assembly should be created for each party.</span></span> <span data-ttu-id="fbd2d-138">同じロール リンクの種類を両方のアセンブリ内に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-138">The role link type should be duplicated in each assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbd2d-139">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fbd2d-139">In This Section</span></span>  
  
-   [<span data-ttu-id="fbd2d-140">オーケストレーションでロール リンクを作成する方法</span><span class="sxs-lookup"><span data-stu-id="fbd2d-140">How to Create Role Links in Orchestrations</span></span>](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [<span data-ttu-id="fbd2d-141">ロール リンク図形を使用する方法</span><span class="sxs-lookup"><span data-stu-id="fbd2d-141">How to Use the Role Link Shape</span></span>](../core/how-to-use-the-role-link-shape.md)  
  
-   [<span data-ttu-id="fbd2d-142">ロール リンク ウィザードを使用する方法</span><span class="sxs-lookup"><span data-stu-id="fbd2d-142">How to Use the Role Link Wizard</span></span>](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="fbd2d-143">参照</span><span class="sxs-lookup"><span data-stu-id="fbd2d-143">See Also</span></span>  
 <span data-ttu-id="fbd2d-144">[パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="fbd2d-144">[How to Configure the Party Resolution Pipeline Component](../core/how-to-configure-the-party-resolution-pipeline-component.md) </span></span>  
 [<span data-ttu-id="fbd2d-145">オーケストレーションでポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbd2d-145">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)
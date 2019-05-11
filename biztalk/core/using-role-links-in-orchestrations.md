---
title: オーケストレーションでロール リンクの使用 |Microsoft Docs
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
ms.openlocfilehash: 3508252cd77f002d635958f0f2bdc0202ace2d56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396555"
---
# <a name="using-role-links-in-orchestrations"></a><span data-ttu-id="7a6b0-102">オーケストレーションでロール リンクの使用</span><span class="sxs-lookup"><span data-stu-id="7a6b0-102">Using Role Links in Orchestrations</span></span>
<span data-ttu-id="7a6b0-103">ロール リンクは、オーケストレーションと取引先パートナーとの間の相互作用の抽象化の形式です。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-103">Role links are a form of abstraction for the interactions between your orchestration and your trading partners.</span></span> <span data-ttu-id="7a6b0-104">ロール リンクを使用して、取引先との対話には取引先パートナーの解決、メッセージの内容、またはデータベースの検索結果のビジネス プロセス全体をそのまま維持しながらに基づいて動的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-104">Role links enable you to dynamically choose which trading partner to interact with based on trading partner resolution, message content, or the results of a database lookup while maintaining your overall business process intact.</span></span>  
  
 <span data-ttu-id="7a6b0-105">たとえば、企業間取引シナリオでは複数の購入者、1 つの納入業者、およびサプライヤーの出荷業者を複数。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-105">For example, in a business-to-business scenario, there are multiple buyers, a single supplier, and multiple shipping agencies for the supplier.</span></span> <span data-ttu-id="7a6b0-106">購入者は、注文書を業者に送信するときに、購入者は、注文書を送信し、適切な割引を適用するパーティの解決を供給します。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-106">When a buyer sends a purchase order to the supplier, the supplier knows through party resolution which buyer is sending the purchase order and can apply the appropriate discount.</span></span> <span data-ttu-id="7a6b0-107">供給業者は、出荷業者は、配信を担当する実行時にさらに、注文された商品をに基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-107">Moreover, based on the goods ordered, the supplier determines at run time which shipping agency will be in charge of the delivery.</span></span> <span data-ttu-id="7a6b0-108">各出荷業者には、独自のトランスポート プロトコルがありますが、サプライヤーことができます、同じビジネス プロセス実行時に使用をすべての出荷業者を処理し、対話する機関を決定します。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-108">Although each shipping agency may have its own transport protocol, the supplier can use the same business process at run time to handle all the shipping agencies and determine which agency to interact with.</span></span> <span data-ttu-id="7a6b0-109">出荷業者は、トランスポート プロトコルを更新する場合、後の段階で、たとえば、FTP HTTP からから-業者がのみ BizTalk エクスプローラまたは BizTalk Server 管理コンソールを使用して、その出荷業者に関連付けられている送信ポートを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-109">At a later stage, if a shipping agency updates its transport protocol—for example, from FTP to HTTP—the supplier only needs to use BizTalk Explorer or the BizTalk Server Administration console to update the send port associated with that particular shipping agency.</span></span> <span data-ttu-id="7a6b0-110">供給業者は、オーケストレーションが存在する、そのビジネス プロセスを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-110">The supplier does not need to change its business process, which resides in the orchestration.</span></span>  
  
## <a name="roles"></a><span data-ttu-id="7a6b0-111">ロール</span><span class="sxs-lookup"><span data-stu-id="7a6b0-111">Roles</span></span>  
 <span data-ttu-id="7a6b0-112">オーケストレーションでは、2 つのロールがあります。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-112">There are two roles in an orchestration:</span></span>  
  
-   <span data-ttu-id="7a6b0-113">メッセージ受信して処理する「実装」ロール。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-113">An "implements" role to receive and process messages.</span></span> <span data-ttu-id="7a6b0-114">このロールは、プロバイダーでとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-114">This role is also known as the provider.</span></span>  
  
-   <span data-ttu-id="7a6b0-115">メッセージを送信する「使用」ロール。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-115">A "uses" role to send messages.</span></span> <span data-ttu-id="7a6b0-116">この役割は、コンシューマーとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-116">This role is also known as the consumer.</span></span>  
  
## <a name="role-links"></a><span data-ttu-id="7a6b0-117">ロール リンク</span><span class="sxs-lookup"><span data-stu-id="7a6b0-117">Role Links</span></span>  
 <span data-ttu-id="7a6b0-118">ロール リンクには、コンシューマーまたはプロバイダー ロール、またはそれぞれの 1 つを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-118">A role link can include either a consumer or a provider role, or one of each.</span></span> <span data-ttu-id="7a6b0-119">コンシューマー ロールは、プロバイダーの役割によって提供されるサービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-119">A consumer role consumes the services provided by the provider role.</span></span> <span data-ttu-id="7a6b0-120">これらのロールの一方または両方のロール リンクを定義するときに、リンクしているパートナーによって補完ロールが実行されたことと見なされます。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-120">When you define a role link with one or both of these roles, it is assumed that the complementary role is being fulfilled by the partner with whom you are linking.</span></span>  
  
 <span data-ttu-id="7a6b0-121">ロール リンクには、 **SourceParty**プロパティ、 **DestinationParty**プロパティ、およびイニシャライズ ロール。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-121">A role link has a **SourceParty** property, a **DestinationParty** property, and an initiating role.</span></span> <span data-ttu-id="7a6b0-122">イニシャライズ ロールは、最初の通信が発生すると、およびそのため、ロール リンクの値を設定して開始ロール、 **DestinationParty**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-122">An initiating role is the role on which the first communication occurs, and which therefore initiates the role link by setting the value of the **DestinationParty** property.</span></span>  
  
 <span data-ttu-id="7a6b0-123">明示的に設定イニシャライズ ロールでは、メッセージを送信するため、コンシューマーが場合、 **DestinationParty**オーケストレーション内のプロパティ (1 回、1 回だけ)。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-123">If the initiating role is a consumer for sending messages, you explicitly set the **DestinationParty** property (once and only once) in your orchestration.</span></span> <span data-ttu-id="7a6b0-124">これを行うには、値を設定、 **DestinationParty**で、**式**ConfirmOrder がロール リンクの名前であり、PartnerName と OrganizationName が、次の例のように、図形パーティのパラメーター:</span><span class="sxs-lookup"><span data-stu-id="7a6b0-124">To do so, you set the value of the **DestinationParty** in the **Expression** shape, as in the following example, where ConfirmOrder is the name of a role link, and PartnerName and OrganizationName are parameters of a party:</span></span>  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 <span data-ttu-id="7a6b0-125">イニシャライズ ロールがプロバイダーの場合、メッセージの受信、 **DestinationParty**プロパティは、受信側によって自動的に初期化します。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-125">If the initiating role is a provider for receiving messages, the **DestinationParty** property is initialized automatically by the receiver.</span></span> <span data-ttu-id="7a6b0-126">**DestinationParty**プロバイダー自体に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-126">The **DestinationParty** is set to the provider itself.</span></span> <span data-ttu-id="7a6b0-127">**SourceParty**プロパティは読み取り専用、およびセキュリティ識別子 (SID) 送信者のまたはパーティに関連付けられている証明書に基づいてパーティ名を解決するのには信頼されているパイプライン コンポーネントを通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-127">The **SourceParty** property is read-only, and is supplied through a trusted pipeline component to resolve the party name based on the security identifier (SID) of the sender or on a certificate associated with the party.</span></span> <span data-ttu-id="7a6b0-128">パイプライン コンポーネントを実行しているホストとしてマークする必要があります**信頼されている認証**です。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-128">The host running the pipeline component must be marked as **Authentication Trusted**.</span></span> <span data-ttu-id="7a6b0-129">値を取得することができます、 **SourceParty**で、**式**次のサンプル コードを使用して図形。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-129">You can get the value of the **SourceParty** in the **Expression** shape by using the following sample code:</span></span>  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a><span data-ttu-id="7a6b0-130">ロール リンクの種類</span><span class="sxs-lookup"><span data-stu-id="7a6b0-130">Role Link Types</span></span>  
 <span data-ttu-id="7a6b0-131">ロール リンクは、1 つまたは 2 つのいずれかのロールで構成されるロール リンクの種類のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-131">A role link is an instance of a role link type, which consists of either one or two roles.</span></span> <span data-ttu-id="7a6b0-132">ロール リンクの種類を使用する場合は、次を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-132">When working with a role link type, consider the following:</span></span>  
  
-   <span data-ttu-id="7a6b0-133">1 つのロール リンクの種類内の特定のポートの型に 1 回だけ参照することができます。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-133">You can refer only once to any given port type within a single role link type.</span></span>  
  
-   <span data-ttu-id="7a6b0-134">ロール リンクの種類の定義には、ポートの種類が含まれているため、それを使用するロール リンクの種類のポートの種類のスコープを網羅する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-134">Because a role link type definition includes port types, the scope of a port type must encompass that of any role link type that uses it.</span></span>  
  
-   <span data-ttu-id="7a6b0-135">ビジネス アクティビティ サービス (BAS) を使用する場合が関連付けられているロール リンクの種類と同じ BizTalk アセンブリで構造化パラメータ スキーマを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-135">When working with Business Activity Services (BAS), the structured parameter schema must be defined in the same BizTalk assembly as the role link type it is associated with.</span></span> <span data-ttu-id="7a6b0-136">スキーマは、さまざまな役割を果たす当事者がロール リンクの種類を含むアセンブリを共有している場合、ロール リンクの種類およびそのロール リンクの種類を構成する個々 のロールではなくに関連付けであるため両方のパーティが同じ構造化パラメータに表示されます。スキーマです。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-136">Because the schema is associated with the role link type and not with the individual roles that make up that role link type, if the parties that play the different roles share the assembly containing the role link type, both parties will see the same structured parameter schemas.</span></span> <span data-ttu-id="7a6b0-137">2 つのパーティで同じロール リンクの種類を使用している場合、異なるパラメーター スキーマがあります、各パーティの別のアセンブリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-137">If the two parties use the same role link type but must have different parameter schemas, a different assembly should be created for each party.</span></span> <span data-ttu-id="7a6b0-138">ロール リンクの種類は、各アセンブリ内で重複する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6b0-138">The role link type should be duplicated in each assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a6b0-139">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7a6b0-139">In This Section</span></span>  
  
-   [<span data-ttu-id="7a6b0-140">オーケストレーションでロール リンクを作成する方法</span><span class="sxs-lookup"><span data-stu-id="7a6b0-140">How to Create Role Links in Orchestrations</span></span>](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [<span data-ttu-id="7a6b0-141">ロール リンク図形を使用する方法</span><span class="sxs-lookup"><span data-stu-id="7a6b0-141">How to Use the Role Link Shape</span></span>](../core/how-to-use-the-role-link-shape.md)  
  
-   [<span data-ttu-id="7a6b0-142">ロール リンク ウィザードを使用する方法</span><span class="sxs-lookup"><span data-stu-id="7a6b0-142">How to Use the Role Link Wizard</span></span>](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="7a6b0-143">参照</span><span class="sxs-lookup"><span data-stu-id="7a6b0-143">See Also</span></span>  
 <span data-ttu-id="7a6b0-144">[パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="7a6b0-144">[How to Configure the Party Resolution Pipeline Component](../core/how-to-configure-the-party-resolution-pipeline-component.md) </span></span>  
 [<span data-ttu-id="7a6b0-145">オーケストレーションでのポートの使用</span><span class="sxs-lookup"><span data-stu-id="7a6b0-145">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)
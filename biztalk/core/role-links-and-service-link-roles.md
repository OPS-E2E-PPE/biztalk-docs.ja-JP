---
title: ロール リンクとサービス リンク ロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, orchestrations
- service link roles
- role links
- roles, orchestrations
- roles
- roles, about roles
- service link roles, about service link roles
- orchestrations, roles
- role links, about role links
- orchestrations, deleting
ms.assetid: 23b4ca34-a1a5-44d4-a50d-661277681c72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6630b1ad22ba86f3efe8a19409f3b731880c8a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268682"
---
# <a name="role-links-and-service-link-roles"></a><span data-ttu-id="45a29-102">ロール リンクとサービス リンク ロール</span><span class="sxs-lookup"><span data-stu-id="45a29-102">Role Links and Service Link Roles</span></span>
<span data-ttu-id="45a29-103">A*ロール*サービスを使用するか、サービスを実装するポートの種類のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="45a29-103">A *role* is a collection of port types that either uses a service or implements a service.</span></span> <span data-ttu-id="45a29-104">ロールは、パーティが単一または複数のオーケストレーションを持つ場合の対話処理の種類を表します。</span><span class="sxs-lookup"><span data-stu-id="45a29-104">A role represents the type of interaction that a party can have with one or many orchestrations.</span></span> <span data-ttu-id="45a29-105">パーティの数が増えるにつれて、ロールによって管理を柔軟かつ簡単に行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="45a29-105">Roles provide flexibility and ease of management as the number of parties increase.</span></span> <span data-ttu-id="45a29-106">たとえば、あるオーケストレーションで出荷業者のロールを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="45a29-106">For example, an orchestration might use the role of a Shipper.</span></span> <span data-ttu-id="45a29-107">出荷業者は、1 つまたは 2 つのパーティが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a29-107">The Shipper would have one or two parties associated with it.</span></span> <span data-ttu-id="45a29-108">オーケストレーションでアイテムの出荷業者を決定する際には、出荷業者ロールのパーティの価格が比較されます。</span><span class="sxs-lookup"><span data-stu-id="45a29-108">When the orchestration decides which shipping company to use to ship an item, it compares the prices of the parties in the Shipper role.</span></span>  
  
 <span data-ttu-id="45a29-109">A*ロール リンクの種類*は、2 つのサービスやオーケストレーション間のリレーションシップを表すプロパティです。</span><span class="sxs-lookup"><span data-stu-id="45a29-109">A *role link type* is a property that characterizes the relationship between two services or orchestrations.</span></span> <span data-ttu-id="45a29-110">関係にかかわる各サービスが受け持つ役割を定義し、各ロールから提供されるポートの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="45a29-110">It defines the part played by each of the services in the relationship and specifies the port types provided by each role.</span></span>  
  
 <span data-ttu-id="45a29-111">パーティ (つまり、組織単位) は、オーケストレーションと連携する BizTalk Server 外部のエンティティを表します。</span><span class="sxs-lookup"><span data-stu-id="45a29-111">A party, or organizational unit, represents an entity outside of BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="45a29-112">BizTalk Server では、メッセージ交換の対象となる各組織は、パーティで表されます。</span><span class="sxs-lookup"><span data-stu-id="45a29-112">In BizTalk Server, each organization with which you exchange messages is represented by a party.</span></span> <span data-ttu-id="45a29-113">パーティをロールに参加させてパーティと連携する方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="45a29-113">You can define how the party interacts by enlisting it in a role.</span></span>  
  
 <span data-ttu-id="45a29-114">ロール リンクの種類がオーケストレーションに関連付けられている場合、ロール リンクの種類を展開または削除できます。</span><span class="sxs-lookup"><span data-stu-id="45a29-114">You can deploy or remove a role link type when it is associated with an orchestration.</span></span>  
  
## <a name="orchestrations-and-roles"></a><span data-ttu-id="45a29-115">オーケストレーションとロール</span><span class="sxs-lookup"><span data-stu-id="45a29-115">Orchestrations and Roles</span></span>  
 <span data-ttu-id="45a29-116">ロール リンクの種類を使用するオーケストレーションを展開すると、構成データベースがロールを保存します。</span><span class="sxs-lookup"><span data-stu-id="45a29-116">When you deploy an orchestration that uses a role link type, the Configuration database saves the role.</span></span> <span data-ttu-id="45a29-117">複数のオーケストレーションでロールを使用できるため、管理データベースは、ロール リンクの種類を 1 つだけ保存します。</span><span class="sxs-lookup"><span data-stu-id="45a29-117">Because a role can be used by more than one orchestration, the Management database saves only one copy of the role link type.</span></span>  
  
 <span data-ttu-id="45a29-118">同じ名前および名前空間を持つ個別のオーケストレーション (.odx) ファイルに 2 つのロール リンクの種類を含む BizTalk プロジェクトを使用している場合、BizTalk プロジェクトはコンパイル処理を行いません。</span><span class="sxs-lookup"><span data-stu-id="45a29-118">If your BizTalk project contains two role link types in separate orchestration (.odx) files that have the same name and namespace, your BizTalk project does not compile.</span></span>  
  
### <a name="orchestration-removals-that-use-roles"></a><span data-ttu-id="45a29-119">ロールを使用するオーケストレーションの削除</span><span class="sxs-lookup"><span data-stu-id="45a29-119">Orchestration Removals that use Roles</span></span>  
 <span data-ttu-id="45a29-120">複数のオーケストレーションでロール リンクの種類を使用できるため、ロールを使用するオーケストレーションを含むアセンブリを展開解除すると、管理データベースは、該当するロールを使用しているオーケストレーションがない場合にそのロールだけを削除します。</span><span class="sxs-lookup"><span data-stu-id="45a29-120">Because a role link type can be used by more than one orchestration, when you undeploy an assembly that contains an orchestration that uses a role, the Management database removes the role only if no other orchestrations are using the role.</span></span>  
  
 <span data-ttu-id="45a29-121">また、管理データベースは、参加しているパーティがない場合、ロールだけを削除します。</span><span class="sxs-lookup"><span data-stu-id="45a29-121">Additionally, the Management database removes a role only if there are no parties enlisted with it.</span></span> <span data-ttu-id="45a29-122">参加しているパーティを持つロールを上書きできないのと同様に、参加しているパーティを持つロールは削除もできません。</span><span class="sxs-lookup"><span data-stu-id="45a29-122">Just as you cannot overwrite a role that has parties enlisted with it, you cannot remove a role that has parties enlisted with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a29-123">参照</span><span class="sxs-lookup"><span data-stu-id="45a29-123">See Also</span></span>  
 <span data-ttu-id="45a29-124">[オーケストレーションでロール リンクの使用](../core/using-role-links-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="45a29-124">[Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="45a29-125">成果物</span><span class="sxs-lookup"><span data-stu-id="45a29-125">Artifacts</span></span>](../core/artifacts.md)
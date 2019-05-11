---
title: ロール リンクとサービス リンク ロール |Microsoft Docs
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
ms.openlocfilehash: f7b52a13878363e79b9b2ffa3e600de16aeacd3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254716"
---
# <a name="role-links-and-service-link-roles"></a><span data-ttu-id="3893b-102">ロール リンクとサービス リンク ロール</span><span class="sxs-lookup"><span data-stu-id="3893b-102">Role Links and Service Link Roles</span></span>
<span data-ttu-id="3893b-103">A*ロール*またはサービスを使用して、サービスを実装するポートの種類のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3893b-103">A *role* is a collection of port types that either uses a service or implements a service.</span></span> <span data-ttu-id="3893b-104">ロールは、パーティは、1 つまたは複数のオーケストレーションを持つことができますの対話の種類を表します。</span><span class="sxs-lookup"><span data-stu-id="3893b-104">A role represents the type of interaction that a party can have with one or many orchestrations.</span></span> <span data-ttu-id="3893b-105">ロールは、柔軟性とパーティの増加の数と管理の容易さを提供します。</span><span class="sxs-lookup"><span data-stu-id="3893b-105">Roles provide flexibility and ease of management as the number of parties increase.</span></span> <span data-ttu-id="3893b-106">たとえば、オーケストレーションは、出荷業者のロールを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3893b-106">For example, an orchestration might use the role of a Shipper.</span></span> <span data-ttu-id="3893b-107">出荷業者は、1 つまたは 2 つのパーティが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3893b-107">The Shipper would have one or two parties associated with it.</span></span> <span data-ttu-id="3893b-108">オーケストレーションは、使用して商品の出荷業者を決定したら、出荷業者ロールのパーティの価格を比較します。</span><span class="sxs-lookup"><span data-stu-id="3893b-108">When the orchestration decides which shipping company to use to ship an item, it compares the prices of the parties in the Shipper role.</span></span>  
  
 <span data-ttu-id="3893b-109">A*ロール リンクの種類*は、2 つのサービスやオーケストレーション間のリレーションシップを表すプロパティです。</span><span class="sxs-lookup"><span data-stu-id="3893b-109">A *role link type* is a property that characterizes the relationship between two services or orchestrations.</span></span> <span data-ttu-id="3893b-110">リレーションシップ内のサービスの各部分を定義し、各ロールで提供されるポートの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3893b-110">It defines the part played by each of the services in the relationship and specifies the port types provided by each role.</span></span>  
  
 <span data-ttu-id="3893b-111">パーティ、または組織単位、オーケストレーションと連携する BizTalk Server 外部のエンティティを表します。</span><span class="sxs-lookup"><span data-stu-id="3893b-111">A party, or organizational unit, represents an entity outside of BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="3893b-112">BizTalk Server では、メッセージを交換する各組織は、パーティによって表されます。</span><span class="sxs-lookup"><span data-stu-id="3893b-112">In BizTalk Server, each organization with which you exchange messages is represented by a party.</span></span> <span data-ttu-id="3893b-113">パーティがロールに参加させてと連携する方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3893b-113">You can define how the party interacts by enlisting it in a role.</span></span>  
  
 <span data-ttu-id="3893b-114">デプロイまたはオーケストレーションに関連付けられているときに、ロール リンクの種類を削除できます。</span><span class="sxs-lookup"><span data-stu-id="3893b-114">You can deploy or remove a role link type when it is associated with an orchestration.</span></span>  
  
## <a name="orchestrations-and-roles"></a><span data-ttu-id="3893b-115">オーケストレーションとロール</span><span class="sxs-lookup"><span data-stu-id="3893b-115">Orchestrations and Roles</span></span>  
 <span data-ttu-id="3893b-116">ロール リンクの種類を使用するオーケストレーションを展開するときに、ロールが構成データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="3893b-116">When you deploy an orchestration that uses a role link type, the Configuration database saves the role.</span></span> <span data-ttu-id="3893b-117">ロールは、1 つ以上のオーケストレーションで使用できる、ので、管理データベースは、ロール リンクの種類の 1 つだけコピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="3893b-117">Because a role can be used by more than one orchestration, the Management database saves only one copy of the role link type.</span></span>  
  
 <span data-ttu-id="3893b-118">BizTalk プロジェクトに同じ名前および名前空間を持つ個別のオーケストレーション (.odx) ファイルで 2 つのロール リンクの種類が含まれている場合、BizTalk プロジェクトはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="3893b-118">If your BizTalk project contains two role link types in separate orchestration (.odx) files that have the same name and namespace, your BizTalk project does not compile.</span></span>  
  
### <a name="orchestration-removals-that-use-roles"></a><span data-ttu-id="3893b-119">ロールを使用してオーケストレーションの削除</span><span class="sxs-lookup"><span data-stu-id="3893b-119">Orchestration Removals that use Roles</span></span>  
 <span data-ttu-id="3893b-120">ロールを使用するオーケストレーションを含むアセンブリを展開解除すると、ロール リンクの種類を 1 つ以上のオーケストレーションで使用できる、ため、管理データベースは、他のオーケストレーションが、ロールを使用していない場合にのみ、ロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="3893b-120">Because a role link type can be used by more than one orchestration, when you undeploy an assembly that contains an orchestration that uses a role, the Management database removes the role only if no other orchestrations are using the role.</span></span>  
  
 <span data-ttu-id="3893b-121">さらに、それに参加しているパーティがない場合にのみ、管理データベースは、ロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="3893b-121">Additionally, the Management database removes a role only if there are no parties enlisted with it.</span></span> <span data-ttu-id="3893b-122">それに参加しているパーティを持つロールを上書きすることはできず、同様、それに参加しているパーティを持つロールを削除できません。</span><span class="sxs-lookup"><span data-stu-id="3893b-122">Just as you cannot overwrite a role that has parties enlisted with it, you cannot remove a role that has parties enlisted with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3893b-123">参照</span><span class="sxs-lookup"><span data-stu-id="3893b-123">See Also</span></span>  
 <span data-ttu-id="3893b-124">[オーケストレーションでロール リンクの使用](../core/using-role-links-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="3893b-124">[Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="3893b-125">アイテム</span><span class="sxs-lookup"><span data-stu-id="3893b-125">Artifacts</span></span>](../core/artifacts.md)
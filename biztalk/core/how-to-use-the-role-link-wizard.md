---
title: ロール リンク ウィザードを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- links [roles]
- Role Link Wizard [Orchestration Designer]
- roles, links
- Orchestration Designer, Role Link Wizard
- role links, Role Link Wizard [Orchestration Designer]
- links [roles], about links
ms.assetid: ddc33d87-c08d-4193-9483-4644ef302853
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5336dcbb129b01be8fc03c43756bb1fc1ac53063
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333199"
---
# <a name="how-to-use-the-role-link-wizard"></a><span data-ttu-id="e4d51-102">ロール リンク ウィザードを使用する方法</span><span class="sxs-lookup"><span data-stu-id="e4d51-102">How to Use the Role Link Wizard</span></span>
<span data-ttu-id="e4d51-103">ロール リンク ウィザードを使用すると、新しいロール リンクを作成または既存のものを変更できます。</span><span class="sxs-lookup"><span data-stu-id="e4d51-103">The Role Link Wizard enables you to create a new role link or modify an existing one.</span></span> <span data-ttu-id="e4d51-104">設定または表示名、型、およびロール リンクだけでなく、実装ロールおよびロール リンクの種類を構成する使用ロールのアクセス制限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d51-104">You can use it to set or view the name, type, and access restriction of the role link, as well as the implements role and the uses role that compose the role link type.</span></span> <span data-ttu-id="e4d51-105">ロール リンクの機能については、次を参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4d51-105">To understand how role links work, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="e4d51-106">**ロール リンク名**:ロール リンク名に入力してを構成している既存のロール リンクの現在の名前か、自動的に生成された名前は、新しいロール リンクを作成する場合。</span><span class="sxs-lookup"><span data-stu-id="e4d51-106">**Role link name**: The role link name is filled in for you and is either the current name of an existing role link that you are configuring, or an automatically generated name if you are creating a new role link.</span></span> <span data-ttu-id="e4d51-107">いずれの場合も、名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e4d51-107">In either case you can modify the name.</span></span>  
  
 <span data-ttu-id="e4d51-108">**ロール リンクの種類**:既存のロール リンクの種類を選択したり、新しく作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4d51-108">**Role link type**: You can select an existing role link type, or create a new one.</span></span> <span data-ttu-id="e4d51-109">新規または既存のロール リンクの種類を構成しているかどうかは、オーケストレーションがサービスに参加する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4d51-109">Whether you are configuring a new or existing role link type, you can specify how your orchestration participates in the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4d51-110">ロール リンクを定義するため、既存のロール リンクの種類を使用できるように、ロール リンクを作成するには、ロール リンクの種類と関連付けられているポートの種類の前に作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e4d51-110">We recommend that you create the role link type and associated port type prior to create the role link so that you can use an existing role link type for defining your role link.</span></span> <span data-ttu-id="e4d51-111">詳細については、次を参照してください。[オーケストレーションでロール リンクを作成する方法](../core/how-to-create-role-links-in-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4d51-111">For more information, see [How to Create Role Links in Orchestrations](../core/how-to-create-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="e4d51-112">**ロール リンクの使用法**:新しいロール リンクの種類を作成する場合、両方の実装と使用ロールが自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="e4d51-112">**Role link usage**: If you create a new role link type, both the implements and uses roles are automatically created for you.</span></span> <span data-ttu-id="e4d51-113">オーケストレーションがサービスに参加する方法を反映するロールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e4d51-113">You can select the role that reflects how your orchestration participates in the service.</span></span> <span data-ttu-id="e4d51-114">ウィザードの手順を完了すると後、は、ロール識別子の名前変更または実装に合わせてロールを削除できます。</span><span class="sxs-lookup"><span data-stu-id="e4d51-114">After you have completed the steps in the wizard, you can rename the role identifiers or remove a role to better match your implementation.</span></span> <span data-ttu-id="e4d51-115">ロール リンクの種類には、いずれかのロールの種類のいずれかまたはロールの種類ごとの 1 つを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d51-115">A role link type must contain one of either role type or one of each role type.</span></span> <span data-ttu-id="e4d51-116">クリックすると**OK**、それぞれの名前に対応する未構成のロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4d51-116">When you click **OK**, unconfigured roles are created corresponding to each name.</span></span> <span data-ttu-id="e4d51-117">種類 ウィンドウで、ロールのポートの種類を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4d51-117">You can also select port types for the roles in the Types window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4d51-118">ロール リンクの種類のポートの種類を作成し、以前に定義されたポートの種類を選択するには、ポート構成ウィザードを起動する場合は、ポートの種類のアクセス制限がロール リンクの種類のアクセス制限と競合しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e4d51-118">If you invoke the Port Configuration Wizard to create a port type for your role link type, and want to select a previously defined port type, ensure that the access restrictions of the port type do not conflict with the access restrictions of the role link type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d51-119">参照</span><span class="sxs-lookup"><span data-stu-id="e4d51-119">See Also</span></span>  
 [<span data-ttu-id="e4d51-120">オーケストレーションでのロール リンクの使用</span><span class="sxs-lookup"><span data-stu-id="e4d51-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)
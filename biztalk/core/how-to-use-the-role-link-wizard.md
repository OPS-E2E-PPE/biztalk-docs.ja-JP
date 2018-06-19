---
title: ロール リンク ウィザードを使用する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6d31abcc8fcc2bfaf1ebd641e1e52ad08d1c9c9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255858"
---
# <a name="how-to-use-the-role-link-wizard"></a><span data-ttu-id="5f60b-102">ロール リンク ウィザードを使用する方法</span><span class="sxs-lookup"><span data-stu-id="5f60b-102">How to Use the Role Link Wizard</span></span>
<span data-ttu-id="5f60b-103">ロール リンク ウィザードを使用すると、新しいロール リンクの作成や既存のロール リンクの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5f60b-103">The Role Link Wizard enables you to create a new role link or modify an existing one.</span></span> <span data-ttu-id="5f60b-104">ロール リンク ウィザードでは、ロール リンクの種類を構成する使用ロールと実装ロール、およびロール リンクについて、名前、種類、アクセス制限の設定や表示を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5f60b-104">You can use it to set or view the name, type, and access restriction of the role link, as well as the implements role and the uses role that compose the role link type.</span></span> <span data-ttu-id="5f60b-105">ロール リンクの機能を理解するのを参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f60b-105">To understand how role links work, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="5f60b-106">**ロール リンク名**: ロール リンク名に入力して、新しいロール リンクを作成する場合は、現在の名前を構成している既存のロール リンクか、自動的に生成された名前は、します。</span><span class="sxs-lookup"><span data-stu-id="5f60b-106">**Role link name**: The role link name is filled in for you and is either the current name of an existing role link that you are configuring, or an automatically generated name if you are creating a new role link.</span></span> <span data-ttu-id="5f60b-107">どちらの場合も名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5f60b-107">In either case you can modify the name.</span></span>  
  
 <span data-ttu-id="5f60b-108">**ロール リンクの種類**: 既存のロール リンクの種類を選択または新規に作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f60b-108">**Role link type**: You can select an existing role link type, or create a new one.</span></span> <span data-ttu-id="5f60b-109">ロール リンクの種類が新規または既存のどちらで構成されていても、オーケストレーションがサービスに参加する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f60b-109">Whether you are configuring a new or existing role link type, you can specify how your orchestration participates in the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f60b-110">ロール リンクを作成する前にロール リンクの種類を作成してポートの種類を関連付け、既存のロール リンクの種類をロール リンクの定義に使用できるようにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5f60b-110">We recommend that you create the role link type and associated port type prior to create the role link so that you can use an existing role link type for defining your role link.</span></span> <span data-ttu-id="5f60b-111">詳細については、次を参照してください。[オーケストレーションでロール リンクを作成する方法](../core/how-to-create-role-links-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f60b-111">For more information, see [How to Create Role Links in Orchestrations](../core/how-to-create-role-links-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="5f60b-112">**ロール リンクの使用法**: 新しいロール リンクを作成する場合、両方の実装を入力し、使用して役割が自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="5f60b-112">**Role link usage**: If you create a new role link type, both the implements and uses roles are automatically created for you.</span></span> <span data-ttu-id="5f60b-113">オーケストレーションがサービスに参加する方法を表すロールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5f60b-113">You can select the role that reflects how your orchestration participates in the service.</span></span> <span data-ttu-id="5f60b-114">ウィザードの手順を完了すると、実装に合わせてロールの識別子の名前を変更したり、ロールを削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f60b-114">After you have completed the steps in the wizard, you can rename the role identifiers or remove a role to better match your implementation.</span></span> <span data-ttu-id="5f60b-115">ロール リンクの種類には、いずれかのロールの種類を 1 つ、または各ロールの種類を 1 つずつ含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f60b-115">A role link type must contain one of either role type or one of each role type.</span></span> <span data-ttu-id="5f60b-116">クリックすると、 **OK**、未構成の役割が作成される各名前に対応します。</span><span class="sxs-lookup"><span data-stu-id="5f60b-116">When you click **OK**, unconfigured roles are created corresponding to each name.</span></span> <span data-ttu-id="5f60b-117">また、[種類] ウィンドウではロールのポートの種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5f60b-117">You can also select port types for the roles in the Types window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f60b-118">ポート構成ウィザードを呼び出してロール リンクの種類に対するポートの種類を作成する際に、以前定義したポートの種類を選択する場合、ポートの種類のアクセス制限がロール リンクの種類のアクセス制限と競合していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5f60b-118">If you invoke the Port Configuration Wizard to create a port type for your role link type, and want to select a previously defined port type, ensure that the access restrictions of the port type do not conflict with the access restrictions of the role link type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f60b-119">参照</span><span class="sxs-lookup"><span data-stu-id="5f60b-119">See Also</span></span>  
 [<span data-ttu-id="5f60b-120">オーケストレーションでロール リンクの使用</span><span class="sxs-lookup"><span data-stu-id="5f60b-120">Using Role Links in Orchestrations</span></span>](../core/using-role-links-in-orchestrations.md)
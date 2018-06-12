---
title: 権利の割り当て |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, assigning permissions
- security, user accounts
- document library, new messages
- document library, unparsed
- messages, document library
- privileges
- permissions
- unparsed document library
- security, permissions
ms.assetid: cee44240-aa00-4080-9e7f-728b2421102b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a0d152442bf375c43d371e5ca5c3fcfb9dc5939
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848962"
---
# <a name="assigning-rights"></a><span data-ttu-id="63e0d-102">権利の割り当てください。</span><span class="sxs-lookup"><span data-stu-id="63e0d-102">Assigning Rights</span></span>
<span data-ttu-id="63e0d-103">前のトピックで作成された各サイトのグループは、ドキュメント ライブラリでは、次のアクセス許可を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e0d-103">The following permissions should be granted on the Document libraries for each site group created in the preceding topic:</span></span>  
  
|<span data-ttu-id="63e0d-104">ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="63e0d-104">Document library</span></span>|<span data-ttu-id="63e0d-105">サイト グループ</span><span class="sxs-lookup"><span data-stu-id="63e0d-105">Site groups</span></span>|<span data-ttu-id="63e0d-106">カスタム ドキュメント ライブラリのアクセス許可を適用するには</span><span class="sxs-lookup"><span data-stu-id="63e0d-106">Custom document library permissions to apply</span></span>|  
|----------------------|-----------------|--------------------------------------------------|  
|<span data-ttu-id="63e0d-107">テンプレート ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="63e0d-107">Templates document library</span></span>|<span data-ttu-id="63e0d-108">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="63e0d-108">Payments_Creators</span></span><br /><br /> <span data-ttu-id="63e0d-109">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="63e0d-109">Payments_Repairers</span></span><br /><br /> <span data-ttu-id="63e0d-110">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="63e0d-110">Payments_Approvers</span></span>|<span data-ttu-id="63e0d-111">アイテムの表示</span><span class="sxs-lookup"><span data-stu-id="63e0d-111">View items</span></span>|  
|<span data-ttu-id="63e0d-112">未解析 (下の詳細)</span><span class="sxs-lookup"><span data-stu-id="63e0d-112">Unparsed (details below)</span></span>|<span data-ttu-id="63e0d-113">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="63e0d-113">Payments_Repairers</span></span>|<span data-ttu-id="63e0d-114">表示、挿入、編集、アイテムの削除</span><span class="sxs-lookup"><span data-stu-id="63e0d-114">View, insert, edit, delete items</span></span>|  
|<span data-ttu-id="63e0d-115">新しい SWIFT MT メッセージ (以下詳細)</span><span class="sxs-lookup"><span data-stu-id="63e0d-115">New SWIFT MT Messages (details below)</span></span>|<span data-ttu-id="63e0d-116">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="63e0d-116">Payments_Creators</span></span>|<span data-ttu-id="63e0d-117">表示、挿入、編集、アイテムの削除</span><span class="sxs-lookup"><span data-stu-id="63e0d-117">View, insert, edit, delete items</span></span>|  
|<span data-ttu-id="63e0d-118">新しい SWIFT MX メッセージ (以下詳細)</span><span class="sxs-lookup"><span data-stu-id="63e0d-118">New SWIFT MX Messages (details below)</span></span>|<span data-ttu-id="63e0d-119">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="63e0d-119">Payments_Creators</span></span>|<span data-ttu-id="63e0d-120">表示、挿入、編集、アイテムの削除</span><span class="sxs-lookup"><span data-stu-id="63e0d-120">View, insert, edit, delete items</span></span>|  
|<span data-ttu-id="63e0d-121">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="63e0d-121">Payments_Repairers</span></span>|<span data-ttu-id="63e0d-122">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="63e0d-122">Payments_Repairers</span></span>|<span data-ttu-id="63e0d-123">表示、挿入、編集、アイテムの削除</span><span class="sxs-lookup"><span data-stu-id="63e0d-123">View, insert, edit, delete items</span></span>|  
|<span data-ttu-id="63e0d-124">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="63e0d-124">Payments_Approvers</span></span>|<span data-ttu-id="63e0d-125">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="63e0d-125">Payments_Approvers</span></span>|<span data-ttu-id="63e0d-126">表示、挿入、編集、アイテムの削除</span><span class="sxs-lookup"><span data-stu-id="63e0d-126">View, insert, edit, delete items</span></span>|  
|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="63e0d-127">_Outbox</span><span class="sxs-lookup"><span data-stu-id="63e0d-127">_Outbox</span></span>|<span data-ttu-id="63e0d-128">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="63e0d-128">Payments_Creators</span></span><br /><br /> <span data-ttu-id="63e0d-129">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="63e0d-129">Payments_Repairers</span></span><br /><br /> <span data-ttu-id="63e0d-130">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="63e0d-130">Payments_Approvers</span></span>|<span data-ttu-id="63e0d-131">表示、挿入、編集、アイテムの削除</span><span class="sxs-lookup"><span data-stu-id="63e0d-131">View, insert, edit, delete items</span></span>|  
  
## <a name="unparsed-document-library"></a><span data-ttu-id="63e0d-132">未解析のドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="63e0d-132">Unparsed Document Library</span></span>  
 <span data-ttu-id="63e0d-133">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair プロセスが、特殊な方法での解析に失敗したメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="63e0d-133">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair process deals with messages that fail parsing in a special manner.</span></span> <span data-ttu-id="63e0d-134">未解析のメッセージ (メッセージを XML に変換することはできません) は、未解析の 1 つのメッセージ ドキュメント ライブラリにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="63e0d-134">Unparsed messages (messages that cannot be translated into XML) are routed to a single unparsed message document library.</span></span> <span data-ttu-id="63e0d-135">のみ特定のユーザーではなく全体のグループ、フォルダーへのアクセスを許可するのには、未解析のドキュメント ライブラリを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63e0d-135">The unparsed document library should be restricted to allow only specific people, rather than entire groups, to access the folder.</span></span> <span data-ttu-id="63e0d-136">未解析のフォルダーが可能な限り安全であるようになります。</span><span class="sxs-lookup"><span data-stu-id="63e0d-136">This will ensure that the unparsed folder is as secure as possible.</span></span>  
  
 <span data-ttu-id="63e0d-137">未解析のメッセージを修復する権限を持つユーザーは、MMC の構成コンソールで定義されている、少なくとも 1 つの部門の修復のロールのアクセス許可を必要し、NT グループに登録する必要もあります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="63e0d-137">Users who have permissions to repair unparsed messages need permissions in the repair role for at least one department defined in the MMC configuration console, and also need to be enrolled in the NT Group [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Users Group.</span></span>  
  
## <a name="new-swift-mt-mx-messages-document-library"></a><span data-ttu-id="63e0d-138">新しい SWIFT MT/MX メッセージ ドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="63e0d-138">New SWIFT MT/ MX Messages Document Library</span></span>  
 <span data-ttu-id="63e0d-139">新しい SWIFT MT メッセージと新しい SWIFT MX メッセージ ドキュメント ライブラリは、MRSR サイトの展開時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="63e0d-139">The New SWIFT MT Messages and New SWIFT MX Messages document libraries are created at the time of deploying the MRSR site.</span></span> <span data-ttu-id="63e0d-140">新しい SWIFT MT メッセージと新しい SWIFT MX メッセージ ドキュメント ライブラリでは、新しい SWIFT XML テンプレートや「定型」メッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="63e0d-140">The New SWIFT MT Messages and New SWIFT MX Messages document libraries store new SWIFT XML templates or "boilerplate" messages.</span></span> <span data-ttu-id="63e0d-141">これらのメッセージを使用して、新しい SWIFT InfoPath XML 形式で表されるメッセージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="63e0d-141">You can use these messages to create new SWIFT messages represented in InfoPath XML format.</span></span> <span data-ttu-id="63e0d-142">これらのメッセージは、ドキュメント ライブラリにアップロード ボタンをクリックすると、ユーザーが新しい SWIFT MT メッセージと新しい SWIFT MX メッセージ ドキュメント ライブラリにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="63e0d-142">These messages are uploaded into the New SWIFT MT Messages and New SWIFT MX Messages document libraries by the user by clicking on the Upload button in the document library.</span></span> <span data-ttu-id="63e0d-143">さらに、指定したユーザーにアクセスを制限する SWIFT メッセージの新しいテンプレートを配布できます。</span><span class="sxs-lookup"><span data-stu-id="63e0d-143">You can further distribute the New SWIFT Message templates to restrict access to specified users.</span></span> <span data-ttu-id="63e0d-144">これを行うには、最初、新しいドキュメント ライブラリを作成して、ドキュメント ライブラリに必要な XML テンプレートをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="63e0d-144">To do so you first create a new document library, and then copy the XML templates required for the document library.</span></span>  
  
 <span data-ttu-id="63e0d-145">FormPublish ツールの詳細については、次を参照してください。 [FormPublish ツール](http://msdn.microsoft.com/09a6ed31-5917-4776-9a5e-955af440cdac)「ツール」セクションでします。</span><span class="sxs-lookup"><span data-stu-id="63e0d-145">For more information about the FormPublish tool, see [FormPublish Tool](http://msdn.microsoft.com/09a6ed31-5917-4776-9a5e-955af440cdac) in the Tools section.</span></span>
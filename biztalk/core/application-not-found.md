---
title: "アプリケーションが見つかりません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c37680b2-b38a-40f3-bb27-7b7281299ec3
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2a2b42a74001cfdc374d20052a8369ae535347d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="application-not-found"></a><span data-ttu-id="15849-102">アプリケーションが見つかりません</span><span class="sxs-lookup"><span data-stu-id="15849-102">Application not found</span></span>
## <a name="details"></a><span data-ttu-id="15849-103">詳細</span><span class="sxs-lookup"><span data-stu-id="15849-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15849-104">製品名</span><span class="sxs-lookup"><span data-stu-id="15849-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="15849-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="15849-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="15849-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="15849-106">Event ID</span></span>|<span data-ttu-id="15849-107">0</span><span class="sxs-lookup"><span data-stu-id="15849-107">0</span></span>|  
|<span data-ttu-id="15849-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="15849-108">Event Source</span></span>|<span data-ttu-id="15849-109">0</span><span class="sxs-lookup"><span data-stu-id="15849-109">0</span></span>|  
|<span data-ttu-id="15849-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="15849-110">Component</span></span>|<span data-ttu-id="15849-111">0</span><span class="sxs-lookup"><span data-stu-id="15849-111">0</span></span>|  
|<span data-ttu-id="15849-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="15849-112">Symbolic Name</span></span>|<span data-ttu-id="15849-113">0</span><span class="sxs-lookup"><span data-stu-id="15849-113">0</span></span>|  
|<span data-ttu-id="15849-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="15849-114">Message Text</span></span>|<span data-ttu-id="15849-115">アプリケーション "{0}" が見つかりません。既定の BizTalk 構成データベースにアプリケーションが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="15849-115">Application "{0}" not found.Verify the application exists in the default BizTalk configuration database</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="15849-116">説明</span><span class="sxs-lookup"><span data-stu-id="15849-116">Explanation</span></span>  
 <span data-ttu-id="15849-117">BizTalk が、BizTalk データベースに存在しないアプリケーションを使用していることを示します。</span><span class="sxs-lookup"><span data-stu-id="15849-117">This error indicates BizTalk is using an application that does not exist in the BizTalk databases.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15849-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="15849-118">User Action</span></span>  
 <span data-ttu-id="15849-119">有効なアプリケーションを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="15849-119">Use the following procedure to configure a valid application.</span></span>  
  
#### <a name="to-configure-a-valid-application"></a><span data-ttu-id="15849-120">有効なアプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="15849-120">To configure a valid application</span></span>  
  
1.  <span data-ttu-id="15849-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="15849-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="15849-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="15849-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="15849-123">アプリケーションがそこに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="15849-123">Ensure that the application exists there.</span></span> <span data-ttu-id="15849-124">存在しない場合は、別の有効なアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="15849-124">If not, select a different valid application.</span></span>
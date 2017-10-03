---
title: "受信本文のパス式に一致するものが見つかりません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0382348-96c4-414c-9dda-a390d491dee8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f733099d35150c22e888f89e720d4039208ce24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-find-match-for-inbound-body-path-expression"></a><span data-ttu-id="41357-102">受信本文のパス式に一致する内容が見つかりません</span><span class="sxs-lookup"><span data-stu-id="41357-102">Unable to find match for inbound body path expression</span></span>
## <a name="details"></a><span data-ttu-id="41357-103">詳細</span><span class="sxs-lookup"><span data-stu-id="41357-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41357-104">製品名</span><span class="sxs-lookup"><span data-stu-id="41357-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="41357-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="41357-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="41357-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="41357-106">Event ID</span></span>|<span data-ttu-id="41357-107">0</span><span class="sxs-lookup"><span data-stu-id="41357-107">0</span></span>|  
|<span data-ttu-id="41357-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="41357-108">Event Source</span></span>|<span data-ttu-id="41357-109">0</span><span class="sxs-lookup"><span data-stu-id="41357-109">0</span></span>|  
|<span data-ttu-id="41357-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="41357-110">Component</span></span>|<span data-ttu-id="41357-111">0</span><span class="sxs-lookup"><span data-stu-id="41357-111">0</span></span>|  
|<span data-ttu-id="41357-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="41357-112">Symbolic Name</span></span>|<span data-ttu-id="41357-113">0</span><span class="sxs-lookup"><span data-stu-id="41357-113">0</span></span>|  
|<span data-ttu-id="41357-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="41357-114">Message Text</span></span>|<span data-ttu-id="41357-115">メッセージ内に受信本文のパス式 "{0}" に一致する内容が見つかりません</span><span class="sxs-lookup"><span data-stu-id="41357-115">Unable to find match for inbound body path expression "{0}" in message</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="41357-116">説明</span><span class="sxs-lookup"><span data-stu-id="41357-116">Explanation</span></span>  
 <span data-ttu-id="41357-117">受信メッセージで実行された本文のパス式は、一致が返されませんでした。</span><span class="sxs-lookup"><span data-stu-id="41357-117">The body path expression executed on the incoming message did not return any match.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41357-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="41357-118">User Action</span></span>  
 <span data-ttu-id="41357-119">本文のパス式が正しいこと、および受信メッセージのデータが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="41357-119">Make sure that body path expression is correct, and the incoming message has the correct data.</span></span>  
  
1.  <span data-ttu-id="41357-120">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="41357-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="41357-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="41357-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="41357-122">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="41357-122">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="41357-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="41357-123">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="41357-124">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41357-124">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="41357-125">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="41357-125">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="41357-126">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="41357-126">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="41357-127">Wcf **[***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブです。</span><span class="sxs-lookup"><span data-stu-id="41357-127">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="41357-128">**受信 BizTalk メッセージ本文**セクションの情報を確認**本文のパス式**です。</span><span class="sxs-lookup"><span data-stu-id="41357-128">In the **Inbound BizTalk message body** section, check the information for **Body path expression**.</span></span>
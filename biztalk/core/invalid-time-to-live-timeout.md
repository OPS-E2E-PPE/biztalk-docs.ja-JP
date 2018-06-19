---
title: 有効期限のタイムアウト時間が無効です |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2ddb6de-8c3b-4dee-a984-980e1caea95e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9171fd311a07317c0480e6e4d1ef35742e0e8bcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262098"
---
# <a name="invalid-time-to-live-timeout"></a><span data-ttu-id="98fef-102">有効期限タイムアウトが無効です</span><span class="sxs-lookup"><span data-stu-id="98fef-102">Invalid time to live timeout</span></span>
## <a name="details"></a><span data-ttu-id="98fef-103">詳細</span><span class="sxs-lookup"><span data-stu-id="98fef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98fef-104">製品名</span><span class="sxs-lookup"><span data-stu-id="98fef-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="98fef-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="98fef-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="98fef-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="98fef-106">Event ID</span></span>|<span data-ttu-id="98fef-107">0</span><span class="sxs-lookup"><span data-stu-id="98fef-107">0</span></span>|  
|<span data-ttu-id="98fef-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="98fef-108">Event Source</span></span>|<span data-ttu-id="98fef-109">0</span><span class="sxs-lookup"><span data-stu-id="98fef-109">0</span></span>|  
|<span data-ttu-id="98fef-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="98fef-110">Component</span></span>|<span data-ttu-id="98fef-111">0</span><span class="sxs-lookup"><span data-stu-id="98fef-111">0</span></span>|  
|<span data-ttu-id="98fef-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="98fef-112">Symbolic Name</span></span>|<span data-ttu-id="98fef-113">0</span><span class="sxs-lookup"><span data-stu-id="98fef-113">0</span></span>|  
|<span data-ttu-id="98fef-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="98fef-114">Message Text</span></span>|<span data-ttu-id="98fef-115">有効期限のタイムアウトが無効です。</span><span class="sxs-lookup"><span data-stu-id="98fef-115">Invalid time to live timeout.</span></span> <span data-ttu-id="98fef-116">有効な範囲: 0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒</span><span class="sxs-lookup"><span data-stu-id="98fef-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="98fef-117">説明</span><span class="sxs-lookup"><span data-stu-id="98fef-117">Explanation</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98fef-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="98fef-118">User Action</span></span>  
 <span data-ttu-id="98fef-119">タイムアウト範囲を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="98fef-119">Use the following procedure to configure the timeout range.</span></span>  
  
#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="98fef-120">タイムアウト範囲を構成するには</span><span class="sxs-lookup"><span data-stu-id="98fef-120">To configure the timeout range</span></span>  
  
1.  <span data-ttu-id="98fef-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="98fef-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="98fef-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="98fef-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="98fef-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="98fef-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="98fef-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="98fef-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="98fef-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98fef-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="98fef-126">ポート**型**一覧で、 **Wcf-netmsmq**です。</span><span class="sxs-lookup"><span data-stu-id="98fef-126">In the port **Type** list, select **WCF-NetMsmq**.</span></span>  
  
7.  <span data-ttu-id="98fef-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="98fef-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="98fef-128">**Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="98fef-128">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="98fef-129">**キューの設定**セクションで、確認、**メッセージ ライブ (dd:hh:mm:ss) を時間**範囲が有効です。</span><span class="sxs-lookup"><span data-stu-id="98fef-129">In the **Queue Settings** section, ensure the **Message time to live (dd:hh:mm:ss)** range is valid.</span></span> <span data-ttu-id="98fef-130">使用可能な値は、0 ～ 23 時間、0 ～ 59 分、0 ～ 59 秒です。</span><span class="sxs-lookup"><span data-stu-id="98fef-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>
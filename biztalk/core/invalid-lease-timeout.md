---
title: 無効なリース タイムアウト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81b7b2a0-e9e6-4165-88bc-f712b5cbacb6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de2eef0627a4297524e0aca62fa9ae64c85e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257354"
---
# <a name="invalid-lease-timeout"></a><span data-ttu-id="f6e12-102">リース タイムアウトが無効です</span><span class="sxs-lookup"><span data-stu-id="f6e12-102">Invalid lease timeout</span></span>
## <a name="details"></a><span data-ttu-id="f6e12-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f6e12-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6e12-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f6e12-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f6e12-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f6e12-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="f6e12-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f6e12-106">Event ID</span></span>|<span data-ttu-id="f6e12-107">0</span><span class="sxs-lookup"><span data-stu-id="f6e12-107">0</span></span>|  
|<span data-ttu-id="f6e12-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f6e12-108">Event Source</span></span>|<span data-ttu-id="f6e12-109">0</span><span class="sxs-lookup"><span data-stu-id="f6e12-109">0</span></span>|  
|<span data-ttu-id="f6e12-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f6e12-110">Component</span></span>|<span data-ttu-id="f6e12-111">0</span><span class="sxs-lookup"><span data-stu-id="f6e12-111">0</span></span>|  
|<span data-ttu-id="f6e12-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f6e12-112">Symbolic Name</span></span>|<span data-ttu-id="f6e12-113">0</span><span class="sxs-lookup"><span data-stu-id="f6e12-113">0</span></span>|  
|<span data-ttu-id="f6e12-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f6e12-114">Message Text</span></span>|<span data-ttu-id="f6e12-115">リース タイムアウトが無効です。</span><span class="sxs-lookup"><span data-stu-id="f6e12-115">Invalid lease timeout.</span></span> <span data-ttu-id="f6e12-116">有効な範囲: 0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒</span><span class="sxs-lookup"><span data-stu-id="f6e12-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6e12-117">説明</span><span class="sxs-lookup"><span data-stu-id="f6e12-117">Explanation</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6e12-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f6e12-118">User Action</span></span>  
 <span data-ttu-id="f6e12-119">タイムアウト設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6e12-119">Use the following procedure to configure the timeout settings.</span></span>  
  
#### <a name="to-configure-the-timeout-settings"></a><span data-ttu-id="f6e12-120">タイムアウト設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="f6e12-120">To configure the timeout settings</span></span>  
  
1.  <span data-ttu-id="f6e12-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="f6e12-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f6e12-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="f6e12-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="f6e12-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="f6e12-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="f6e12-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f6e12-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="f6e12-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6e12-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="f6e12-126">ポート**型**一覧で、 **Wcf-nettcp**です。</span><span class="sxs-lookup"><span data-stu-id="f6e12-126">In the port **Type** list, select **WCF-NetTcP**.</span></span>  
  
7.  <span data-ttu-id="f6e12-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f6e12-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="f6e12-128">**Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="f6e12-128">In the **WCF-NetTcP Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="f6e12-129">**接続プール設定**セクションで、確認、**リース タイムアウト (hh:mm:ss)** 範囲が有効です。</span><span class="sxs-lookup"><span data-stu-id="f6e12-129">In the **Connection Pool settings** section, ensure the **Lease timeout (hh:mm:ss)** range is valid.</span></span> <span data-ttu-id="f6e12-130">使用可能な値は、0 ～ 23 時間、0 ～ 59 分、0 ～ 59 秒です。</span><span class="sxs-lookup"><span data-stu-id="f6e12-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>
---
title: 無効なリース タイムアウト |Microsoft Docs
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
ms.openlocfilehash: 5632ba534240b1d557e525345fcd8b96a4e43344
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990723"
---
# <a name="invalid-lease-timeout"></a><span data-ttu-id="4bb77-102">リース タイムアウトが無効です</span><span class="sxs-lookup"><span data-stu-id="4bb77-102">Invalid lease timeout</span></span>
## <a name="details"></a><span data-ttu-id="4bb77-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4bb77-103">Details</span></span>  

|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  <span data-ttu-id="4bb77-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4bb77-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="4bb77-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4bb77-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    <span data-ttu-id="4bb77-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4bb77-106">Event ID</span></span>     |                                            <span data-ttu-id="4bb77-107">0</span><span class="sxs-lookup"><span data-stu-id="4bb77-107">0</span></span>                                            |
|  <span data-ttu-id="4bb77-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4bb77-108">Event Source</span></span>   |                                            <span data-ttu-id="4bb77-109">0</span><span class="sxs-lookup"><span data-stu-id="4bb77-109">0</span></span>                                            |
|    <span data-ttu-id="4bb77-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4bb77-110">Component</span></span>    |                                            <span data-ttu-id="4bb77-111">0</span><span class="sxs-lookup"><span data-stu-id="4bb77-111">0</span></span>                                            |
|  <span data-ttu-id="4bb77-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4bb77-112">Symbolic Name</span></span>  |                                            <span data-ttu-id="4bb77-113">0</span><span class="sxs-lookup"><span data-stu-id="4bb77-113">0</span></span>                                            |
|  <span data-ttu-id="4bb77-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4bb77-114">Message Text</span></span>   | <span data-ttu-id="4bb77-115">リース タイムアウトが無効です。</span><span class="sxs-lookup"><span data-stu-id="4bb77-115">Invalid lease timeout.</span></span> <span data-ttu-id="4bb77-116">有効な範囲: 0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒</span><span class="sxs-lookup"><span data-stu-id="4bb77-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds</span></span> |

## <a name="explanation"></a><span data-ttu-id="4bb77-117">説明</span><span class="sxs-lookup"><span data-stu-id="4bb77-117">Explanation</span></span>  

## <a name="user-action"></a><span data-ttu-id="4bb77-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4bb77-118">User Action</span></span>  
 <span data-ttu-id="4bb77-119">タイムアウト設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4bb77-119">Use the following procedure to configure the timeout settings.</span></span>  

#### <a name="to-configure-the-timeout-settings"></a><span data-ttu-id="4bb77-120">タイムアウト設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="4bb77-120">To configure the timeout settings</span></span>  

1. <span data-ttu-id="4bb77-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4bb77-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="4bb77-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="4bb77-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="4bb77-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="4bb77-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="4bb77-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb77-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="4bb77-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bb77-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="4bb77-126">ポート**型**一覧で、 **Wcf-nettcp**します。</span><span class="sxs-lookup"><span data-stu-id="4bb77-126">In the port **Type** list, select **WCF-NetTcP**.</span></span>  

7. <span data-ttu-id="4bb77-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="4bb77-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="4bb77-128">**Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="4bb77-128">In the **WCF-NetTcP Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="4bb77-129">**接続プール設定**セクションを確認してください、**リース タイムアウト (hh:mm:ss)** 範囲が無効です。</span><span class="sxs-lookup"><span data-stu-id="4bb77-129">In the **Connection Pool settings** section, ensure the **Lease timeout (hh:mm:ss)** range is valid.</span></span> <span data-ttu-id="4bb77-130">使用可能な値は、0 ～ 23 時間、0 ～ 59 分、0 ～ 59 秒です。</span><span class="sxs-lookup"><span data-stu-id="4bb77-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>

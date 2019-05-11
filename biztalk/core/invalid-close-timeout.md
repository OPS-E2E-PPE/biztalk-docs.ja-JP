---
title: クローズ タイムアウトが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4510329-9fd9-428f-91a3-d72723e9a5e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e27f6164fbbbbc571d2751eeb590b135ef1102a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330861"
---
# <a name="invalid-close-timeout"></a><span data-ttu-id="7dff9-102">クローズ タイムアウトが無効です</span><span class="sxs-lookup"><span data-stu-id="7dff9-102">Invalid close timeout</span></span>
## <a name="details"></a><span data-ttu-id="7dff9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7dff9-103">Details</span></span>  

|                 |                                                                                          |
|-----------------|------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7dff9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7dff9-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="7dff9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7dff9-105">Product Version</span></span> |                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    <span data-ttu-id="7dff9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7dff9-106">Event ID</span></span>     |                                            <span data-ttu-id="7dff9-107">0</span><span class="sxs-lookup"><span data-stu-id="7dff9-107">0</span></span>                                             |
|  <span data-ttu-id="7dff9-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7dff9-108">Event Source</span></span>   |                                            <span data-ttu-id="7dff9-109">0</span><span class="sxs-lookup"><span data-stu-id="7dff9-109">0</span></span>                                             |
|    <span data-ttu-id="7dff9-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7dff9-110">Component</span></span>    |                                            <span data-ttu-id="7dff9-111">0</span><span class="sxs-lookup"><span data-stu-id="7dff9-111">0</span></span>                                             |
|  <span data-ttu-id="7dff9-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7dff9-112">Symbolic Name</span></span>  |                                            <span data-ttu-id="7dff9-113">0</span><span class="sxs-lookup"><span data-stu-id="7dff9-113">0</span></span>                                             |
|  <span data-ttu-id="7dff9-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7dff9-114">Message Text</span></span>   | <span data-ttu-id="7dff9-115">クローズ タイムアウトが無効です。</span><span class="sxs-lookup"><span data-stu-id="7dff9-115">Invalid close timeout.</span></span> <span data-ttu-id="7dff9-116">有効範囲:0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒。</span><span class="sxs-lookup"><span data-stu-id="7dff9-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span> |

## <a name="explanation"></a><span data-ttu-id="7dff9-117">説明</span><span class="sxs-lookup"><span data-stu-id="7dff9-117">Explanation</span></span>  

## <a name="user-action"></a><span data-ttu-id="7dff9-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7dff9-118">User Action</span></span>  
 <span data-ttu-id="7dff9-119">タイムアウト範囲を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7dff9-119">Use the following procedure to configure the timeout range.</span></span>  

#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="7dff9-120">タイムアウト範囲を構成するには</span><span class="sxs-lookup"><span data-stu-id="7dff9-120">To configure the timeout range</span></span>  

1. <span data-ttu-id="7dff9-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7dff9-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="7dff9-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="7dff9-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="7dff9-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="7dff9-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="7dff9-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7dff9-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="7dff9-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7dff9-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="7dff9-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7dff9-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="7dff9-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7dff9-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="7dff9-128">**WCF [**<em>トランスポートの種類</em>**] プロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="7dff9-128">In the **WCF [**<em>transport type</em>**] Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="7dff9-129">タイムアウト範囲が有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dff9-129">Ensure the timeout range is valid.</span></span> <span data-ttu-id="7dff9-130">指定できる値は、0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒です。</span><span class="sxs-lookup"><span data-stu-id="7dff9-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>

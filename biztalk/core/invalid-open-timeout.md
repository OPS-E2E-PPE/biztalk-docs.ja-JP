---
title: オープン タイムアウトが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0047cf43-fcc3-40b4-abeb-bf1b6e7a422b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32e06d5f26eafe5d5184a995adc7103e659a739
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023616"
---
# <a name="invalid-open-timeout"></a><span data-ttu-id="5746a-102">オープン タイムアウトが無効です</span><span class="sxs-lookup"><span data-stu-id="5746a-102">Invalid open timeout</span></span>
## <a name="details"></a><span data-ttu-id="5746a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5746a-103">Details</span></span>  

|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5746a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5746a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="5746a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5746a-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    <span data-ttu-id="5746a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5746a-106">Event ID</span></span>     |                                            <span data-ttu-id="5746a-107">0</span><span class="sxs-lookup"><span data-stu-id="5746a-107">0</span></span>                                            |
|  <span data-ttu-id="5746a-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5746a-108">Event Source</span></span>   |                                            <span data-ttu-id="5746a-109">0</span><span class="sxs-lookup"><span data-stu-id="5746a-109">0</span></span>                                            |
|    <span data-ttu-id="5746a-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5746a-110">Component</span></span>    |                                            <span data-ttu-id="5746a-111">0</span><span class="sxs-lookup"><span data-stu-id="5746a-111">0</span></span>                                            |
|  <span data-ttu-id="5746a-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5746a-112">Symbolic Name</span></span>  |                                            <span data-ttu-id="5746a-113">0</span><span class="sxs-lookup"><span data-stu-id="5746a-113">0</span></span>                                            |
|  <span data-ttu-id="5746a-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5746a-114">Message Text</span></span>   | <span data-ttu-id="5746a-115">オープン タイムアウトが無効です。</span><span class="sxs-lookup"><span data-stu-id="5746a-115">Invalid open timeout.</span></span> <span data-ttu-id="5746a-116">有効な範囲: 0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒。</span><span class="sxs-lookup"><span data-stu-id="5746a-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span> |

## <a name="explanation"></a><span data-ttu-id="5746a-117">説明</span><span class="sxs-lookup"><span data-stu-id="5746a-117">Explanation</span></span>  

## <a name="user-action"></a><span data-ttu-id="5746a-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5746a-118">User Action</span></span>  
 <span data-ttu-id="5746a-119">タイムアウト範囲を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5746a-119">Use the following procedure to configure the timeout range.</span></span>  

#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="5746a-120">タイムアウト範囲を構成するには</span><span class="sxs-lookup"><span data-stu-id="5746a-120">To configure the timeout range</span></span>  

1. <span data-ttu-id="5746a-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="5746a-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="5746a-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="5746a-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="5746a-123">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="5746a-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="5746a-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5746a-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="5746a-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5746a-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="5746a-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="5746a-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="5746a-127">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="5746a-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="5746a-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="5746a-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="5746a-129">タイムアウト範囲が有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5746a-129">Ensure the timeout range is valid.</span></span> <span data-ttu-id="5746a-130">使用可能な値は、0 ～ 23 時間、0 ～ 59 分、0 ～ 59 秒です。</span><span class="sxs-lookup"><span data-stu-id="5746a-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>

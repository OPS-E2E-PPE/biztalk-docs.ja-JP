---
title: 有効期限タイムアウトまでの時間が無効です |Microsoft Docs
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
ms.openlocfilehash: 8c984130ad3a85d6441a192506202489759b5bc9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330310"
---
# <a name="invalid-time-to-live-timeout"></a><span data-ttu-id="7ae2c-102">有効期限タイムアウトが無効です</span><span class="sxs-lookup"><span data-stu-id="7ae2c-102">Invalid time to live timeout</span></span>
## <a name="details"></a><span data-ttu-id="7ae2c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7ae2c-103">Details</span></span>  

|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7ae2c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7ae2c-104">Product Name</span></span>   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="7ae2c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7ae2c-105">Product Version</span></span> |                   [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    <span data-ttu-id="7ae2c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7ae2c-106">Event ID</span></span>     |                                               <span data-ttu-id="7ae2c-107">0</span><span class="sxs-lookup"><span data-stu-id="7ae2c-107">0</span></span>                                                |
|  <span data-ttu-id="7ae2c-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7ae2c-108">Event Source</span></span>   |                                               <span data-ttu-id="7ae2c-109">0</span><span class="sxs-lookup"><span data-stu-id="7ae2c-109">0</span></span>                                                |
|    <span data-ttu-id="7ae2c-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7ae2c-110">Component</span></span>    |                                               <span data-ttu-id="7ae2c-111">0</span><span class="sxs-lookup"><span data-stu-id="7ae2c-111">0</span></span>                                                |
|  <span data-ttu-id="7ae2c-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7ae2c-112">Symbolic Name</span></span>  |                                               <span data-ttu-id="7ae2c-113">0</span><span class="sxs-lookup"><span data-stu-id="7ae2c-113">0</span></span>                                                |
|  <span data-ttu-id="7ae2c-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7ae2c-114">Message Text</span></span>   | <span data-ttu-id="7ae2c-115">有効期限タイムアウト時間が無効です。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-115">Invalid time to live timeout.</span></span> <span data-ttu-id="7ae2c-116">有効範囲:0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒</span><span class="sxs-lookup"><span data-stu-id="7ae2c-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds</span></span> |

## <a name="explanation"></a><span data-ttu-id="7ae2c-117">説明</span><span class="sxs-lookup"><span data-stu-id="7ae2c-117">Explanation</span></span>  

## <a name="user-action"></a><span data-ttu-id="7ae2c-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7ae2c-118">User Action</span></span>  
 <span data-ttu-id="7ae2c-119">タイムアウト範囲を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-119">Use the following procedure to configure the timeout range.</span></span>  

#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="7ae2c-120">タイムアウト範囲を構成するには</span><span class="sxs-lookup"><span data-stu-id="7ae2c-120">To configure the timeout range</span></span>  

1. <span data-ttu-id="7ae2c-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="7ae2c-122">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="7ae2c-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="7ae2c-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="7ae2c-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="7ae2c-126">ポート**型**一覧で、 **Wcf-netmsmq**します。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-126">In the port **Type** list, select **WCF-NetMsmq**.</span></span>  

7. <span data-ttu-id="7ae2c-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="7ae2c-128">**Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-128">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="7ae2c-129">**キューの設定**セクションを確認してください、**ライブ (dd:hh:mm:ss) までの時間をメッセージ**範囲が無効です。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-129">In the **Queue Settings** section, ensure the **Message time to live (dd:hh:mm:ss)** range is valid.</span></span> <span data-ttu-id="7ae2c-130">指定できる値は、0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒です。</span><span class="sxs-lookup"><span data-stu-id="7ae2c-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>

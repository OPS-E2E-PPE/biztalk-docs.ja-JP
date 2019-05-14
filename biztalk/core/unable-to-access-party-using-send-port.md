---
title: パーティにアクセスできませんを使用してポートの送信 |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffacba77-76e8-4f03-be26-134a9999d6c1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b31650411fcdfdf3aaba70f3e25ee377d442cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292849"
---
# <a name="unable-to-access-party-using-send-port"></a><span data-ttu-id="fd88a-102">パーティにアクセスできませんを使用してポートを送信。</span><span class="sxs-lookup"><span data-stu-id="fd88a-102">Unable to access party using send port</span></span>
## <a name="details"></a><span data-ttu-id="fd88a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fd88a-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="fd88a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fd88a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="fd88a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fd88a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="fd88a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fd88a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="fd88a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fd88a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="fd88a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="fd88a-108">EDI</span></span> |
|    <span data-ttu-id="fd88a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fd88a-109">Component</span></span>    |                                       <span data-ttu-id="fd88a-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="fd88a-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="fd88a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fd88a-111">Symbolic Name</span></span>  |                       <span data-ttu-id="fd88a-112">UnableToLocateAS2PartyBySendPortNameError</span><span class="sxs-lookup"><span data-stu-id="fd88a-112">UnableToLocateAS2PartyBySendPortNameError</span></span>                        |
|  <span data-ttu-id="fd88a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fd88a-113">Message Text</span></span>   |                      <span data-ttu-id="fd88a-114">パーティにアクセスできません。 を使用してポートを送信します。 {0}</span><span class="sxs-lookup"><span data-stu-id="fd88a-114">Unable to access party using send port: {0}</span></span>                       |

## <a name="explanation"></a><span data-ttu-id="fd88a-115">説明</span><span class="sxs-lookup"><span data-stu-id="fd88a-115">Explanation</span></span>  
 <span data-ttu-id="fd88a-116">このエラーは、送信パイプラインがパーティに関連付けられた、指定した送信ポート、送信 AS2 メッセージを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="fd88a-116">This error indicates the send pipeline could not find a party associated with the specified send port for the outgoing AS2 message.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fd88a-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fd88a-117">User Action</span></span>  
 <span data-ttu-id="fd88a-118">このエラーを解決するには、指定された送信ポートとパーティを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="fd88a-118">To resolve this error, associate a party with the specified send port:</span></span>  

1. <span data-ttu-id="fd88a-119">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="fd88a-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="fd88a-120">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、 をクリック**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="fd88a-120">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  

3. <span data-ttu-id="fd88a-121">正しいパーティを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="fd88a-121">Right-click the correct party.</span></span>  

4. <span data-ttu-id="fd88a-122">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd88a-122">Click **Properties**.</span></span>  

5. <span data-ttu-id="fd88a-123">[*パーティ名*]**パーティ プロパティ** ダイアログ ボックスで、左側のウィンドウでクリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="fd88a-123">In the [*party name*] **Party Properties** dialog box, in the left pane, click **Send Ports**.</span></span>  

6. <span data-ttu-id="fd88a-124">送信ポート名を入力、**送信ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="fd88a-124">Enter the Send port name in the **Send Ports** list.</span></span>  

7. <span data-ttu-id="fd88a-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd88a-125">Click **OK**.</span></span>

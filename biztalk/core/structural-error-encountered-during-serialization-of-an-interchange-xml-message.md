---
title: インターチェンジ XML メッセージのシリアル化中に発生した構造のエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97939bfd-d1ee-455a-9952-4f25db020e7c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d2b57fb3c520b283fa8d0fbb160efb87d3378e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244150"
---
# <a name="structural-error-encountered-during-serialization-of-an-interchange-xml-message"></a><span data-ttu-id="50ba4-102">インターチェンジ XML メッセージのシリアル化中に発生した構造のエラー</span><span class="sxs-lookup"><span data-stu-id="50ba4-102">Structural error encountered during serialization of an interchange XML message</span></span>
## <a name="details"></a><span data-ttu-id="50ba4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="50ba4-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="50ba4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="50ba4-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="50ba4-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="50ba4-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="50ba4-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="50ba4-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="50ba4-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="50ba4-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="50ba4-108">EDI</span><span class="sxs-lookup"><span data-stu-id="50ba4-108">EDI</span></span> |
|    <span data-ttu-id="50ba4-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="50ba4-109">Component</span></span>    |                                       <span data-ttu-id="50ba4-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="50ba4-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="50ba4-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="50ba4-111">Symbolic Name</span></span>  |                                  <span data-ttu-id="50ba4-112">InvalidXmlNodeFound</span><span class="sxs-lookup"><span data-stu-id="50ba4-112">InvalidXmlNodeFound</span></span>                                   |
|  <span data-ttu-id="50ba4-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="50ba4-113">Message Text</span></span>   |    <span data-ttu-id="50ba4-114">インターチェンジ Xml メッセージのシリアル化中に発生した構造のエラー</span><span class="sxs-lookup"><span data-stu-id="50ba4-114">Structural error encountered during serialization of an Interchange Xml message</span></span>     |

## <a name="explanation"></a><span data-ttu-id="50ba4-115">説明</span><span class="sxs-lookup"><span data-stu-id="50ba4-115">Explanation</span></span>  
 <span data-ttu-id="50ba4-116">このエラーは、インターチェンジ XML メッセージのシリアル化中に構造エラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="50ba4-116">This error indicates that a structural error was encountered during serialization of an interchange XML message.</span></span> <span data-ttu-id="50ba4-117">BTS は XML StartElement または EndElement が検索しますが、代わりにさまざまな XML ノード型が発生しました。</span><span class="sxs-lookup"><span data-stu-id="50ba4-117">BTS was looking for an XML StartElement or EndElement but instead a different XML node type was encountered.</span></span>  

## <a name="user-action"></a><span data-ttu-id="50ba4-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="50ba4-118">User Action</span></span>  
 <span data-ttu-id="50ba4-119">このエラーを解決するには、メッセージの構造が正しいこと、もう一度やり直してを確認します。</span><span class="sxs-lookup"><span data-stu-id="50ba4-119">To resolve this error, make sure the message structure is correct, and try again:</span></span>  

1. <span data-ttu-id="50ba4-120">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="50ba4-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="50ba4-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 をクリック**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="50ba4-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and click **BizTalk Group**.</span></span>  

3. <span data-ttu-id="50ba4-122">右側のウィンドウでをクリックして、**グループ ハブ**タブ。</span><span class="sxs-lookup"><span data-stu-id="50ba4-122">In the right pane, click the **Group Hub** tab.</span></span>  

4. <span data-ttu-id="50ba4-123">クリックして**中断されたサービス インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="50ba4-123">Click **Suspended Service instances**.</span></span>  

5. <span data-ttu-id="50ba4-124">メッセージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="50ba4-124">Double-click the message.</span></span>  

6. <span data-ttu-id="50ba4-125">**サービスの詳細**ウィンドウで、をクリックして、**メッセージ**タブ。</span><span class="sxs-lookup"><span data-stu-id="50ba4-125">In the **Service Details** window, click the **Messages** tab.</span></span>  

7. <span data-ttu-id="50ba4-126">メッセージをもう一度ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="50ba4-126">Double-click the message again.</span></span>  

8. <span data-ttu-id="50ba4-127">左側のウィンドウで次のようにクリックします。**メッセージ部分/Body**します。</span><span class="sxs-lookup"><span data-stu-id="50ba4-127">In the left pane, click **Message Parts / Body**.</span></span>  

9. <span data-ttu-id="50ba4-128">メッセージの構造が正しいかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="50ba4-128">Determine if the message structure is correct.</span></span>

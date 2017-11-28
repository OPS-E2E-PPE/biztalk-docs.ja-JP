---
title: "インターチェンジ XML メッセージのシリアル化中に発生した構造のエラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97939bfd-d1ee-455a-9952-4f25db020e7c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44b56cce9fdd3704f7e6ddc2ba5b5bebb62d36e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="structural-error-encountered-during-serialization-of-an-interchange-xml-message"></a><span data-ttu-id="6530f-102">インターチェンジ XML メッセージのシリアル化中に発生した構造のエラー</span><span class="sxs-lookup"><span data-stu-id="6530f-102">Structural error encountered during serialization of an interchange XML message</span></span>
## <a name="details"></a><span data-ttu-id="6530f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6530f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6530f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6530f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6530f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6530f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="6530f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6530f-106">Event ID</span></span>|-|  
|<span data-ttu-id="6530f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6530f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6530f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6530f-108"> EDI</span></span>|  
|<span data-ttu-id="6530f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6530f-109">Component</span></span>|<span data-ttu-id="6530f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6530f-110">EDI Engine</span></span>|  
|<span data-ttu-id="6530f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6530f-111">Symbolic Name</span></span>|<span data-ttu-id="6530f-112">InvalidXmlNodeFound</span><span class="sxs-lookup"><span data-stu-id="6530f-112">InvalidXmlNodeFound</span></span>|  
|<span data-ttu-id="6530f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6530f-113">Message Text</span></span>|<span data-ttu-id="6530f-114">インターチェンジ XML メッセージのシリアル化中に構造エラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="6530f-114">Structural error encountered during serialization of an Interchange Xml message</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6530f-115">説明</span><span class="sxs-lookup"><span data-stu-id="6530f-115">Explanation</span></span>  
 <span data-ttu-id="6530f-116">このエラーは、インターチェンジ XML メッセージのシリアル化中に構造エラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="6530f-116">This error indicates that a structural error was encountered during serialization of an interchange XML message.</span></span> <span data-ttu-id="6530f-117">BTS は XML StartElement または EndElement を探していましたが、異なる XML ノードの種類が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6530f-117">BTS was looking for an XML StartElement or EndElement but instead a different XML node type was encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6530f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6530f-118">User Action</span></span>  
 <span data-ttu-id="6530f-119">このエラーを解決するには、メッセージ構造が正しいことを確認して、やり直します。</span><span class="sxs-lookup"><span data-stu-id="6530f-119">To resolve this error, make sure the message structure is correct, and try again:</span></span>  
  
1.  <span data-ttu-id="6530f-120">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="6530f-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6530f-121">コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、] をクリック**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="6530f-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and click **BizTalk Group**.</span></span>  
  
3.  <span data-ttu-id="6530f-122">右側のウィンドウでをクリックして、**グループ ハブ**タブです。</span><span class="sxs-lookup"><span data-stu-id="6530f-122">In the right pane, click the **Group Hub** tab.</span></span>  
  
4.  <span data-ttu-id="6530f-123">をクリックして**中断されたサービス インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="6530f-123">Click **Suspended Service instances**.</span></span>  
  
5.  <span data-ttu-id="6530f-124">メッセージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6530f-124">Double-click the message.</span></span>  
  
6.  <span data-ttu-id="6530f-125">**サービスの詳細**ウィンドウで、をクリックして、**メッセージ**タブです。</span><span class="sxs-lookup"><span data-stu-id="6530f-125">In the **Service Details** window, click the **Messages** tab.</span></span>  
  
7.  <span data-ttu-id="6530f-126">メッセージを再びダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6530f-126">Double-click the message again.</span></span>  
  
8.  <span data-ttu-id="6530f-127">左側のウィンドウでをクリックして**メッセージ部分/Body**です。</span><span class="sxs-lookup"><span data-stu-id="6530f-127">In the left pane, click **Message Parts / Body**.</span></span>  
  
9. <span data-ttu-id="6530f-128">メッセージ構造が正しいかどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="6530f-128">Determine if the message structure is correct.</span></span>
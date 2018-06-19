---
title: パーティにアクセスできませんを使用して送信ポート |。Microsoft ドキュメント
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
ms.openlocfilehash: 2aa582319226b114720ef234b8e3f65e416a94d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286530"
---
# <a name="unable-to-access-party-using-send-port"></a><span data-ttu-id="85b30-102">送信ポートを使用してパーティにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="85b30-102">Unable to access party using send port</span></span>
## <a name="details"></a><span data-ttu-id="85b30-103">詳細</span><span class="sxs-lookup"><span data-stu-id="85b30-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85b30-104">製品名</span><span class="sxs-lookup"><span data-stu-id="85b30-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="85b30-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="85b30-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="85b30-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="85b30-106">Event ID</span></span>|-|  
|<span data-ttu-id="85b30-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="85b30-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="85b30-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="85b30-108"> EDI</span></span>|  
|<span data-ttu-id="85b30-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="85b30-109">Component</span></span>|<span data-ttu-id="85b30-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="85b30-110">AS2 Engine</span></span>|  
|<span data-ttu-id="85b30-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="85b30-111">Symbolic Name</span></span>|<span data-ttu-id="85b30-112">UnableToLocateAS2PartyBySendPortNameError</span><span class="sxs-lookup"><span data-stu-id="85b30-112">UnableToLocateAS2PartyBySendPortNameError</span></span>|  
|<span data-ttu-id="85b30-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="85b30-113">Message Text</span></span>|<span data-ttu-id="85b30-114">パーティにアクセスできませんを使用して送信ポート: {0}。</span><span class="sxs-lookup"><span data-stu-id="85b30-114">Unable to access party using send port: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="85b30-115">説明</span><span class="sxs-lookup"><span data-stu-id="85b30-115">Explanation</span></span>  
 <span data-ttu-id="85b30-116">このエラーは、送信パイプラインが、送信 AS2 メッセージに対して指定された送信ポートに関連付けられたパーティを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="85b30-116">This error indicates the send pipeline could not find a party associated with the specified send port for the outgoing AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="85b30-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="85b30-117">User Action</span></span>  
 <span data-ttu-id="85b30-118">このエラーを解決するには、指定された送信ポートにパーティを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="85b30-118">To resolve this error, associate a party with the specified send port:</span></span>  
  
1.  <span data-ttu-id="85b30-119">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="85b30-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="85b30-120">コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、] をクリック**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="85b30-120">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  
  
3.  <span data-ttu-id="85b30-121">適切なパーティを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="85b30-121">Right-click the correct party.</span></span>  
  
4.  <span data-ttu-id="85b30-122">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85b30-122">Click **Properties**.</span></span>  
  
5.  <span data-ttu-id="85b30-123">[*パーティ名*]**パーティ プロパティ**ダイアログ ボックスで、左側のウィンドウでをクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="85b30-123">In the [*party name*] **Party Properties** dialog box, in the left pane, click **Send Ports**.</span></span>  
  
6.  <span data-ttu-id="85b30-124">[送信ポートの名前を入力、**送信ポート**] ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="85b30-124">Enter the Send port name in the **Send Ports** list.</span></span>  
  
7.  <span data-ttu-id="85b30-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85b30-125">Click **OK**.</span></span>
---
title: "アグリーメントにアクセスできません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72890ee9-54c9-48ed-8c6e-8b329d79c68b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a28b2b3587781d66e8788ca88931c7c5522bac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-agreement"></a><span data-ttu-id="5a5b6-102">アグリーメントにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="5a5b6-102">Unable to access agreement</span></span>
## <a name="details"></a><span data-ttu-id="5a5b6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5a5b6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a5b6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5a5b6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5a5b6-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5a5b6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5a5b6-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5a5b6-106">Event ID</span></span>|-|  
|<span data-ttu-id="5a5b6-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5a5b6-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5a5b6-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5a5b6-108"> EDI</span></span>|  
|<span data-ttu-id="5a5b6-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5a5b6-109">Component</span></span>|<span data-ttu-id="5a5b6-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5a5b6-110">EDI Engine</span></span>|  
|<span data-ttu-id="5a5b6-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5a5b6-111">Symbolic Name</span></span>|<span data-ttu-id="5a5b6-112">UnableToLocateAS2PartyError</span><span class="sxs-lookup"><span data-stu-id="5a5b6-112">UnableToLocateAS2PartyError</span></span>|  
|<span data-ttu-id="5a5b6-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5a5b6-113">Message Text</span></span>|<span data-ttu-id="5a5b6-114">アグリーメントにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-114">Unable to access agreement.</span></span> <span data-ttu-id="5a5b6-115">AS2From: {0} AS2To: {1} です。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-115">AS2From: {0} AS2To: {1}.</span></span> <span data-ttu-id="5a5b6-116">エラー: {2}</span><span class="sxs-lookup"><span data-stu-id="5a5b6-116">Error: {2}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a5b6-117">説明</span><span class="sxs-lookup"><span data-stu-id="5a5b6-117">Explanation</span></span>  
 <span data-ttu-id="5a5b6-118">このエラーは、BizTalk Server が、指定された修飾子と値のパーティを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-118">This error indicates BizTalk Server could not find a party for the given qualifier and value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a5b6-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5a5b6-119">User Action</span></span>  
 <span data-ttu-id="5a5b6-120">このエラーを解決するには、特定の修飾子のパーティ エイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-120">To resolve this error, create a party alias for the given qualifier:</span></span>  
  
1.  <span data-ttu-id="5a5b6-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5a5b6-122">コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、] をクリック**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  
  
3.  <span data-ttu-id="5a5b6-123">適切なパーティを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-123">Right-click the correct party.</span></span>  
  
4.  <span data-ttu-id="5a5b6-124">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-124">Click **Properties**.</span></span>  
  
5.  <span data-ttu-id="5a5b6-125">[*パーティ名*]**パーティ プロパティ** ダイアログ ボックスで、入力**ediint-as2 From Value**で、**名前**列です。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-125">In the [*party name*] **Party Properties** dialog box, enter **EDIINT-AS2 From Value** in the **Name** column.</span></span>  
  
6.  <span data-ttu-id="5a5b6-126">パーティ名を入力、**値**列です。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-126">Enter the party name in the **Value** column.</span></span>  
  
7.  <span data-ttu-id="5a5b6-127">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a5b6-127">Click **OK**.</span></span>
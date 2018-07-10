---
title: アグリーメントにアクセスできません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72890ee9-54c9-48ed-8c6e-8b329d79c68b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9c8d8126a7b38d95adfce1e813dd2a86ccde24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024536"
---
# <a name="unable-to-access-agreement"></a><span data-ttu-id="6207d-102">アグリーメントにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="6207d-102">Unable to access agreement</span></span>
## <a name="details"></a><span data-ttu-id="6207d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6207d-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6207d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6207d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6207d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6207d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6207d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6207d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6207d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6207d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6207d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6207d-108"> EDI</span></span> |
|    <span data-ttu-id="6207d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6207d-109">Component</span></span>    |                                       <span data-ttu-id="6207d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6207d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6207d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6207d-111">Symbolic Name</span></span>  |                              <span data-ttu-id="6207d-112">UnableToLocateAS2PartyError</span><span class="sxs-lookup"><span data-stu-id="6207d-112">UnableToLocateAS2PartyError</span></span>                               |
|  <span data-ttu-id="6207d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6207d-113">Message Text</span></span>   |            <span data-ttu-id="6207d-114">アグリーメントにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6207d-114">Unable to access agreement.</span></span> <span data-ttu-id="6207d-115">AS2From: {0} AS2To:{1}します。</span><span class="sxs-lookup"><span data-stu-id="6207d-115">AS2From: {0} AS2To: {1}.</span></span> <span data-ttu-id="6207d-116">エラー: {2}</span><span class="sxs-lookup"><span data-stu-id="6207d-116">Error: {2}</span></span>             |

## <a name="explanation"></a><span data-ttu-id="6207d-117">説明</span><span class="sxs-lookup"><span data-stu-id="6207d-117">Explanation</span></span>  
 <span data-ttu-id="6207d-118">このエラーは、BizTalk Server が、指定された修飾子と値のパーティを見つけられなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="6207d-118">This error indicates BizTalk Server could not find a party for the given qualifier and value.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6207d-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6207d-119">User Action</span></span>  
 <span data-ttu-id="6207d-120">このエラーを解決するには、特定の修飾子のパーティ エイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6207d-120">To resolve this error, create a party alias for the given qualifier:</span></span>  

1. <span data-ttu-id="6207d-121">クリックして**開始**、] をクリックして**すべてのプログラム**、] をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6207d-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="6207d-122">[コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、] をクリック**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="6207d-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  

3. <span data-ttu-id="6207d-123">適切なパーティを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="6207d-123">Right-click the correct party.</span></span>  

4. <span data-ttu-id="6207d-124">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6207d-124">Click **Properties**.</span></span>  

5. <span data-ttu-id="6207d-125">[*パーティ名*]**パーティ プロパティ**] ダイアログ ボックスに、入力**ediint-as2 From 値**で、**名前**列。</span><span class="sxs-lookup"><span data-stu-id="6207d-125">In the [*party name*] **Party Properties** dialog box, enter **EDIINT-AS2 From Value** in the **Name** column.</span></span>  

6. <span data-ttu-id="6207d-126">パーティ名を入力、**値**列。</span><span class="sxs-lookup"><span data-stu-id="6207d-126">Enter the party name in the **Value** column.</span></span>  

7. <span data-ttu-id="6207d-127">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6207d-127">Click **OK**.</span></span>

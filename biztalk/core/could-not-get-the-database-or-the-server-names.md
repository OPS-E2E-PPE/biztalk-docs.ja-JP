---
title: "データベースまたはサーバー名を取得できませんでした |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0590f43b-0aec-491f-bca5-c50ab12552a5
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16c694acdc78b704eb6f2578df99239442fd897e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="could-not-get-the-database-or-the-server-names"></a><span data-ttu-id="5f54b-102">データベース名またはサーバー名を取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="5f54b-102">Could not get the database or the server names</span></span>
## <a name="details"></a><span data-ttu-id="5f54b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5f54b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f54b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5f54b-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5f54b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5f54b-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5f54b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5f54b-106">Event ID</span></span>|-|  
|<span data-ttu-id="5f54b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5f54b-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5f54b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5f54b-108"> EDI</span></span>|  
|<span data-ttu-id="5f54b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5f54b-109">Component</span></span>|<span data-ttu-id="5f54b-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5f54b-110">EDI Engine</span></span>|  
|<span data-ttu-id="5f54b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5f54b-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="5f54b-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5f54b-112">Message Text</span></span>|<span data-ttu-id="5f54b-113">データベース名またはサーバー名を取得できませんでした</span><span class="sxs-lookup"><span data-stu-id="5f54b-113">Could not get the database or the server names</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5f54b-114">説明</span><span class="sxs-lookup"><span data-stu-id="5f54b-114">Explanation</span></span>  
 <span data-ttu-id="5f54b-115">このエラーは、BizTalk がレジストリから BizTalkMgmtDb 名とサーバー名を読み取れなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5f54b-115">This error indicates BizTalk could not read the BizTalkMgmtDb name and Server name from registry.</span></span> <span data-ttu-id="5f54b-116">このエラーの考えられる原因の 1 つとして、BizTalk グループが構成されていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="5f54b-116">One possible reason for this error is the BizTalk Group is not configured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5f54b-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5f54b-117">User Action</span></span>  
 <span data-ttu-id="5f54b-118">このエラーを解決するには、次のようにして BizTalk グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="5f54b-118">To resolve this error, configure the BizTalk Group:</span></span>  
  
1.  <span data-ttu-id="5f54b-119">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5f54b-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5f54b-120">コンソール ルートで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]] を展開します。</span><span class="sxs-lookup"><span data-stu-id="5f54b-120">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
3.  <span data-ttu-id="5f54b-121">右クリック**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="5f54b-121">Right-click **BizTalk Group**.</span></span>  
  
4.  <span data-ttu-id="5f54b-122">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f54b-122">Click **Properties**.</span></span>  
  
5.  <span data-ttu-id="5f54b-123">左側のウィンドウでをクリックして**全般**です。</span><span class="sxs-lookup"><span data-stu-id="5f54b-123">In the left pane, click **General**.</span></span>  
  
6.  <span data-ttu-id="5f54b-124">確認、**サーバー**名および**データベース**名が正しい。</span><span class="sxs-lookup"><span data-stu-id="5f54b-124">Verify the **Server** name and **Database** name are correct.</span></span>
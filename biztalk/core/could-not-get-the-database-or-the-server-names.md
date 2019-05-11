---
title: データベース名またはサーバー名を取得できませんでした。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0590f43b-0aec-491f-bca5-c50ab12552a5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 720e84c9d2305b85ec79f76873778e476f670900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354342"
---
# <a name="could-not-get-the-database-or-the-server-names"></a><span data-ttu-id="db853-102">データベース名またはサーバー名を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="db853-102">Could not get the database or the server names</span></span>
## <a name="details"></a><span data-ttu-id="db853-103">詳細</span><span class="sxs-lookup"><span data-stu-id="db853-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="db853-104">製品名</span><span class="sxs-lookup"><span data-stu-id="db853-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="db853-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="db853-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="db853-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="db853-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="db853-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="db853-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="db853-108">EDI</span><span class="sxs-lookup"><span data-stu-id="db853-108">EDI</span></span> |
|    <span data-ttu-id="db853-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="db853-109">Component</span></span>    |                                       <span data-ttu-id="db853-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="db853-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="db853-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="db853-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="db853-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="db853-112">Message Text</span></span>   |                     <span data-ttu-id="db853-113">データベース名またはサーバー名を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="db853-113">Could not get the database or the server names</span></span>                     |

## <a name="explanation"></a><span data-ttu-id="db853-114">説明</span><span class="sxs-lookup"><span data-stu-id="db853-114">Explanation</span></span>  
 <span data-ttu-id="db853-115">このエラーは、BizTalk から読み取れませんでした BizTalkMgmtDb 名とサーバー名レジストリを示します。</span><span class="sxs-lookup"><span data-stu-id="db853-115">This error indicates BizTalk could not read the BizTalkMgmtDb name and Server name from registry.</span></span> <span data-ttu-id="db853-116">このエラーの考えられる理由の 1 つは、BizTalk グループが構成されていません。</span><span class="sxs-lookup"><span data-stu-id="db853-116">One possible reason for this error is the BizTalk Group is not configured.</span></span>  

## <a name="user-action"></a><span data-ttu-id="db853-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="db853-117">User Action</span></span>  
 <span data-ttu-id="db853-118">このエラーを解決するには、BizTalk グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="db853-118">To resolve this error, configure the BizTalk Group:</span></span>  

1. <span data-ttu-id="db853-119">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="db853-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="db853-120">コンソール ルートで [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="db853-120">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

3. <span data-ttu-id="db853-121">右クリックして**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="db853-121">Right-click **BizTalk Group**.</span></span>  

4. <span data-ttu-id="db853-122">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db853-122">Click **Properties**.</span></span>  

5. <span data-ttu-id="db853-123">左側のウィンドウで次のようにクリックします。**全般**します。</span><span class="sxs-lookup"><span data-stu-id="db853-123">In the left pane, click **General**.</span></span>  

6. <span data-ttu-id="db853-124">確認、 **Server**名と**データベース**名が正しい。</span><span class="sxs-lookup"><span data-stu-id="db853-124">Verify the **Server** name and **Database** name are correct.</span></span>

---
title: スケジューラはバッチをスケジュールできませんでした。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ac6d79c-c995-4c95-a4da-ee2f50b9a13a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbd425c8f7faacaa38ac11375905f701f597faf6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984403"
---
# <a name="scheduler-was-unable-to-schedule-the-batch"></a><span data-ttu-id="5ca22-102">スケジューラはバッチをスケジュールできませんでした</span><span class="sxs-lookup"><span data-stu-id="5ca22-102">Scheduler was unable to schedule the batch</span></span>
## <a name="details"></a><span data-ttu-id="5ca22-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5ca22-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5ca22-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5ca22-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5ca22-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5ca22-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5ca22-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5ca22-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5ca22-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5ca22-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5ca22-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5ca22-108"> EDI</span></span> |
|    <span data-ttu-id="5ca22-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5ca22-109">Component</span></span>    |                                    <span data-ttu-id="5ca22-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="5ca22-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="5ca22-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5ca22-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="5ca22-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5ca22-112">Message Text</span></span>   |                       <span data-ttu-id="5ca22-113">スケジューラはバッチをスケジュールできませんでした</span><span class="sxs-lookup"><span data-stu-id="5ca22-113">Scheduler was unable to schedule the batch</span></span>                       |

## <a name="explanation"></a><span data-ttu-id="5ca22-114">説明</span><span class="sxs-lookup"><span data-stu-id="5ca22-114">Explanation</span></span>  
 <span data-ttu-id="5ca22-115">このエラーは、スケジューラが次回のバッチ リリースを特定できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5ca22-115">This error indicates the scheduler could not determine the next occurrence of a batch release.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5ca22-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5ca22-116">User Action</span></span>  
 <span data-ttu-id="5ca22-117">このエラーを解決するには、バッチ リリース スケジュールが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ca22-117">To resolve this error, make sure the batch release schedule is valid:</span></span>  

1. <span data-ttu-id="5ca22-118">クリックして**開始**、] をクリックして**すべてのプログラム**、] をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="5ca22-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="5ca22-119">[コンソール ルートで [ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、] をクリック**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="5ca22-119">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  

3. <span data-ttu-id="5ca22-120">適切なパーティを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5ca22-120">Right-click the correct party.</span></span>  

4. <span data-ttu-id="5ca22-121">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ca22-121">Click **Properties**.</span></span>  

5. <span data-ttu-id="5ca22-122">[*パーティ名*]**パーティ プロパティ**] ダイアログ ボックスで、左側のウィンドウでクリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="5ca22-122">In the [*party name*] **Party Properties** dialog box, in the left pane, click **Send Ports**.</span></span>  

6. <span data-ttu-id="5ca22-123">送信ポート名を入力、**送信ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="5ca22-123">Enter the Send port name in the **Send Ports** list.</span></span>  

7. <span data-ttu-id="5ca22-124">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ca22-124">Click **OK**.</span></span>

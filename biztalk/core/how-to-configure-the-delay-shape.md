---
title: 遅延図形を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer], configuring
- Delay shape [Orchestration Designer]
- Delay shape [Orchestration Designer], timeouts
- Delay shape [Orchestration Designer], about Delay shape
- configuring [Orchestration Designer], Delay shapes
ms.assetid: 727be28d-932a-41d5-af3f-3ee6f7129a17
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b76448398facd3af7f3b9712491f9895ffb406d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-configure-the-delay-shape"></a><span data-ttu-id="7a559-102">遅延図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="7a559-102">How to Configure the Delay Shape</span></span>
<span data-ttu-id="7a559-103">![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")</span><span class="sxs-lookup"><span data-stu-id="7a559-103">![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")</span></span>  
<span data-ttu-id="7a559-104">遅延図形</span><span class="sxs-lookup"><span data-stu-id="7a559-104">Delay shape</span></span>  
  
 <span data-ttu-id="7a559-105">タイムアウトを指定する 2 つの方法がある、 **遅延**:</span><span class="sxs-lookup"><span data-stu-id="7a559-105">There are two ways to specify the timeout for a **Delay**:</span></span>  
  
-   <span data-ttu-id="7a559-106">使用する **System.DateTime**, それが原因で、オーケストレーションを指定した日付まで一時停止、および日時に達した。</span><span class="sxs-lookup"><span data-stu-id="7a559-106">You can use **System.DateTime**, which causes your orchestration to pause until the specified date and time is reached.</span></span>  
  
     <span data-ttu-id="7a559-107">System.DateTime.UtcNow.AddSeconds(60)</span><span class="sxs-lookup"><span data-stu-id="7a559-107">System.DateTime.UtcNow.AddSeconds(60)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a559-108">遅延が表現する必要が世界協定時刻 (UTC) を使用する場合 **DateTime**します。</span><span class="sxs-lookup"><span data-stu-id="7a559-108">Delays must be expressed in Coordinated Universal Time (UTC) when using **DateTime**.</span></span>  
  
-   <span data-ttu-id="7a559-109">使用する **System.TimeSpan**, 、それが原因で時間の指定した時間一時停止するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="7a559-109">You can use **System.TimeSpan**, which causes your orchestration to pause for the specified length of time.</span></span>  
  
     <span data-ttu-id="7a559-110">System.TimeSpan(0, 1, 0)</span><span class="sxs-lookup"><span data-stu-id="7a559-110">System.TimeSpan(0, 1, 0)</span></span>  
  
 <span data-ttu-id="7a559-111">場合、 **遅延** 図形内部にある、 **リッスン** 図形をする必要はありません、式の末尾にセミコロンを追加します。</span><span class="sxs-lookup"><span data-stu-id="7a559-111">If your **Delay** shape is inside a **Listen** shape, you do not need to add a semicolon at the end of the expression.</span></span>  
  
 <span data-ttu-id="7a559-112">詳細については **System.DateTime** と **System.TimeSpan**, の「DateTime 構造体」および「TimeSpan 構造体」を参照してください、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 連結ヘルプ コレクションです。</span><span class="sxs-lookup"><span data-stu-id="7a559-112">For more information about **System.DateTime** and **System.TimeSpan**, see "DateTime Structure" and "TimeSpan Structure" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a559-113">複数のコンピューターのインストール環境で、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server が別々 のコンピューターにインストールされていると、 **遅延** 図形が時間のために予想よりも早く終了する可能性があります [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] マシンは同期されていません。</span><span class="sxs-lookup"><span data-stu-id="7a559-113">In a multiple machines installation environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are installed on separated machines, the **Delay** shape may end earlier than expected because of the times on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] machines are unsynchronized.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a559-114">ストレス条件下で指定されたタイムアウト、 **遅延** 図形に指定したものよりも後で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a559-114">Under the stress condition, the timeout specified in the **Delay** shape may occur later than what you have specified.</span></span> <span data-ttu-id="7a559-115">この遅れは、ストレス条件下でスレッドが不足するために起こります。</span><span class="sxs-lookup"><span data-stu-id="7a559-115">This is because of the thread starvation under the stress condition.</span></span>  
  
### <a name="to-configure-a-delay-shape"></a><span data-ttu-id="7a559-116">遅延図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="7a559-116">To configure a Delay shape</span></span>  
  
1.  <span data-ttu-id="7a559-117">BizTalk 式エディターが表示されていない場合を右クリックし、 **遅延** 図形を **遅延の編集**, は、[プロパティ] ウィンドウで、 **省略記号** (**.**) ボタンをクリックして、 **式** プロパティです。</span><span class="sxs-lookup"><span data-stu-id="7a559-117">If BizTalk Expression Editor is not visible, right-click the **Delay** shape and click **Edit Delay**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="7a559-118">BizTalk 式エディターを返す式を作成、 **System.DateTime** オブジェクトまたは **System.TimeSpan** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7a559-118">In BizTalk Expression Editor, create an expression that returns a **System.DateTime** object or a **System.TimeSpan** object.</span></span> <span data-ttu-id="7a559-119">詳細については、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a559-119">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>
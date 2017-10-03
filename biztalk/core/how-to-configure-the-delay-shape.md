---
title: "遅延図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer], configuring
- Delay shape [Orchestration Designer]
- Delay shape [Orchestration Designer], timeouts
- Delay shape [Orchestration Designer], about Delay shape
- configuring [Orchestration Designer], Delay shapes
ms.assetid: 727be28d-932a-41d5-af3f-3ee6f7129a17
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b76448398facd3af7f3b9712491f9895ffb406d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-delay-shape"></a><span data-ttu-id="12c11-102">遅延図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="12c11-102">How to Configure the Delay Shape</span></span>
![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")  
<span data-ttu-id="12c11-103">遅延図形</span><span class="sxs-lookup"><span data-stu-id="12c11-103">Delay shape</span></span>  
  
 <span data-ttu-id="12c11-104">タイムアウトを指定する 2 つの方法、**遅延**:</span><span class="sxs-lookup"><span data-stu-id="12c11-104">There are two ways to specify the timeout for a **Delay**:</span></span>  
  
-   <span data-ttu-id="12c11-105">使用することができます**System.DateTime**それが原因で、指定した日付までを一時停止するオーケストレーション、および日時に達した。</span><span class="sxs-lookup"><span data-stu-id="12c11-105">You can use **System.DateTime**, which causes your orchestration to pause until the specified date and time is reached.</span></span>  
  
     <span data-ttu-id="12c11-106">System.DateTime.UtcNow.AddSeconds(60)</span><span class="sxs-lookup"><span data-stu-id="12c11-106">System.DateTime.UtcNow.AddSeconds(60)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12c11-107">遅延表現する必要が世界協定時刻 (UTC) で使用するときに**DateTime**です。</span><span class="sxs-lookup"><span data-stu-id="12c11-107">Delays must be expressed in Coordinated Universal Time (UTC) when using **DateTime**.</span></span>  
  
-   <span data-ttu-id="12c11-108">使用することができます**System.TimeSpan**、それが原因で、オーケストレーションを時間の指定された長さの一時停止します。</span><span class="sxs-lookup"><span data-stu-id="12c11-108">You can use **System.TimeSpan**, which causes your orchestration to pause for the specified length of time.</span></span>  
  
     <span data-ttu-id="12c11-109">System.TimeSpan(0, 1, 0)</span><span class="sxs-lookup"><span data-stu-id="12c11-109">System.TimeSpan(0, 1, 0)</span></span>  
  
 <span data-ttu-id="12c11-110">場合、**遅延**図形内部にある、**リッスン**図形、する必要はありません、式の末尾にセミコロンを追加します。</span><span class="sxs-lookup"><span data-stu-id="12c11-110">If your **Delay** shape is inside a **Listen** shape, you do not need to add a semicolon at the end of the expression.</span></span>  
  
 <span data-ttu-id="12c11-111">詳細については**System.DateTime**と**System.TimeSpan**、"DateTime 構造体」および「TimeSpan 構造体」を参照して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクションです。</span><span class="sxs-lookup"><span data-stu-id="12c11-111">For more information about **System.DateTime** and **System.TimeSpan**, see "DateTime Structure" and "TimeSpan Structure" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12c11-112">複数のコンピューターのインストール環境で、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server が別々 のコンピューターにインストールされていると、**遅延**図形が時間のために予想よりも早く終了する可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]マシンは同期されていません。</span><span class="sxs-lookup"><span data-stu-id="12c11-112">In a multiple machines installation environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are installed on separated machines, the **Delay** shape may end earlier than expected because of the times on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] machines are unsynchronized.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12c11-113">ストレス条件下で指定されたタイムアウト、**遅延**図形に指定したよりも後で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12c11-113">Under the stress condition, the timeout specified in the **Delay** shape may occur later than what you have specified.</span></span> <span data-ttu-id="12c11-114">この遅れは、ストレス条件下でスレッドが不足するために起こります。</span><span class="sxs-lookup"><span data-stu-id="12c11-114">This is because of the thread starvation under the stress condition.</span></span>  
  
### <a name="to-configure-a-delay-shape"></a><span data-ttu-id="12c11-115">遅延図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="12c11-115">To configure a Delay shape</span></span>  
  
1.  <span data-ttu-id="12c11-116">BizTalk 式エディターが表示されていない場合を右クリックし、**遅延**図形をクリックして**遅延の編集**、[プロパティ] ウィンドウで次のようにクリックしますまたは、**省略記号**( **。...**) ボタンをクリックして、**式**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="12c11-116">If BizTalk Expression Editor is not visible, right-click the **Delay** shape and click **Edit Delay**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="12c11-117">BizTalk 式エディタで、作成を返す式、 **System.DateTime**オブジェクトまたは**System.TimeSpan**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="12c11-117">In BizTalk Expression Editor, create an expression that returns a **System.DateTime** object or a **System.TimeSpan** object.</span></span> <span data-ttu-id="12c11-118">詳細については、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="12c11-118">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>
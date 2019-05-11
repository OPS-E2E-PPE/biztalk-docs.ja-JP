---
title: 遅延図形を構成する方法 |Microsoft Docs
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdfe0ca86475f3d330faea1fa5cd084fa3af4910
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386125"
---
# <a name="how-to-configure-the-delay-shape"></a><span data-ttu-id="466e0-102">遅延図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="466e0-102">How to Configure the Delay Shape</span></span>
<span data-ttu-id="466e0-103">![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")</span><span class="sxs-lookup"><span data-stu-id="466e0-103">![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")</span></span>  
<span data-ttu-id="466e0-104">遅延図形</span><span class="sxs-lookup"><span data-stu-id="466e0-104">Delay shape</span></span>  
  
 <span data-ttu-id="466e0-105">タイムアウトを指定する 2 つの方法がある、**遅延**:</span><span class="sxs-lookup"><span data-stu-id="466e0-105">There are two ways to specify the timeout for a **Delay**:</span></span>  
  
- <span data-ttu-id="466e0-106">使用することができます**System.DateTime**を指定した日付まで一時停止するオーケストレーションを停止して、時間に到達します。</span><span class="sxs-lookup"><span data-stu-id="466e0-106">You can use **System.DateTime**, which causes your orchestration to pause until the specified date and time is reached.</span></span>  
  
   <span data-ttu-id="466e0-107">System.DateTime.UtcNow.AddSeconds(60)</span><span class="sxs-lookup"><span data-stu-id="466e0-107">System.DateTime.UtcNow.AddSeconds(60)</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="466e0-108">使用する場合、遅延で世界協定時刻 (UTC) でが表現する必要があります**DateTime**します。</span><span class="sxs-lookup"><span data-stu-id="466e0-108">Delays must be expressed in Coordinated Universal Time (UTC) when using **DateTime**.</span></span>  
  
- <span data-ttu-id="466e0-109">使用することができます**System.TimeSpan**、指定した長さの時間一時停止するオーケストレーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="466e0-109">You can use **System.TimeSpan**, which causes your orchestration to pause for the specified length of time.</span></span>  
  
   <span data-ttu-id="466e0-110">System.TimeSpan(0, 1, 0)</span><span class="sxs-lookup"><span data-stu-id="466e0-110">System.TimeSpan(0, 1, 0)</span></span>  
  
  <span data-ttu-id="466e0-111">場合、**遅延**内の図形は、**リッスン**図形、する必要はありません、式の末尾にセミコロンを追加します。</span><span class="sxs-lookup"><span data-stu-id="466e0-111">If your **Delay** shape is inside a **Listen** shape, you do not need to add a semicolon at the end of the expression.</span></span>  
  
  <span data-ttu-id="466e0-112">詳細については**System.DateTime**と**System.TimeSpan**の「DateTime 構造体」および「TimeSpan 構造体」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクションです。</span><span class="sxs-lookup"><span data-stu-id="466e0-112">For more information about **System.DateTime** and **System.TimeSpan**, see "DateTime Structure" and "TimeSpan Structure" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="466e0-113">複数のマシンのインストール環境で、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server が別々 のコンピューターにインストールされていると、**遅延**図形がで時間が原因で予期される値よりも早く終了する可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]マシンは同期されません。</span><span class="sxs-lookup"><span data-stu-id="466e0-113">In a multiple machines installation environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are installed on separated machines, the **Delay** shape may end earlier than expected because of the times on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] machines are unsynchronized.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="466e0-114">ストレス条件下で、タイムアウトが指定された、**遅延**図形に指定したものよりも後で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="466e0-114">Under the stress condition, the timeout specified in the **Delay** shape may occur later than what you have specified.</span></span> <span data-ttu-id="466e0-115">この遅れは、ストレス条件下でスレッドが不足するために起こります。</span><span class="sxs-lookup"><span data-stu-id="466e0-115">This is because of the thread starvation under the stress condition.</span></span>  
  
### <a name="to-configure-a-delay-shape"></a><span data-ttu-id="466e0-116">遅延図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="466e0-116">To configure a Delay shape</span></span>  
  
1.  <span data-ttu-id="466e0-117">BizTalk 式エディターが表示されていない場合を右クリックし、 **遅延** 図形を **遅延の編集**, は、[プロパティ] ウィンドウで、 **省略記号** (**...**) ボタンをクリックして、 **式** プロパティです。</span><span class="sxs-lookup"><span data-stu-id="466e0-117">If BizTalk Expression Editor is not visible, right-click the **Delay** shape and click **Edit Delay**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="466e0-118">BizTalk 式エディターで、作成を返す式、 **System.DateTime**オブジェクトまたは**System.TimeSpan**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="466e0-118">In BizTalk Expression Editor, create an expression that returns a **System.DateTime** object or a **System.TimeSpan** object.</span></span> <span data-ttu-id="466e0-119">詳細については、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="466e0-119">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>
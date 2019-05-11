---
title: ソリューションのシナリオの手順 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77751c15-9b67-4587-8bc8-2be65f13d339
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd2f7623487670041ed2684fc096b669eaef1a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394022"
---
# <a name="scenario-solution-steps"></a><span data-ttu-id="5d22e-102">ソリューションのシナリオの手順</span><span class="sxs-lookup"><span data-stu-id="5d22e-102">Scenario Solution Steps</span></span>
<span data-ttu-id="5d22e-103">ESB 例外管理フレームワークは、請求書メッセージに、処理中にエラーが発生する無効なデータが含まれている場合では、このトピックで前述したように、例外を処理するためのシンプルなソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-103">The ESB Exception Management Framework provides a simple solution for handling an exception when an invoice message contains invalid data that causes an error during processing, as described earlier in this topic.</span></span> <span data-ttu-id="5d22e-104">以下は、1 つの方法がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5d22e-104">The following is one approach you could take:</span></span>  
  
1.  <span data-ttu-id="5d22e-105">チームの開発者に、Microsoft BizTalk に基づいて最後に配置された、財務報告アプリケーションに対する責任を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5d22e-105">Assign responsibility for the recently deployed Financial Reporting application based on Microsoft BizTalk to a developer on your team.</span></span>  
  
2.  <span data-ttu-id="5d22e-106">ESB 管理ポータルで新しい ESB エラー メッセージが到着します。メッセージでは、財務報告の BizTalk アプリケーション内のオーケストレーションでのデータ整合性の問題を示します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-106">A new ESB fault message arrives in the ESB Management Portal; the message indicates a data integrity issue in an orchestration in the Financial Reporting BizTalk application.</span></span>  
  
3.  <span data-ttu-id="5d22e-107">管理者やオペレーターが、新しい例外の開発者に通知します。 または、開発者が、例外が発生したときに自動で通知に登録します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-107">The administrator or operator notifies the developer of the new exception, or the developer registers for automatic notification when an exception occurs.</span></span> <span data-ttu-id="5d22e-108">次の理由の 1 つこの通知が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d22e-108">This notification may occur for one of the following reasons:</span></span>  
  
    -   <span data-ttu-id="5d22e-109">例外でイベントに基づくビジネス アクティビティ監視 (BAM) 定義済みのしきい値を超えたために発生します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-109">It may occur because the exception exceeded a threshold predefined in event-based Business Activity Monitoring (BAM).</span></span>  
  
    -   <span data-ttu-id="5d22e-110">これは、BizTalk サブスクリプションは、特定のアプリケーション、サービス、スコープ、および開発者に、例外を転送するエラー コードに存在するために発生します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-110">It may occur because a BizTalk subscription exists for the specific application, service, scope, and fault code that forwards the exception to the developer.</span></span>  
  
4.  <span data-ttu-id="5d22e-111">開発者は、エラー メッセージ、個別のオーケストレーションのメッセージと、永続化されたコンテキスト プロパティの値を調べます。</span><span class="sxs-lookup"><span data-stu-id="5d22e-111">The developer examines the fault message, the individual orchestration messages, and their persisted context property values.</span></span> <span data-ttu-id="5d22e-112">開発者は、ESB 管理ポータル、または BizTalk サブスクリプションによる Microsoft Outlook を使用して、この情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5d22e-112">Developers can view this information through the ESB Management Portal or by using Microsoft Outlook through a BizTalk subscription.</span></span>  
  
5.  <span data-ttu-id="5d22e-113">開発者は、これは、一般的なエラーであることを決定します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-113">The developer determines that this is a common error.</span></span> <span data-ttu-id="5d22e-114">必要になります手動介入し、修正によって、システムを再送信を続けて、財務チーム。</span><span class="sxs-lookup"><span data-stu-id="5d22e-114">It will require manual intervention and correction by the Finance team, followed by resubmission to the system.</span></span>  
  
6.  <span data-ttu-id="5d22e-115">開発者は、作成し、特定のアプリケーションおよび例外の種類をサブスクライブする独立した BizTalk オーケストレーション プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-115">The developer creates and deploys an independent BizTalk orchestration project that subscribes to the specific application and exception type.</span></span>  
  
7.  <span data-ttu-id="5d22e-116">オーケストレーション プロジェクトで、ESB エラー メッセージから無効なメッセージを取得、修正のために財務チームにメッセージを送信、オーケストレーションに修正されたメッセージを相関し、再送信します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-116">The orchestration project retrieves the invalid message from the ESB fault message, sends the message to the Finance team for correction, correlates the corrected message back to the orchestration, and resubmits it.</span></span>  
  
8.  <span data-ttu-id="5d22e-117">1 週間後、開発者は、検出を無効なメッセージのアプリケーション例外の傾向が大幅に短縮されましたので、このソリューションがデプロイされた ESB 管理ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="5d22e-117">A week later, the developer navigates to the ESB Management Portal to discover that application exception trends for invalid messages have decreased dramatically since this solution was deployed.</span></span>
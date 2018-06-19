---
title: 運用環境の BizTalk Server 環境のスケーリング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a972b983-5ec5-4a2a-934f-b2788ccd424e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6dfd90864f6698c54558c65aa3a87b96c0459c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302954"
---
# <a name="scaling-a-production-biztalk-server-environment"></a><span data-ttu-id="8f35f-102">運用環境の BizTalk Server 環境のスケーリング</span><span class="sxs-lookup"><span data-stu-id="8f35f-102">Scaling a Production BizTalk Server Environment</span></span>
<span data-ttu-id="8f35f-103">このセクションでは、BizTalk Server ソリューション、ロード テストの結果、および一般的な観測とラボの結果に基づく推奨事項の概要のロード テストの実行に使用されたラボ環境の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="8f35f-103">This section provides an overview of the lab environment that was used to perform load testing of a BizTalk Server solution, a summary of the load test results, and general observations and recommendations based upon the findings in the lab.</span></span>  
  
 <span data-ttu-id="8f35f-104">これらのトピックで提供される情報のことができ、スケーリングのガイドとして使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="8f35f-104">The information provided in these topics can and should be used as a guide for scaling your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="8f35f-105">定期処理を完了することをお勧めこのガイダンスに加えロード テストの開発サイクル全体を通じて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="8f35f-105">In addition to this guidance we recommend that you complete periodic load testing throughout the development cycle of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f35f-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8f35f-106">In This Section</span></span>  
  
-   [<span data-ttu-id="8f35f-107">シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="8f35f-107">Scenario Overview</span></span>](../technical-guides/scenario-overview.md)  
  
-   [<span data-ttu-id="8f35f-108">主要業績評価指標</span><span class="sxs-lookup"><span data-stu-id="8f35f-108">Key Performance Indicators</span></span>](../technical-guides/key-performance-indicators.md)  
  
-   [<span data-ttu-id="8f35f-109">監視と推奨事項</span><span class="sxs-lookup"><span data-stu-id="8f35f-109">Observations and Recommendations</span></span>](../technical-guides/observations-and-recommendations.md)
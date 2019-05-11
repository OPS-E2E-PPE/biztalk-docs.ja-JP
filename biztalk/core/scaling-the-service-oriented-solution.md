---
title: スケーリング、サービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, service solutions
- service solution tutorial, scaling
ms.assetid: 6c22a68d-03e7-4174-b612-0e2246aa9413
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 895b0ad325e9dce4086c90bccf932f73226780e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308910"
---
# <a name="scaling-the-service-oriented-solution"></a><span data-ttu-id="a547d-102">スケーリング、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="a547d-102">Scaling the Service Oriented Solution</span></span>
<span data-ttu-id="a547d-103">短いメッセージを維持しながらより高いスループットをサポートするために、ソリューションを拡張するには、待機時間は、ソリューションのインライン バージョンを使用することが必要です。</span><span class="sxs-lookup"><span data-stu-id="a547d-103">To scale the solution to support higher throughput while maintaining low message latency requires you to use the inline version of the solution.</span></span> <span data-ttu-id="a547d-104">インライン ソリューションは、バックエンド システムと対話するときに、メッセージ ボックス データベースを無視します。</span><span class="sxs-lookup"><span data-stu-id="a547d-104">The inline solution bypasses the MessageBox database when interacting with the back-end systems.</span></span>  
  
 <span data-ttu-id="a547d-105">オーケストレーションを実行する BizTalk Server 処理サーバーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a547d-105">You can also add BizTalk Server processing servers to run orchestrations.</span></span> <span data-ttu-id="a547d-106">これにより、新しい要求が迅速に処理できるように、各サーバーの使用率が低下します。</span><span class="sxs-lookup"><span data-stu-id="a547d-106">This decreases the utilization of each server so that new requests can be processed quickly.</span></span> <span data-ttu-id="a547d-107">メッセージのスループットを処理するための十分な追加の容量があるように、メッセージ ボックス サーバーをスケールもできます。</span><span class="sxs-lookup"><span data-stu-id="a547d-107">You can also scale up the MessageBox server so that it has enough additional capacity to handle the message throughput.</span></span>  
  
 <span data-ttu-id="a547d-108">ただし、サービス指向アーキテクチャ ソリューションでは、複数のメッセージ ボックス データベースからのメリットはありません。</span><span class="sxs-lookup"><span data-stu-id="a547d-108">However, the service oriented architecture solution does not benefit from having multiple MessageBox databases.</span></span> <span data-ttu-id="a547d-109">複数のメッセージ ボックスには、分散トランザクション コーディネーター (DTC) トランザクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="a547d-109">Multiple MessageBoxes require distributed transaction coordinator (DTC) transactions.</span></span> <span data-ttu-id="a547d-110">トランザクションは、メッセージの全体的な待機時間を増やします。</span><span class="sxs-lookup"><span data-stu-id="a547d-110">The transactions increase overall message latency.</span></span>  
  
 <span data-ttu-id="a547d-111">MQSeries ヘッダーの情報を追加するパイプライン コンポーネントを排除することにより、応答時間を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a547d-111">You can decrease response time by eliminating the pipeline component that adds MQSeries header information.</span></span> <span data-ttu-id="a547d-112">詳細については、次を参照してください。[サービス指向ソリューションの実装が強調表示](../core/implementation-highlights-of-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="a547d-112">For more information, see [Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a547d-113">参照</span><span class="sxs-lookup"><span data-stu-id="a547d-113">See Also</span></span>  
 [<span data-ttu-id="a547d-114">開発、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="a547d-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)
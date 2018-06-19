---
title: スケーリング、サービス指向ソリューション |Microsoft ドキュメント
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
ms.openlocfilehash: 3026664d3a365630c93bf1c61d7cf635fdd9dc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269178"
---
# <a name="scaling-the-service-oriented-solution"></a><span data-ttu-id="a4be7-102">スケーリング、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="a4be7-102">Scaling the Service Oriented Solution</span></span>
<span data-ttu-id="a4be7-103">短いメッセージ待機時間を維持しながら高いスループットをサポートできるようにソリューションを拡張するには、インライン バージョンのソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4be7-103">To scale the solution to support higher throughput while maintaining low message latency requires you to use the inline version of the solution.</span></span> <span data-ttu-id="a4be7-104">インライン ソリューションはバックエンド システムとやり取りするとき、メッセージ ボックス データベースをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="a4be7-104">The inline solution bypasses the MessageBox database when interacting with the back-end systems.</span></span>  
  
 <span data-ttu-id="a4be7-105">オーケストレーションを実行する BizTalk Server 処理サーバーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4be7-105">You can also add BizTalk Server processing servers to run orchestrations.</span></span> <span data-ttu-id="a4be7-106">これによって各サーバーの使用率が低下して新しい要求が迅速に処理されます。</span><span class="sxs-lookup"><span data-stu-id="a4be7-106">This decreases the utilization of each server so that new requests can be processed quickly.</span></span> <span data-ttu-id="a4be7-107">メッセージ ボックス サーバーをスケール アップして、メッセージ スループットの増加に対応できるだけの容量を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4be7-107">You can also scale up the MessageBox server so that it has enough additional capacity to handle the message throughput.</span></span>  
  
 <span data-ttu-id="a4be7-108">ただし、サービス指向アーキテクチャ ソリューションでは、複数のメッセージ ボックス データベースを使用してもパフォーマンスの向上は期待できません。</span><span class="sxs-lookup"><span data-stu-id="a4be7-108">However, the service oriented architecture solution does not benefit from having multiple MessageBox databases.</span></span> <span data-ttu-id="a4be7-109">複数のメッセージ ボックス データベースを使用する場合は分散トランザクション コーディネータ (DTC) トランザクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4be7-109">Multiple MessageBoxes require distributed transaction coordinator (DTC) transactions.</span></span> <span data-ttu-id="a4be7-110">このトランザクションを使用すると、全体としてのメッセージ待機時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="a4be7-110">The transactions increase overall message latency.</span></span>  
  
 <span data-ttu-id="a4be7-111">応答時間は MQSeries のヘッダー情報を追加するパイプライン コンポーネントを除外することによって短縮できます。</span><span class="sxs-lookup"><span data-stu-id="a4be7-111">You can decrease response time by eliminating the pipeline component that adds MQSeries header information.</span></span> <span data-ttu-id="a4be7-112">詳細については、次を参照してください。[サービス指向ソリューションの実装が強調表示](../core/implementation-highlights-of-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="a4be7-112">For more information, see [Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4be7-113">参照</span><span class="sxs-lookup"><span data-stu-id="a4be7-113">See Also</span></span>  
 [<span data-ttu-id="a4be7-114">指向ソリューションのサービスの開発</span><span class="sxs-lookup"><span data-stu-id="a4be7-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)
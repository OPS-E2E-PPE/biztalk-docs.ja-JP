---
title: "テストとチューニングのボトルネックを実行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d41d95-3a76-4eb0-b07d-14c6b6dccdaa
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d21b558f75824340718f7bd6efa3f10ae9926ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="performing-bottleneck-testing-and-tuning"></a><span data-ttu-id="6a27d-102">テストとチューニングのボトルネックを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a27d-102">Performing Bottleneck Testing and Tuning</span></span>
<span data-ttu-id="6a27d-103">システムのボトルネックを確認し、それに応じてシステムをチューニングするパフォーマンスのテストを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a27d-103">You should complete performance testing to determine bottlenecks in the system and to tune the system accordingly.</span></span>  
  
## <a name="testing-a-subsystem"></a><span data-ttu-id="6a27d-104">サブシステムのテスト</span><span class="sxs-lookup"><span data-stu-id="6a27d-104">Testing a Subsystem</span></span>  
 <span data-ttu-id="6a27d-105">システムのボトルネックを特定するためのベスト プラクティスは、たとえば、システム全体のサブセットに対してパフォーマンス テストの実行には。</span><span class="sxs-lookup"><span data-stu-id="6a27d-105">A best practice for identifying system bottlenecks is to run performance tests on subsets of the entire system, for example:</span></span>  
  
-   <span data-ttu-id="6a27d-106">メッセージを送信またはからのメッセージを受信する外部システムのベースライン パフォーマンス パラメーターを確立[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6a27d-106">Establish baseline performance parameters for external systems that send messages to or receive message from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="6a27d-107">オーケストレーションの参加が、開始しないでください。</span><span class="sxs-lookup"><span data-stu-id="6a27d-107">Enlist orchestrations, but do not start them.</span></span> <span data-ttu-id="6a27d-108">メッセージを受信キュー/ファイルの場所にドロップし、受信アダプターのドレイン キュー/ファイルの場所を受信し、メッセージ ボックス データベースにメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="6a27d-108">Drop messages into the inbound queues/file locations and let the inbound receive adapters drain the queue/file locations and publish messages into the MessageBox database.</span></span> <span data-ttu-id="6a27d-109">これにより、受信を分離するポートをその最大持続的な入力率を判断できます。</span><span class="sxs-lookup"><span data-stu-id="6a27d-109">This allows you to isolate your receive ports to determine their maximum sustained input rate.</span></span>  
  
-   <span data-ttu-id="6a27d-110">メッセージは、メッセージ ボックス データベースに取り込まれたが、いったん受信アダプターを停止、オーケストレーション プロセスを有効にするや送信アダプター、およびしするオーケストレーションの転送速度を測定および送信アダプターがメッセージを処理することがことができます。</span><span class="sxs-lookup"><span data-stu-id="6a27d-110">Once the messages are pulled into the MessageBox database, stop the receive adapters, enable the orchestration processes and/or send adapters, and then measure the rate at which orchestrations and/or send adapters are processing messages.</span></span>  
  
## <a name="testing-the-end-to-end-system"></a><span data-ttu-id="6a27d-111">エンド ツー エンド システムをテストします。</span><span class="sxs-lookup"><span data-stu-id="6a27d-111">Testing the End-to-End System</span></span>  
 <span data-ttu-id="6a27d-112">エンド ツー エンドのパフォーマンスのについては説明しませんが、アプリケーション サブシステムのパフォーマンスを分離する効果的な方法は上記で説明されているため入力と出力のレートのテストです。</span><span class="sxs-lookup"><span data-stu-id="6a27d-112">Testing of input and output rates as described in preceding section is an effective way to isolate performance of the application subsystem, although it does not describe end-to-end performance.</span></span> <span data-ttu-id="6a27d-113">同じ共有リソース (たとえば、メッセージ ボックス データベース) に対して競合する複数のリソースが開始されるまで、いくつかのボトルネックを識別できないため、エンド ツー エンドのパフォーマンスをテストすることも必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a27d-113">You should also test end-to-end performance because some bottlenecks cannot be identified until multiple resources begin to contend for the same shared resource (for example, the MessageBox database).</span></span>  
  
 <span data-ttu-id="6a27d-114">負荷を生成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、Microsoft BizTalk LoadGen 2007 ツールの使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="6a27d-114">To generate load against a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, consider using the Microsoft BizTalk LoadGen 2007 tool.</span></span> <span data-ttu-id="6a27d-115">LoadGen 2007 ツールの詳細については、次を参照してください。 [Microsoft BizTalk LoadGen 2007](http://go.microsoft.com/fwlink/?LinkID=59841) (http://go.microsoft.com/fwlink/?LinkID=59841)。</span><span class="sxs-lookup"><span data-stu-id="6a27d-115">For more information about the LoadGen 2007 tool see [Microsoft BizTalk LoadGen 2007](http://go.microsoft.com/fwlink/?LinkID=59841) (http://go.microsoft.com/fwlink/?LinkID=59841).</span></span>  
  
 <span data-ttu-id="6a27d-116">生成用のレポートのパフォーマンスを分析して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、パフォーマンス分析のログ (PAL) のツールの使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="6a27d-116">To generate and analyze a performance report for a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, consider using the Performance Analysis of Logs (PAL) tool.</span></span> <span data-ttu-id="6a27d-117">PAL ツールの詳細については、次を参照してください。[パフォーマンス分析のログ (PAL) のツールを使用して](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)です。</span><span class="sxs-lookup"><span data-stu-id="6a27d-117">For more information about the PAL tool, see [Using the Performance Analysis of Logs (PAL) Tool](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md).</span></span>  
  
## <a name="what-developers-operators-and-administrators-should-know"></a><span data-ttu-id="6a27d-118">どのような開発者、演算子、および管理者が知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a27d-118">What Developers, Operators, and Administrators Should Know</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6a27d-119">開発者にでも精通している必要がある[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス特性およびチューニングできます。</span><span class="sxs-lookup"><span data-stu-id="6a27d-119"> developers should be well versed on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance characteristics and tuning.</span></span> <span data-ttu-id="6a27d-120">オペレーターや管理者がメッセージ ボックス データベースのスケール アウト側面、SAN に精通する必要がありますの調整、ネットワークは、次のチューニング、および SQL Server データベースのチューニング (たとえばを参照してください[SQL Server の設定を変更しないで](../technical-guides/sql-server-settings-that-should-not-be-changed.md))。</span><span class="sxs-lookup"><span data-stu-id="6a27d-120">Operators and administrators should be knowledgeable about MessageBox database scale-out aspects, SAN tuning, network tuning, and SQL Server database tuning (for example, see [SQL Server Settings That Should Not Be Changed](../technical-guides/sql-server-settings-that-should-not-be-changed.md)).</span></span> <span data-ttu-id="6a27d-121">開発者、演算子、および管理者は、チューニングする方法を認識する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高スループットと低待機時間。</span><span class="sxs-lookup"><span data-stu-id="6a27d-121">Developers, operators, and administrators should be aware of how to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for high-throughput and low-latency.</span></span>
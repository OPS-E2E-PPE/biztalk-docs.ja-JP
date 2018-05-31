---
title: ポリシーと使用状況情報を監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c0d2fd0-e65f-4c96-a5f5-81c9afc9c04e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8ea9c6151b617e2eef2aa5404d6415f8dd71ded
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008715"
---
# <a name="monitoring-policies-and-usage-information"></a><span data-ttu-id="424b8-102">ポリシーと使用状況情報の監視</span><span class="sxs-lookup"><span data-stu-id="424b8-102">Monitoring Policies and Usage Information</span></span>
<span data-ttu-id="424b8-103">SOA サービス マネージャーでは、作成と監視ポリシーを編集できるようにするメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="424b8-103">The SOA Service Manager provides a mechanism that allows you to create and edit monitoring policies.</span></span> <span data-ttu-id="424b8-104">たとえば、図 1 には、ポリシー テンプレートを適用して、アプリケーションの監視をアクティブ化の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="424b8-104">For example, Figure 1 shows the screen for applying a policy template and activating monitoring for an application.</span></span>  
  
 <span data-ttu-id="424b8-105">![監視機能](../esb-toolkit/media/ch9-monitoringfeatures.jpg "Ch9 MonitoringFeatures")</span><span class="sxs-lookup"><span data-stu-id="424b8-105">![Monitoring Features](../esb-toolkit/media/ch9-monitoringfeatures.jpg "Ch9-MonitoringFeatures")</span></span>  
  
 <span data-ttu-id="424b8-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="424b8-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="424b8-107">**ワークベンチ ページで使用可能な監視機能を示す、SOA サービス マネージャー**</span><span class="sxs-lookup"><span data-stu-id="424b8-107">**The SOA Service Manager showing the monitoring features available on the Workbench page**</span></span>  
  
 <span data-ttu-id="424b8-108">個々 の送信ポートと受信場所および SOA サービス マネージャーもアプリケーション、サービスの利用状況情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="424b8-108">The SOA Service Manager also provides usage information for applications, services, and individual send ports and receive locations.</span></span> <span data-ttu-id="424b8-109">この情報には、時間、サービスの使用法、および応答時間の情報を各操作の相対的な使用状況と使用状況を表示するグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="424b8-109">This information includes charts that display the relative usage of each operation and usage over time, service usage, and response time information.</span></span> <span data-ttu-id="424b8-110">図 2 は、いくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="424b8-110">Figure 2 shows some examples.</span></span>  
  
 <span data-ttu-id="424b8-111">![監視グラフ](../esb-toolkit/media/ch9-monitoringcharts.jpg "Ch9 MonitoringCharts")</span><span class="sxs-lookup"><span data-stu-id="424b8-111">![Monitoring Charts](../esb-toolkit/media/ch9-monitoringcharts.jpg "Ch9-MonitoringCharts")</span></span>  
  
 <span data-ttu-id="424b8-112">**図 2**</span><span class="sxs-lookup"><span data-stu-id="424b8-112">**Figure 2**</span></span>  
  
 <span data-ttu-id="424b8-113">**SOA サービス マネージャーは、サーバーとアプリケーションの動作とパフォーマンスの監視を支援する生成できるグラフの選択**</span><span class="sxs-lookup"><span data-stu-id="424b8-113">**A selection of the charts that the SOA Service Manager can generate to assist in monitoring server and application behavior and performance**</span></span>  
  
 <span data-ttu-id="424b8-114">さらに、SOA サービス マネージャーには、図 3 に示すように、サイズ、応答時間、操作名、および関連付けられている SOAP メッセージを含む個々 のメッセージの詳細を表示できるようにする機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="424b8-114">In addition, SOA Service Manager includes features that allow you to view details of individual messages, including the size, response time, operation name, and the associated SOAP messages, as shown in Figure 3.</span></span>  
  
 <span data-ttu-id="424b8-115">![Soap メッセージの詳細](../esb-toolkit/media/ch9-soapmessagedetails.jpg "Ch9 SoapMessageDetails")</span><span class="sxs-lookup"><span data-stu-id="424b8-115">![Soap Message Details](../esb-toolkit/media/ch9-soapmessagedetails.jpg "Ch9-SoapMessageDetails")</span></span>  
  
 <span data-ttu-id="424b8-116">**図 3**</span><span class="sxs-lookup"><span data-stu-id="424b8-116">**Figure 3**</span></span>  
  
 <span data-ttu-id="424b8-117">**SOA サービス マネージャーが個々 のメッセージの詳細を表示**</span><span class="sxs-lookup"><span data-stu-id="424b8-117">**The SOA Service Manager showing details of an individual message**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="424b8-118">SOA サービス マネージャーとワークベンチの製品は、BizTalk Server と統合する SOA ソフトウェア, Inc. の製品です。</span><span class="sxs-lookup"><span data-stu-id="424b8-118">SOA Service Manager and Workbench products are products from SOA Software, Inc. that integrate with BizTalk Server.</span></span> <span data-ttu-id="424b8-119">SOA ソフトウェアや、製品、およびダウンロード、最新のインストールと運用手順の詳細については、次を参照してください。、 [SOA ソフトウェア](http://go.microsoft.com/fwlink/?LinkId=188559)Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="424b8-119">For more information about SOA Software and their products, and to download the latest installation and operational instructions, see the [SOA Software](http://go.microsoft.com/fwlink/?LinkId=188559) Web site.</span></span>
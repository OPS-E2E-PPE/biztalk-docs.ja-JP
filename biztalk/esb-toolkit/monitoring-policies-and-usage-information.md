---
title: "ポリシーと使用状況情報を監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c0d2fd0-e65f-4c96-a5f5-81c9afc9c04e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4909b96e74d34d469decd11c1ffba0e49217ff7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-policies-and-usage-information"></a><span data-ttu-id="b4b01-102">ポリシーと使用状況情報の監視</span><span class="sxs-lookup"><span data-stu-id="b4b01-102">Monitoring Policies and Usage Information</span></span>
<span data-ttu-id="b4b01-103">SOA サービス マネージャーでは、作成と監視ポリシーを編集できるようにするメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="b4b01-103">The SOA Service Manager provides a mechanism that allows you to create and edit monitoring policies.</span></span> <span data-ttu-id="b4b01-104">たとえば、図 1 には、ポリシー テンプレートを適用して、アプリケーションの監視をアクティブ化の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4b01-104">For example, Figure 1 shows the screen for applying a policy template and activating monitoring for an application.</span></span>  
  
 <span data-ttu-id="b4b01-105">![監視機能](../esb-toolkit/media/ch9-monitoringfeatures.jpg "Ch9 MonitoringFeatures")</span><span class="sxs-lookup"><span data-stu-id="b4b01-105">![Monitoring Features](../esb-toolkit/media/ch9-monitoringfeatures.jpg "Ch9-MonitoringFeatures")</span></span>  
  
 <span data-ttu-id="b4b01-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="b4b01-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="b4b01-107">**ワークベンチ ページで使用可能な監視機能を示す、SOA サービス マネージャー**</span><span class="sxs-lookup"><span data-stu-id="b4b01-107">**The SOA Service Manager showing the monitoring features available on the Workbench page**</span></span>  
  
 <span data-ttu-id="b4b01-108">個々 の送信ポートと受信場所および SOA サービス マネージャーもアプリケーション、サービスの利用状況情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b4b01-108">The SOA Service Manager also provides usage information for applications, services, and individual send ports and receive locations.</span></span> <span data-ttu-id="b4b01-109">この情報には、時間、サービスの使用法、および応答時間の情報を各操作の相対的な使用状況と使用状況を表示するグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4b01-109">This information includes charts that display the relative usage of each operation and usage over time, service usage, and response time information.</span></span> <span data-ttu-id="b4b01-110">図 2 は、いくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="b4b01-110">Figure 2 shows some examples.</span></span>  
  
 <span data-ttu-id="b4b01-111">![監視グラフ](../esb-toolkit/media/ch9-monitoringcharts.jpg "Ch9 MonitoringCharts")</span><span class="sxs-lookup"><span data-stu-id="b4b01-111">![Monitoring Charts](../esb-toolkit/media/ch9-monitoringcharts.jpg "Ch9-MonitoringCharts")</span></span>  
  
 <span data-ttu-id="b4b01-112">**図 2**</span><span class="sxs-lookup"><span data-stu-id="b4b01-112">**Figure 2**</span></span>  
  
 <span data-ttu-id="b4b01-113">**SOA サービス マネージャーは、サーバーとアプリケーションの動作とパフォーマンスの監視を支援する生成できるグラフの選択**</span><span class="sxs-lookup"><span data-stu-id="b4b01-113">**A selection of the charts that the SOA Service Manager can generate to assist in monitoring server and application behavior and performance**</span></span>  
  
 <span data-ttu-id="b4b01-114">さらに、SOA サービス マネージャーには、図 3 に示すように、サイズ、応答時間、操作名、および関連付けられている SOAP メッセージを含む個々 のメッセージの詳細を表示できるようにする機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4b01-114">In addition, SOA Service Manager includes features that allow you to view details of individual messages, including the size, response time, operation name, and the associated SOAP messages, as shown in Figure 3.</span></span>  
  
 <span data-ttu-id="b4b01-115">![Soap メッセージの詳細](../esb-toolkit/media/ch9-soapmessagedetails.jpg "Ch9 SoapMessageDetails")</span><span class="sxs-lookup"><span data-stu-id="b4b01-115">![Soap Message Details](../esb-toolkit/media/ch9-soapmessagedetails.jpg "Ch9-SoapMessageDetails")</span></span>  
  
 <span data-ttu-id="b4b01-116">**図 3**</span><span class="sxs-lookup"><span data-stu-id="b4b01-116">**Figure 3**</span></span>  
  
 <span data-ttu-id="b4b01-117">**SOA サービス マネージャーが個々 のメッセージの詳細を表示**</span><span class="sxs-lookup"><span data-stu-id="b4b01-117">**The SOA Service Manager showing details of an individual message**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4b01-118">SOA サービス マネージャーとワークベンチの製品の統合 SOA ソフトウェア社から製品[!INCLUDE[prague](../includes/prague-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b4b01-118">SOA Service Manager and Workbench products are products from SOA Software, Inc. that integrate with [!INCLUDE[prague](../includes/prague-md.md)].</span></span> <span data-ttu-id="b4b01-119">SOA ソフトウェアや、製品、およびダウンロード、最新のインストールと運用手順の詳細については、次を参照してください。、 [SOA ソフトウェア](http://go.microsoft.com/fwlink/?LinkId=188559)Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="b4b01-119">For more information about SOA Software and their products, and to download the latest installation and operational instructions, see the [SOA Software](http://go.microsoft.com/fwlink/?LinkId=188559) Web site.</span></span>
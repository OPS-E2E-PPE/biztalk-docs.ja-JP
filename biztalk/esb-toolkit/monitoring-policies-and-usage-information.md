---
title: ポリシーと使用状況の監視 |Microsoft Docs
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
ms.openlocfilehash: 939f0722cf4e38ca9a7734bfc1cba6b1960d8d18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400075"
---
# <a name="monitoring-policies-and-usage-information"></a><span data-ttu-id="4f71e-102">ポリシーと使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="4f71e-102">Monitoring Policies and Usage Information</span></span>
<span data-ttu-id="4f71e-103">SOA サービス マネージャーを作成および監視ポリシーを編集できるようにするメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f71e-103">The SOA Service Manager provides a mechanism that allows you to create and edit monitoring policies.</span></span> <span data-ttu-id="4f71e-104">たとえば、図 1 には、ポリシー テンプレートを適用して、アプリケーションの監視をアクティブ化するための画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f71e-104">For example, Figure 1 shows the screen for applying a policy template and activating monitoring for an application.</span></span>  
  
 <span data-ttu-id="4f71e-105">![監視機能](../esb-toolkit/media/ch9-monitoringfeatures.jpg "Ch9 MonitoringFeatures")</span><span class="sxs-lookup"><span data-stu-id="4f71e-105">![Monitoring Features](../esb-toolkit/media/ch9-monitoringfeatures.jpg "Ch9-MonitoringFeatures")</span></span>  
  
 <span data-ttu-id="4f71e-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="4f71e-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="4f71e-107">**Workbench のページで使用可能な監視機能を示す、SOA サービス マネージャー**</span><span class="sxs-lookup"><span data-stu-id="4f71e-107">**The SOA Service Manager showing the monitoring features available on the Workbench page**</span></span>  
  
 <span data-ttu-id="4f71e-108">SOA サービス マネージャーでは、アプリケーション、サービスの使用状況の情報も提供し、個々 の送信ポートおよび受信場所。</span><span class="sxs-lookup"><span data-stu-id="4f71e-108">The SOA Service Manager also provides usage information for applications, services, and individual send ports and receive locations.</span></span> <span data-ttu-id="4f71e-109">この情報には、時間、サービスの使用状況、および応答時間の情報を各操作の相対的な使用状況と使用状況を表示するグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f71e-109">This information includes charts that display the relative usage of each operation and usage over time, service usage, and response time information.</span></span> <span data-ttu-id="4f71e-110">図 2 は、いくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="4f71e-110">Figure 2 shows some examples.</span></span>  
  
 <span data-ttu-id="4f71e-111">![監視グラフ](../esb-toolkit/media/ch9-monitoringcharts.jpg "Ch9 MonitoringCharts")</span><span class="sxs-lookup"><span data-stu-id="4f71e-111">![Monitoring Charts](../esb-toolkit/media/ch9-monitoringcharts.jpg "Ch9-MonitoringCharts")</span></span>  
  
 <span data-ttu-id="4f71e-112">**図 2**</span><span class="sxs-lookup"><span data-stu-id="4f71e-112">**Figure 2**</span></span>  
  
 <span data-ttu-id="4f71e-113">**SOA サービス マネージャーは、サーバーとアプリケーションの動作とパフォーマンスの監視を支援するために生成できるグラフの選択**</span><span class="sxs-lookup"><span data-stu-id="4f71e-113">**A selection of the charts that the SOA Service Manager can generate to assist in monitoring server and application behavior and performance**</span></span>  
  
 <span data-ttu-id="4f71e-114">さらに、SOA サービス マネージャーには、図 3 に示すように、サイズ、応答時間、操作名、および関連付けられている SOAP メッセージを含む、個々 のメッセージの詳細を表示できるようにする機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f71e-114">In addition, SOA Service Manager includes features that allow you to view details of individual messages, including the size, response time, operation name, and the associated SOAP messages, as shown in Figure 3.</span></span>  
  
 <span data-ttu-id="4f71e-115">![Soap メッセージの詳細](../esb-toolkit/media/ch9-soapmessagedetails.jpg "Ch9 SoapMessageDetails")</span><span class="sxs-lookup"><span data-stu-id="4f71e-115">![Soap Message Details](../esb-toolkit/media/ch9-soapmessagedetails.jpg "Ch9-SoapMessageDetails")</span></span>  
  
 <span data-ttu-id="4f71e-116">**図 3**</span><span class="sxs-lookup"><span data-stu-id="4f71e-116">**Figure 3**</span></span>  
  
 <span data-ttu-id="4f71e-117">**個々 のメッセージの詳細を示す、SOA サービス マネージャー**</span><span class="sxs-lookup"><span data-stu-id="4f71e-117">**The SOA Service Manager showing details of an individual message**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f71e-118">Service Manager の SOA および Workbench 製品は、SOA Software, Inc. から BizTalk Server と統合する製品です。</span><span class="sxs-lookup"><span data-stu-id="4f71e-118">SOA Service Manager and Workbench products are products from SOA Software, Inc. that integrate with BizTalk Server.</span></span> <span data-ttu-id="4f71e-119">SOA のソフトウェアと独自の製品についてと、最新のインストールと運用手順のダウンロードの詳細については、次を参照してください。、 [SOA ソフトウェア](http://go.microsoft.com/fwlink/?LinkId=188559)Web サイト。</span><span class="sxs-lookup"><span data-stu-id="4f71e-119">For more information about SOA Software and their products, and to download the latest installation and operational instructions, see the [SOA Software](http://go.microsoft.com/fwlink/?LinkId=188559) Web site.</span></span>
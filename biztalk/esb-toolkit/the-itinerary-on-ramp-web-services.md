---
title: "道順のランプで Web サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7551974-b9d2-4ae3-b54c-3aa5ba058e95
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36d3724a6cd57dca8157c05e95d9e196f0fb6cf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-itinerary-on-ramp-web-services"></a><span data-ttu-id="e6497-102">道順のランプで Web サービス</span><span class="sxs-lookup"><span data-stu-id="e6497-102">The Itinerary On-Ramp Web Services</span></span>
<span data-ttu-id="e6497-103">行程 Web サービスが、itinerary 入り口行程サービスによって、Microsoft BizTalk ターゲットにし、それ以降の処理または ESB 操作のためのメッセージを送信するクライアントできるようにするメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="e6497-103">The Itinerary Web service is an itinerary on-ramp that exposes a method that allows clients to submit messages for processing by the Itinerary Service and then onward to the target Microsoft BizTalk or ESB operations.</span></span>  
  
 <span data-ttu-id="e6497-104">行程 Web サービスに渡しますペイロード ESB 行程パイプライン コンポーネントでこれらのサービスが定義されていることを確認する旅程を検証する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]構成します。</span><span class="sxs-lookup"><span data-stu-id="e6497-104">The Itinerary Web service passes the payload to the ESB Itinerary pipeline components, which validates the itinerary to verify that these services are defined in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuration.</span></span> <span data-ttu-id="e6497-105">コンポーネントは、検証済みの日程を含むメッセージに特殊なコンテキスト プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6497-105">Then the component adds special context properties to the message containing the validated itinerary.</span></span>  
  
 <span data-ttu-id="e6497-106">場合は、ジェネリック itinerary 入り口、日程を含む SOAP ヘッダーはメッセージの送信中に指定されていません。</span><span class="sxs-lookup"><span data-stu-id="e6497-106">In the case of a generic itinerary on-ramp, a SOAP header containing an itinerary is not provided during message submission.</span></span> <span data-ttu-id="e6497-107">したがって、ESB 行程セレクター パイプライン コンポーネントは、ESB 行程パイプライン コンポーネントの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6497-107">Accordingly, the ESB Itinerary Selector pipeline component is used in place of the ESB Itinerary pipeline component.</span></span> <span data-ttu-id="e6497-108">ESB 行程セレクター パイプライン コンポーネントは、定義済みの競合回避モジュールの接続文字列に基づく旅程を解決し、ESB 行程パイプライン コンポーネントを提供する同じ検証を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6497-108">The ESB Itinerary Selector pipeline component resolves the itinerary based on a pre-defined resolver connection string, and it provides the same validation that the ESB Itinerary pipeline component provides.</span></span>  
  
 <span data-ttu-id="e6497-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一方向の両方をサポートする行程サービスおよび要求-応答メッセージ交換パターンの 2 つのバリエーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6497-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes two variations of the Itinerary service to support both one-way and request-response message-exchange patterns.</span></span> <span data-ttu-id="e6497-110">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ASP.NET (ASMX) および Windows Communication Foundation (WCF) のバージョンのこれらのサービスの両方を含むジェネリックのバージョンの WCF サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e6497-110">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains an ASP.NET (ASMX) and a Windows Communication Foundation (WCF) version of both of these services, and it provides generic versions of the WCF services.</span></span>  
  
 <span data-ttu-id="e6497-111">指定された一方向の itinerary サービスの名前は**ESB です。ItineraryService**、 **ESB です。ItineraryServices.WCF**、および**ESB です。ItineraryServices.Generic.WCF**です。</span><span class="sxs-lookup"><span data-stu-id="e6497-111">The names of the provided one-way itinerary services are **ESB.ItineraryService**, **ESB.ItineraryServices.WCF**, and **ESB.ItineraryServices.Generic.WCF**.</span></span>  
  
 <span data-ttu-id="e6497-112">提供されている双方向 itinerary サービスの名前は**ESB です。ItineraryServices.Response**、 **ESB です。ItineraryServices.Response.WCF**、および**ESB です。ItineraryServices.Generic.Response.WCF**です。</span><span class="sxs-lookup"><span data-stu-id="e6497-112">The names of the provided two-way itinerary services are **ESB.ItineraryServices.Response**, **ESB.ItineraryServices.Response.WCF**, and **ESB.ItineraryServices.Generic.Response.WCF**.</span></span>  
  
 <span data-ttu-id="e6497-113">各行程 Web サービスには、次の方法によって公開されます。</span><span class="sxs-lookup"><span data-stu-id="e6497-113">Each of the Itinerary Web services exposes the following methods:</span></span>  
  
-   <span data-ttu-id="e6497-114">**SubmitRequest**です。</span><span class="sxs-lookup"><span data-stu-id="e6497-114">**SubmitRequest**.</span></span> <span data-ttu-id="e6497-115">このメソッドは、ASMX ベースのサービスのインスタンスを受け取り、 **XmlNode**を送信するメッセージを含むクラスです。</span><span class="sxs-lookup"><span data-stu-id="e6497-115">For the ASMX-based service, this method takes an instance of the **XmlNode** class that contains the message to submit.</span></span> <span data-ttu-id="e6497-116">WCF に基づくサービスの場合は、このメソッドは、送信するメッセージを含む XML 文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e6497-116">For the WCF-based service, this method takes an XML string that contains the message to submit.</span></span>  
  
-   <span data-ttu-id="e6497-117">**SubmitRequestResponse**です。</span><span class="sxs-lookup"><span data-stu-id="e6497-117">**SubmitRequestResponse**.</span></span> <span data-ttu-id="e6497-118">このメソッドは、ASMX ベースのサービスのインスタンスへの参照を受け取ります、 **XmlNode**クラスで送信するメッセージを含みのインスタンスの応答メッセージが返されます、 **XmlNode**に渡されるです。</span><span class="sxs-lookup"><span data-stu-id="e6497-118">For the ASMX-based service, this method takes a reference to an instance of the **XmlNode** class that contains the message to submit and returns the response message in the instance of the **XmlNode** passed to it.</span></span> <span data-ttu-id="e6497-119">このメソッドは、WCF ベースのサービスへの参照を受け取ります、**オブジェクト**XML 文字列を送信するメッセージを含むの配列を返しますとなる型**XmlNodes**で、**オブジェクト**に渡されました。</span><span class="sxs-lookup"><span data-stu-id="e6497-119">For the WCF-based service, this method takes a reference to an **Object** type that is an XML string that contains the message to submit and returns an array of **XmlNodes** in the **Object** that was passed to it.</span></span>  
  
 <span data-ttu-id="e6497-120">行程 Web サービスの使用の詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="e6497-120">For more information about using the Itinerary Web services, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6497-121">既定では、行程 Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="e6497-121">By default, the Itinerary Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="e6497-122">クライアント アクセス用の SSL を要求して、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec を使用して、ESBExceptions データベースをホストするサーバー間の接続を保護し、適切なサービスを構成する必要があります。ファイル レベルのアクセス制御リスト (ACL) のアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="e6497-122">You should configure the service to require SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and the server that hosts the ESBExceptions database using a network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>
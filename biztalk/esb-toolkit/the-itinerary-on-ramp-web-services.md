---
title: スケジュール オンランプ Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7551974-b9d2-4ae3-b54c-3aa5ba058e95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e0f30d93514fded12d20a06d9fa27fbcd632bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980715"
---
# <a name="the-itinerary-on-ramp-web-services"></a><span data-ttu-id="7cb67-102">スケジュール オンランプ Web サービス</span><span class="sxs-lookup"><span data-stu-id="7cb67-102">The Itinerary On-Ramp Web Services</span></span>
<span data-ttu-id="7cb67-103">旅行プランの Web サービスは、itinerary 入り口行程サービスによって、Microsoft BizTalk のターゲットにし、それ以降の処理や ESB 操作のメッセージを送信するクライアントを許可するメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-103">The Itinerary Web service is an itinerary on-ramp that exposes a method that allows clients to submit messages for processing by the Itinerary Service and then onward to the target Microsoft BizTalk or ESB operations.</span></span>  
  
 <span data-ttu-id="7cb67-104">旅行プランの Web サービス ペイロードを渡します ESB 行程のパイプライン コンポーネントでこれらのサービスが定義されていることを確認する旅行プランを検証、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]構成します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-104">The Itinerary Web service passes the payload to the ESB Itinerary pipeline components, which validates the itinerary to verify that these services are defined in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] configuration.</span></span> <span data-ttu-id="7cb67-105">コンポーネントは、特別なコンテキスト プロパティを検証済みのスケジュールを含むメッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-105">Then the component adds special context properties to the message containing the validated itinerary.</span></span>  
  
 <span data-ttu-id="7cb67-106">場合は、汎用的なスケジュール オンランプ入口、日程を格納している SOAP ヘッダーはメッセージの送信中に指定されていません。</span><span class="sxs-lookup"><span data-stu-id="7cb67-106">In the case of a generic itinerary on-ramp, a SOAP header containing an itinerary is not provided during message submission.</span></span> <span data-ttu-id="7cb67-107">したがって、ESB スケジュール セレクターのパイプライン コンポーネントは、ESB 行程のパイプライン コンポーネントの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7cb67-107">Accordingly, the ESB Itinerary Selector pipeline component is used in place of the ESB Itinerary pipeline component.</span></span> <span data-ttu-id="7cb67-108">ESB スケジュール セレクターのパイプライン コンポーネントが、定義済みの競合回避モジュールの接続文字列に基づいてスケジュールを解決し、ESB 行程のパイプライン コンポーネントを提供するのと同じ検証を提供します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-108">The ESB Itinerary Selector pipeline component resolves the itinerary based on a pre-defined resolver connection string, and it provides the same validation that the ESB Itinerary pipeline component provides.</span></span>  
  
 <span data-ttu-id="7cb67-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一方向の両方をサポートするサービスをスケジュールおよび要求-応答メッセージ交換パターンの 2 つのバリエーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7cb67-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes two variations of the Itinerary service to support both one-way and request-response message-exchange patterns.</span></span> <span data-ttu-id="7cb67-110">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ASP.NET (ASMX) および Windows Communication Foundation (WCF) のバージョンのこれらのサービスの両方が含まれています。 ジェネリック バージョンの WCF サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-110">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains an ASP.NET (ASMX) and a Windows Communication Foundation (WCF) version of both of these services, and it provides generic versions of the WCF services.</span></span>  
  
 <span data-ttu-id="7cb67-111">指定された一方向のスケジュール サービスの名前は**ESB します。ItineraryService**、 **ESB します。ItineraryServices.WCF**、および**ESB します。ItineraryServices.Generic.WCF**します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-111">The names of the provided one-way itinerary services are **ESB.ItineraryService**, **ESB.ItineraryServices.WCF**, and **ESB.ItineraryServices.Generic.WCF**.</span></span>  
  
 <span data-ttu-id="7cb67-112">指定された双方向のスケジュール サービスの名前は**ESB します。ItineraryServices.Response**、 **ESB します。ItineraryServices.Response.WCF**、および**ESB します。ItineraryServices.Generic.Response.WCF**します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-112">The names of the provided two-way itinerary services are **ESB.ItineraryServices.Response**, **ESB.ItineraryServices.Response.WCF**, and **ESB.ItineraryServices.Generic.Response.WCF**.</span></span>  
  
 <span data-ttu-id="7cb67-113">旅行プランの Web サービスの各は、次のメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-113">Each of the Itinerary Web services exposes the following methods:</span></span>  
  
- <span data-ttu-id="7cb67-114">**SubmitRequest**します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-114">**SubmitRequest**.</span></span> <span data-ttu-id="7cb67-115">このメソッドの ASMX ベースのサービスのインスタンスを受け取り、 **XmlNode**を送信するメッセージを含むクラスです。</span><span class="sxs-lookup"><span data-stu-id="7cb67-115">For the ASMX-based service, this method takes an instance of the **XmlNode** class that contains the message to submit.</span></span> <span data-ttu-id="7cb67-116">WCF ベースのサービスには、このメソッドは、送信するメッセージを含む XML 文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7cb67-116">For the WCF-based service, this method takes an XML string that contains the message to submit.</span></span>  
  
- <span data-ttu-id="7cb67-117">**SubmitRequestResponse**します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-117">**SubmitRequestResponse**.</span></span> <span data-ttu-id="7cb67-118">ASMX ベースのサービスには、このメソッドのインスタンスへの参照を受け取ります、 **XmlNode**クラスを送信するメッセージを含み、のインスタンスで、応答メッセージを返す、 **XmlNode**に渡されます。です。</span><span class="sxs-lookup"><span data-stu-id="7cb67-118">For the ASMX-based service, this method takes a reference to an instance of the **XmlNode** class that contains the message to submit and returns the response message in the instance of the **XmlNode** passed to it.</span></span> <span data-ttu-id="7cb67-119">WCF ベースのサービスの場合、このメソッドはへの参照を**オブジェクト**を送信するメッセージを含みの配列を返す XML 文字列である型**XmlNodes**で、 **オブジェクト**に渡されました。</span><span class="sxs-lookup"><span data-stu-id="7cb67-119">For the WCF-based service, this method takes a reference to an **Object** type that is an XML string that contains the message to submit and returns an array of **XmlNodes** in the **Object** that was passed to it.</span></span>  
  
  <span data-ttu-id="7cb67-120">旅行プランの Web サービスの使用に関する詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="7cb67-120">For more information about using the Itinerary Web services, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cb67-121">既定では、旅行プランの Web サービスはセキュリティで保護の Sockets Layer (SSL) クライアントがアクセスするときに要求するように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="7cb67-121">By default, the Itinerary Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="7cb67-122">クライアント アクセス用の SSL を必要とし、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec を使用して ESBExceptions データベースをホストするサーバー間の接続を保護し、適切なサービスを構成する必要があります。ファイル レベルのアクセス制御リスト (ACL) のアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="7cb67-122">You should configure the service to require SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and the server that hosts the ESBExceptions database using a network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>
---
title: WCF サービスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0969fb98cbf9ea79f4e32138d795b6b4de81f513
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354620"
---
# <a name="consuming-wcf-services"></a><span data-ttu-id="3c5dc-102">WCF サービスの使用</span><span class="sxs-lookup"><span data-stu-id="3c5dc-102">Consuming WCF Services</span></span>
<span data-ttu-id="3c5dc-103">WCF サービスの使用には、既存の WCF サービスをビジネス プロセスに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-103">Consuming WCF services enables you to add existing WCF services to your business process.</span></span> <span data-ttu-id="3c5dc-104">いくつかの WCF サービスは、1 つのオーケストレーションに集計できます。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-104">You can aggregate several WCF services into a single orchestration.</span></span>  
  
 <span data-ttu-id="3c5dc-105">BizTalk WCF サービス使用ウィザードを使用して、オーケストレーションから (呼び出し)、WCF サービスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-105">You can consume (call) a WCF service from your orchestration by using the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="3c5dc-106">BizTalk WCF サービス使用ウィザードに作成、ポートの種類とメッセージの種類が必要な WCF サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-106">The BizTalk WCF Service Consuming Wizard creates port types and message types necessary for consuming WCF services.</span></span> <span data-ttu-id="3c5dc-107">BizTalk WCF サービス使用ウィザードでは、コマンド ライン ツールの開発や、システム指定のバインド WCF アダプタと Wcf-custom アダプタと送信ポートを構成するウィザードでインポートできる 2 つのバインド ファイルも作成します。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-107">The BizTalk WCF Service Consuming Wizard also creates two binding files that can be imported by the development command-line tool or wizard to configure the send ports with the system-provided binding WCF adapters and the WCF-Custom adapter.</span></span> <span data-ttu-id="3c5dc-108">ウィザードを使用すると、SOAP ヘッダーを使用する WCF サービスを使用、利用する WCF サービスの URI を変更して使用する Web サービスの WCF を動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-108">The wizard allows you to use SOAP headers with a consumed WCF service, change the URI of a consumed WCF service, and dynamically set the WCF for a consumed Web service.</span></span> <span data-ttu-id="3c5dc-109">WCF 送信アダプタが WCF サービスを使用して、WCF 受信場所の WCF サービスを発行します。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-109">WCF send adapters consume WCF services and WCF receive locations publish WCF services.</span></span>  
  
 <span data-ttu-id="3c5dc-110">BizTalk WCF 送信アダプタは、WCF 定義済みバインドを表す 5 つの物理送信アダプタ**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、**NetNamedPipeBinding**、および**NetMsmqBinding**します。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-110">The BizTalk WCF send adapters include five physical send adapters that represent the WCF predefined bindings **BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="3c5dc-111">BizTalk WCF アダプターでは、WCF バインドと、送信ポートの動作情報を自由に構成するためのカスタム アダプターも含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-111">The BizTalk WCF adapters also include the custom adapters that enable you to freely configure WCF binding and behavior information for a send port.</span></span> <span data-ttu-id="3c5dc-112">WCF 送信ハンドラーを構成し、ポートを送信する方法の詳細については、の各 WCF アダプタの操作方法に関するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c5dc-112">For more information about how to configure a WCF send handler and send port, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c5dc-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3c5dc-113">In This Section</span></span>  
  
-   [<span data-ttu-id="3c5dc-114">WCF サービスを WCF 送信アダプターと共に使用する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="3c5dc-114">Considerations When Consuming WCF Services with the WCF Send Adapters</span></span>](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [<span data-ttu-id="3c5dc-115">消費済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3c5dc-115">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [<span data-ttu-id="3c5dc-116">WCF アダプター コンテキスト プロパティによる動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="3c5dc-116">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="3c5dc-117">BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="3c5dc-117">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [<span data-ttu-id="3c5dc-118">オーケストレーションで型指定されたエラー コントラクトを処理する方法</span><span class="sxs-lookup"><span data-stu-id="3c5dc-118">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [<span data-ttu-id="3c5dc-119">WCF 送信アダプター用の SOAP アクションの指定</span><span class="sxs-lookup"><span data-stu-id="3c5dc-119">Specifying SOAP Actions for WCF Send Adapters</span></span>](../core/specifying-soap-actions-for-wcf-send-adapters.md)
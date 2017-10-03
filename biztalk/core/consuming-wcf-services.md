---
title: "WCF サービスの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fc0764295cbbc793b07757691e1f0c730a4049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="consuming-wcf-services"></a><span data-ttu-id="5cf7a-102">WCF サービスの利用</span><span class="sxs-lookup"><span data-stu-id="5cf7a-102">Consuming WCF Services</span></span>
<span data-ttu-id="5cf7a-103">WCF サービスを利用して、既存の WCF サービスをビジネス プロセスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-103">Consuming WCF services enables you to add existing WCF services to your business process.</span></span> <span data-ttu-id="5cf7a-104">複数の WCF サービスを 1 つのオーケストレーションに集計できます。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-104">You can aggregate several WCF services into a single orchestration.</span></span>  
  
 <span data-ttu-id="5cf7a-105">BizTalk WCF サービス使用ウィザードを使用して、オーケストレーションから WCF サービスを利用 (呼び出し) することができます。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-105">You can consume (call) a WCF service from your orchestration by using the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="5cf7a-106">BizTalk WCF サービス使用ウィザードで、WCF サービスの利用に必要なポートの種類とメッセージの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-106">The BizTalk WCF Service Consuming Wizard creates port types and message types necessary for consuming WCF services.</span></span> <span data-ttu-id="5cf7a-107">また、このウィザードでは、開発用コマンド ライン ツールまたはウィザードでインポート可能な 2 つのバインド ファイルも作成します。これにより、システムで提供されているバインド WCF アダプタと WCF-Custom アダプタを使用して送信ポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-107">The BizTalk WCF Service Consuming Wizard also creates two binding files that can be imported by the development command-line tool or wizard to configure the send ports with the system-provided binding WCF adapters and the WCF-Custom adapter.</span></span> <span data-ttu-id="5cf7a-108">ウィザードを使用すると、利用する WCF サービスで SOAP ヘッダーを使用できるだけではなく、利用する WCF サービスの URI を変更したり、利用する Web サービスの WCF を動的に設定したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-108">The wizard allows you to use SOAP headers with a consumed WCF service, change the URI of a consumed WCF service, and dynamically set the WCF for a consumed Web service.</span></span> <span data-ttu-id="5cf7a-109">WCF 送信アダプターは WCF サービスを利用し、WCF 受信場所は WCF サービスを公開します。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-109">WCF send adapters consume WCF services and WCF receive locations publish WCF services.</span></span>  
  
 <span data-ttu-id="5cf7a-110">BizTalk WCF 送信アダプタは、WCF 定義済みバインドを表す 5 つの物理送信アダプターを含める**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、**NetNamedPipeBinding**、および**NetMsmqBinding**です。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-110">The BizTalk WCF send adapters include five physical send adapters that represent the WCF predefined bindings **BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="5cf7a-111">BizTalk WCF アダプターには、送信ポートの WCF バインドと動作情報を自在に構成できるカスタム アダプターも含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-111">The BizTalk WCF adapters also include the custom adapters that enable you to freely configure WCF binding and behavior information for a send port.</span></span> <span data-ttu-id="5cf7a-112">WCF 送信ハンドラを構成してポートを送信する方法の詳細については、の各 WCF アダプタの操作方法に関するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="5cf7a-112">For more information about how to configure a WCF send handler and send port, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5cf7a-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5cf7a-113">In This Section</span></span>  
  
-   [<span data-ttu-id="5cf7a-114">WCF での WCF サービスを使用する際の考慮事項の送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="5cf7a-114">Considerations When Consuming WCF Services with the WCF Send Adapters</span></span>](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [<span data-ttu-id="5cf7a-115">消費済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="5cf7a-115">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [<span data-ttu-id="5cf7a-116">WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="5cf7a-116">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="5cf7a-117">BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="5cf7a-117">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [<span data-ttu-id="5cf7a-118">オーケストレーションで型指定されたエラー コントラクトを処理する方法</span><span class="sxs-lookup"><span data-stu-id="5cf7a-118">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [<span data-ttu-id="5cf7a-119">送信アダプタの WCF の SOAP アクションの指定</span><span class="sxs-lookup"><span data-stu-id="5cf7a-119">Specifying SOAP Actions for WCF Send Adapters</span></span>](../core/specifying-soap-actions-for-wcf-send-adapters.md)
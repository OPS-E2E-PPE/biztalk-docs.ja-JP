---
title: オーケストレーションで WCF メッセージにおける SOAP ヘッダーへのアクセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- orchestrations, WCF services
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: fe02fb02-18d6-4fc6-89e0-b06bdbfa5cb4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 747e92359bf894eb96229cc8e1f1d227db8d5cb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361875"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-orchestrations"></a><span data-ttu-id="87e94-102">オーケストレーションで WCF メッセージにおける SOAP ヘッダーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="87e94-102">Accessing SOAP Headers in WCF Messages with Orchestrations</span></span>
<span data-ttu-id="87e94-103">オーケストレーションにおける受信 WCF メッセージの SOAP ヘッダーの値にアクセスするには、コンテキスト プロパティを使用する**WCF です。InboundHeaders**します。</span><span class="sxs-lookup"><span data-stu-id="87e94-103">To access the SOAP header values of incoming WCF messages in orchestrations, you use the context property **WCF.InboundHeaders**.</span></span> <span data-ttu-id="87e94-104">WCF アダプタを受信メッセージのカスタム SOAP ヘッダーと標準 SOAP ヘッダーのコピー、 **WCF です。InboundHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="87e94-104">The WCF adapters copy custom SOAP headers and standard SOAP headers in the inbound messages to the **WCF.InboundHeaders** property.</span></span> <span data-ttu-id="87e94-105">WCF アダプタでは、プロパティの昇格または書き込みをプログラムによってコンテキスト プロパティにする を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="87e94-105">The WCF adapters also allow you to select the properties you would like to promote or write to the context properties programmatically.</span></span> <span data-ttu-id="87e94-106">参照してください[公開された WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)の詳細。</span><span class="sxs-lookup"><span data-stu-id="87e94-106">See [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md) for more details.</span></span>  
  
 <span data-ttu-id="87e94-107">コンテキスト プロパティに含まれる値は、XML データを格納している文字列、 \<**ヘッダー** \>の子要素としてのルート要素と、受信 SOAP ヘッダーのコピー、 \< **ヘッダー** \>要素。</span><span class="sxs-lookup"><span data-stu-id="87e94-107">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="87e94-108">このデータにアクセスする最も簡単な方法は、BizTalk 式エディターを使用する、**メッセージの割り当て**または**式**図形、内の文字列を読み込み、 **XmlDocument**、および使用特定のフィールドにアクセスする XPath クエリです。</span><span class="sxs-lookup"><span data-stu-id="87e94-108">The simplest way to access this data is to use the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape, load the string in an **XmlDocument**, and use XPath queries to access specific fields.</span></span> <span data-ttu-id="87e94-109">BizTalk 式エディターで XML ドキュメントの作成の詳細については、次を参照してください。 [xlang-s 言語](../core/xlang-s-language.md)します。</span><span class="sxs-lookup"><span data-stu-id="87e94-109">For more information about creating XML documents in the BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
 <span data-ttu-id="87e94-110">次のコード例、要求 SOAP ヘッダーを取得する、**メッセージの割り当て**または**式**図形、 **WCF です。InboundHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="87e94-110">The following code example gets the request SOAP header in a **Message Assignment** or **Expression** shape for the **WCF.InboundHeaders** property:</span></span>  
  
```  
stringVar = inboundMessageInstance(WCF.InboundHeaders);  
```  
  
 <span data-ttu-id="87e94-111">コンテキスト プロパティは、特定のメッセージに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="87e94-111">Context properties are associated with a particular message.</span></span> <span data-ttu-id="87e94-112">メッセージング エンジンは、要求メッセージから応答メッセージに SOAP ヘッダーの値を自動的にマップしません。</span><span class="sxs-lookup"><span data-stu-id="87e94-112">The Messaging Engine does not automatically map the values of the SOAP headers from the request message to the response message.</span></span> <span data-ttu-id="87e94-113">経由の SOAP ヘッダーの値を設定する必要があります具体的には、WCF サービスの応答メッセージを作成するときに、 **WCF です。OutboundCustomHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="87e94-113">When creating the response message for a WCF service, you must specifically set the SOAP header values through the **WCF.OutboundCustomHeaders** property.</span></span> <span data-ttu-id="87e94-114">次のコマンドは、SOAP ヘッダー コンテキスト プロパティの設定の最も簡単なメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="87e94-114">The following command is the simplest method of setting a SOAP header context property:</span></span>  
  
```  
outboundMessageInstance(WCF.OutbounCustomHeaders) = "<headers><Origination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Home</Origination><Destination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Work</Destination></headers>"  
```  
  
 <span data-ttu-id="87e94-115">作成して、コンテキスト プロパティを設定することも、 **XmlDocument**の文字列値の書き込みと、 **XmlDocument**をコンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="87e94-115">You can also set the context property by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span>  
  
 <span data-ttu-id="87e94-116">WCF アダプタで SOAP ヘッダーをアクセスする方法の詳細についてで、SDK サンプルの「を使用してカスタム SOAP ヘッダー with the WCF Adapters」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)します。</span><span class="sxs-lookup"><span data-stu-id="87e94-116">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample "Using Custom SOAP Headers with the WCF Adapters" at [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e94-117">参照</span><span class="sxs-lookup"><span data-stu-id="87e94-117">See Also</span></span>  
 <span data-ttu-id="87e94-118">[パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーへのアクセス](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="87e94-118">[Accessing SOAP Headers in WCF Messages with Pipeline Components](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md) </span></span>  
 <span data-ttu-id="87e94-119">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="87e94-119">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="87e94-120">消費済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="87e94-120">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)
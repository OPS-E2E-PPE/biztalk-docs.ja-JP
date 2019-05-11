---
title: SOAP ヘッダーによる Web サービスを発行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, pipelines
- SOAP headers, BizTalk Web Services Publishing Wizard
- pipelines, SOAP headers
- orchestrations, SOAP headers
ms.assetid: c362caff-b75f-4c1b-9013-d2b9c74f5c65
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd85029e2d38134123b3667f06de3ceadab6f3b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398345"
---
# <a name="publishing-web-services-with-soap-headers"></a><span data-ttu-id="1ebd0-102">SOAP ヘッダーで Web サービスの公開</span><span class="sxs-lookup"><span data-stu-id="1ebd0-102">Publishing Web Services with SOAP Headers</span></span>
<span data-ttu-id="1ebd0-103">BizTalk Web サービス公開ウィザードを実行すると、Web サービスに SOAP ヘッダーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-103">You add SOAP headers to your Web services when you run the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="1ebd0-104">SOAP ヘッダーをサポートする Web サービスを公開すると、追加されたヘッダーは、SOAP ヘッダーの文字列表記を含むコンテキスト プロパティとして、オーケストレーションおよびパイプライン コンポーネントに対して使用可能となります。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-104">When you publish a Web service that supports SOAP headers, the headers become available to orchestrations and pipeline components as context properties that contain string representations of the SOAP headers.</span></span>  
  
## <a name="defined-soap-headers"></a><span data-ttu-id="1ebd0-105">定義済みの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1ebd0-105">Defined SOAP headers</span></span>  
 <span data-ttu-id="1ebd0-106">ウィザードを使用して、定義済みの SOAP ヘッダーを追加すると、ウィザードによってコンテキスト プロパティが作成されます。このプロパティには、SOAP ヘッダーのルート要素に対応する名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-106">When you add a defined SOAP header using the wizard, the wizard creates a context property with a name that corresponds to the root element of the SOAP header.</span></span> <span data-ttu-id="1ebd0-107">定義済みのすべての SOAP ヘッダー コンテキスト プロパティは、名前空間を持つ **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-107">All defined SOAP header context properties have the namespace **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**.</span></span> <span data-ttu-id="1ebd0-108">SOAP ヘッダーのコンテキスト プロパティは、SOAP アダプタによって SOAP 要求が BizTalk メッセージに変換されるときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-108">When the SOAP adapter converts the SOAP request to a BizTalk message, it creates one SOAP header context property.</span></span>  
  
 <span data-ttu-id="1ebd0-109">簡単な SOAP 要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-109">The following example shows a simple SOAP request:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
       <soap:Header>  
             <OrigDest xmlns="http://SOAPHeaderWS.ItemAvailability">  
                    <Origination>Work</Origination>  
                    <Destination>Home</Destination>  
             </OrigDest>  
       </soap:Header>  
       <soap:Body>  
  
       </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="1ebd0-110">SOAP アダプターが 1 つの SOAP ヘッダー コンテキスト プロパティを BizTalk メッセージを作成、単純な SOAP 要求を**OrigDest**および文字列。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-110">For the simple SOAP request, the SOAP adapter created a BizTalk message with one SOAP header context property **OrigDest** and the string.</span></span>  
  
 <span data-ttu-id="1ebd0-111">次の例は、SOAP アダプタによって作成される文字列を示しています。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-111">The following example shows the string created by the SOAP adapter:</span></span>  
  
```  
"<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader"><Origination xmlns="">Home</Origination><Destination xmlns="">Work</Destination> </OrigDest>"  
```  
  
## <a name="unknown-soap-headers"></a><span data-ttu-id="1ebd0-112">不明な SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1ebd0-112">Unknown SOAP headers</span></span>  
 <span data-ttu-id="1ebd0-113">ウィザードで不明な SOAP ヘッダーをサポートするために選択した場合、コンテキスト プロパティは、名前と作成されます**UnknownHeaders**と名前空間 **http://schemas.microsoft.com/BizTalk/2003/soap-properties**します。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-113">If you choose to support unknown SOAP headers in the wizard, the wizard creates a context property with the name **UnknownHeaders** and the namespace **http://schemas.microsoft.com/BizTalk/2003/soap-properties**.</span></span> <span data-ttu-id="1ebd0-114">**UnknownHeaders**コンテキスト プロパティには、すべての受信の不明な SOAP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-114">The **UnknownHeaders** context property contains all of the received unknown SOAP headers.</span></span>  
  
 <span data-ttu-id="1ebd0-115">たとえば、ルート要素名を持つの不明な SOAP ヘッダーを受信する**CustomerGroup**、 **UnknownHeaders**コンテキスト プロパティには、文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-115">For example, if you receive an unknown SOAP header with the root element name, **CustomerGroup**, the **UnknownHeaders** context property contains the string:</span></span>  
  
```  
"<?xml version="1.0" encoding="utf-16"?><UnknownHeaders><CustomerGroup xmlns="http://SOAPHeaderWS/CustomerGroup"><Id xmlns="">My Customer</Id>  
</CustomerGroup></UnknownHeaders>"  
```  
  
 <span data-ttu-id="1ebd0-116">定義の追加の詳細については、SOAP ヘッダーまたは不明な SOAP ヘッダーをサポートするを参照してください[オーケストレーション Web サービスとして公開](../core/publishing-an-orchestration-as-a-web-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-116">For more information about adding defined SOAP headers or supporting unknown SOAP headers, see [Publishing an Orchestration as a Web Service](../core/publishing-an-orchestration-as-a-web-service.md).</span></span> <span data-ttu-id="1ebd0-117">参照してください[Web サービスとして公開スキーマ](../core/publishing-schemas-as-a-web-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ebd0-117">Also see [Publishing Schemas as a Web Service](../core/publishing-schemas-as-a-web-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ebd0-118">参照</span><span class="sxs-lookup"><span data-stu-id="1ebd0-118">See Also</span></span>  
 [<span data-ttu-id="1ebd0-119">公開済み Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="1ebd0-119">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)
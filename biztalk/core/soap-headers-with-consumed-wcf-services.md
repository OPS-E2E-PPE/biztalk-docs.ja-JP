---
title: 消費済み WCF サービスでの SOAP ヘッダー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- SOAP headers, WCF services
- consuming, SOAP headers
- WCF services, SOAP headers
- SOAP headers, consuming [WCF services]
ms.assetid: 0582ee26-b549-4b50-b365-36824010dab0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f9cb3433ecaff2f87e1cd4168b21cedfec05727
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244408"
---
# <a name="soap-headers-with-consumed-wcf-services"></a><span data-ttu-id="f4266-102">消費済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f4266-102">SOAP Headers with Consumed WCF Services</span></span>
<span data-ttu-id="f4266-103">カスタム SOAP ヘッダーで WCF サービスにメッセージを送信するこれらのヘッダーで設定しなければなりません (たとえば式図形) 内のオーケストレーションとパイプライン コンポーネントには (コード)、コンテキスト プロパティとして**OutboundCustomHeaders**です。</span><span class="sxs-lookup"><span data-stu-id="f4266-103">To send a message to a WCF service with the custom SOAP headers, these headers must be set in your orchestrations (in the Expression shape, for example) and pipeline components (in code) as the context property **OutboundCustomHeaders**.</span></span> <span data-ttu-id="f4266-104">このコンテキスト プロパティは、ターゲットの名前空間 **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties** 、カスタム SOAP ヘッダーの文字列表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4266-104">This context property is in the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**, and contains string representations of the custom SOAP headers.</span></span>  
  
 <span data-ttu-id="f4266-105">次の XML 送信メッセージ内のデータのカスタム SOAP ヘッダーの文字列表現の例を示しています、 **OutboundCustomHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f4266-105">The data in the following XML outgoing message shows an example of the string representation of custom SOAP headers for the **OutboundCustomHeaders** property:</span></span>  
  
```  
<headers>  
<Origination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Home</Origination>  
<Destination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Work</Destination>  
</headers>  
```  
  
 <span data-ttu-id="f4266-106">受信 SOAP ヘッダーにも SOAP ヘッダーを表す文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4266-106">Inbound SOAP headers also contain string representations of the SOAP headers.</span></span> <span data-ttu-id="f4266-107">その値は、要求 SOAP ヘッダーを作成するときの値と似ています。</span><span class="sxs-lookup"><span data-stu-id="f4266-107">The values are similar to creating a request SOAP header.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4266-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f4266-108">In This Section</span></span>  
  
-   [<span data-ttu-id="f4266-109">オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="f4266-109">Using SOAP Headers in WCF Messages with Orchestrations</span></span>](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [<span data-ttu-id="f4266-110">パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="f4266-110">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a><span data-ttu-id="f4266-111">参照</span><span class="sxs-lookup"><span data-stu-id="f4266-111">See Also</span></span>  
 <span data-ttu-id="f4266-112">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f4266-112">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="f4266-113">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="f4266-113">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)
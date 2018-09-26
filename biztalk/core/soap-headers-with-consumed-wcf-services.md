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
ms.openlocfilehash: f60e0ae7f9cf2e6a224ce9d919c7c4d5e6f3119c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277490"
---
# <a name="soap-headers-with-consumed-wcf-services"></a><span data-ttu-id="e9975-102">消費済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e9975-102">SOAP Headers with Consumed WCF Services</span></span>
<span data-ttu-id="e9975-103">カスタム SOAP ヘッダーで WCF サービスにメッセージを送信するこれらのヘッダーで設定しなければなりません (たとえば式図形) 内のオーケストレーションとパイプライン コンポーネントには (コード)、コンテキスト プロパティとして**OutboundCustomHeaders**です。</span><span class="sxs-lookup"><span data-stu-id="e9975-103">To send a message to a WCF service with the custom SOAP headers, these headers must be set in your orchestrations (in the Expression shape, for example) and pipeline components (in code) as the context property **OutboundCustomHeaders**.</span></span> <span data-ttu-id="e9975-104">このコンテキスト プロパティがターゲットの名前空間内に**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**、カスタム SOAP ヘッダーの文字列表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9975-104">This context property is in the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**, and contains string representations of the custom SOAP headers.</span></span>  
  
 <span data-ttu-id="e9975-105">次の XML 送信メッセージ内のデータのカスタム SOAP ヘッダーの文字列表現の例を示しています、 **OutboundCustomHeaders**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e9975-105">The data in the following XML outgoing message shows an example of the string representation of custom SOAP headers for the **OutboundCustomHeaders** property:</span></span>  
  
```  
<headers>  
<Origination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Home</Origination>  
<Destination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Work</Destination>  
</headers>  
```  
  
 <span data-ttu-id="e9975-106">受信 SOAP ヘッダーにも SOAP ヘッダーを表す文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9975-106">Inbound SOAP headers also contain string representations of the SOAP headers.</span></span> <span data-ttu-id="e9975-107">その値は、要求 SOAP ヘッダーを作成するときの値と似ています。</span><span class="sxs-lookup"><span data-stu-id="e9975-107">The values are similar to creating a request SOAP header.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9975-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e9975-108">In This Section</span></span>  
  
-   [<span data-ttu-id="e9975-109">オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="e9975-109">Using SOAP Headers in WCF Messages with Orchestrations</span></span>](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [<span data-ttu-id="e9975-110">パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="e9975-110">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a><span data-ttu-id="e9975-111">参照</span><span class="sxs-lookup"><span data-stu-id="e9975-111">See Also</span></span>  
 <span data-ttu-id="e9975-112">[WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e9975-112">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="e9975-113">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e9975-113">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)
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
# <a name="soap-headers-with-consumed-wcf-services"></a>消費済み WCF サービスでの SOAP ヘッダー
カスタム SOAP ヘッダーで WCF サービスにメッセージを送信するこれらのヘッダーで設定しなければなりません (たとえば式図形) 内のオーケストレーションとパイプライン コンポーネントには (コード)、コンテキスト プロパティとして**OutboundCustomHeaders**です。 このコンテキスト プロパティは、ターゲットの名前空間 **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties** 、カスタム SOAP ヘッダーの文字列表現が含まれています。  
  
 次の XML 送信メッセージ内のデータのカスタム SOAP ヘッダーの文字列表現の例を示しています、 **OutboundCustomHeaders**プロパティ。  
  
```  
<headers>  
<Origination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Home</Origination>  
<Destination xmlns="http://SOAPHeaderSchemas.OrigDestSOAPHeader">Work</Destination>  
</headers>  
```  
  
 受信 SOAP ヘッダーにも SOAP ヘッダーを表す文字列が含まれます。 その値は、要求 SOAP ヘッダーを作成するときの値と似ています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーションでの WCF メッセージにおける SOAP ヘッダーの使用](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [パイプライン コンポーネントでの WCF メッセージにおける SOAP ヘッダーの使用](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a>参照  
 [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)   
 [公開済み WCF サービスでの SOAP ヘッダー](../core/soap-headers-with-published-wcf-services.md)
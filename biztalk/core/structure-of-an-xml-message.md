---
title: XML メッセージの構造 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bba81-2f2b-41f3-b8b2-c2fb9c15ea5a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4e7501165dca01c81ad43a0e79184f7e5614ae9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295810"
---
# <a name="structure-of-an-xml-message"></a>XML メッセージの構造
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、XML インスタンス メッセージは XML タグの有効な階層になっており、0 個以上の XML エンベロープおよび 1 つ以上の XML ドキュメントで構成されます。 たとえば、次の XML インスタンス メッセージは、単一の XML ドキュメント (太字で示されている) を含む 1 つの XML エンベロープ (通常フォントで示されている) で構成されています。  
  
```  
<ns0:envelope xmlns:ns0="http://myEnvelopeNamespaceURI.org">  
    <header>  
        <firstName>John</firstName>  
        <lastName>Scott</lastName>  
    </header>  
    <body>  
        <ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">            <message>Hello</message>        </ns1:document>  
    </body>  
</ns0:envelope>  
```  
  
 XML エンベロープと XML エンベロープに含まれる XML ドキュメントは、有効な XML インスタンス メッセージにさまざまな方法で結合できます。 以降では、これらのさまざまな組み合わせについて説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML メッセージ エンベロープ](../core/xml-message-envelopes.md)  
  
-   [入れ子になった XML メッセージ エンベロープ](../core/nested-xml-message-envelopes.md)
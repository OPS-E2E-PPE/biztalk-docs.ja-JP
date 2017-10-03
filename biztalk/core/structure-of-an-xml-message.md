---
title: "XML メッセージの構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a5bba81-2f2b-41f3-b8b2-c2fb9c15ea5a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f35e48e90ffb089342c268b7b6a45069e2f9869
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="structure-of-an-xml-message"></a><span data-ttu-id="b6539-102">XML メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="b6539-102">Structure of an XML Message</span></span>
<span data-ttu-id="b6539-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、XML インスタンス メッセージは XML タグの有効な階層になっており、0 個以上の XML エンベロープおよび 1 つ以上の XML ドキュメントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b6539-103">In the context of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], an XML instance message is a valid hierarchy of XML tags that together constitute zero or more XML envelopes and one or more XML documents.</span></span> <span data-ttu-id="b6539-104">たとえば、次の XML インスタンス メッセージは、単一の XML ドキュメント (太字で示されている) を含む 1 つの XML エンベロープ (通常フォントで示されている) で構成されています。</span><span class="sxs-lookup"><span data-stu-id="b6539-104">For example, the following XML instance message consists of a single XML envelope (in regular font) that contains a single XML document (shown in bold type).</span></span>  
  
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
  
 <span data-ttu-id="b6539-105">XML エンベロープと XML エンベロープに含まれる XML ドキュメントは、有効な XML インスタンス メッセージにさまざまな方法で結合できます。</span><span class="sxs-lookup"><span data-stu-id="b6539-105">XML envelopes and the XML documents that they contain can be combined into valid XML instance messages in several different ways.</span></span> <span data-ttu-id="b6539-106">以降では、これらのさまざまな組み合わせについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b6539-106">The remainder of this section describes these different combinations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6539-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b6539-107">In This Section</span></span>  
  
-   [<span data-ttu-id="b6539-108">XML メッセージ エンベロープ</span><span class="sxs-lookup"><span data-stu-id="b6539-108">XML Message Envelopes</span></span>](../core/xml-message-envelopes.md)  
  
-   [<span data-ttu-id="b6539-109">入れ子になった XML メッセージ エンベロープ</span><span class="sxs-lookup"><span data-stu-id="b6539-109">Nested XML Message Envelopes</span></span>](../core/nested-xml-message-envelopes.md)
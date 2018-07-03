---
title: XML メッセージ エンベロープ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d01cd85d-7bf7-49fa-aa25-322213bce066
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f4b60dfbc128baead6b0a1ad38d319ba7b6e8fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972411"
---
# <a name="xml-message-envelopes"></a><span data-ttu-id="d8b07-102">XML メッセージ エンベロープ</span><span class="sxs-lookup"><span data-stu-id="d8b07-102">XML Message Envelopes</span></span>
<span data-ttu-id="d8b07-103">XML エンベロープには、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって送受信される XML インスタンス メッセージに関連する 2 つの用途があります。</span><span class="sxs-lookup"><span data-stu-id="d8b07-103">XML envelopes serve two purposes within XML instance messages sent and received by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
- <span data-ttu-id="d8b07-104">XML エンベロープには、XML ドキュメント内のデータを補足するデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="d8b07-104">XML envelopes can contain data that supplements the data within the XML documents.</span></span> <span data-ttu-id="d8b07-105">XML 逆アセンブラーでこのデータをメッセージ コンテキストに昇格することにより、さまざまな BizTalk Server コンポーネントから簡単にアクセスすることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="d8b07-105">This data can be promoted into the message context by the XML disassembler to provide easier access from a variety of BizTalk Server components.</span></span> <span data-ttu-id="d8b07-106">送信 XML インスタンス メッセージの場合、XML アセンブラーを使用すると、メッセージ コンテキストからインスタンス メッセージの送信に含めるエンベロープに値を降格できます。</span><span class="sxs-lookup"><span data-stu-id="d8b07-106">For outbound XML instance messages, the XML assembler can demote values from the message context into an envelope for inclusion in the instance message transmission.</span></span>  
  
- <span data-ttu-id="d8b07-107">XML エンベロープを使用して、複数の XML ドキュメントを単一の有効な XML インスタンス メッセージに結合できます。</span><span class="sxs-lookup"><span data-stu-id="d8b07-107">XML envelopes can be used to combine multiple XML documents into a single, valid XML instance message.</span></span> <span data-ttu-id="d8b07-108">単一のルート タグ内にある複数のドキュメントをラップするエンベロープがない場合、複数のドキュメントを含む XML インスタンス メッセージは、整形式 XML として扱われません。</span><span class="sxs-lookup"><span data-stu-id="d8b07-108">Without an envelope to wrap multiple documents within a single root tag, an XML instance message containing multiple documents would not qualify as well-formed XML.</span></span>  
  
  <span data-ttu-id="d8b07-109">通常の XML エンベロープ (太字で示されている) には、エンベロープに含まれる 1 つ以上の XML ドキュメント (通常フォントで示されている) を区切るためのデータとタグの両方が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d8b07-109">A typical XML envelope (shown in bold type) contains both data and a tag used to delimit the one or more XML documents (shown in regular font) that it contains.</span></span>  
  
```  
  
  <envelope fieldAttrib1="..." fieldAttrib2="..." ...>     <fieldElem1>...</fieldElem1>     <fieldElem2>...</fieldElem2>     ...     <body>  
    <document1>  
        ...  
    </document1>  
    <document2>  
        ...  
    </document2>  
    ...  
</body>    ...</envelope>  
```  
  
 <span data-ttu-id="d8b07-110">XML エンベロープ (太字で示されている) には、エンベロープに含まれる XML ドキュメント (通常フォントで示されている) を区切るデータやタグを格納する必要はありませんが、これは一般的な方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="d8b07-110">Less common, but still valid, an XML envelope (shown in bold type) need not contain any data or a tag for delimiting the XML documents (shown in regular type) that it contains.</span></span>  
  
```  
  
      <envelope>  
    <document1>  
        ...  
    </document1>  
    <document2>  
        ...  
    </document2>  
    ...  
</envelope>  
```  
  
 <span data-ttu-id="d8b07-111">この場合、XML エンベロープに含まれるのは、開始エンベロープ タグおよび終了エンベロープ タグだけです。</span><span class="sxs-lookup"><span data-stu-id="d8b07-111">In such cases, the XML envelope consists of nothing other than the starting and ending envelope tags.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b07-112">参照</span><span class="sxs-lookup"><span data-stu-id="d8b07-112">See Also</span></span>  
 <span data-ttu-id="d8b07-113">[入れ子になった XML メッセージ エンベロープ](../core/nested-xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="d8b07-113">[Nested XML Message Envelopes](../core/nested-xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="d8b07-114">[XML メッセージの構造](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="d8b07-114">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="d8b07-115">エンベロープ用スキーマの作成方法</span><span class="sxs-lookup"><span data-stu-id="d8b07-115">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)
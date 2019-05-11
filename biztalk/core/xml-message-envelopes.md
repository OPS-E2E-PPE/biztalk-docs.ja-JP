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
ms.openlocfilehash: 8276e2986231c391479112b25e01bea778566093
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246414"
---
# <a name="xml-message-envelopes"></a><span data-ttu-id="1ec16-102">XML メッセージ エンベロープ</span><span class="sxs-lookup"><span data-stu-id="1ec16-102">XML Message Envelopes</span></span>
<span data-ttu-id="1ec16-103">XML エンベロープは Microsoft によって送受信された、XML インスタンス メッセージ内で 2 つの目的を果たします[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1ec16-103">XML envelopes serve two purposes within XML instance messages sent and received by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
- <span data-ttu-id="1ec16-104">XML エンベロープには、XML ドキュメント内のデータを補完する、データを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1ec16-104">XML envelopes can contain data that supplements the data within the XML documents.</span></span> <span data-ttu-id="1ec16-105">このデータは、さまざまな BizTalk Server コンポーネントから簡単にアクセスを提供する XML 逆アセンブラーによってメッセージ コンテキストに昇格できます。</span><span class="sxs-lookup"><span data-stu-id="1ec16-105">This data can be promoted into the message context by the XML disassembler to provide easier access from a variety of BizTalk Server components.</span></span> <span data-ttu-id="1ec16-106">XML インスタンス メッセージの送信、XML アセンブラーは、エンベロープ インスタンス メッセージの送信に含めることに、メッセージ コンテキストから値を降格することができます。</span><span class="sxs-lookup"><span data-stu-id="1ec16-106">For outbound XML instance messages, the XML assembler can demote values from the message context into an envelope for inclusion in the instance message transmission.</span></span>  
  
- <span data-ttu-id="1ec16-107">XML エンベロープは、1 つ、有効な XML インスタンス メッセージを複数の XML ドキュメントに組み込んで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ec16-107">XML envelopes can be used to combine multiple XML documents into a single, valid XML instance message.</span></span> <span data-ttu-id="1ec16-108">単一のルート タグ内で複数のドキュメントをラップするエンベロープのないを複数のドキュメントを含む XML インスタンス メッセージは整形式 XML として扱われません。</span><span class="sxs-lookup"><span data-stu-id="1ec16-108">Without an envelope to wrap multiple documents within a single root tag, an XML instance message containing multiple documents would not qualify as well-formed XML.</span></span>  
  
  <span data-ttu-id="1ec16-109">(太字で表示)、一般的な XML エンベロープには、データと (フォントで表示される正規表現) が含まれている 1 つまたは複数の XML ドキュメントを区切るために使用されるタグの両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1ec16-109">A typical XML envelope (shown in bold type) contains both data and a tag used to delimit the one or more XML documents (shown in regular font) that it contains.</span></span>  
  
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
  
 <span data-ttu-id="1ec16-110">あまり一般的ではまだ有効でない XML エンベロープ (太字で表示) は必要なすべてのデータや (参照の通常の型) が含まれている XML ドキュメントの区切り記号としてタグには含まれません。</span><span class="sxs-lookup"><span data-stu-id="1ec16-110">Less common, but still valid, an XML envelope (shown in bold type) need not contain any data or a tag for delimiting the XML documents (shown in regular type) that it contains.</span></span>  
  
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
  
 <span data-ttu-id="1ec16-111">このような場合は、XML エンベロープの開始および終了エンベロープ タグ以外は何で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1ec16-111">In such cases, the XML envelope consists of nothing other than the starting and ending envelope tags.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec16-112">参照</span><span class="sxs-lookup"><span data-stu-id="1ec16-112">See Also</span></span>  
 <span data-ttu-id="1ec16-113">[入れ子になった XML メッセージ エンベロープ](../core/nested-xml-message-envelopes.md) </span><span class="sxs-lookup"><span data-stu-id="1ec16-113">[Nested XML Message Envelopes](../core/nested-xml-message-envelopes.md) </span></span>  
 <span data-ttu-id="1ec16-114">[XML メッセージの構造](../core/structure-of-an-xml-message.md) </span><span class="sxs-lookup"><span data-stu-id="1ec16-114">[Structure of an XML Message](../core/structure-of-an-xml-message.md) </span></span>  
 [<span data-ttu-id="1ec16-115">エンベロープ用スキーマの作成方法</span><span class="sxs-lookup"><span data-stu-id="1ec16-115">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)
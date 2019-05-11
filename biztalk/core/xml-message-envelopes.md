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
# <a name="xml-message-envelopes"></a>XML メッセージ エンベロープ
XML エンベロープは Microsoft によって送受信された、XML インスタンス メッセージ内で 2 つの目的を果たします[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- XML エンベロープには、XML ドキュメント内のデータを補完する、データを含めることができます。 このデータは、さまざまな BizTalk Server コンポーネントから簡単にアクセスを提供する XML 逆アセンブラーによってメッセージ コンテキストに昇格できます。 XML インスタンス メッセージの送信、XML アセンブラーは、エンベロープ インスタンス メッセージの送信に含めることに、メッセージ コンテキストから値を降格することができます。  
  
- XML エンベロープは、1 つ、有効な XML インスタンス メッセージを複数の XML ドキュメントに組み込んで使用できます。 単一のルート タグ内で複数のドキュメントをラップするエンベロープのないを複数のドキュメントを含む XML インスタンス メッセージは整形式 XML として扱われません。  
  
  (太字で表示)、一般的な XML エンベロープには、データと (フォントで表示される正規表現) が含まれている 1 つまたは複数の XML ドキュメントを区切るために使用されるタグの両方が含まれています。  
  
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
  
 あまり一般的ではまだ有効でない XML エンベロープ (太字で表示) は必要なすべてのデータや (参照の通常の型) が含まれている XML ドキュメントの区切り記号としてタグには含まれません。  
  
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
  
 このような場合は、XML エンベロープの開始および終了エンベロープ タグ以外は何で構成されます。  
  
## <a name="see-also"></a>参照  
 [入れ子になった XML メッセージ エンベロープ](../core/nested-xml-message-envelopes.md)   
 [XML メッセージの構造](../core/structure-of-an-xml-message.md)   
 [エンベロープ用スキーマの作成方法](../core/how-to-create-schemas-for-envelopes.md)
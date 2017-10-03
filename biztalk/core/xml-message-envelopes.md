---
title: "XML メッセージ エンベロープ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d01cd85d-7bf7-49fa-aa25-322213bce066
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3adb33866a3e6fdaee387934d2edededaab08aac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xml-message-envelopes"></a>XML メッセージ エンベロープ
XML エンベロープには、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって送受信される XML インスタンス メッセージに関連する 2 つの用途があります。  
  
-   XML エンベロープには、XML ドキュメント内のデータを補足するデータを格納できます。 XML 逆アセンブラーでこのデータをメッセージ コンテキストに昇格することにより、さまざまな BizTalk Server コンポーネントから簡単にアクセスすることが可能になります。 送信 XML インスタンス メッセージの場合、XML アセンブラーを使用すると、メッセージ コンテキストからインスタンス メッセージの送信に含めるエンベロープに値を降格できます。  
  
-   XML エンベロープを使用して、複数の XML ドキュメントを単一の有効な XML インスタンス メッセージに結合できます。 単一のルート タグ内にある複数のドキュメントをラップするエンベロープがない場合、複数のドキュメントを含む XML インスタンス メッセージは、整形式 XML として扱われません。  
  
 通常の XML エンベロープ (太字で示されている) には、エンベロープに含まれる 1 つ以上の XML ドキュメント (通常フォントで示されている) を区切るためのデータとタグの両方が格納されます。  
  
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
  
 XML エンベロープ (太字で示されている) には、エンベロープに含まれる XML ドキュメント (通常フォントで示されている) を区切るデータやタグを格納する必要はありませんが、これは一般的な方法ではありません。  
  
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
  
 この場合、XML エンベロープに含まれるのは、開始エンベロープ タグおよび終了エンベロープ タグだけです。  
  
## <a name="see-also"></a>参照  
 [入れ子になった XML メッセージ エンベロープ](../core/nested-xml-message-envelopes.md)   
 [XML メッセージの構造](../core/structure-of-an-xml-message.md)   
 [エンベロープ用スキーマを作成する方法](../core/how-to-create-schemas-for-envelopes.md)
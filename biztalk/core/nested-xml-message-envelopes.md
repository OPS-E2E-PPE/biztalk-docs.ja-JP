---
title: "XML メッセージ エンベロープを入れ子になった |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e880cef1-4e73-4bce-a06e-8c4d23bc5a8c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b0f505dd9ba7da71df1cb460f9c9a6610763d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="nested-xml-message-envelopes"></a>入れ子になった XML メッセージ エンベロープ
XML エンベロープを入れ子にすることによって、複雑なドキュメント構造を作成できます。 入れ子になった XML エンベロープには、柔軟型と正規型の 2 つの形態があります。 次の例は、柔軟型のエンベロープ ドキュメントを示しています。ドキュメントおよびエンベロープ (太字部分) が上位のエンベロープ内の同じレベルに出現しています。  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 次の例は、正規型のエンベロープ ドキュメントに準拠した、同様のインスタンス メッセージを示しています。すべてのドキュメントが最下位のエンベロープ内の同じレベルに出現しています。  
  
```  
<envelope1>  
    <envelope2>  
        <document1/>  
        <document2/>  
        <document3/>  
        <document4/>  
    </envelope2>  
</envelope1>  
  
```  
  
 XML 逆アセンブラーは、前述の 2 つの形態のインスタンス メッセージを受け取ると、いずれも document1、document2、document3、および document4 を生成します。 各ドキュメントのメッセージ コンテキストには、対応するドキュメントから昇格されたプロパティのほかに、上位の各エンベロープ内で昇格されたプロパティが含まれます。 次の表は、昇格されるプロパティを示しています。これらのプロパティは、柔軟型および正規型の例で、各エンベロープおよびドキュメントの最初の列で指定されたプロパティ昇格に基づき、ラップ解除された各ドキュメントのメッセージ コンテキストに追加されます。  
  
|指定されたプロパティ昇格|結果のメッセージ コンテキスト プロパティ (柔軟型の例)|結果のメッセージ コンテキスト プロパティ (正規型の例)|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|envelope1: p1<br /><br /> envelope2: p3<br /><br /> document1: p2<br /><br /> document2: p4 および p5<br /><br /> document3: プロモーションがありません<br /><br /> document4 を生成: プロモーションがありません|document1: p1、p2<br /><br /> document2: p1、p3、p4、p5<br /><br /> document3: p1、p3<br /><br /> document4 を生成: p1|document1: p1、p2、p3<br /><br /> document2: p1、p3、p4、p5<br /><br /> document3: p1、p3<br /><br /> document4 を生成: p1、p3|  
  
## <a name="see-also"></a>参照  
 [XML メッセージ エンベロープ](../core/xml-message-envelopes.md)   
 [XML メッセージの構造](../core/structure-of-an-xml-message.md)   
 [エンベロープ用スキーマを作成する方法](../core/how-to-create-schemas-for-envelopes.md)
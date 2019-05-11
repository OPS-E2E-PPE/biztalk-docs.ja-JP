---
title: XML メッセージ エンベロープを入れ子になった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e880cef1-4e73-4bce-a06e-8c4d23bc5a8c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b341930a30c8653cb2db378a24c6600f48de0891
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263355"
---
# <a name="nested-xml-message-envelopes"></a>入れ子になった XML メッセージ エンベロープ
複雑なドキュメント構造を作成する XML エンベロープを入れ子にすることができます。 入れ子になった XML エンベロープに柔軟で canonical と呼ばれる 2 つの形式で発生します。 次の例では、エンベロープ ドキュメントをドキュメントおよびエンベロープ (太字で表示する) ことができますが表示される上位のエンベロープ内の同じレベルでの柔軟な形式を示します。  
  
```  
<envelope1>  
    <document1/>    <envelope2>  
        <document2/>  
        <document3/>  
    </envelope2>    <document4/>  
</envelope1>  
```  
  
 次の例では、最も内側のエンベロープ内の同じレベルに表示されるすべてのドキュメントのエンベロープのドキュメントの正規の形式に準拠している同様のインスタンス メッセージを示します。  
  
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
  
 フォームの説明のいずれかで、インスタンス メッセージを指定する、XML 逆アセンブラーは document1、document2、document3、および document4 を生成を生成します。 これらのドキュメントのそれぞれのメッセージ コンテキストには、外側のエンベロープの各内で昇格させたプロパティと、対応するドキュメントから昇格されたプロパティが含まれます。 次の表に表示される昇格させたプロパティが両方、柔軟で標準的な例については、さまざまなエンベロープの最初の列で指定されたプロパティ昇格に基づきラップされていない各ドキュメントのメッセージ コンテキストに含めるとドキュメント。  
  
|指定したプロパティの昇格|柔軟な例については、結果のメッセージ コンテキスト プロパティ|標準的な例の結果のメッセージ コンテキスト プロパティ|  
|-----------------------------------|---------------------------------------------------------------|----------------------------------------------------------------|  
|envelope1: p1<br /><br /> envelope2: p3<br /><br /> 文書 1: p2<br /><br /> 文書 2: p4 および p5<br /><br /> document3: no promotions<br /><br /> document4: no promotions|文書 1: p1、p2<br /><br /> 文書 2: p1、p3、p4、p5<br /><br /> document3: p1、p3<br /><br /> document4 を生成: p1|文書 1: p1、p2、p3<br /><br /> 文書 2: p1、p3、p4、p5<br /><br /> document3: p1、p3<br /><br /> document4 を生成: p1、p3|  
  
## <a name="see-also"></a>参照  
 [XML メッセージ エンベロープ](../core/xml-message-envelopes.md)   
 [XML メッセージの構造](../core/structure-of-an-xml-message.md)   
 [エンベロープ用スキーマの作成方法](../core/how-to-create-schemas-for-envelopes.md)
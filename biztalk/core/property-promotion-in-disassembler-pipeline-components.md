---
title: "逆アセンブラー パイプライン コンポーネントのプロパティの昇格 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, promoting properties
- XML Disassembler [pipeline component], properties
- pipeline components, properties
- promoting properties, disassembler pipeline components
- BizTalk Framework Assembler [pipeline component], properties
- Flat File Disassembler [pipeline component], properties
ms.assetid: aa37b308-8aa2-45f4-9383-aca4f2c925ce
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9770b0e66b85dcc41400002e2e0c1780bc51c3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="property-promotion-in-disassembler-pipeline-components"></a>逆アセンブラー パイプライン コンポーネントのプロパティの昇格
プロパティの昇格とは、XML ドキュメントから XPath 式を使ってプロパティ値を抽出し、メッセージ コンテキストに設定することによって、プロパティ値に基づくメッセージのルーティングを可能にするプロセスです。  
  
 昇格させたプロパティには、既定値はありません。 または値を修正するには、そのプロパティの XML フィールドが存在し、ドキュメント構造の検証プロパティは場合**False**、プロパティは昇格されません。  
  
 カスタム パイプライン コンポーネントでは、複数値 (つまり、配列化された) プロパティを昇格させることができます。 複数値プロパティを含むメッセージは、コンテンツ ベースのルーティング (CBR) シナリオでのみサポートされます。オーケストレーションにルーティングしたり、追跡目的で使用することはできません。  
  
 終了タグが存在する空要素では、既定値や固定値は昇格されません。 たとえば、 \<field1 > は、次の XML は昇格されません。  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 ただし、次の例のように、終了タグのない空要素は昇格されます。  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 ドキュメントから datetime データを読み取り、それをコンテキスト プロパティに設定するとき、データが UTC 形式であった場合、その形式が維持されます。 datetime データがローカル時刻にオフセット値を加えた形式になっている場合、BizTalk Server によって、datetime の形式が UTC 形式に変換されます。この UTC 形式は、ローカル時刻にオフセット値を加算することによって取得されます。 datetime 形式にタイム ゾーンも UTC 形式も指定されていなかった場合、ローカル時刻と見なされ、現在のタイム ゾーンに基づいて UTC に変換されます。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
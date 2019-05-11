---
title: 逆アセンブラー パイプライン コンポーネントのプロパティの昇格 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, promoting properties
- XML Disassembler [pipeline component], properties
- pipeline components, properties
- promoting properties, disassembler pipeline components
- BizTalk Framework Assembler [pipeline component], properties
- Flat File Disassembler [pipeline component], properties
ms.assetid: aa37b308-8aa2-45f4-9383-aca4f2c925ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26e8b358b70c12ecf5567c19377fa8419f5bea83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398463"
---
# <a name="property-promotion-in-disassembler-pipeline-components"></a>逆アセンブラー パイプライン コンポーネントのプロパティの昇格
プロパティの昇格は、プロパティ値を XPath 式を使用して XML ドキュメントから抽出してメッセージのルーティングのために使用できるように、メッセージ コンテキストに配置するプロセスです。  
  
 昇格させたプロパティには、既定値はありません。 または値を修正するには、そのプロパティの XML フィールドが存在しないか、およびドキュメント構造の検証プロパティが場合**False**、プロパティは昇格されません。  
  
 カスタム パイプライン コンポーネントで昇格できる複数の値 (つまり、配列化された) プロパティ。 複数値プロパティを含むメッセージは、コンテンツ ベースのルーティング (CBR) シナリオでのみサポートします。オーケストレーションにルーティングすることはできません、または追跡の目的で使用します。  
  
 XML 逆アセンブラーは、既定値は昇格しませんまたは終了タグがある場合は、空の要素の値を修正しました。 たとえば、 \<field1\>は、次の XML は昇格されません。  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 ただし、(次の例で示す) のように終了タグのない空の要素を昇格します。  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 ドキュメントとデータが UTC 形式である場合、コンテキスト プロパティに配置することから datetime データを読み取るときにその形式が維持されます。 Datetime データがローカル + オフセット形式である場合は、BizTalk Server は、datetime 形式を現地時刻にオフセットを加算した結果を UTC 形式に変換します。 Datetime 形式がタイム ゾーンまたは UTC 形式を指定しない場合、時刻はローカルと見なされ、現在のタイム ゾーンに基づいて UTC に変換されます。  
  
## <a name="see-also"></a>参照  
 [XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
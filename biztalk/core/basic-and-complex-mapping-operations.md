---
title: 基本的なと複雑なマッピング操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da864b48-6255-4847-9a6f-13e489e8658d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3ca1e0819de255e70d4f66064f52cdc70f7189c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529155"
---
# <a name="basic-and-complex-mapping-operations"></a>基本的なと複雑なマッピング操作
BizTalk マッパーでは、マッピングのシナリオが単純な親子ツリー型の操作からループ レコードや階層に関連する詳細で複雑な操作に至るまでのさまざまなソリューションを提供します。 マッピング シナリオの複雑さは、基本設定とビジネス ニーズによって異なります: XML Schema definition (XSD) 言語は、かなり柔軟に構造化された形式の定義を提供します。 ほぼすべてのマッピング シナリオが 2 つのカテゴリのいずれかに分類されます。 基本的なマッピングと複雑なマッピング。  
  
## <a name="basic-mapping"></a>基本的なマッピング  
 基本的なマッピングは、最も一般的な種類のマッピングを作成することができます。 基本的なマップでは、入力と出力の項目は、一対一のリレーションシップを持ちます。 入力の項目は、1 つだけの出力項目にマップされます。 さまざまな種類の変換および変換が複数の使用などの基本的なマッピングで可能な*functoid*コピーされる値を操作する functoid を連鎖するには、基になるシナリオは比較的と簡単です。 基本的なマッピング操作では、(一度だけ発生する) 送信先スキーマの 1 つの親レコードの下のフィールドに 2 つの異なる親レコードからフィールドのマッピングも含まれます。  
  
## <a name="complex-mapping"></a>複雑なマッピング  
 複雑なマッピングには、1 つのインスタンスに対して複数回発生するレコードやフィールドが含まれます。、**レコード**または**フィールド要素**スキーマ ツリー内のノード。 このようなノードがその**Max Occurs** 1 つ以上の対応する要素にあります、インスタンス メッセージを示すプロパティを 1 (1) よりも大きい値に設定します。 BizTalk マップが可変のマッピングには、この型を使用する場合 (とも呼ばれます*ループ*)、Extensible Stylesheet Language (XSL) スタイル シートのコンパイラで生成するために反復処理する対象となる適切なループ パスを決定できる必要があります、必要な出力。  
  
 一般に、送信先スキーマのループ レコード内のフィールドに、送信元スキーマのループ レコード内のフィールドをリンクできます。 入力インスタンス メッセージに対応する要素の数は、出力インスタンス メッセージで作成した要素の数を決定します。 元と送信先スキーマの例は、次の XSD フラグメントを検討してください。  
  
### <a name="source-schema-fragment"></a>ソース スキーマのフラグメント  
  
```  
<xs:element minOccurs="1" maxOccurs="5"  
            name="SrcLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
  
```  
  
### <a name="destination-schema-fragment"></a>送信先スキーマのフラグメント  
  
```  
<xs:element minOccurs="0" maxOccurs="unbounded"  
            name="DstLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
```  
  
 : これらのフラグメントで  
  
- **SrcLoopingRecord**、**レコード**、入力インスタンス メッセージ内のノードが 5 回に 1 つから発生することができます。 子も含まれています。**フィールド要素**ノード**Field1** (文字列) と**Field2** (整数)、親の各インスタンスに対して一度だけ発生します。  
  
- **DstLoopingRecord**、**レコード**、出力インスタンス メッセージ内のノードは、ゼロ (0) 回以上、無制限に発生することができます。 子も含まれています。**フィールド要素**ノード**FieldA** (文字列) と**FieldB** (整数)、親の各インスタンスに対して一度だけ発生します。  
  
  Field1 は FieldA にマップされ、Field2 がマップされていると仮定 FieldB に、入力インスタンス メッセージから次のフラグメントが、それらのマッピングを処理、出力インスタンス メッセージから次のフラグメントが生成されます。  
  
### <a name="input-instance-message-fragment"></a>入力インスタンス メッセージのフラグメント  
  
```  
<SrcLoopingRecord>  
    <Field1>A string</Field1>  
    <Field2>10</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>Another string</Field1>  
    <Field2>11</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>A ball of string</Field1>  
    <Field2>12</Field2>  
</SrcLoopingRecord>  
```  
  
### <a name="output-instance-message-fragment"></a>出力インスタンス メッセージのフラグメント  
  
```  
<DstLoopingRecord>  
    <FieldA>A string</FieldA>  
    <FieldB>10</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
  <FieldA>Another string</FieldA>  
  <FieldB>11</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
    <FieldA>A ball of string</FieldA>  
    <FieldB>12</FieldB>  
</DstLoopingRecord>  
```  
  
 出現回数、 **SrcLoopingRecord** (3) の入力インスタンス メッセージ内の要素の出現回数を決定する、 **DstLoopingRecord**出力インスタンス メッセージ内の要素。  
  
 BizTalk マッパーでサポートされていないマッピングの種類は、複数のループ パスの使用です。 この種類マッピングにはには、送信先スキーマの 1 つのループ レコード内のフィールドにマップされる送信元スキーマ内の 2 つまたは複数のループ レコードからフィールドが含まれます。 これは、問題など、出力インスタンス メッセージで生成される要素の数を決定する効果的な方法はありません。 マップのコンパイル警告を示すの宛先ノードが複数の送信元ループ パスを持つ複数のループ パスがあります。 ただし、これは、警告のみと、最初の送信元ループ パスでのイテレーションの数は、出力インスタンス メッセージに生成される要素の数を決定するために使用します。 ループを使用して動作の明示的な制御を行う、**ループ**functoid。  
  
 Microsoft BizTalk Server では、新しい種類のテーブルドリブン ループというループが導入されました。 テーブルドリブン ループは、出力インスタンス メッセージは、入力インスタンス メッセージからデータに基づく、定数、送信元スキーマ、または functoid からのリンクの 1 つまたは複数を組み合わせる必要がある場合に便利です。 このような場合は、出力インスタンス メッセージに複数のレコードが別の定数と組み合わせるか、入力インスタンス メッセージ内の複数レコードからのデータに基づく入力インスタンス メッセージ内の 1 つのレコードからデータに基づくことができます。 テーブル ドリブンの詳細については、ループを使用して、**テーブル ループ**と**テーブル抽出**functoid を参照してください[テーブル ループ functoid およびテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)します。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)
---
title: "基本的なと複雑なマッピング操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da864b48-6255-4847-9a6f-13e489e8658d
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82876310cfa497f8002e7df680281122e90884af
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="basic-and-complex-mapping-operations"></a>基本のマッピング操作と複雑なマッピング操作
BizTalk マッパーは、単純な親子ツリー型の操作から、ループ レコードや階層を含む詳細で複雑な操作まで、さまざまなマッピング シナリオに対するソリューションを提供します。 マッピング シナリオの複雑さは、基本設定とビジネス ニーズによって異なります。: XML Schema definition (XSD) 言語では、柔軟性が構造化された形式を定義する際にします。 ほぼすべてのマッピング シナリオは、2 つのカテゴリ (基本的なマッピングと複雑なマッピング) のいずれかに分類されます。  
  
## <a name="basic-mapping"></a>基本的なマッピング  
 基本的なマッピングとは、最も一般的なマッピングのことをいいます。 基本的なマップでは、入力項目と出力項目が 1 対 1 の関係になります。 入力項目は、対応する 1 つの出力項目にのみマップされます。 さまざまな種類の変換や翻訳は複数の使用などの基本的なマッピングでは可能ですが *functoid* し、コピーされる値を操作する functoid を連鎖するには、基になるシナリオは比較的簡単です。 基本的なマッピング操作では、2 つの異なる親レコード (一度だけ発生する) に属するフィールドを、送信先スキーマの単一の親レコードに属するフィールドへマッピングすることもあります。  
  
## <a name="complex-mapping"></a>複雑なマッピング  
 複雑なマッピングは、1 つのインスタンスに対して複数回発生するレコードやフィールド、 **レコード** または **フィールド要素** スキーマ ツリー内のノードです。 このようなノードがその **Max Occurs** プロパティ (1) より大きい値に設定の 1 つ以上の対応する要素にありますインスタンス メッセージを示します。 BizTalk マップがこの種の count 変数のマッピングを使用する場合 (とも呼ばれる *ループ*)、拡張スタイル シート言語 (XSL) スタイル シート コンパイラは、必要な出力を生成する反復処理する適切なループ パスを決定できる必要があります。  
  
 通常、送信元スキーマのループ レコードのフィールドを、送信先スキーマのループ レコードのフィールドにリンクできます。 入力インスタンス メッセージ内にある要素の数によって、出力インスタンス メッセージ内に作成される要素の数が決まります。 送信元スキーマおよび送信先スキーマを基にした、次の XSD フラグメントを考えてみます。  
  
### <a name="source-schema-fragment"></a>送信元スキーマのフラグメント  
  
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
  
 これらのフラグメントを説明します。  
  
-   **SrcLoopingRecord**, 、 **レコード** 入力インスタンス メッセージ内のノードが 5 回に 1 つから発生することができます。 子プロセスも含まれています。 **フィールド要素** ノード **Field1** (文字列) と **Field2** (整数)、親の各インスタンスに対して一度だけ発生します。  
  
-   **DstLoopingRecord**, 、 **レコード** 出力インスタンス メッセージ内のノードは、ゼロ (0) または複数の時間を無制限に発生することができます。 子プロセスも含まれています。 **フィールド要素** ノード **FieldA** (文字列) と **FieldB** (整数)、親の各インスタンスに対して一度だけ発生します。  
  
 Field1 と FieldA、および Field2 と FieldB がマップされ、次に示す入力インスタンス メッセージのフラグメントがこれらをマップすると仮定した場合、出力インスタンス メッセージから次のフラグメントが生成されます。  
  
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
  
 出現回数、 **SrcLoopingRecord** (3) の入力インスタンス メッセージ内の要素の出現回数を決定する、 **DstLoopingRecord** 出力インスタンス メッセージ内の要素。  
  
 BizTalk マッパーでサポートされていないマッピングでは、複数のループ パスが使用されます。 このようなマッピングでは、送信元スキーマの 2 つ以上のループ レコードに属するフィールドから、送信先スキーマの単一のルーピング レコードに属するフィールドへのマップ操作が行われます。 これは、問題、出力インスタンス メッセージで生成される要素の数を決定する効果的な方法はありません。 複数のループ パスを使用すると、送信先ノードが複数の送信元ループ パスを持つことを示す、マップのコンパイル警告が発生します。 ただし、これは単なる警告であり、最初の送信元ループ パスの繰り返し回数が使用されて、出力インスタンス メッセージに生成される要素の数が決定されます。 ループの動作を使用して明示的に制御を行う、 **ループ** functoid です。  
  
 Microsoft BizTalk Server では、ループ、テーブルドリブン ループと呼ばれる新しい種類が導入されました。 1 つ以上の定数、送信元スキーマからのリンク、または Functoid を組み合わせた入力インスタンス メッセージのデータに基づいて、出力インスタンス メッセージを使用する必要がある場合、テーブルドリブン ループは便利です。 この場合、出力インスタンス メッセージは、異なる定数を組み合わせた入力インスタンス メッセージの単一のレコードのデータに基づいて (または、入力インスタンス メッセージの複数のレコードのデータに基づいて)、複数のレコードを持つことができます。 詳細については、テーブルドリブン ループを使用して、**テーブル ループ**と**テーブル抽出**functoid を参照してください[テーブル ループ functoid とテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)です。  
  
## <a name="see-also"></a>参照  
 [マップ](../core/maps.md)   
 [BizTalk マッパーを使用してマップを作成します。](../core/creating-maps-using-biztalk-mapper.md)
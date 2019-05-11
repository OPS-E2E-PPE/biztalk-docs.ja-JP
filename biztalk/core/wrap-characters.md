---
title: 囲み文字 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7268f46-9bf6-4c76-9b3a-b4ee0e8db997
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb046f40af842bf49834873090b8c3864f37dcd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262081"
---
# <a name="wrap-characters"></a>囲み文字

## <a name="overview"></a>概要
囲み文字は、特別な意味を持つ、データ文字のいずれかの非表示にするためにフィールドのデータの文字をラップするために使用される単一の文字です。 たとえば、次のように、次の特性を持つものとして、フラット ファイル レコードを定義する場合。  
  
- Name = Record1  
  
- [区切り記号]  
  
- 子区切り記号 = コンマ (,)  
  
- 子の順序 = 挿入辞  
  
- エスケープ文字 = 円記号 (\\)  
  
- タグ = RECORD1  
  
- Field1、Field2、および Field3 という 3 つのフィールドでは、各シャープ記号 (#) を使用して、囲み文字として定義されます。  
  
  次のレコードの次のフラット ファイル データが適用されます。  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 データは、次の XML のフラグメントに逆アセンブルします。  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 太字で表示されるデータの文字 field1、field2、および field3 を囲む囲み文字 (#) が削除されていることに注意してください。  
  
 各の元のシーケンスを生成、フィールドのデータの文字の前後に囲み文字を挿入、フラット ファイル アセンブラーでは、レコードの XML バージョンを同等のフラット ファイル レコードに変換する逆の操作を実行するときフラット ファイルの文字。  
  
 定義されているエスケープ文字は、囲み文字と組み合わせて使用できます。 たとえば、Field1 の値が (太字で表示) 次のように変更します。  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 この XML フラグメントをアセンブルすると、指定すると、レコードとフィールドの定義を使用してフラット ファイルの文字の次のシーケンスが生成されます (エスケープされた数値記号文字シーケンスは太字で表示)。  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 BizTalk エディターを使用してフラット ファイル スキーマを作成するときに使用して、スキーマ全体の既定の囲み文字を定義することができます、**既定の囲み文字**と**既定の囲み文字の種類**のプロパティ、**スキーマ**ノード。 次に、この既定の囲み文字またはを使用して、カスタム フィールド固有の囲み文字を使用するか、スキーマの各フィールドを構成、**囲み文字**と**囲み文字の種類**プロパティ、**フィールド要素**または**フィールド属性**フラット ファイル スキーマのノード。
  
## <a name="see-also"></a>参照  
- [特殊文字をフィールド値の一部として解釈させる方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- 文字のプロパティをラップ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    -  既定の囲み文字 (フラット ファイル スキーマのノード プロパティ
    -  既定囲み文字の種類 (フラット ファイル スキーマのノード プロパティ
    -  囲み文字 (フラット ファイル スキーマのノード プロパティ  
    -  囲み文字の種類 (フラット ファイル スキーマのノード プロパティ
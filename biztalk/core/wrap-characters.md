---
title: "囲み文字 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7268f46-9bf6-4c76-9b3a-b4ee0e8db997
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f95ed10811232b15762c31bfc435ac7772a53b3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wrap-characters"></a>囲み文字

## <a name="overview"></a>概要
囲み文字は単一の文字であり、この文字でフィールド内のデータ文字を囲むことにより、データ文字が持つ特殊な意味を無効にします。 たとえば、次のような特性を持つフラット ファイル レコードを定義したとします。  
  
-   名前 = Record1  
  
-   [区切り記号]  
  
-   子区切り記号 = コンマ (,)  
  
-   子の順序 = 挿入辞  
  
-   エスケープ文字 = 円記号 (\\)  
  
-   タグ = RECORD1  
  
-   3 つのフィールド (Field1、Field2、および Field3) は、囲み文字にシャープ記号 (#) を使用します。  
  
 今度は、このレコードに次のようなフラット ファイル データを適用したとします。  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 データは、XML の次のフラグメントに逆アセンブルします。  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 太字のデータ文字 (Field1、Field2、および Field3) の囲み文字 (#) は削除されるので注意してください。  
  
 各の元のシーケンスを生成する、フィールドのデータの文字の前後に囲み文字が挿入、フラット ファイル アセンブラーでは、XML 形式のレコードを同等のフラット ファイル レコードに変換する逆の操作を実行するときにフラット ファイルの文字です。  
  
 定義されたエスケープ文字と囲み文字を同時に使用できます。 たとえば、Field1 の値が次のように変更されると仮定します (太字で表記)。  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 提供されているレコードとフィールドの定義でこの XML フラグメントをアセンブルすると、フラット ファイルの文字が次の順序で生成されます (エスケープのシャープ記号を太字で表記)。  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 BizTalk エディターを使用してフラット ファイル スキーマを作成するときにを使用して、スキーマ全体の既定の囲み文字を定義することができます、**既定の囲み文字**と**既定の囲み文字の種類**のプロパティ、**スキーマ**ノード。 次に、この既定の囲み文字または、独自のカスタム フィールドに固有の囲み文字を使用して、使用するスキーマの各フィールドを構成、**囲み文字**と**囲み文字の種類**プロパティ、**フィールド要素**または**フィールド属性**フラット ファイル スキーマのノードです。
  
## <a name="see-also"></a>参照  
- [フィールドの値の一部として特殊文字を解釈する方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- 文字のプロパティをラップ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:  
    -  既定の囲み文字 (フラット ファイル スキーマのノード プロパティ
    -  既定囲み文字の種類 (フラット ファイル スキーマのノード プロパティ
    -  囲み文字 (フラット ファイル スキーマのノード プロパティ  
    -  囲み文字の種類 (フラット ファイル スキーマのノード プロパティ
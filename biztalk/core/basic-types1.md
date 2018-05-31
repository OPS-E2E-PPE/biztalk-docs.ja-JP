---
title: 基本的な Types1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, data types
- JD Edwards OneWorld adapters, business functions
- .NET Framework, mapping [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], data types
- adapters [JD Edwards OneWorld adapters], .NET Framework
- JD Edwards OneWorld adapters, .NET Framework
- adapters [JD Edwards OneWorld adapters], business functions
ms.assetid: d306ea1b-fb74-4fa3-9681-405252928df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90cda6259567adf5236d0c28e576900d8b25271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231858"
---
# <a name="basic-types"></a>基本型
Microsoft BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld ビジネス関数へのアクセスのみ提供します。 ビジネス関数メタデータは、ビジネス関数インターフェイスをとおして読み取られ、ビジネス関数の一覧および関連するデータ構造の検索に使用されます。 メタデータは、すべてのビジネス関数メソッドのすべてのケースで厳密に型指定されます。  
  
 すべてのビジネス関数メソッドがある同じ呼び出し規約: 派生は、システムは、3 つのパラメーターとデータ構造体へのポインター。 次の表に、ビジネス関数のデータ型がどのように表現されるかを示します。  
  
 **ビジネス関数のデータ型**  
  
|JD Edwards OneWorld のデータ型|Description|WDSL 変換|  
|-----------------------------------|-----------------|---------------------|  
|char|文字の文字列。|xsd:string の 1|  
|int|短整数。|xsd:short|  
|long|長整数。|xsd:short|  
|文字列|参照してください[文字列値の処理](../core/handling-string-values1.md)です。|xsd:string|  
|JDEDATE|日付の特殊な実装。|xsd:date|  
|MATH_NUMERIC|浮動小数点数の特殊な実装 (通貨の値を含む)。|32 の xsd:string|  
|Byte|単一の符号なし文字。|xsd:string の 1|  
  
 次の表に、JD Edwards OneWorld の基本データ型の一覧と、これらのデータ型が Microsoft .NET Framework にどのようにマップされるかを示します。  
  
 **基本データ型と、Microsoft .NET Framework のマップ**  
  
|JD Edwards OneWorld XE|.NET Framework|  
|----------------------------|--------------------|  
|char|文字列|  
|int|Short|  
|long|Short|  
|文字列|文字列|  
|JDEDATE|System.DateTime|  
|MATH_NUMERIC|文字列|  
|Byte|文字列|  
  
> [!NOTE]
>  引数が 1 つだけで、引数の戻り値の型が void である場合、ホルダーはクラスに置き換えられ、出力部分は戻り値になります。 例:  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 次はメソッド シグネチャの例です。  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a>文字数制限のある文字列  
 JD Edwards OneWorld では、一部の文字列に文字数制限があります。 文字数制限を超えると、エラーになります。 文字列の文字数の制限を確認するには、Microsoft アダプター ウィザードを使用できます。  
  
## <a name="see-also"></a>参照  
 [MATH_NUMERIC 型の使用](../core/using-the-math-numeric-type2.md)   
 [文字列値の処理](../core/handling-string-values1.md)   
 [付録 a: データ型](../core/appendix-a-data-types.md)
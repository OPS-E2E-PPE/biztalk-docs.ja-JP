---
title: 基本的な Types1 |Microsoft Docs
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
ms.openlocfilehash: 1c1cfd31eacd56c19e5b1daf2288be098d9448c3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529141"
---
# <a name="basic-types"></a>基本的な型
Microsoft の BizTalk Adapter for JD Edwards OneWorld では、JD Edwards OneWorld ビジネス関数にのみアクセスを提供します。 ビジネス関数メタデータは読み取り専用ビジネス関数のインターフェイスを使用してビジネス関数の一覧を検索するために使用し、関連するデータ構造。 メタデータはすべてのビジネス関数メソッドのすべてのケースで厳密に型指定します。  
  
 すべてのビジネス関数メソッドと同じ呼び出し規約がある: システムから派生している 3 つのパラメーターとデータ構造体へのポインター。 次の表では、ビジネス関数のデータ型の表現方法を示します。  
  
 **ビジネス関数のデータ型**  
  
|JD Edwards OneWorld のデータ型|説明|WDSL 変換|  
|-----------------------------------|-----------------|---------------------|  
|char|文字の文字列。|xsd:string の 1|  
|ssNoversion|短整数。|xsd:short|  
|long|長整数。|xsd:short|  
|String|参照してください[文字列値を処理する](../core/handling-string-values1.md)します。|xsd:string|  
|JDEDATE|日付の特殊な実装。|xsd:date|  
|MATH_NUMERIC|浮動小数点数、通貨値などの特殊な実装。|32 の xsd:string|  
|バイト|1 つの符号なし文字。|xsd:string の 1|  
  
 次の表には、JD Edwards OneWorld と Microsoft .NET Framework への割り当て方法の基本型の一覧が含まれています。  
  
 **基本的な型および Microsoft .NET Framework への割り当て方法**  
  
|JD Edwards OneWorld XE|.NET Framework|  
|----------------------------|--------------------|  
|char|String|  
|ssNoversion|Short|  
|long|Short|  
|String|String|  
|JDEDATE|System.DateTime|  
|MATH_NUMERIC|String|  
|バイト|String|  
  
> [!NOTE]
>  1 つの引数があるし、void 戻り値の引数では、クラスによって所有者が置き換えられ、出力の部分が戻り値になります。 以下に例を示します。  
  
```  
org.apache.axis.holders.DateHolder becomes a java.util.Date.   
```  
  
 メソッドのシグネチャの例を次に示します。  
  
```  
void testDate1(org.apache.axis.holders.DateHolder date1  
        org.apache.axis.holders.DateHolder date2);  
  
java.util.Date testDate2(java.util.Date date);  
```  
  
## <a name="character-limited-strings"></a>文字列の文字制限  
 JD Edwards OneWorld では、一部の文字列は文字は限定されています。 任意の余分な文字には、エラーが発生します。 文字列の文字の制限を表示するには、Microsoft アダプター ウィザードを使用することができます。  
  
## <a name="see-also"></a>参照  
 [MATH_NUMERIC 型の使用](../core/using-the-math-numeric-type2.md)   
 [文字列値の処理](../core/handling-string-values1.md)   
 [付録 a:データ型](../core/appendix-a-data-types.md)
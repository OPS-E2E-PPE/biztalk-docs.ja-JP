---
title: MATH_NUMERIC 型 1 を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards EnterpriseOne adapters], currency
- JD Edwards EnterpriseOne adapters, exponents
- adapters [JD Edwards EnterpriseOne adapters], exponents
- MATH_NUMERIC type
- currency, values [JD Edwards EnterpriseOne adapters]
- JD Edwards EnterpriseOne adapters, currency
- exponents, values [JD Edwards EnterpriseOne adapters]
ms.assetid: 2a302216-f0a6-4afb-8f7d-bb1475ea1c57
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4a5df2d15f489d52c8e3d6dfc575f9e644c646
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288514"
---
# <a name="using-the-mathnumeric-type"></a>MATH_NUMERIC 型の使用
ここでは、MATH_NUMERIC 型および指数の処理方法、最大桁数、および最大 10 進桁数の詳細について説明します。 また、次のものに関する説明も含まれています。  
  
-   指数  
  
-   無効な値  
  
-   演算の精度  
  
-   Currency  
  
 MATH_NUMERIC 型は数値文字列型です。 この型を使用するには、次の形式のパラメーター値を入力します。  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 場所  
  
 `<OptionalSign>`指定できます`+`または`-`です。 `+`既定値です。  
  
 `<IntegerAndFractionalPart>` は最大 32 桁で、小数点記号は含みません。 小数点の記号はロケール固有 JD Edwards EnterpriseOne のインストールになど、通常はピリオド (.) またはコンマ (,) です。 値はすべて整数、すべて小数、または整数と小数の組み合わせのいずれでもかまいませんが、32 桁を超えることはできません。  
  
 `<OptionalExponentPart>` は次の記述と同じです。  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 場所  
  
 `<OptionalSign>`指定できます`+`または`-`です。 `+`既定値です。  
  
 `<ExponentDigits>` は最大 2 桁です。 指定できる値は、-63 ～ 63 です (0 は除く)。  
  
## <a name="valid-values"></a>有効な値  
 例として**有効**MATH_NUMERIC 値。  
  
-   123.045  
  
-   4089 (3 桁ごとのコンマがないことに注意してください)  
  
-   -9084  
  
-   -230.75  
  
-   0.010503  
  
-   1.023e-10 は、0.0000000001023 と同じです  
  
-   0.097e5 または 0.097e+5 は、9700 と同じです  
  
-   1.0e-32 (0.00000000000000000000000000000001 と同じ。この値が有効なのは、整数 "0" が無視され、小数点以下の桁数が 32 であるためです)  
  
## <a name="invalid-values"></a>無効な値  
 無効な値は値の種類に依存します。 小さすぎる小数部はゼロと解釈されます (すべての有効桁が失われます)。 有効桁が多すぎる整数は、予期しない結果になります。 この場合、必ずしもエラー状態が発生するとは限りません。 指数が長すぎるか短すぎても、無効な値が返されます。  
  
 例として**無効な**MATH_NUMERIC 値。  
  
-   1034.00000000000000000000000000001023 - 有効桁が多すぎます  
  
-   1.023e-64 - 指数部が小さすぎます  
  
-   0.00317e64 - 指数部が大きすぎます  
  
 符合と小数点記号以外に数字以外の文字が含まれていると、無効な値になります。  
  
## <a name="exponents"></a>指数  
 指数は、値を入力し、便宜上 JD Edwards EnterpriseOne MATH_NUMERIC によって提供されます。 ただし、ほとんどの値は指数なしで返ります (32 有効桁がすべて示されます)。  
  
## <a name="precision-for-operations"></a>演算の精度  
 演算によって精度が失われると、丸めが行われます。 例:  
  
 1.9e-31/10.0 = 0.00000000000000000000000000000002 です。  
  
 1.9e-31/100.0 = 0.00000000000000000000000000000000  
  
 それ以外では、非常に大きい正の値どうしを乗算した場合に、予期しない結果が発生します。 1.01e32 * 2.053e32 信頼性の高い結果を生成しませんし、エラーは発生しません。 実際に使用する場合には、通常、これらの範囲を超えることはありません。  
  
## <a name="currency"></a>Currency  
 JD Edwards EnterpriseOne のビジネス関数が通貨値を予期している場合、常に 4 文字の通貨コード用の別のパラメーターがあります。 JD Edwards EnterpriseOne システム用に構成された既定値とは異なる通貨を使用しない限り、このコードを渡す必要はありません。  
  
## <a name="see-also"></a>参照  
 [付録 b: データ型](../core/appendix-b-data-types.md)
---
title: MATH_NUMERIC 型 2 を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exponents, JD Edwards OneWorld adapters
- currency, JD Edwards OneWorld adapters
- MATH_NUMERIC type
- adapters [JD Edwards OneWorld adapters], currency
ms.assetid: 14d04576-0028-4af4-84bd-92c4ca492126
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13de687f158bc18f4fa6a036ab239a25774d02ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998907"
---
# <a name="using-the-mathnumeric-type"></a>MATH_NUMERIC 型の使用
ここでは、MATH_NUMERIC 型および指数の処理方法、最大桁数、および最大 10 進桁数の詳細について説明します。 次の項目についても説明します。  
  
- 指数  
  
- 無効な値  
  
- 演算の精度  
  
- 通貨  
  
  MATH_NUMERIC 型は数値文字列型です。 この型を使用するには、次の形式のパラメーター値を入力します。  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
```  
  
 場所  
  
- `<OptionalSign>` `+`または`-`します。 `+` 既定値です。  
  
- `<IntegerAndFractionalPart>` は最大 32 桁で、小数点記号は含みません。 この小数点の記号は JD Edwards OneWorld インストールのロケールに固有であり、通常はピリオド (.) またはコンマ (,) となります。 値はすべて整数、すべて小数、または整数と小数の組み合わせのいずれでもかまいませんが、32 桁を超えることはできません。  
  
- `<OptionalExponentPart>` は次の記述と同じです。  
  
  ```  
  'e' <OptionalSign><ExponentDigits>  
  ```  
  
  場所  
  
- `<OptionalSign>` `+`またはします。 `+` 既定値です。  
  
- `<ExponentDigits>` は最大 2 桁です。 指定できる値は、-63 ～ 63 です (0 は除く)。  
  
## <a name="valid-values"></a>有効な値  
 有効な MATH_NUMERIC 値の例は次のとおりです。  
  
-   123.045  
  
-   4089 (3 桁ごとのコンマがないことに注意してください)  
  
-   -9084  
  
-   -230.75  
  
-   0.010503  
  
-   1.023e-10 は、0.0000000001023 と同じです  
  
-   0.097e5 または 0.097e+5 は、9700 と同じです  
  
-   1.0e-32 (0.00000000000000000000000000000001 に等しい)  
  
     (この値が有効なのは、整数 '0' が無視され、小数点以下の桁数が 32 であるためです。)  
  
## <a name="invalid-values"></a>無効な値  
 無効な値は値の種類に依存します。 小さすぎる小数部はゼロと解釈されます (すべての有効桁が失われます)。 有効桁が多すぎる整数は、予期しない結果になります。 こ場合、必ずしもエラー状態が発生するとは限りません。  
  
 指数が大きすぎるか小さは、無効な値として返します。  
  
 無効な MATH_NUMERIC 値の例は次のとおりです。  
  
- 1034.00000000000000000000000000001023 - 有効桁が多すぎます  
  
- 1.023e-64 - 指数部が小さすぎます  
  
- 0.00317e64 - 指数部が大きすぎます  
  
  符合と小数点記号以外に数字以外の文字が含まれていると、無効な値になります。  
  
## <a name="exponents"></a>指数  
 値を入力しやすくするために、JD Edwards OneWorld MATH_NUMERIC により、指数が指定されます。 ただし、ほとんどの値は指数なしで返ります (32 有効桁がすべて示されます)。  
  
## <a name="precision-for-operations"></a>演算の精度  
 演算によって精度が失われると、丸めが行われます。 以下に例を示します。  
  
 1.9e-31 / 10.0 = 0.00000000000000000000000000000002  
  
 1.9e-31/100.0 = 0.00000000000000000000000000000000  
  
 それ以外では、非常に大きい正の値どうしを乗算した場合に、予期しない結果が発生します。  
  
 1.01e32 * 2.053e32 信頼性の高い結果を生成しないと、エラーは発生しません。  
  
 実際に使用する場合には、通常、これらの範囲を超えることはありません。  
  
## <a name="currency"></a>通貨  
 JD Edwards OneWorld のビジネス関数が通貨値を予期している場合、常に 4 文字の通貨コード用の別のパラメーターがあります。 JD Edwards OneWorld システム用に構成された既定値とは異なる通貨を使用しない限り、このコードを渡す必要はありません。  
  
## <a name="see-also"></a>参照  
 [付録 A: データ型](../core/appendix-a-data-types.md)
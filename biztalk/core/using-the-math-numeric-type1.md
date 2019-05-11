---
title: MATH_NUMERIC 型 1 を使用して |Microsoft Docs
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
ms.openlocfilehash: 519605c89cc808c91e1045c191dc01ec46739ae8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396007"
---
# <a name="using-the-mathnumeric-type"></a>MATH_NUMERIC 型の使用
このトピックでは、MATH_NUMERIC 型および指数の処理方法の詳細、桁の数字の最大数および 10 進数字の最大数について説明します。 詳細についてでも含まれます。  
  
- 指数  
  
- 無効な値  
  
- 操作の有効桁数  
  
- 通貨  
  
  MATH_NUMERIC 型は、数値の文字列型です。 これを使用するには、次の形式のパラメーター値を入力します。  
  
```  
<OptionalSign><IntegerAndFractionalPart><OptionalExponentPart>  
  
```  
  
 場所  
  
 `<OptionalSign>` には、`+` または `-` を指定できます。 `+` 既定値です。  
  
 `<IntegerAndFractionalPart>` 最大 32 桁で小数点の記号を含みません。 小数点の記号はロケール固有 JD Edwards EnterpriseOne のインストールに、通常はピリオド (.) またはコンマ (,) です。 数字の中にすべての整数、すべて小数、または一部整数および一部の分数を使用できますが、32 を超えることはできません。  
  
 `<OptionalExponentPart>` 等価です。  
  
```  
'e' <OptionalSign><ExponentDigits>  
```  
  
 場所  
  
 `<OptionalSign>` には、`+` または `-` を指定できます。 `+` 既定値です。  
  
 `<ExponentDigits>` 2 桁の数字は最大です。 63 ~ 0 を除く-63 の値が許可されます。  
  
## <a name="valid-values"></a>有効な値  
 例の**有効**MATH_NUMERIC 値。  
  
-   123.045  
  
-   4089 (数千にコンマがない場合に注意してください)  
  
-   -9084  
  
-   -230.75  
  
-   0.010503  
  
-   1.023e-10 では、これは 0.0000000001023 に相当  
  
-   0.097 e 5 または 0.097 e + 5 は、9700 と同じです。  
  
-   数が 1.0 e-32、0.00000000000000000000000000000001 と同じになります (この場合、整数 '0' は無視されます、ため、これは有効な 32 小数点以下の桁数)。  
  
## <a name="invalid-values"></a>無効な値  
 無効な値は、値の種類によって異なります。 小さすぎる小数部は 0 として解釈されます (すべての有効桁数が失われます)。 有効桁が多すぎますが整数には、予期しない結果をによりします。 JD Edwards EnterpriseOne 常には発生しませんエラー条件は、この場合。 指数が大きすぎるか小さすぎるは、無効な値も返します。  
  
 例の**無効な**MATH_NUMERIC 値。  
  
- 1034.00000000000000000000000000001023 - 有効桁が多すぎます  
  
- 1.023e-64 - 指数部が小さすぎます  
  
- 0.00317 e 64 - 指数部が大きすぎます  
  
  記号と小数点の記号の適切なもの以外の数字以外の文字と、値が無効です。  
  
## <a name="exponents"></a>指数  
 指数は、値を入力するため便利なように、JD Edwards EnterpriseOne MATH_NUMERIC によって提供されます。 ただし、ほとんどの値は指数せず (すべて 32 桁で表示される) に戻ります。  
  
## <a name="precision-for-operations"></a>操作の有効桁数  
 有効桁数が失われる演算によって、丸め処理に発生します。 以下に例を示します。  
  
 1.9e-31/10.0 = 0.00000000000000000000000000000002 します。  
  
 1.9e-31 / 100.0 = 0.00000000000000000000000000000000  
  
 その他の場合は、予期しない結果が発生をもう 1 つ非常に大きい正の値を乗算する場合。 1.01e32 * 2.053e32 信頼性の高い結果を生成しないと、エラーは発生しません。 ほとんどのビジネス シナリオでは、これらの範囲が超過していません。  
  
## <a name="currency"></a>通貨  
 JD Edwards EnterpriseOne のビジネス関数には、通貨の値が必要ですが、ときに、ビジネス関数は常に 4 文字の通貨コード用の個別のパラメーターを持ちます。 JD Edwards EnterpriseOne システム用に構成された既定値以外の通貨を使用している場合を除き、このコードに渡す必要はありません。  
  
## <a name="see-also"></a>参照  
 [付録 b:データ型](../core/appendix-b-data-types.md)
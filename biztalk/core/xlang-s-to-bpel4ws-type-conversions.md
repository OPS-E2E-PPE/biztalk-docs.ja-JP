---
title: Xlang-s から BPEL4WS への変換の入力 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XLANG/s
- XLANG/s, warning
- XLANG/s, BPEL4WS
- XLANG/s, converting
ms.assetid: a35d4dba-9344-43c8-86e6-a373a4452579
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a184251428568305c553b63bbb164785758aca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244062"
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a>Xlang-s BPEL4WS 型への変換から
次の表では、さまざまな xlang/s 構成要素と BPEL4WS 構成要素の間の変換について説明します。  
  
> [!CAUTION]
>  XPath 1.1 は、指数関数的または double 形式の数字をサポートしていません。 Xlang/s オーケストレーションにおけるこれらの形式のリテラル値をエクスポートする BPEL4WS、%f 形式と精度の損失を使用してなる可能性があります。  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a>リテラル (リテラルが式の一部である場合)  
  
|XLANG/秒|BPEL4WS|  
|--------------|-------------|  
|文字の文字列|XPath 文字列|  
|整数、実数|XPath 数値|  
|ブール値"true"、"false"|XPath true() 関数、false() 関数|  
  
## <a name="literals-standalone-assignment"></a>リテラル (スタンドアロン代入)  
  
|XLANG/秒|BPEL4WS|  
|--------------|-------------|  
|リテラル定数|XSD に相当|  
  
## <a name="variables"></a>変数:  
  
|XLANG/秒|BPEL4WS|  
|--------------|-------------|  
|変数参照|bpws:getContainerData(%varName%, part, %locationPath%)|  
|メッセージのリファレンス (.NET 型)|bpws:getContainerData(%msgName%, part, %locationPath%)|  
|メッセージ部分の参照|bpws:getContainerData(%msgName%, %locationPath%)|  
|識別フィールドの参照|bpws:getContainerData(%msgName%, %partName%, %locationPath%)|  
|メッセージ データ プロパティの参照|bpws:getContainerProperty(%msgName%, %propertyQName%)|  
  
## <a name="operators"></a>演算子  
  
|XLANG/秒|BPEL4WS|  
|--------------|-------------|  
|単項 +|無視|  
|単項演算子-|XPath 単項演算子-|  
|単項!|XPath not() 関数|  
|バイナリ & &、&#124;&#124;|XPath"and"、"or"演算子|  
|バイナリ = =、! =、< =、<>、=、>|XPath '='、'! =', '<=', '<', '>=', '>' operators|  
|バイナリ +、-、*、両方の整数オペランド %|XPath '+'、'-'、' *'、"mod"演算子|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a>BPEL4WS で使用できない xlang/s 構成要素  
  
-   メッセージ コンテキスト プロパティの参照  
  
-   サービス プロパティの参照  
  
-   ポート プロパティの参照  
  
-   サービス リンク プロパティの参照  
  
-   単項演算子 – 整数型以外の種類  
  
-   単項 ~  
  
-   キャスト演算子  
  
-   バイナリ/整数オペランドを  
  
-   バイナリ +、-、*、%、/整数以外のオペランドを  
  
-   バイナリ < =、<>、=、> の非文字列オペランド  
  
-   ビット処理演算子 &、^、&#124;  
  
-   シフト演算子 <<>>,  
  
-   Checked 式  
  
-   Intrinsic 式  
  
-   前と後のインクリメントおよびデクリメント + +、-  
  
-   オブジェクト呼び出し (で、せず out や ref パラメーター)  
  
-   'new' 演算子
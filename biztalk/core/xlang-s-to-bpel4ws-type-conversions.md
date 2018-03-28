---
title: XLANG の BPEL4WS への変換の入力 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02412b86b8649b73cadb4715793f085682a1de74
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="xlang-s-to-bpel4ws-type-conversions"></a>BPEL4WS の型変換に XLANG s
次の表は、さまざまな XLANG/s 構成要素と BPEL4WS 構成要素間の変換の詳細を示しています。  
  
> [!CAUTION]
>  XPath 1.1 は、指数形式または double 形式の数値をサポートしていません。 XLANG/s オーケストレーションにおけるこれらの形式のリテラル値は、%f 形式を使用して BPEL4WS にエクスポートされますが、精度が低下する可能性があります。  
  
## <a name="literals-if-the-literal-is-part-of-an-expression"></a>リテラル (リテラルが式の一部である場合)  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|文字列、文字|XPath 文字列|  
|整数、実数|XPath 数値|  
|ブール値 "true"、"false"|XPath true() 関数、false() 関数|  
  
## <a name="literals-standalone-assignment"></a>リテラル (スタンドアロン代入)  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|リテラル定数|XSD に相当|  
  
## <a name="variables"></a>変数  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|変数の参照|bpws:getContainerData(%varName%,  part, %locationPath%)|  
|メッセージの参照 (.NET 型)|bpws:getContainerData(%msgName%, part, %locationPath%)|  
|メッセージ部分の参照|bpws:getContainerData(%msgName%, %locationPath%)|  
|識別フィールドの参照|bpws:getContainerData(%msgName%, %partName%, %locationPath%)|  
|メッセージ データ プロパティの参照|bpws:getContainerProperty(%msgName%, %propertyQName%)|  
  
## <a name="operators"></a>演算子  
  
|XLANG/s|BPEL4WS|  
|--------------|-------------|  
|単項演算子 +|無視|  
|単項 -|XPath 単項演算子 -|  
|単項演算子 !|XPath not() 関数|  
|バイナリ & &、&#124; と #124 文字です。|XPath "and" 演算子、"or" 演算子|  
|バイナリ ==、!=、<=、<、>=、>|XPath "="、"! ='、' < ='、' <'、' > ='、' >' 演算子|  
|両方の整数オペランドのバイナリ +、-、*、%|XPath "+"、"-"、"*"、"mod" 演算子|  
  
## <a name="xlangs-constructs-that-are-disallowed-in-bpel4ws"></a>BPEL4WS で使用できない XLANG/s 構成要素  
  
-   メッセージ コンテキスト プロパティの参照  
  
-   サービス プロパティの参照  
  
-   部分プロパティの参照  
  
-   サービス リンク プロパティの参照  
  
-   整数以外の型の単項演算子 –  
  
-   単項演算子 ~  
  
-   キャスト演算子  
  
-   整数オペランドのバイナリ /  
  
-   整数以外のオペランドのバイナリ +、-、*、%  
  
-   文字列型以外のオペランドのバイナリ <=、<、>=、>  
  
-   ビット処理演算子 &、^、&#124;文字です。  
  
-   シフト演算子 <<、>>  
  
-   checked 式  
  
-   intrinsic 式  
  
-   前置および後置インクリメントおよびデクリメント ++、--  
  
-   オブジェクト呼び出し (out や ref のパラメーターの有無にかかわらず)  
  
-   "new" 演算子
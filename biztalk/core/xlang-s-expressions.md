---
title: Xlang-s 式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a477ee2c-7fd7-43bd-a194-0d68d79613fc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe22d2ed03f213e8240aba867fff545a2e488b73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394700"
---
# <a name="xlang-s-expressions"></a>Xlang-s 式
式は、演算子とオペランドのシーケンスです。 このトピックでは、xlang/s が各種の式に対してサポートする構文を示しています。  
  
## <a name="basic-expressions"></a>基本的な式  
 次のコードは、基本式の構文を示しています。  
  
```  
primary-expression:  
     literal  
     enum-constant  
     variable-reference  
     invocation-expression  
     message-field-reference  
     message-property-reference  
     message-part-property-reference  
     correlation-property-reference  
     port-property-reference  
     service-property-reference  
     service-link-property-reference  
     message-part-reference  
     parenthesized-expression  
     object-reference  
     checked-expression  
     unchecked-expression  
     intrinsic-expression  
     xpath-expression  
     exists-expression  
enum-constant:  
     enum-type-name.enum-member  
enum-type-name:  
     type-name  
enum-member:  
     identifier  
parenthesized-expression:  
     (expression)  
checked-expression:  
     checked(expression)  
     checked(statement)  
unchecked-expression:  
     unchecked(expression)  
     unchecked(statement)  
unary-expression:  
     primary-expression  
     + unary-expression  
     - unary-expression  
     ! unary-expression  
     ~ unary-expression  
     cast-expression  
     property-reference exists  
cast-expression:  
     (type-name) unary-expression  
multiplicative-expression:  
     exists-expression  
     multiplicative-expression * unary-expression  
     multiplicative-expression / unary-expression  
     multiplicative-expression % unary-expression  
additive-expression:  
     multiplicative-expression  
     additive-expression + multiplicative-expression  
     additive-expression – multiplicative-expression  
shift-expression:  
     additive-expression  
     shift-expression << additive-expression  
     shift-expression >> additive-expression  
relational-expression:  
     shift-expression  
     relational-expression < shift-expression  
     relational-expression > shift-expression  
     relational-expression <= shift-expression  
     relational-expression >= shift-expression  
equality-expression:  
     relational-expression  
     equality-expression == relational-expression  
     equality-expression != relational-expression  
and-expression:  
     equality-expression  
     and-expression & equality-expression  
exclusive-or-expression:  
     and-expression  
     exclusive-or-expression ^ and-expression  
inclusive-or-expression:  
     exclusive-or-expression  
     inclusive-or-expression | exclusive-or-expression  
conditional-and-expression:  
     inclusive-or-expression  
     conditional-and-expression && inclusive-or-expression  
conditional-or-expression:  
     conditional-and-expression  
     conditional-or-expression || conditional-and-expression  
conditional-expression:  
     conditional-or-expression  
exists-expression:  
     property-reference exists  
     property-reference exists message-reference  
     property-reference exists message-part-reference  
xpath-expression:  
     xpath(message-part-reference, string-expression)  
     xpath(string-expression)  
intrinsic-expression:  
     succeeded(identifier)  
assignment-expression:  
     variable-assignment  
     object-assignment  
variable-assignment:  
     variable-reference = conditional-expression  
object-assignment:  
     object-reference = object-creation-expression  
     object-reference = conditional-expression  
     object-reference = invocation-expression  
object-creation-expression:  
     new class-name(method-argument-list) //method-argument-list is optional  
     new class-name[integer-expression]  
invocation-expression:  
     object-reference.method-name(method-argument-list) //method-argument-list is optional  
```  
  
## <a name="service-and-method-arguments"></a>サービスおよびメソッドの引数  
 次のコードは、サービスおよびメソッドの引数の構文を示しています。  
  
```  
service-argument-list:  
     service-argument  
     service-argument-list, service-argument  
service-argument:  
     param-direction message-reference //param-direction is optional  
     param-direction variable-reference //param-direction is optional  
     param-direction object-name //param-direction is optional  
     correlation-reference  
     service-link-name  
     port-name  
     conditional-expression  
method-argument-list:  
     method-argument  
     method-argument-list, method-argument  
method-argument:  
     message-reference  
     param-direction variable-reference //param-direction is optional  
     param-direction object-name //param-direction is optional  
     conditional-expression  
     param-direction message-part-reference //param-direction is optional  
     param-direction message-field-reference //param-direction is optional  
```  
  
## <a name="top-level-expressions"></a>最上位レベルの式  
 次のコードは、最上位レベルの式の構文を示しています。  
  
```  
expression:  
     conditional-expression  
     assignment-expression  
     invocation-expression  
constant-expression:  
     conditional-expression  
boolean-expression:  
     conditional-expression  
integer-expression:  
     conditional-expression  
date-time-expression:  
     conditional-expression  
time-span--expression:  
     conditional-expression  
string-expression:  
     conditional-expression  
```  
  
## <a name="see-also"></a>参照  
 [Xlang-s データ型](../core/xlang-s-data-types.md)   
 [Xlang-s ステートメント](../core/xlang-s-statements.md)   
 [Xlang-s の変数および演算子](../core/xlang-s-variables-and-operators.md)   
 [Xlang-s の予約語](../core/xlang-s-reserved-words.md)   
 [XLANG-s から BPEL4WS への種類の変換](../core/xlang-s-to-bpel4ws-type-conversions.md)
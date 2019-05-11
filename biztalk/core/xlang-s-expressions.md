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
# <a name="xlang-s-expressions"></a><span data-ttu-id="62802-102">Xlang-s 式</span><span class="sxs-lookup"><span data-stu-id="62802-102">XLANG-s Expressions</span></span>
<span data-ttu-id="62802-103">式は、演算子とオペランドのシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="62802-103">An expression is a sequence of operators and operands.</span></span> <span data-ttu-id="62802-104">このトピックでは、xlang/s が各種の式に対してサポートする構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="62802-104">This topic illustrates the syntax that XLANG/s supports for various expressions.</span></span>  
  
## <a name="basic-expressions"></a><span data-ttu-id="62802-105">基本的な式</span><span class="sxs-lookup"><span data-stu-id="62802-105">Basic Expressions</span></span>  
 <span data-ttu-id="62802-106">次のコードは、基本式の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="62802-106">The following code shows the syntax for basic expressions:</span></span>  
  
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
  
## <a name="service-and-method-arguments"></a><span data-ttu-id="62802-107">サービスおよびメソッドの引数</span><span class="sxs-lookup"><span data-stu-id="62802-107">Service and Method Arguments</span></span>  
 <span data-ttu-id="62802-108">次のコードは、サービスおよびメソッドの引数の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="62802-108">The following code shows the syntax for service and method arguments:</span></span>  
  
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
  
## <a name="top-level-expressions"></a><span data-ttu-id="62802-109">最上位レベルの式</span><span class="sxs-lookup"><span data-stu-id="62802-109">Top-Level Expressions</span></span>  
 <span data-ttu-id="62802-110">次のコードは、最上位レベルの式の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="62802-110">The following code shows the syntax for top-level expressions:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62802-111">参照</span><span class="sxs-lookup"><span data-stu-id="62802-111">See Also</span></span>  
 <span data-ttu-id="62802-112">[Xlang-s データ型](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="62802-112">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="62802-113">[Xlang-s ステートメント](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="62802-113">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="62802-114">[Xlang-s の変数および演算子](../core/xlang-s-variables-and-operators.md) </span><span class="sxs-lookup"><span data-stu-id="62802-114">[XLANG-s Variables and Operators](../core/xlang-s-variables-and-operators.md) </span></span>  
 <span data-ttu-id="62802-115">[Xlang-s の予約語](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="62802-115">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="62802-116">XLANG-s から BPEL4WS への種類の変換</span><span class="sxs-lookup"><span data-stu-id="62802-116">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)
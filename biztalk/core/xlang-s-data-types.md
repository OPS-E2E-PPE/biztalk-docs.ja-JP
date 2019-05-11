---
title: Xlang-s データ型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- Orchestration Designer, managing data
- Orchestration Designer, variables
- orchestrations, variables
- Orchestration Designer, expressions
ms.assetid: 5b08aaa6-1533-4bac-a76d-f9162e39bf4f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cc0d20336169ec1198c21dcbe932ff5a823a568
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394712"
---
# <a name="xlang-s-data-types"></a><span data-ttu-id="1f102-102">Xlang-s データ型</span><span class="sxs-lookup"><span data-stu-id="1f102-102">XLANG-s Data Types</span></span>
<span data-ttu-id="1f102-103">XLANG/秒の反射効果が標準値の型を定義します。 そのC#の対応します。</span><span class="sxs-lookup"><span data-stu-id="1f102-103">XLANG/s defines standard value types that are reflections of their C# counterparts.</span></span> <span data-ttu-id="1f102-104">以下の**ブール**、**バイト**、 **Char**、 **Decimal**、**二重**、 **Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、 **UInt16**、 **UInt32**、および**UInt64**します。</span><span class="sxs-lookup"><span data-stu-id="1f102-104">These include **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**.</span></span> <span data-ttu-id="1f102-105">XLANG/秒では、1 次元の配列をサポートしていますが、配列リテラルがサポートされません。</span><span class="sxs-lookup"><span data-stu-id="1f102-105">XLANG/s supports single-dimensional arrays, but does not support array literals.</span></span>  
  
 <span data-ttu-id="1f102-106">XLANG/秒では、メッセージの処理の豊富なサポートもあります。</span><span class="sxs-lookup"><span data-stu-id="1f102-106">XLANG/s also has rich support for message handling.</span></span> <span data-ttu-id="1f102-107">メッセージは、スキーマ、.NET クラス、Web メッセージの種類 (WSDL)、または複雑なメッセージの種類に基づいて作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f102-107">Messages can be based on schemas, .NET classes, Web message types (WSDL), or complex message types.</span></span> <span data-ttu-id="1f102-108">XLANG/秒には、次の複合データ型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1f102-108">XLANG/s supports the following complex data types:</span></span>  
  
-   <span data-ttu-id="1f102-109">**メッセージの種類。**</span><span class="sxs-lookup"><span data-stu-id="1f102-109">**messagetype.**</span></span> <span data-ttu-id="1f102-110">このデータ型は、データ要素および XSD ベースのメッセージの組み合わせとして定義されているマルチパート メッセージの種類およびメソッド メッセージの種類 (クラスまたはインターフェイスのメソッドのシグネチャの形式に一致するメッセージ) を定義します。</span><span class="sxs-lookup"><span data-stu-id="1f102-110">This data type defines multipart message types which are defined as combinations of data elements and XSD-based messages and Method-Message types (messages that match the signature format of a method of a class or interface).</span></span>  
  
-   <span data-ttu-id="1f102-111">**porttype。**</span><span class="sxs-lookup"><span data-stu-id="1f102-111">**porttype.**</span></span> <span data-ttu-id="1f102-112">このデータ型は、その種類のポートのインスタンスが対処できるポート operations のコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f102-112">This data type defines a collection of port operations that a port instance of that type can act upon.</span></span>  
  
-   <span data-ttu-id="1f102-113">**correlationsettype.**</span><span class="sxs-lookup"><span data-stu-id="1f102-113">**correlationsettype.**</span></span> <span data-ttu-id="1f102-114">このデータ型は、関連付けセット変数の任意のインスタンスで使用されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f102-114">This data type defines the data that will be used in any instance of a correlation set variable.</span></span> <span data-ttu-id="1f102-115">関連付けセットのデータは、システムを移動するメッセージがビジネス プロセスの適切な実行中のインスタンスにディスパッチされることを確認するためのルーティング メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="1f102-115">Correlation set data is the routing mechanism used to ensure that messages moving through the system are dispatched to the appropriate running instance of a business process.</span></span> <span data-ttu-id="1f102-116">たとえば、注文書を処理するため、取引先に送信する場合、その発注に対応するビジネス プロセスの適切なインスタンスが、戻り値で呼び出される命令型は。</span><span class="sxs-lookup"><span data-stu-id="1f102-116">For example, if a purchase order is sent to a trading partner for processing, it is imperative that the correct instance of the business process corresponding to that purchase order be invoked on its return.</span></span>  
  
-   <span data-ttu-id="1f102-117">**servicelinktype.**</span><span class="sxs-lookup"><span data-stu-id="1f102-117">**servicelinktype.**</span></span> <span data-ttu-id="1f102-118">このデータ型のセットを定義する**porttype**ビジネス プロセスで使用されるポートの論理的に一貫したグループを形成する値。</span><span class="sxs-lookup"><span data-stu-id="1f102-118">This data type defines the set of **porttype** values that form a logically consistent group of ports used in a business process.</span></span> <span data-ttu-id="1f102-119">サービス リンクの使用は、実行時にポートのグループに動的に割り当てることができる強力なメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="1f102-119">The use of service links is a powerful mechanism that allows dynamic assignment to a group of ports at run time.</span></span> <span data-ttu-id="1f102-120">これにより、複数の取引先パートナーとの対話に使用できる 1 つのビジネス プロセスを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="1f102-120">This allows you to define a single business process that can be used to interact with multiple trading partners.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f102-121">参照</span><span class="sxs-lookup"><span data-stu-id="1f102-121">See Also</span></span>  
 <span data-ttu-id="1f102-122">[Xlang-s ステートメント](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="1f102-122">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="1f102-123">[Xlang-s の変数および演算子](../core/xlang-s-variables-and-operators.md) </span><span class="sxs-lookup"><span data-stu-id="1f102-123">[XLANG-s Variables and Operators](../core/xlang-s-variables-and-operators.md) </span></span>  
 <span data-ttu-id="1f102-124">[Xlang-s 式](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="1f102-124">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="1f102-125">[Xlang-s の予約語](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="1f102-125">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="1f102-126">XLANG-s から BPEL4WS への種類の変換</span><span class="sxs-lookup"><span data-stu-id="1f102-126">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)
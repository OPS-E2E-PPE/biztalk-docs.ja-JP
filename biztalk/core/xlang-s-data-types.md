---
title: XLANG のデータ タイプ |Microsoft ドキュメント
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
ms.openlocfilehash: c21ed77c5fdd56485514d17ed75e921c63a56212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290442"
---
# <a name="xlang-s-data-types"></a><span data-ttu-id="c8362-102">XLANG のデータ型</span><span class="sxs-lookup"><span data-stu-id="c8362-102">XLANG-s Data Types</span></span>
<span data-ttu-id="c8362-103">XLANG/s は、C# の対応する型のリフレクションである、値の標準型を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8362-103">XLANG/s defines standard value types that are reflections of their C# counterparts.</span></span> <span data-ttu-id="c8362-104">これらが含まれます**ブール**、**バイト**、 **Char**、 **Decimal**、**二重**、 **Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、 **UInt16**、 **UInt32**、および**UInt64**です。</span><span class="sxs-lookup"><span data-stu-id="c8362-104">These include **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**.</span></span> <span data-ttu-id="c8362-105">XLANG/s は 1 次元配列をサポートしますが、配列リテラルをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="c8362-105">XLANG/s supports single-dimensional arrays, but does not support array literals.</span></span>  
  
 <span data-ttu-id="c8362-106">XLANG/s では、メッセージ処理に対するさまざまなサポートも提供されます。</span><span class="sxs-lookup"><span data-stu-id="c8362-106">XLANG/s also has rich support for message handling.</span></span> <span data-ttu-id="c8362-107">メッセージは、スキーマ、.NET クラス、Web メッセージの種類 (WSDL)、または複雑なメッセージの種類に基づいて作成できます。</span><span class="sxs-lookup"><span data-stu-id="c8362-107">Messages can be based on schemas, .NET classes, Web message types (WSDL), or complex message types.</span></span> <span data-ttu-id="c8362-108">XLANG/s は、次の複合データ型をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c8362-108">XLANG/s supports the following complex data types:</span></span>  
  
-   <span data-ttu-id="c8362-109">**messagetype です。**</span><span class="sxs-lookup"><span data-stu-id="c8362-109">**messagetype.**</span></span> <span data-ttu-id="c8362-110">このデータ型は、データ要素および XSD ベース メッセージの組み合わせとして定義されるマルチパート メッセージの種類と、メソッド メッセージの種類 (クラスまたはインターフェイスのメソッドの署名形式に一致するメッセージ) を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8362-110">This data type defines multipart message types which are defined as combinations of data elements and XSD-based messages and Method-Message types (messages that match the signature format of a method of a class or interface).</span></span>  
  
-   <span data-ttu-id="c8362-111">**porttype。**</span><span class="sxs-lookup"><span data-stu-id="c8362-111">**porttype.**</span></span> <span data-ttu-id="c8362-112">このデータ型は、その型のポート インスタンスが動作できるポートの操作のコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="c8362-112">This data type defines a collection of port operations that a port instance of that type can act upon.</span></span>  
  
-   <span data-ttu-id="c8362-113">**correlationsettype です。**</span><span class="sxs-lookup"><span data-stu-id="c8362-113">**correlationsettype.**</span></span> <span data-ttu-id="c8362-114">このデータ型は、関連付けセット変数のインスタンスで使用されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="c8362-114">This data type defines the data that will be used in any instance of a correlation set variable.</span></span> <span data-ttu-id="c8362-115">関連付けセットのデータは、システム内を移動するメッセージがビジネス プロセスの適切な実行中インスタンスに送信されるようにするためのルーティング メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="c8362-115">Correlation set data is the routing mechanism used to ensure that messages moving through the system are dispatched to the appropriate running instance of a business process.</span></span> <span data-ttu-id="c8362-116">たとえば、注文書が処理のために取引先に送信された場合は、戻り時に、その注文書に対応するビジネス プロセスの正しいインスタンスが呼び出されることが重要になります。</span><span class="sxs-lookup"><span data-stu-id="c8362-116">For example, if a purchase order is sent to a trading partner for processing, it is imperative that the correct instance of the business process corresponding to that purchase order be invoked on its return.</span></span>  
  
-   <span data-ttu-id="c8362-117">**servicelinktype です。**</span><span class="sxs-lookup"><span data-stu-id="c8362-117">**servicelinktype.**</span></span> <span data-ttu-id="c8362-118">このデータ型のセットを定義する**porttype**ビジネス プロセスで使用するポートの論理的な一貫性のグループを形成する値。</span><span class="sxs-lookup"><span data-stu-id="c8362-118">This data type defines the set of **porttype** values that form a logically consistent group of ports used in a business process.</span></span> <span data-ttu-id="c8362-119">サービス リンクを使用することによって、実行時にポートのグループの動的な割り当てを可能にする強力なメカニズムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c8362-119">The use of service links is a powerful mechanism that allows dynamic assignment to a group of ports at run time.</span></span> <span data-ttu-id="c8362-120">これによって、複数の取引先とやり取りするために使用できる 1 つのビジネス プロセスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="c8362-120">This allows you to define a single business process that can be used to interact with multiple trading partners.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8362-121">参照</span><span class="sxs-lookup"><span data-stu-id="c8362-121">See Also</span></span>  
 <span data-ttu-id="c8362-122">[XLANG のステートメント](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="c8362-122">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="c8362-123">[XLANG の変数および演算子](../core/xlang-s-variables-and-operators.md) </span><span class="sxs-lookup"><span data-stu-id="c8362-123">[XLANG-s Variables and Operators](../core/xlang-s-variables-and-operators.md) </span></span>  
 <span data-ttu-id="c8362-124">[XLANG の式](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="c8362-124">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="c8362-125">[XLANG s の予約語](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="c8362-125">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="c8362-126">XLANG-s BPEL4WS 型への変換から</span><span class="sxs-lookup"><span data-stu-id="c8362-126">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)
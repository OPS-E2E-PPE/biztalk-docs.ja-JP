---
title: プロパティの昇格 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties, promoting
- promoting properties
- promoting properties, about promoting properties
ms.assetid: e1825028-7dd9-4eae-a383-4db12a83a402
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1c5ac3e6e9aeadccc4eaefcb1457821ef36a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266426"
---
# <a name="promoting-properties"></a><span data-ttu-id="efe6d-102">プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="efe6d-102">Promoting Properties</span></span>
<span data-ttu-id="efe6d-103">プロパティの昇格昇格させること**フィールド要素**または**フィールド属性**するスキーマのノード**識別フィールド**または**プロパティフィールド**です。</span><span class="sxs-lookup"><span data-stu-id="efe6d-103">Promotion of properties involves either promoting **Field Element** or **Field Attribute** nodes in a schema to be **Distinguished Fields** or **Property Fields**.</span></span> <span data-ttu-id="efe6d-104">昇格することも**レコード**ノードとして**プロパティ フィールド**単純コンテンツがある場合 (**Content-type**のプロパティ、**レコード**ノード設定**SimpleContent**)。</span><span class="sxs-lookup"><span data-stu-id="efe6d-104">You can also promote **Record** nodes as **Property Fields** if they have simple content (**Content Type** property of the **Record** node set to **SimpleContent**).</span></span> <span data-ttu-id="efe6d-105">このセクションでは、いずれかとしてノードを昇格するための手順を説明**識別フィールド**または**プロパティ フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="efe6d-105">This section provides step-by-step instructions for promoting nodes as either **Distinguished Fields** or as **Property Fields**.</span></span>  
  
 <span data-ttu-id="efe6d-106">昇格する、**レコード**(コンテンツを含む単純な)、**フィールド要素**、または**フィールド属性**ノードとして、**プロパティ フィールド**、最初の月を定義する、特殊な種類のスキーマには、プロパティ スキーマが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="efe6d-106">To promote a **Record** (with simple content), **Field Element**, or **Field Attribute** node as a **Property Field**, you may first define a special type of schema called a property schema.</span></span> <span data-ttu-id="efe6d-107">プロパティ スキーマの構造化されていないセットを定義する**フィールド要素**を昇格するノード**レコード**(コンテンツを含む単純な)、**フィールド要素**、または**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="efe6d-107">Property schemas define an unstructured set of **Field Element** nodes into which you promote **Record** (with simple content), **Field Element**, or **Field Attribute** nodes.</span></span> <span data-ttu-id="efe6d-108">プロパティ スキーマを作成するための詳しい手順については、「[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="efe6d-108">For step-by-step instructions for creating a property schema, see [How to Create Property Schemas](../core/how-to-create-property-schemas.md).</span></span>  
  
 <span data-ttu-id="efe6d-109">また、使用することができます、**クイック昇格**機能では、自動的に作成され、新しいを昇格するときに、1 つのプロパティ スキーマを更新**フィールド要素**、**フィールド属性**、または**レコード**(単純コンテンツ) を含むノードです。</span><span class="sxs-lookup"><span data-stu-id="efe6d-109">Alternatively, you can use the **Quick Promotion** feature, which will automatically create and update a single property schema whenever you promote a new **Field Element**, **Field Attribute**, or **Record** (with simple content) node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efe6d-110">双方向にフィールドを昇格させることができます、**識別フィールド**と**プロパティ フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="efe6d-110">You can promote a field as both a **Distinguished Field** and a **Property Field**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efe6d-111">**クイック昇格**機能は、昇格させたノードの名前を持つ新しいプロパティを挿入することで、プロパティ スキーマを変更します。</span><span class="sxs-lookup"><span data-stu-id="efe6d-111">The **Quick Promotion** feature modifies the property schema by inserting a new property with the name of the promoted node.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="efe6d-112">いったん昇格させた場合は、スキーマのフィールドの移動または名前の変更は行わないでください。</span><span class="sxs-lookup"><span data-stu-id="efe6d-112">Do not move or rename a field in the schema once you have promoted it.</span></span> <span data-ttu-id="efe6d-113">スキーマ フィールドの移動または名前変更を行うと、BizTalk エディターは、昇格させたフィールドの場所を定義する XPath を更新しません。</span><span class="sxs-lookup"><span data-stu-id="efe6d-113">When you move or rename a schema field, BizTalk Editor does not update the XPath defining the location of the promoted field.</span></span>  
  
## <a name="xsd-and-clr-data-types"></a><span data-ttu-id="efe6d-114">XSD データ型および CLR データ型</span><span class="sxs-lookup"><span data-stu-id="efe6d-114">XSD and CLR Data Types</span></span>  
 <span data-ttu-id="efe6d-115">プロパティの昇格を行うときなど、場合によっては、XSD データ型が共通言語ランタイム (CLR) データ型に昇格されることがあります。</span><span class="sxs-lookup"><span data-stu-id="efe6d-115">In some places, such as in property promotion, XSD data types are promoted to Common Language Runtime (CLR) data types.</span></span> <span data-ttu-id="efe6d-116">次の表は、昇格できる XSD データ型と対応する CLR データ型を示しています。</span><span class="sxs-lookup"><span data-stu-id="efe6d-116">The following table shows the XSD data types that can be promoted and the corresponding CLR data types.</span></span>  
  
|<span data-ttu-id="efe6d-117">XSD データ型</span><span class="sxs-lookup"><span data-stu-id="efe6d-117">XSD Data Type</span></span>|<span data-ttu-id="efe6d-118">CLR データ型</span><span class="sxs-lookup"><span data-stu-id="efe6d-118">CLR Data Type</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="efe6d-119">anyURI</span><span class="sxs-lookup"><span data-stu-id="efe6d-119">anyURI</span></span>|<span data-ttu-id="efe6d-120">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-120">String</span></span>|  
|<span data-ttu-id="efe6d-121">ブール値</span><span class="sxs-lookup"><span data-stu-id="efe6d-121">Boolean</span></span>|<span data-ttu-id="efe6d-122">ブール値</span><span class="sxs-lookup"><span data-stu-id="efe6d-122">Boolean</span></span>|  
|<span data-ttu-id="efe6d-123">Byte</span><span class="sxs-lookup"><span data-stu-id="efe6d-123">Byte</span></span>|<span data-ttu-id="efe6d-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="efe6d-124">sbyte</span></span>|  
|<span data-ttu-id="efe6d-125">日付</span><span class="sxs-lookup"><span data-stu-id="efe6d-125">Date</span></span>|<span data-ttu-id="efe6d-126">DateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-126">DateTime</span></span>|  
|<span data-ttu-id="efe6d-127">dateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-127">dateTime</span></span>|<span data-ttu-id="efe6d-128">DateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-128">DateTime</span></span>|  
|<span data-ttu-id="efe6d-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="efe6d-129">Decimal</span></span>|<span data-ttu-id="efe6d-130">Decimal</span><span class="sxs-lookup"><span data-stu-id="efe6d-130">Decimal</span></span>|  
|<span data-ttu-id="efe6d-131">Double</span><span class="sxs-lookup"><span data-stu-id="efe6d-131">Double</span></span>|<span data-ttu-id="efe6d-132">Double</span><span class="sxs-lookup"><span data-stu-id="efe6d-132">Double</span></span>|  
|<span data-ttu-id="efe6d-133">ENTITY</span><span class="sxs-lookup"><span data-stu-id="efe6d-133">ENTITY</span></span>|<span data-ttu-id="efe6d-134">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-134">String</span></span>|  
|<span data-ttu-id="efe6d-135">Float</span><span class="sxs-lookup"><span data-stu-id="efe6d-135">Float</span></span>|<span data-ttu-id="efe6d-136">単一</span><span class="sxs-lookup"><span data-stu-id="efe6d-136">Single</span></span>|  
|<span data-ttu-id="efe6d-137">gDay</span><span class="sxs-lookup"><span data-stu-id="efe6d-137">gDay</span></span>|<span data-ttu-id="efe6d-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-138">DateTime</span></span>|  
|<span data-ttu-id="efe6d-139">gMonth</span><span class="sxs-lookup"><span data-stu-id="efe6d-139">gMonth</span></span>|<span data-ttu-id="efe6d-140">DateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-140">DateTime</span></span>|  
|<span data-ttu-id="efe6d-141">gMonthDay</span><span class="sxs-lookup"><span data-stu-id="efe6d-141">gMonthDay</span></span>|<span data-ttu-id="efe6d-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-142">DateTime</span></span>|  
|<span data-ttu-id="efe6d-143">gYear</span><span class="sxs-lookup"><span data-stu-id="efe6d-143">gYear</span></span>|<span data-ttu-id="efe6d-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-144">DateTime</span></span>|  
|<span data-ttu-id="efe6d-145">gYearMonth</span><span class="sxs-lookup"><span data-stu-id="efe6d-145">gYearMonth</span></span>|<span data-ttu-id="efe6d-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-146">DateTime</span></span>|  
|<span data-ttu-id="efe6d-147">ID</span><span class="sxs-lookup"><span data-stu-id="efe6d-147">ID</span></span>|<span data-ttu-id="efe6d-148">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-148">String</span></span>|  
|<span data-ttu-id="efe6d-149">IDREF</span><span class="sxs-lookup"><span data-stu-id="efe6d-149">IDREF</span></span>|<span data-ttu-id="efe6d-150">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-150">String</span></span>|  
|<span data-ttu-id="efe6d-151">int</span><span class="sxs-lookup"><span data-stu-id="efe6d-151">Int</span></span>|<span data-ttu-id="efe6d-152">Int32</span><span class="sxs-lookup"><span data-stu-id="efe6d-152">Int32</span></span>|  
|<span data-ttu-id="efe6d-153">Integer</span><span class="sxs-lookup"><span data-stu-id="efe6d-153">Integer</span></span>|<span data-ttu-id="efe6d-154">Decimal</span><span class="sxs-lookup"><span data-stu-id="efe6d-154">Decimal</span></span>|  
|<span data-ttu-id="efe6d-155">言語</span><span class="sxs-lookup"><span data-stu-id="efe6d-155">Language</span></span>|<span data-ttu-id="efe6d-156">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-156">String</span></span>|  
|<span data-ttu-id="efe6d-157">名前</span><span class="sxs-lookup"><span data-stu-id="efe6d-157">Name</span></span>|<span data-ttu-id="efe6d-158">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-158">String</span></span>|  
|<span data-ttu-id="efe6d-159">NCName</span><span class="sxs-lookup"><span data-stu-id="efe6d-159">NCName</span></span>|<span data-ttu-id="efe6d-160">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-160">String</span></span>|  
|<span data-ttu-id="efe6d-161">negativeInteger</span><span class="sxs-lookup"><span data-stu-id="efe6d-161">negativeInteger</span></span>|<span data-ttu-id="efe6d-162">Decimal</span><span class="sxs-lookup"><span data-stu-id="efe6d-162">Decimal</span></span>|  
|<span data-ttu-id="efe6d-163">NMTOKEN</span><span class="sxs-lookup"><span data-stu-id="efe6d-163">NMTOKEN</span></span>|<span data-ttu-id="efe6d-164">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-164">String</span></span>|  
|<span data-ttu-id="efe6d-165">nonNegativeInteger</span><span class="sxs-lookup"><span data-stu-id="efe6d-165">nonNegativeInteger</span></span>|<span data-ttu-id="efe6d-166">Decimal</span><span class="sxs-lookup"><span data-stu-id="efe6d-166">Decimal</span></span>|  
|<span data-ttu-id="efe6d-167">nonPositiveInteger</span><span class="sxs-lookup"><span data-stu-id="efe6d-167">nonPositiveInteger</span></span>|<span data-ttu-id="efe6d-168">Decimal</span><span class="sxs-lookup"><span data-stu-id="efe6d-168">Decimal</span></span>|  
|<span data-ttu-id="efe6d-169">normalizedString</span><span class="sxs-lookup"><span data-stu-id="efe6d-169">normalizedString</span></span>|<span data-ttu-id="efe6d-170">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-170">String</span></span>|  
|<span data-ttu-id="efe6d-171">NOTATION</span><span class="sxs-lookup"><span data-stu-id="efe6d-171">NOTATION</span></span>|<span data-ttu-id="efe6d-172">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-172">String</span></span>|  
|<span data-ttu-id="efe6d-173">positiveInteger</span><span class="sxs-lookup"><span data-stu-id="efe6d-173">positiveInteger</span></span>|<span data-ttu-id="efe6d-174">Decimal</span><span class="sxs-lookup"><span data-stu-id="efe6d-174">Decimal</span></span>|  
|<span data-ttu-id="efe6d-175">QName</span><span class="sxs-lookup"><span data-stu-id="efe6d-175">QName</span></span>|<span data-ttu-id="efe6d-176">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-176">String</span></span>|  
|<span data-ttu-id="efe6d-177">Short</span><span class="sxs-lookup"><span data-stu-id="efe6d-177">Short</span></span>|<span data-ttu-id="efe6d-178">Int16</span><span class="sxs-lookup"><span data-stu-id="efe6d-178">Int16</span></span>|  
|<span data-ttu-id="efe6d-179">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-179">String</span></span>|<span data-ttu-id="efe6d-180">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-180">String</span></span>|  
|<span data-ttu-id="efe6d-181">[時刻]</span><span class="sxs-lookup"><span data-stu-id="efe6d-181">Time</span></span>|<span data-ttu-id="efe6d-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="efe6d-182">DateTime</span></span>|  
|<span data-ttu-id="efe6d-183">トークン</span><span class="sxs-lookup"><span data-stu-id="efe6d-183">Token</span></span>|<span data-ttu-id="efe6d-184">文字列</span><span class="sxs-lookup"><span data-stu-id="efe6d-184">String</span></span>|  
|<span data-ttu-id="efe6d-185">unsignedByte</span><span class="sxs-lookup"><span data-stu-id="efe6d-185">unsignedByte</span></span>|<span data-ttu-id="efe6d-186">Byte</span><span class="sxs-lookup"><span data-stu-id="efe6d-186">Byte</span></span>|  
|<span data-ttu-id="efe6d-187">unsignedInt</span><span class="sxs-lookup"><span data-stu-id="efe6d-187">unsignedInt</span></span>|<span data-ttu-id="efe6d-188">UInt32</span><span class="sxs-lookup"><span data-stu-id="efe6d-188">UInt32</span></span>|  
|<span data-ttu-id="efe6d-189">unsignedShort</span><span class="sxs-lookup"><span data-stu-id="efe6d-189">unsignedShort</span></span>|<span data-ttu-id="efe6d-190">UInt16</span><span class="sxs-lookup"><span data-stu-id="efe6d-190">UInt16</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="efe6d-191">base64Binary、duration、ENTITES、hexBinary、IDREFS、long、NMTOKENS、および unsignedLong の XSD データ型は、昇格ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="efe6d-191">XSD Data Type of base64Binary, duration, ENTITES, hexBinary, IDREFS, long, NMTOKENS, and unsignedLong are not supported for promotion.</span></span>  
  
## <a name="limitations-for-promoting-properties"></a><span data-ttu-id="efe6d-192">プロパティの昇格の制限事項</span><span class="sxs-lookup"><span data-stu-id="efe6d-192">Limitations for Promoting Properties</span></span>  
 <span data-ttu-id="efe6d-193">プロパティを昇格する際は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="efe6d-193">When promoting properties, consider the following:</span></span>  
  
-   <span data-ttu-id="efe6d-194">昇格させたプロパティの長さは 256 文字までに制限されますが、書き込みプロパティには長さの制限がありません。</span><span class="sxs-lookup"><span data-stu-id="efe6d-194">Promoted properties are limited to 256 characters in length while written properties have no length limitation.</span></span>  
  
-   <span data-ttu-id="efe6d-195">昇格させたプロパティはメッセージ ルーティングに使用されるので、比較と保存を効率よく行うためにサイズが制限されます。</span><span class="sxs-lookup"><span data-stu-id="efe6d-195">Promoted properties are used in message routing and are limited in size for reasons of efficiency in comparison and storage.</span></span> <span data-ttu-id="efe6d-196">書き込みプロパティにはサイズの制限がありませんが、コンテキストに大きな値を使用すると、値を処理してメッセージと共に渡す必要があるため、パフォーマンスに影響します</span><span class="sxs-lookup"><span data-stu-id="efe6d-196">While written properties have no hard limits on size, using excessively large values in the context will have an impact on performance, because those values must still be processed and passed with the message.</span></span> <span data-ttu-id="efe6d-197">書き込みプロパティの例としては、識別フィールドが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="efe6d-197">Distinguished Fields are the examples of written properties.</span></span>  
  
-   <span data-ttu-id="efe6d-198">レコード ノードは、としては昇格されません**識別フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="efe6d-198">Record nodes can never be promoted as **Distinguished Fields**.</span></span>  
  
-   <span data-ttu-id="efe6d-199">昇格するプロパティは非繰り返し要素または属性に限定されます。</span><span class="sxs-lookup"><span data-stu-id="efe6d-199">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
-   <span data-ttu-id="efe6d-200">同じルート ノードに属するフィールドを同じプロパティに昇格しないでください。</span><span class="sxs-lookup"><span data-stu-id="efe6d-200">Do not promote fields belonging to the same root node to the same property.</span></span> <span data-ttu-id="efe6d-201">このような昇格は、コンパイル エラーまたは展開エラーになります。</span><span class="sxs-lookup"><span data-stu-id="efe6d-201">Such promotions produce compilation or deployment errors.</span></span>  
  
-   <span data-ttu-id="efe6d-202">メッセージ コンテキスト内では、昇格されていないために使用できないプロパティがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="efe6d-202">Within a message context, there are some properties that are not available since they are not promoted.</span></span>  <span data-ttu-id="efe6d-203">BTS.ReceiveLocationName プロパティは、そのようなプロパティの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="efe6d-203">The BTS.ReceiveLocationName property is one such property.</span></span> <span data-ttu-id="efe6d-204">開発環境に新しいプロパティ スキーマまたは新しい BizTalk Server プロジェクトを追加できる場合は、オーケストレーション内からこのプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="efe6d-204">If you can add a new property schema or a new BizTalk Server project to your development it is possible to access this property from within an orchestration.</span></span>  
  
     <span data-ttu-id="efe6d-205">プロパティの値は、プロパティのターゲットの名前空間およびプロパティ名によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="efe6d-205">Property values are identified by the property target namespace and property name.</span></span>  <span data-ttu-id="efe6d-206">次に、受信場所にアクセスするためのコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="efe6d-206">The following example shows how to access the receive location in code.</span></span>  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a><span data-ttu-id="efe6d-207">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="efe6d-207">In This Section</span></span>  
  
-   [<span data-ttu-id="efe6d-208">開く方法、プロパティの昇格 ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="efe6d-208">How to Open the Promote Properties Dialog Box</span></span>](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [<span data-ttu-id="efe6d-209">識別フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="efe6d-209">How to Copy Data to the Message Context as Distinguished Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [<span data-ttu-id="efe6d-210">プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="efe6d-210">How to Copy Data to the Message Context as Property Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)
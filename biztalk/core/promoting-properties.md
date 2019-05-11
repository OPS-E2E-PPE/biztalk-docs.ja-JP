---
title: プロパティの昇格 |Microsoft Docs
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
ms.openlocfilehash: 0c8f10ba41a497a8595632947deaac31c5f48426
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398510"
---
# <a name="promoting-properties"></a><span data-ttu-id="b87da-102">プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="b87da-102">Promoting Properties</span></span>
<span data-ttu-id="b87da-103">プロパティの昇格には、昇格させることが含まれます**フィールド要素**または**フィールド属性**するスキーマ内のノード**識別フィールド**または**プロパティフィールド**します。</span><span class="sxs-lookup"><span data-stu-id="b87da-103">Promotion of properties involves either promoting **Field Element** or **Field Attribute** nodes in a schema to be **Distinguished Fields** or **Property Fields**.</span></span> <span data-ttu-id="b87da-104">昇格することも**レコード**ノードとして**プロパティ フィールド**単純コンテンツがある場合 (**Content-type**のプロパティ、**レコード**ノード設定**SimpleContent**)。</span><span class="sxs-lookup"><span data-stu-id="b87da-104">You can also promote **Record** nodes as **Property Fields** if they have simple content (**Content Type** property of the **Record** node set to **SimpleContent**).</span></span> <span data-ttu-id="b87da-105">このセクションのいずれかとしてノードを昇格する手順について説明します**識別フィールド**または**プロパティ フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="b87da-105">This section provides step-by-step instructions for promoting nodes as either **Distinguished Fields** or as **Property Fields**.</span></span>  
  
 <span data-ttu-id="b87da-106">昇格させる、**レコード**(単純なコンテンツの場合) を含む**フィールド要素**、または**フィールド属性**ノードとして、**プロパティ フィールド**、最初の月を定義する、特殊な種類のスキーマには、プロパティ スキーマが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b87da-106">To promote a **Record** (with simple content), **Field Element**, or **Field Attribute** node as a **Property Field**, you may first define a special type of schema called a property schema.</span></span> <span data-ttu-id="b87da-107">プロパティ スキーマの非構造化データのセットを定義する**フィールド要素**を昇格するノード**レコード**(単純なコンテンツの場合) を含む**フィールド要素**、または**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="b87da-107">Property schemas define an unstructured set of **Field Element** nodes into which you promote **Record** (with simple content), **Field Element**, or **Field Attribute** nodes.</span></span> <span data-ttu-id="b87da-108">プロパティ スキーマを作成する手順については、次を参照してください。[プロパティ スキーマを作成する方法](../core/how-to-create-property-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="b87da-108">For step-by-step instructions for creating a property schema, see [How to Create Property Schemas](../core/how-to-create-property-schemas.md).</span></span>  
  
 <span data-ttu-id="b87da-109">また、使用することができます、**クイック昇格**は自動的に作成し、新しい昇格する場合に、1 つのプロパティ スキーマを更新する機能**フィールド要素**、**フィールド属性**、または**レコード**(単純コンテンツ) を含むノードです。</span><span class="sxs-lookup"><span data-stu-id="b87da-109">Alternatively, you can use the **Quick Promotion** feature, which will automatically create and update a single property schema whenever you promote a new **Field Element**, **Field Attribute**, or **Record** (with simple content) node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b87da-110">両方のフィールドを昇格させることができます、**識別フィールド**と**プロパティ フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="b87da-110">You can promote a field as both a **Distinguished Field** and a **Property Field**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b87da-111">**クイック昇格**機能は、昇格されたノードの名前を持つ新しいプロパティを挿入することで、プロパティ スキーマを変更します。</span><span class="sxs-lookup"><span data-stu-id="b87da-111">The **Quick Promotion** feature modifies the property schema by inserting a new property with the name of the promoted node.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b87da-112">移動または昇格するいると、スキーマのフィールドの名前を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="b87da-112">Do not move or rename a field in the schema once you have promoted it.</span></span> <span data-ttu-id="b87da-113">移動またはスキーマのフィールドの名前を変更すると、BizTalk エディターは、昇格させたフィールドの場所を定義する XPath を更新できません。</span><span class="sxs-lookup"><span data-stu-id="b87da-113">When you move or rename a schema field, BizTalk Editor does not update the XPath defining the location of the promoted field.</span></span>  
  
## <a name="xsd-and-clr-data-types"></a><span data-ttu-id="b87da-114">XSD と CLR データ型</span><span class="sxs-lookup"><span data-stu-id="b87da-114">XSD and CLR Data Types</span></span>  
 <span data-ttu-id="b87da-115">いくつかの場所でなどのプロパティの昇格、XSD データ型に昇格共通言語ランタイム (CLR) データ型。</span><span class="sxs-lookup"><span data-stu-id="b87da-115">In some places, such as in property promotion, XSD data types are promoted to Common Language Runtime (CLR) data types.</span></span> <span data-ttu-id="b87da-116">次の表は、昇格できる XSD データ型と対応する CLR データ型を示します。</span><span class="sxs-lookup"><span data-stu-id="b87da-116">The following table shows the XSD data types that can be promoted and the corresponding CLR data types.</span></span>  
  
|<span data-ttu-id="b87da-117">XSD データ型</span><span class="sxs-lookup"><span data-stu-id="b87da-117">XSD Data Type</span></span>|<span data-ttu-id="b87da-118">CLR データ型</span><span class="sxs-lookup"><span data-stu-id="b87da-118">CLR Data Type</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="b87da-119">anyURI</span><span class="sxs-lookup"><span data-stu-id="b87da-119">anyURI</span></span>|<span data-ttu-id="b87da-120">String</span><span class="sxs-lookup"><span data-stu-id="b87da-120">String</span></span>|  
|<span data-ttu-id="b87da-121">ブール値</span><span class="sxs-lookup"><span data-stu-id="b87da-121">Boolean</span></span>|<span data-ttu-id="b87da-122">ブール値</span><span class="sxs-lookup"><span data-stu-id="b87da-122">Boolean</span></span>|  
|<span data-ttu-id="b87da-123">バイト</span><span class="sxs-lookup"><span data-stu-id="b87da-123">Byte</span></span>|<span data-ttu-id="b87da-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="b87da-124">sbyte</span></span>|  
|<span data-ttu-id="b87da-125">date</span><span class="sxs-lookup"><span data-stu-id="b87da-125">Date</span></span>|<span data-ttu-id="b87da-126">DateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-126">DateTime</span></span>|  
|<span data-ttu-id="b87da-127">dateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-127">dateTime</span></span>|<span data-ttu-id="b87da-128">DateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-128">DateTime</span></span>|  
|<span data-ttu-id="b87da-129">10 進数</span><span class="sxs-lookup"><span data-stu-id="b87da-129">Decimal</span></span>|<span data-ttu-id="b87da-130">10 進数</span><span class="sxs-lookup"><span data-stu-id="b87da-130">Decimal</span></span>|  
|<span data-ttu-id="b87da-131">Double</span><span class="sxs-lookup"><span data-stu-id="b87da-131">Double</span></span>|<span data-ttu-id="b87da-132">Double</span><span class="sxs-lookup"><span data-stu-id="b87da-132">Double</span></span>|  
|<span data-ttu-id="b87da-133">エンティティ</span><span class="sxs-lookup"><span data-stu-id="b87da-133">ENTITY</span></span>|<span data-ttu-id="b87da-134">String</span><span class="sxs-lookup"><span data-stu-id="b87da-134">String</span></span>|  
|<span data-ttu-id="b87da-135">float</span><span class="sxs-lookup"><span data-stu-id="b87da-135">Float</span></span>|<span data-ttu-id="b87da-136">単一</span><span class="sxs-lookup"><span data-stu-id="b87da-136">Single</span></span>|  
|<span data-ttu-id="b87da-137">gDay</span><span class="sxs-lookup"><span data-stu-id="b87da-137">gDay</span></span>|<span data-ttu-id="b87da-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-138">DateTime</span></span>|  
|<span data-ttu-id="b87da-139">gMonth</span><span class="sxs-lookup"><span data-stu-id="b87da-139">gMonth</span></span>|<span data-ttu-id="b87da-140">DateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-140">DateTime</span></span>|  
|<span data-ttu-id="b87da-141">gMonthDay</span><span class="sxs-lookup"><span data-stu-id="b87da-141">gMonthDay</span></span>|<span data-ttu-id="b87da-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-142">DateTime</span></span>|  
|<span data-ttu-id="b87da-143">gYear</span><span class="sxs-lookup"><span data-stu-id="b87da-143">gYear</span></span>|<span data-ttu-id="b87da-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-144">DateTime</span></span>|  
|<span data-ttu-id="b87da-145">gYearMonth</span><span class="sxs-lookup"><span data-stu-id="b87da-145">gYearMonth</span></span>|<span data-ttu-id="b87da-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-146">DateTime</span></span>|  
|<span data-ttu-id="b87da-147">ID</span><span class="sxs-lookup"><span data-stu-id="b87da-147">ID</span></span>|<span data-ttu-id="b87da-148">String</span><span class="sxs-lookup"><span data-stu-id="b87da-148">String</span></span>|  
|<span data-ttu-id="b87da-149">IDREF</span><span class="sxs-lookup"><span data-stu-id="b87da-149">IDREF</span></span>|<span data-ttu-id="b87da-150">String</span><span class="sxs-lookup"><span data-stu-id="b87da-150">String</span></span>|  
|<span data-ttu-id="b87da-151">Int</span><span class="sxs-lookup"><span data-stu-id="b87da-151">Int</span></span>|<span data-ttu-id="b87da-152">Int32</span><span class="sxs-lookup"><span data-stu-id="b87da-152">Int32</span></span>|  
|<span data-ttu-id="b87da-153">Integer</span><span class="sxs-lookup"><span data-stu-id="b87da-153">Integer</span></span>|<span data-ttu-id="b87da-154">10 進数</span><span class="sxs-lookup"><span data-stu-id="b87da-154">Decimal</span></span>|  
|<span data-ttu-id="b87da-155">[言語]</span><span class="sxs-lookup"><span data-stu-id="b87da-155">Language</span></span>|<span data-ttu-id="b87da-156">String</span><span class="sxs-lookup"><span data-stu-id="b87da-156">String</span></span>|  
|<span data-ttu-id="b87da-157">名前</span><span class="sxs-lookup"><span data-stu-id="b87da-157">Name</span></span>|<span data-ttu-id="b87da-158">String</span><span class="sxs-lookup"><span data-stu-id="b87da-158">String</span></span>|  
|<span data-ttu-id="b87da-159">NCName</span><span class="sxs-lookup"><span data-stu-id="b87da-159">NCName</span></span>|<span data-ttu-id="b87da-160">String</span><span class="sxs-lookup"><span data-stu-id="b87da-160">String</span></span>|  
|<span data-ttu-id="b87da-161">negativeInteger</span><span class="sxs-lookup"><span data-stu-id="b87da-161">negativeInteger</span></span>|<span data-ttu-id="b87da-162">10 進数</span><span class="sxs-lookup"><span data-stu-id="b87da-162">Decimal</span></span>|  
|<span data-ttu-id="b87da-163">NMTOKEN</span><span class="sxs-lookup"><span data-stu-id="b87da-163">NMTOKEN</span></span>|<span data-ttu-id="b87da-164">String</span><span class="sxs-lookup"><span data-stu-id="b87da-164">String</span></span>|  
|<span data-ttu-id="b87da-165">nonNegativeInteger</span><span class="sxs-lookup"><span data-stu-id="b87da-165">nonNegativeInteger</span></span>|<span data-ttu-id="b87da-166">10 進数</span><span class="sxs-lookup"><span data-stu-id="b87da-166">Decimal</span></span>|  
|<span data-ttu-id="b87da-167">nonPositiveInteger</span><span class="sxs-lookup"><span data-stu-id="b87da-167">nonPositiveInteger</span></span>|<span data-ttu-id="b87da-168">10 進数</span><span class="sxs-lookup"><span data-stu-id="b87da-168">Decimal</span></span>|  
|<span data-ttu-id="b87da-169">normalizedString</span><span class="sxs-lookup"><span data-stu-id="b87da-169">normalizedString</span></span>|<span data-ttu-id="b87da-170">String</span><span class="sxs-lookup"><span data-stu-id="b87da-170">String</span></span>|  
|<span data-ttu-id="b87da-171">表記法</span><span class="sxs-lookup"><span data-stu-id="b87da-171">NOTATION</span></span>|<span data-ttu-id="b87da-172">String</span><span class="sxs-lookup"><span data-stu-id="b87da-172">String</span></span>|  
|<span data-ttu-id="b87da-173">positiveInteger</span><span class="sxs-lookup"><span data-stu-id="b87da-173">positiveInteger</span></span>|<span data-ttu-id="b87da-174">10 進数</span><span class="sxs-lookup"><span data-stu-id="b87da-174">Decimal</span></span>|  
|<span data-ttu-id="b87da-175">QName</span><span class="sxs-lookup"><span data-stu-id="b87da-175">QName</span></span>|<span data-ttu-id="b87da-176">String</span><span class="sxs-lookup"><span data-stu-id="b87da-176">String</span></span>|  
|<span data-ttu-id="b87da-177">Short</span><span class="sxs-lookup"><span data-stu-id="b87da-177">Short</span></span>|<span data-ttu-id="b87da-178">Int16</span><span class="sxs-lookup"><span data-stu-id="b87da-178">Int16</span></span>|  
|<span data-ttu-id="b87da-179">String</span><span class="sxs-lookup"><span data-stu-id="b87da-179">String</span></span>|<span data-ttu-id="b87da-180">String</span><span class="sxs-lookup"><span data-stu-id="b87da-180">String</span></span>|  
|<span data-ttu-id="b87da-181">Time</span><span class="sxs-lookup"><span data-stu-id="b87da-181">Time</span></span>|<span data-ttu-id="b87da-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="b87da-182">DateTime</span></span>|  
|<span data-ttu-id="b87da-183">トークン</span><span class="sxs-lookup"><span data-stu-id="b87da-183">Token</span></span>|<span data-ttu-id="b87da-184">String</span><span class="sxs-lookup"><span data-stu-id="b87da-184">String</span></span>|  
|<span data-ttu-id="b87da-185">unsignedByte</span><span class="sxs-lookup"><span data-stu-id="b87da-185">unsignedByte</span></span>|<span data-ttu-id="b87da-186">バイト</span><span class="sxs-lookup"><span data-stu-id="b87da-186">Byte</span></span>|  
|<span data-ttu-id="b87da-187">unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b87da-187">unsignedInt</span></span>|<span data-ttu-id="b87da-188">UInt32</span><span class="sxs-lookup"><span data-stu-id="b87da-188">UInt32</span></span>|  
|<span data-ttu-id="b87da-189">unsignedShort</span><span class="sxs-lookup"><span data-stu-id="b87da-189">unsignedShort</span></span>|<span data-ttu-id="b87da-190">UInt16</span><span class="sxs-lookup"><span data-stu-id="b87da-190">UInt16</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b87da-191">Base64binary、XSD データ型、期間 ENTITES、hexBinary、IDREFS、long、NMTOKENS、および unsignedLong はサポートされませんを昇格します。</span><span class="sxs-lookup"><span data-stu-id="b87da-191">XSD Data Type of base64Binary, duration, ENTITES, hexBinary, IDREFS, long, NMTOKENS, and unsignedLong are not supported for promotion.</span></span>  
  
## <a name="limitations-for-promoting-properties"></a><span data-ttu-id="b87da-192">プロパティの昇格の制限事項</span><span class="sxs-lookup"><span data-stu-id="b87da-192">Limitations for Promoting Properties</span></span>  
 <span data-ttu-id="b87da-193">プロパティを昇格させるときに、次の操作を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="b87da-193">When promoting properties, consider the following:</span></span>  
  
-   <span data-ttu-id="b87da-194">昇格させたプロパティの長さは 256 文字までに制限されますが、書き込みプロパティには長さの制限がありません。</span><span class="sxs-lookup"><span data-stu-id="b87da-194">Promoted properties are limited to 256 characters in length while written properties have no length limitation.</span></span>  
  
-   <span data-ttu-id="b87da-195">昇格させたプロパティはメッセージ ルーティングに使用されるので、比較と保存を効率よく行うためにサイズが制限されます。</span><span class="sxs-lookup"><span data-stu-id="b87da-195">Promoted properties are used in message routing and are limited in size for reasons of efficiency in comparison and storage.</span></span> <span data-ttu-id="b87da-196">書き込みプロパティにはサイズの制限がありませんが、コンテキストに大きな値を使用すると、値を処理してメッセージと共に渡す必要があるため、パフォーマンスに影響します</span><span class="sxs-lookup"><span data-stu-id="b87da-196">While written properties have no hard limits on size, using excessively large values in the context will have an impact on performance, because those values must still be processed and passed with the message.</span></span> <span data-ttu-id="b87da-197">識別フィールドは、書き込みプロパティの例を示します。</span><span class="sxs-lookup"><span data-stu-id="b87da-197">Distinguished Fields are the examples of written properties.</span></span>  
  
-   <span data-ttu-id="b87da-198">[レコード] ノードは、としては昇格されません**識別フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="b87da-198">Record nodes can never be promoted as **Distinguished Fields**.</span></span>  
  
-   <span data-ttu-id="b87da-199">昇格させたプロパティに制限されている非繰り返し要素または属性。</span><span class="sxs-lookup"><span data-stu-id="b87da-199">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
-   <span data-ttu-id="b87da-200">同じプロパティに同じルート ノードに属するフィールドを昇格しません。</span><span class="sxs-lookup"><span data-stu-id="b87da-200">Do not promote fields belonging to the same root node to the same property.</span></span> <span data-ttu-id="b87da-201">このような昇格では、コンパイルや展開のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b87da-201">Such promotions produce compilation or deployment errors.</span></span>  
  
-   <span data-ttu-id="b87da-202">メッセージ コンテキスト内では昇格されていないため、使用できないいくつかのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b87da-202">Within a message context, there are some properties that are not available since they are not promoted.</span></span>  <span data-ttu-id="b87da-203">BTS します。ReceiveLocationName プロパティはこのような 1 つのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="b87da-203">The BTS.ReceiveLocationName property is one such property.</span></span> <span data-ttu-id="b87da-204">新しいプロパティ スキーマまたは新しい BizTalk Server プロジェクトを追加するには、開発する場合、オーケストレーション内からこのプロパティにアクセスすることです。</span><span class="sxs-lookup"><span data-stu-id="b87da-204">If you can add a new property schema or a new BizTalk Server project to your development it is possible to access this property from within an orchestration.</span></span>  
  
     <span data-ttu-id="b87da-205">プロパティの値は、プロパティのターゲット名前空間およびプロパティ名によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="b87da-205">Property values are identified by the property target namespace and property name.</span></span>  <span data-ttu-id="b87da-206">次の例では、コードで受信場所にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b87da-206">The following example shows how to access the receive location in code.</span></span>  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a><span data-ttu-id="b87da-207">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b87da-207">In This Section</span></span>  
  
-   [<span data-ttu-id="b87da-208">開く方法、昇格のプロパティ ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="b87da-208">How to Open the Promote Properties Dialog Box</span></span>](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [<span data-ttu-id="b87da-209">識別フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="b87da-209">How to Copy Data to the Message Context as Distinguished Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [<span data-ttu-id="b87da-210">プロパティ フィールドとしてメッセージ コンテキストにデータをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="b87da-210">How to Copy Data to the Message Context as Property Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)
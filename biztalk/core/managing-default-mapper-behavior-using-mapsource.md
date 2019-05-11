---
title: 既定のマッパーを使用して動作を管理する&lt;mapsource&gt; |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deea839c-e52e-44c6-ac0d-4396dc5b10d8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7b4173d514fcc7c671cfd367f64dfc2726bba72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329500"
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a><span data-ttu-id="22b09-102">既定のマッパーを使用して動作を管理する&lt;mapsource&gt;</span><span class="sxs-lookup"><span data-stu-id="22b09-102">Managing Default Mapper Behavior Using &lt;mapsource&gt;</span></span>
<span data-ttu-id="22b09-103">BizTalk マッパーの特定の既定動作を変更するには、属性を変更、 **mapsource**直接マップ ソース (.btm) ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="22b09-103">You can modify certain default behaviors of BizTalk Mapper by modifying attributes of the **mapsource** element directly in a map source (.btm) file.</span></span>  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a><span data-ttu-id="22b09-104">値のマッピング Functoid のコード生成の最適化</span><span class="sxs-lookup"><span data-stu-id="22b09-104">Optimizing Value Mapping Functoid Code Generation</span></span>  
 <span data-ttu-id="22b09-105">マッパーが XSLT を呼び出すコードを生成するとき、**値のマッピング**functoid、変数を使用して、結果を格納します。</span><span class="sxs-lookup"><span data-stu-id="22b09-105">When the Mapper generates XSLT code to call the **Value Mapping** functoid, a variable is used to store the result.</span></span> <span data-ttu-id="22b09-106">使用することができます、 **OptimizeValueMapping**フラグを最適化するために、**値のマッピング**functoid 変数が生成されるように場合にのみ、`if`ステートメントの評価が`True`します。</span><span class="sxs-lookup"><span data-stu-id="22b09-106">You can use the **OptimizeValueMapping** flag to optimize the **Value Mapping** functoid so that a variable is generated only when the `if` statement evaluates to `True`.</span></span> <span data-ttu-id="22b09-107">たとえば、 **OptimizeValueMapping**設定**いいえ**:</span><span class="sxs-lookup"><span data-stu-id="22b09-107">For example, with **OptimizeValueMapping** set to **No**:</span></span>  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="22b09-108">このコードを移動することによって最適化できます、**値のマッピング**functoid の呼び出しの本文に、`if`ステートメントでは、呼び出しは、必要なは場合のみが行われることを確認します。</span><span class="sxs-lookup"><span data-stu-id="22b09-108">This code could be optimized by moving the **Value Mapping** functoid invocation into the body of the `if` statement, ensuring that invocation occurs only when it is required.</span></span> <span data-ttu-id="22b09-109">設定**OptimizeValueMapping**に**はい**次のコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="22b09-109">Setting **OptimizeValueMapping** to **Yes** yields the following code:</span></span>  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="22b09-110">マッパーは、この最適化自動的に設定した場合、 **OptimizeValueMapping**の属性、 **mapsource**要素をマップ ソース (.btm) ファイル**はい**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="22b09-110">The Mapper does this optimization automatically if you set the **OptimizeValueMapping** attribute of the **mapsource** element in the map source (.btm) file to **Yes** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a><span data-ttu-id="22b09-111">大きな容量を使用するスキーマ</span><span class="sxs-lookup"><span data-stu-id="22b09-111">Accommodating Schemas with Large Footprints</span></span>  
 <span data-ttu-id="22b09-112">時、マッパーを使用してを深く複雑な構造体や、再帰的なノードのフット プリントが非常に大きなインスタンスを持つスキーマ、マップのテスト、検証、またはマップのコンパイルに時間がかかる場合がありますか、最悪の場合、「メモリ不足」エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="22b09-112">When the Mapper is using a schema that has a very large instance footprint with deep complex structures and/or recursive nodes, testing the map, validating the map, or compiling the map could take a long time or, in the worse case, result in an "out of memory" error.</span></span> <span data-ttu-id="22b09-113">これは、小規模で複雑なスキーマおよびサイズの大きいスキーマに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22b09-113">This could happen with small, complex schemas as well as with large schemas.</span></span>  
  
 <span data-ttu-id="22b09-114">複雑なスキーマの問題は、マッパーが再帰的に読み込む全体のスキーマ ツリーをノードに接続しているリンクがあるか、またはを調べてという事実が原因、**値**プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="22b09-114">The problem with complex schemas is due to the fact that the Mapper has to recursively load the entire schema tree looking for nodes that either have links connected to them or have the **Value** property set on them.</span></span> <span data-ttu-id="22b09-115">設定してこの問題を軽減することができます、 **GenerateDefaultFixedNodes**のフラグ、 **mapsource**に .btm ファイル内の要素**いいえ**よう。</span><span class="sxs-lookup"><span data-stu-id="22b09-115">You can alleviate this problem by setting the **GenerateDefaultFixedNodes** flag of the **mapsource** element in the .btm files to **No** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="22b09-116">この設定で、マッパーはターゲット スキーマの各スキーマのノードに関連付けられた内部コンパイラ ノードを作成するには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="22b09-116">With this setting, the Mapper does not need to create internal compiler nodes associated with each schema node of a target schema.</span></span> <span data-ttu-id="22b09-117">コンパイラによってアカウントにリンクされたノードだけが取得されます。</span><span class="sxs-lookup"><span data-stu-id="22b09-117">Only linked nodes are taken into account by the compiler.</span></span> <span data-ttu-id="22b09-118">これが大幅にメモリ消費量が減少し、「マップのテスト」または「マップの検証」操作をマップのコンパイルや保存を行う場合、処理速度が向上します。</span><span class="sxs-lookup"><span data-stu-id="22b09-118">This significantly reduces the memory consumption and speeds up the process when doing a "test map" or "validate map" operation, compiling the map, or saving the map.</span></span>  
  
 <span data-ttu-id="22b09-119">ただし、ときに、 **GenerateDefaultFixedNodes**にフラグが設定されている**いいえ**、ターゲット スキーマの設定フィールドの既定値は、マップによって生成されたインスタンスで保持されません。</span><span class="sxs-lookup"><span data-stu-id="22b09-119">However, when the **GenerateDefaultFixedNodes** flag is set to **No**, the default field values set in the target schema are not preserved in the instance produced by the map.</span></span> <span data-ttu-id="22b09-120">これは、これらの値が対象のインスタンスに必要な場合の問題です。</span><span class="sxs-lookup"><span data-stu-id="22b09-120">This is a problem when these values are required in the target instance.</span></span> <span data-ttu-id="22b09-121">必要な値でもう一度設定する必要がこれを回避する、マップで明示的にします。</span><span class="sxs-lookup"><span data-stu-id="22b09-121">To circumvent this, the required values have to be set again explicitly in the map.</span></span> <span data-ttu-id="22b09-122">設定することができます、 **GenerateDefaultFixedNodes**フラグを**RequiredDefaults**、すべての必須ノードを考慮することを意味します。</span><span class="sxs-lookup"><span data-stu-id="22b09-122">You can set the **GenerateDefaultFixedNodes** flag to **RequiredDefaults**, which means that all required nodes are taken into account.</span></span> <span data-ttu-id="22b09-123">これは、リンクされたノード、ノードが既定値のノード、 **MinOccurs**プロパティをより大きいまたは 1、および親が必要なノードと等しく設定します。</span><span class="sxs-lookup"><span data-stu-id="22b09-123">This covers linked nodes, nodes that have default values, nodes with the **MinOccurs** property set to greater than or equal to one, and nodes whose parents are required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22b09-124">設定した後**GenerateDefaultFixedNodes**に**いいえ**または**RequiredDefaults**、マップをテストし、出力が場合と同じことを確認する必要があります**GenerateDefaultFixedNodes**の既定値に設定されている**はい**がすべてのノードが考慮コンパイラでします。</span><span class="sxs-lookup"><span data-stu-id="22b09-124">After you set **GenerateDefaultFixedNodes** to **No** or **RequiredDefaults**, you should test the map and verify that the output is the same as when **GenerateDefaultFixedNodes** is set to its default value of **Yes**, in which all nodes are taken into account by the compiler.</span></span>  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a><span data-ttu-id="22b09-125">For-each ループ、条件、使用率を管理して、値のマッピング Functoid</span><span class="sxs-lookup"><span data-stu-id="22b09-125">Managing for-each Usage with Looping, Conditional, and Value Mapping Functoids</span></span>  
 <span data-ttu-id="22b09-126">使用すると、**ループ**functoid、**条件付き**functoid、または**値のマッピング**functoid、`xsl:for-each`ステートメントがコンパイルされたマップで生成されます。</span><span class="sxs-lookup"><span data-stu-id="22b09-126">When you use a **Looping** functoid, a **Conditional** functoid, or a **Value Mapping** functoid, an `xsl:for-each` statement is generated in the compiled map.</span></span> <span data-ttu-id="22b09-127">送信先スキーマの子フィールドに無制限の最大出現回数、`xsl:for-each`ステートメントは、子フィールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="22b09-127">If the child field of the destination schema has unbounded maximum occurrences, the `xsl:for-each` statement is put at the child field.</span></span> <span data-ttu-id="22b09-128">子フィールドには、最大出現回数を無制限にいない場合、`xsl:for-each`ステートメントは、子フィールドの親フィールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="22b09-128">If the child field does not have unbounded maximum occurrences, the `xsl:for-each` statement is put at the parent field of the child field.</span></span>  
  
 <span data-ttu-id="22b09-129">ただし、ための場所、`xsl:for-each`ステートメントが、マップの結果に影響することができます、 `xsl:for-each` に子フィールドの最大出現回数を設定するかどうかに関係なく、送信先スキーマの子フィールドに配置するステートメント**1**します。</span><span class="sxs-lookup"><span data-stu-id="22b09-129">However, because the location of the `xsl:for-each` statement affects the map result, you may want the `xsl:for-each` statement to be put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
 <span data-ttu-id="22b09-130">配置を制御することができます、`xsl:for-each`ステートメントの値を変更することによって、 **TreatElementsAsRecords**マップ (.btm) ファイルに示すように属性します。</span><span class="sxs-lookup"><span data-stu-id="22b09-130">You can control the placement of the `xsl:for-each` statement by modifying the value of the **TreatElementsAsRecords** attribute in the map (.btm) file as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="22b09-131">この属性を設定すると**はい**、`xsl:for-each`ステートメントに、子フィールドの最大出現回数を設定するかどうかに関係なく、送信先スキーマの子フィールドに配置されます**1**します。</span><span class="sxs-lookup"><span data-stu-id="22b09-131">When this attribute is set to **Yes**, the `xsl:for-each` statement is put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a><span data-ttu-id="22b09-132">繰り返されるシーケンス グループをマップするときに、順序を維持</span><span class="sxs-lookup"><span data-stu-id="22b09-132">Preserving the Order When Mapping a Repeating Sequence Group</span></span>  
 <span data-ttu-id="22b09-133">XSD スキーマ内のシーケンス グループは、メッセージ インスタンスで表されないため、ループ コンテキストを提供しません。</span><span class="sxs-lookup"><span data-stu-id="22b09-133">Sequence groups in XSD schemas do not provide a looping context because they are not represented in the message instance.</span></span> <span data-ttu-id="22b09-134">シーケンス グループで可能性をループなし、マッパーのコンパイラは、セグメントの順序を維持するために適切な XSLT を生成しません。</span><span class="sxs-lookup"><span data-stu-id="22b09-134">Without looping possibilities on the sequence group, the Mapper compiler does not generate the appropriate XSLT to maintain the segment order.</span></span> <span data-ttu-id="22b09-135">その結果、入力インスタンスに存在する相対コンテキストが失われ、さらに処理する役に立たなく出力インスタンスは、相対コンテキストによって異なります。</span><span class="sxs-lookup"><span data-stu-id="22b09-135">As a result, relative context that is present in the input instance is lost, which makes the output instances useless for further processing that depends on the relative context.</span></span>  
  
 <span data-ttu-id="22b09-136">使用することができます、 **PreserveSequenceOrder**繰り返しをマッピングするときに、レコードの順序を維持するためにフラグが別の繰り返されるシーケンスをシーケンス処理します。</span><span class="sxs-lookup"><span data-stu-id="22b09-136">You can use the **PreserveSequenceOrder** flag to maintain record order when mapping a repeating sequence to another repeating sequence.</span></span> <span data-ttu-id="22b09-137">フラグの値の設定既定では、**いいえ**以前で作成された既存のマップの機能を保持するために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョン フラグが存在しません。</span><span class="sxs-lookup"><span data-stu-id="22b09-137">By default, the value of the flag is set to **No** to preserve the functionality of existing maps created in earlier [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versions where the flag is not present.</span></span> <span data-ttu-id="22b09-138">を新しく作成されたマップで、フラグが存在するその値を設定して**いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="22b09-138">In the newly created maps, the flag will be present with its value set to **No**.</span></span> <span data-ttu-id="22b09-139">セグメントの順序を維持する必要があります明示的に設定する値**はい**で示すように .btm ファイル。</span><span class="sxs-lookup"><span data-stu-id="22b09-139">To maintain segment order, you must explicitly set the value to **Yes** in the .btm files as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="22b09-140">サンプルの入力インスタンスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="22b09-140">The following is a sample input instance:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="22b09-141">**PreserveSequenceOrder**フラグに設定**いいえ**、出力インスタンスは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="22b09-141">With the **PreserveSequenceOrder** flag set to **No**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="22b09-142">**PreserveSequenceOrder**フラグを設定**はい**、出力インスタンスは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="22b09-142">With the **PreserveSequenceOrder** flag set to **Yes**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22b09-143">参照</span><span class="sxs-lookup"><span data-stu-id="22b09-143">See Also</span></span>  
 [<span data-ttu-id="22b09-144">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="22b09-144">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)
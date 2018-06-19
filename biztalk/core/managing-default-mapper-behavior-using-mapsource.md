---
title: 既定のマッパーを使用して動作を管理する&lt;mapsource&gt; |Microsoft ドキュメント
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
ms.openlocfilehash: 44e2e66350709c6b857d875ec3979fe3f7059648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263378"
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a><span data-ttu-id="abb84-102">既定のマッパーを使用して動作を管理する&lt;mapsource&gt;</span><span class="sxs-lookup"><span data-stu-id="abb84-102">Managing Default Mapper Behavior Using &lt;mapsource&gt;</span></span>
<span data-ttu-id="abb84-103">BizTalk マッパーの特定の既定動作を変更するにはの属性を変更することによって、 **mapsource**直接マップ ソース (.btm) ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="abb84-103">You can modify certain default behaviors of BizTalk Mapper by modifying attributes of the **mapsource** element directly in a map source (.btm) file.</span></span>  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a><span data-ttu-id="abb84-104">値のマッピング Functoid のコード生成の最適化</span><span class="sxs-lookup"><span data-stu-id="abb84-104">Optimizing Value Mapping Functoid Code Generation</span></span>  
 <span data-ttu-id="abb84-105">マッパーが XSLT を呼び出すコードを生成するとき、**値のマッピング**functoid は、変数は、結果を格納するために使用します。</span><span class="sxs-lookup"><span data-stu-id="abb84-105">When the Mapper generates XSLT code to call the **Value Mapping** functoid, a variable is used to store the result.</span></span> <span data-ttu-id="abb84-106">使用することができます、 **OptimizeValueMapping**フラグを最適化するために、**値のマッピング**functoid 変数が生成されるようされる場合にのみ、`if`ステートメントの評価が`True`です。</span><span class="sxs-lookup"><span data-stu-id="abb84-106">You can use the **OptimizeValueMapping** flag to optimize the **Value Mapping** functoid so that a variable is generated only when the `if` statement evaluates to `True`.</span></span> <span data-ttu-id="abb84-107">たとえば、 **OptimizeValueMapping** 'éý'**いいえ**:</span><span class="sxs-lookup"><span data-stu-id="abb84-107">For example, with **OptimizeValueMapping** set to **No**:</span></span>  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="abb84-108">このコードを移動することによって最適化でした、**値のマッピング**の本体に functoid の呼び出し、`if`ステートメントでは、呼び出しのだけことが必要な場合に発生することを確認します。</span><span class="sxs-lookup"><span data-stu-id="abb84-108">This code could be optimized by moving the **Value Mapping** functoid invocation into the body of the `if` statement, ensuring that invocation occurs only when it is required.</span></span> <span data-ttu-id="abb84-109">設定**OptimizeValueMapping**に**はい**次のコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-109">Setting **OptimizeValueMapping** to **Yes** yields the following code:</span></span>  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 <span data-ttu-id="abb84-110">マッパーは、この最適化自動的に設定した場合、 **OptimizeValueMapping**の属性、 **mapsource**マップ ソース (.btm) ファイル内の要素**はい**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-110">The Mapper does this optimization automatically if you set the **OptimizeValueMapping** attribute of the **mapsource** element in the map source (.btm) file to **Yes** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a><span data-ttu-id="abb84-111">大きな容量を使用するスキーマの調整</span><span class="sxs-lookup"><span data-stu-id="abb84-111">Accommodating Schemas with Large Footprints</span></span>  
 <span data-ttu-id="abb84-112">構造が非常に複雑で容量の大きいスキーマをマッパーが使用している場合は、マップのテスト、マップの検証、またはマップのコンパイルに時間がかかり、最悪の場合、"メモリの不足です" エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-112">When the Mapper is using a schema that has a very large instance footprint with deep complex structures and/or recursive nodes, testing the map, validating the map, or compiling the map could take a long time or, in the worse case, result in an "out of memory" error.</span></span> <span data-ttu-id="abb84-113">これは、小規模で複雑なスキーマ、およびサイズの大きいスキーマでに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-113">This could happen with small, complex schemas as well as with large schemas.</span></span>  
  
 <span data-ttu-id="abb84-114">複雑なスキーマで問題が生じることは、マッパーが再帰的に読み込み、スキーマ全体のツリー ノードに接続しているリンクがあるかを探すため、**値**プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-114">The problem with complex schemas is due to the fact that the Mapper has to recursively load the entire schema tree looking for nodes that either have links connected to them or have the **Value** property set on them.</span></span> <span data-ttu-id="abb84-115">この問題を軽減するには、設定、 **GenerateDefaultFixedNodes**のフラグを設定、 **mapsource**に .btm ファイル内の要素**なし**ように。</span><span class="sxs-lookup"><span data-stu-id="abb84-115">You can alleviate this problem by setting the **GenerateDefaultFixedNodes** flag of the **mapsource** element in the .btm files to **No** as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="abb84-116">この設定を使用すると、マッパーはターゲット スキーマの各スキーマ ノードに関連付けられた内部のコンパイラ ノードを作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="abb84-116">With this setting, the Mapper does not need to create internal compiler nodes associated with each schema node of a target schema.</span></span> <span data-ttu-id="abb84-117">コンパイラでは、リンクされたノードだけが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-117">Only linked nodes are taken into account by the compiler.</span></span> <span data-ttu-id="abb84-118">これにより、メモリの使用量が大幅に削減され、"マップのテスト" 操作や "マップの検証" 操作を実行したり、マップのコンパイルや保存を行うときに、処理が高速化されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-118">This significantly reduces the memory consumption and speeds up the process when doing a "test map" or "validate map" operation, compiling the map, or saving the map.</span></span>  
  
 <span data-ttu-id="abb84-119">ただし、ときに、 **GenerateDefaultFixedNodes**にフラグが設定されている**いいえ**、ターゲット スキーマに設定する既定のフィールド値は、マップによって生成されたインスタンスでは保持されません。</span><span class="sxs-lookup"><span data-stu-id="abb84-119">However, when the **GenerateDefaultFixedNodes** flag is set to **No**, the default field values set in the target schema are not preserved in the instance produced by the map.</span></span> <span data-ttu-id="abb84-120">これは、これらの値がターゲット インスタンス内で必要である場合問題になります。</span><span class="sxs-lookup"><span data-stu-id="abb84-120">This is a problem when these values are required in the target instance.</span></span> <span data-ttu-id="abb84-121">この問題を回避するには、必要な値をマップ内で明示的に設定し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="abb84-121">To circumvent this, the required values have to be set again explicitly in the map.</span></span> <span data-ttu-id="abb84-122">設定することができます、 **GenerateDefaultFixedNodes**フラグを**RequiredDefaults**、すべての必須ノードを考慮することを意味します。</span><span class="sxs-lookup"><span data-stu-id="abb84-122">You can set the **GenerateDefaultFixedNodes** flag to **RequiredDefaults**, which means that all required nodes are taken into account.</span></span> <span data-ttu-id="abb84-123">これは、リンクされたノードがについて説明、既定値がノード値のノード、 **MinOccurs**に以上の値を 1 つ、およびノードの親が必要なプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-123">This covers linked nodes, nodes that have default values, nodes with the **MinOccurs** property set to greater than or equal to one, and nodes whose parents are required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abb84-124">設定した後**GenerateDefaultFixedNodes**に**いいえ**または**RequiredDefaults**、マップをテストし、出力が場合と同じであることを確認する必要があります**GenerateDefaultFixedNodes**の既定値に設定されている**はい**、するすべてのノードが考慮コンパイラによってにします。</span><span class="sxs-lookup"><span data-stu-id="abb84-124">After you set **GenerateDefaultFixedNodes** to **No** or **RequiredDefaults**, you should test the map and verify that the output is the same as when **GenerateDefaultFixedNodes** is set to its default value of **Yes**, in which all nodes are taken into account by the compiler.</span></span>  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a><span data-ttu-id="abb84-125">ループ Functoid、条件付き Functoid、および値のマッピング Functoid と for-each の使用の管理</span><span class="sxs-lookup"><span data-stu-id="abb84-125">Managing for-each Usage with Looping, Conditional, and Value Mapping Functoids</span></span>  
 <span data-ttu-id="abb84-126">使用する場合、**ループ**functoid、**条件付き**functoid、または**値のマッピング**functoid、`xsl:for-each`ステートメントがコンパイルされたマップで生成されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-126">When you use a **Looping** functoid, a **Conditional** functoid, or a **Value Mapping** functoid, an `xsl:for-each` statement is generated in the compiled map.</span></span> <span data-ttu-id="abb84-127">マップ先スキーマの子フィールドの最大出現回数が "バインド解除済み" である場合、`xsl:for-each` ステートメントは子フィールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-127">If the child field of the destination schema has unbounded maximum occurrences, the `xsl:for-each` statement is put at the child field.</span></span> <span data-ttu-id="abb84-128">子フィールドの最大出現回数が "バインド解除済み" でない場合、`xsl:for-each` ステートメントはその子フィールドの親フィールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="abb84-128">If the child field does not have unbounded maximum occurrences, the `xsl:for-each` statement is put at the parent field of the child field.</span></span>  
  
 <span data-ttu-id="abb84-129">ただし、ための場所、`xsl:for-each`ステートメントがマップの結果に影響する可能性があります、 `xsl:for-each` に子フィールドの最大出現回数を設定するかどうかに関係なく、送信先スキーマの子フィールドに配置するステートメント**1**です。</span><span class="sxs-lookup"><span data-stu-id="abb84-129">However, because the location of the `xsl:for-each` statement affects the map result, you may want the `xsl:for-each` statement to be put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
 <span data-ttu-id="abb84-130">配置を制御することができます、`xsl:for-each`ステートメントの値を変更することによって、 **TreatElementsAsRecords**ように、マップ (.btm) ファイルに属性します。</span><span class="sxs-lookup"><span data-stu-id="abb84-130">You can control the placement of the `xsl:for-each` statement by modifying the value of the **TreatElementsAsRecords** attribute in the map (.btm) file as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="abb84-131">この属性を設定すると**はい**、`xsl:for-each`ステートメントは、子フィールドの最大出現回数に設定されているかどうかに関係なく、送信先スキーマの子フィールドに配置**1**です。</span><span class="sxs-lookup"><span data-stu-id="abb84-131">When this attribute is set to **Yes**, the `xsl:for-each` statement is put at the child field of the destination schema, regardless of whether the maximum occurrence of the child field is set to **1**.</span></span>  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a><span data-ttu-id="abb84-132">繰り返されるシーケンス グループをマップする順序の保持</span><span class="sxs-lookup"><span data-stu-id="abb84-132">Preserving the Order When Mapping a Repeating Sequence Group</span></span>  
 <span data-ttu-id="abb84-133">XSD スキーマ内のシーケンス グループは、メッセージ インスタンスで表現できないため、ループ コンテキストを提供しません。</span><span class="sxs-lookup"><span data-stu-id="abb84-133">Sequence groups in XSD schemas do not provide a looping context because they are not represented in the message instance.</span></span> <span data-ttu-id="abb84-134">シーケンス グループでループを実現できないので、マッパーのコンパイラではセグメントの順序を維持するための適切な XSLT が生成されません。</span><span class="sxs-lookup"><span data-stu-id="abb84-134">Without looping possibilities on the sequence group, the Mapper compiler does not generate the appropriate XSLT to maintain the segment order.</span></span> <span data-ttu-id="abb84-135">その結果、入力インスタンスに存在する相対コンテキストが失われ、以降、相対コンテキストに依存する処理では出力インスタンスが役に立たなくなります。</span><span class="sxs-lookup"><span data-stu-id="abb84-135">As a result, relative context that is present in the input instance is lost, which makes the output instances useless for further processing that depends on the relative context.</span></span>  
  
 <span data-ttu-id="abb84-136">使用することができます、 **PreserveSequenceOrder**繰り返しをマップするときに、レコードの順序を維持するためにフラグが別の繰り返しシーケンス順序。</span><span class="sxs-lookup"><span data-stu-id="abb84-136">You can use the **PreserveSequenceOrder** flag to maintain record order when mapping a repeating sequence to another repeating sequence.</span></span> <span data-ttu-id="abb84-137">既定では、フラグの値に設定**いいえ**以前で作成された既存のマップの機能を保持するために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]フラグが存在しないバージョンです。</span><span class="sxs-lookup"><span data-stu-id="abb84-137">By default, the value of the flag is set to **No** to preserve the functionality of existing maps created in earlier [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versions where the flag is not present.</span></span> <span data-ttu-id="abb84-138">新しく作成されたマップでフラグが存在するその値を設定して**いいえ**です。</span><span class="sxs-lookup"><span data-stu-id="abb84-138">In the newly created maps, the flag will be present with its value set to **No**.</span></span> <span data-ttu-id="abb84-139">セグメントの順序を維持する必要があります明示的に設定する値**はい**ように、.btm ファイルで。</span><span class="sxs-lookup"><span data-stu-id="abb84-139">To maintain segment order, you must explicitly set the value to **Yes** in the .btm files as shown:</span></span>  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 <span data-ttu-id="abb84-140">以下に、サンプルの入力インスタンスを示します。</span><span class="sxs-lookup"><span data-stu-id="abb84-140">The following is a sample input instance:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="abb84-141">**PreserveSequenceOrder**フラグに設定されて**いいえ**、出力インスタンスは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="abb84-141">With the **PreserveSequenceOrder** flag set to **No**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 <span data-ttu-id="abb84-142">**PreserveSequenceOrder**フラグに設定**はい**、出力インスタンスは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="abb84-142">With the **PreserveSequenceOrder** flag set to **Yes**, the output instance will look like the following:</span></span>  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="abb84-143">参照</span><span class="sxs-lookup"><span data-stu-id="abb84-143">See Also</span></span>  
 [<span data-ttu-id="abb84-144">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="abb84-144">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)
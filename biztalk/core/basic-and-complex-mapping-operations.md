---
title: 基本的なと複雑なマッピング操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da864b48-6255-4847-9a6f-13e489e8658d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f05b4dfdae499538d85caec49bc17a72f9f1e7f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994051"
---
# <a name="basic-and-complex-mapping-operations"></a><span data-ttu-id="303fb-102">基本のマッピング操作と複雑なマッピング操作</span><span class="sxs-lookup"><span data-stu-id="303fb-102">Basic and Complex Mapping Operations</span></span>
<span data-ttu-id="303fb-103">BizTalk マッパーは、単純な親子ツリー型の操作から、ループ レコードや階層を含む詳細で複雑な操作まで、さまざまなマッピング シナリオに対するソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="303fb-103">BizTalk Mapper provides solutions for a variety of mapping scenarios ranging from simple parent-child tree-type operations to detailed, complex operations involving looping records and hierarchies.</span></span> <span data-ttu-id="303fb-104">マッピング シナリオの複雑さは、基本設定とビジネス ニーズによって異なります: XML Schema definition (XSD) 言語は、かなり柔軟に構造化された形式の定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="303fb-104">The complexity of a mapping scenario depends on your preferences and business needs—XML Schema definition (XSD) language gives you considerable flexibility in defining structured formats.</span></span> <span data-ttu-id="303fb-105">ほぼすべてのマッピング シナリオは、2 つのカテゴリ (基本的なマッピングと複雑なマッピング) のいずれかに分類されます。</span><span class="sxs-lookup"><span data-stu-id="303fb-105">Almost all mapping scenarios fall into one of two categories: basic mapping and complex mapping.</span></span>  
  
## <a name="basic-mapping"></a><span data-ttu-id="303fb-106">基本的なマッピング</span><span class="sxs-lookup"><span data-stu-id="303fb-106">Basic Mapping</span></span>  
 <span data-ttu-id="303fb-107">基本的なマッピングとは、最も一般的なマッピングのことをいいます。</span><span class="sxs-lookup"><span data-stu-id="303fb-107">Basic mapping is the most common type of mapping you can create.</span></span> <span data-ttu-id="303fb-108">基本的なマップでは、入力項目と出力項目が 1 対 1 の関係になります。</span><span class="sxs-lookup"><span data-stu-id="303fb-108">In a basic map, input and output items have a one-to-one relationship.</span></span> <span data-ttu-id="303fb-109">入力項目は、対応する 1 つの出力項目にのみマップされます。</span><span class="sxs-lookup"><span data-stu-id="303fb-109">An input item maps to one and only one output item.</span></span> <span data-ttu-id="303fb-110">さまざまな種類の変換および変換が複数の使用などの基本的なマッピングで可能な*functoid*コピーされる値を操作する functoid を連鎖するには、基になるシナリオは比較的と簡単です。</span><span class="sxs-lookup"><span data-stu-id="303fb-110">Although many types of transformations and translations are possible with basic mapping, such as using multiple *functoids* and cascading functoids to manipulate the value being copied, the underlying scenario remains relatively simple.</span></span> <span data-ttu-id="303fb-111">基本的なマッピング操作では、2 つの異なる親レコード (一度だけ発生する) に属するフィールドを、送信先スキーマの単一の親レコードに属するフィールドへマッピングすることもあります。</span><span class="sxs-lookup"><span data-stu-id="303fb-111">Basic mapping operations also include mapping fields from two different parent records (occurring only once) to fields under a single parent record in the destination schema.</span></span>  
  
## <a name="complex-mapping"></a><span data-ttu-id="303fb-112">複雑なマッピング</span><span class="sxs-lookup"><span data-stu-id="303fb-112">Complex Mapping</span></span>  
 <span data-ttu-id="303fb-113">複雑なマッピングには、1 つのインスタンスに対して複数回発生するレコードやフィールドが含まれます。、**レコード**または**フィールド要素**スキーマ ツリー内のノード。</span><span class="sxs-lookup"><span data-stu-id="303fb-113">Complex mapping involves records or fields that occur multiple times for a single instance of the **Record** or **Field Element** node in the schema tree.</span></span> <span data-ttu-id="303fb-114">このようなノードがその**Max Occurs** 1 つ以上の対応する要素にあります、インスタンス メッセージを示すプロパティを 1 (1) よりも大きい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="303fb-114">Such nodes have their **Max Occurs** property set to a value greater than one (1), indicating there may be more than one corresponding element in an instance message.</span></span> <span data-ttu-id="303fb-115">BizTalk マップが可変のマッピングには、この型を使用する場合 (とも呼ばれます*ループ*)、Extensible Stylesheet Language (XSL) スタイル シートのコンパイラで生成するために反復処理する対象となる適切なループ パスを決定できる必要があります、必要な出力。</span><span class="sxs-lookup"><span data-stu-id="303fb-115">When a BizTalk map uses this type of variable count mapping (also known as *looping*), the Extensible Stylesheet Language (XSL) style sheet compiler must be able to determine the proper loop path over which to iterate to produce the required output.</span></span>  
  
 <span data-ttu-id="303fb-116">通常、送信元スキーマのループ レコードのフィールドを、送信先スキーマのループ レコードのフィールドにリンクできます。</span><span class="sxs-lookup"><span data-stu-id="303fb-116">In general, you can link a field in a looping record in the source schema to a field in a looping record in the destination schema.</span></span> <span data-ttu-id="303fb-117">入力インスタンス メッセージ内にある要素の数によって、出力インスタンス メッセージ内に作成される要素の数が決まります。</span><span class="sxs-lookup"><span data-stu-id="303fb-117">The number of corresponding elements in an input instance message determines the number of elements created in the output instance message.</span></span> <span data-ttu-id="303fb-118">送信元スキーマおよび送信先スキーマを基にした、次の XSD フラグメントを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="303fb-118">Consider the following XSD fragments from example source and destination schemas.</span></span>  
  
### <a name="source-schema-fragment"></a><span data-ttu-id="303fb-119">送信元スキーマのフラグメント</span><span class="sxs-lookup"><span data-stu-id="303fb-119">Source Schema Fragment</span></span>  
  
```  
<xs:element minOccurs="1" maxOccurs="5"  
            name="SrcLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
  
```  
  
### <a name="destination-schema-fragment"></a><span data-ttu-id="303fb-120">送信先スキーマのフラグメント</span><span class="sxs-lookup"><span data-stu-id="303fb-120">Destination Schema Fragment</span></span>  
  
```  
<xs:element minOccurs="0" maxOccurs="unbounded"  
            name="DstLoopingRecord">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="" type="xs:string" />   
      <xs:element name="" type="xs:integer" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
```  
  
 <span data-ttu-id="303fb-121">これらのフラグメントを説明します。</span><span class="sxs-lookup"><span data-stu-id="303fb-121">In these fragments:</span></span>  
  
- <span data-ttu-id="303fb-122">**SrcLoopingRecord**、**レコード**、入力インスタンス メッセージ内のノードが 5 回に 1 つから発生することができます。</span><span class="sxs-lookup"><span data-stu-id="303fb-122">**SrcLoopingRecord**, a **Record** node in input instance messages, can occur from one to five times.</span></span> <span data-ttu-id="303fb-123">子も含まれています。**フィールド要素**ノード**Field1** (文字列) と**Field2** (整数)、親の各インスタンスに対して一度だけ発生します。</span><span class="sxs-lookup"><span data-stu-id="303fb-123">It also contains the child **Field Element** nodes **Field1** (a string) and **Field2** (an integer) that occur once for each instance of their parent.</span></span>  
  
- <span data-ttu-id="303fb-124">**DstLoopingRecord**、**レコード**、出力インスタンス メッセージ内のノードは、ゼロ (0) 回以上、無制限に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="303fb-124">**DstLoopingRecord**, a **Record** node in output instance messages, can occur zero (0) or more times, unbounded.</span></span> <span data-ttu-id="303fb-125">子も含まれています。**フィールド要素**ノード**FieldA** (文字列) と**FieldB** (整数)、親の各インスタンスに対して一度だけ発生します。</span><span class="sxs-lookup"><span data-stu-id="303fb-125">It also contains the child **Field Element** nodes **FieldA** (a string) and **FieldB** (an integer) that occur once for each instance of their parent.</span></span>  
  
  <span data-ttu-id="303fb-126">Field1 と FieldA、および Field2 と FieldB がマップされ、次に示す入力インスタンス メッセージのフラグメントがこれらをマップすると仮定した場合、出力インスタンス メッセージから次のフラグメントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="303fb-126">Assuming that Field1 is mapped to FieldA and Field2 is mapped to FieldB, and that the following fragment from an input instance message has processed those mappings, the following fragment from an output instance message would be produced.</span></span>  
  
### <a name="input-instance-message-fragment"></a><span data-ttu-id="303fb-127">入力インスタンス メッセージのフラグメント</span><span class="sxs-lookup"><span data-stu-id="303fb-127">Input Instance Message Fragment</span></span>  
  
```  
<SrcLoopingRecord>  
    <Field1>A string</Field1>  
    <Field2>10</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>Another string</Field1>  
    <Field2>11</Field2>  
</SrcLoopingRecord>  
<SrcLoopingRecord>  
    <Field1>A ball of string</Field1>  
    <Field2>12</Field2>  
</SrcLoopingRecord>  
```  
  
### <a name="output-instance-message-fragment"></a><span data-ttu-id="303fb-128">出力インスタンス メッセージのフラグメント</span><span class="sxs-lookup"><span data-stu-id="303fb-128">Output Instance Message Fragment</span></span>  
  
```  
<DstLoopingRecord>  
    <FieldA>A string</FieldA>  
    <FieldB>10</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
  <FieldA>Another string</FieldA>  
  <FieldB>11</FieldB>  
</DstLoopingRecord>  
<DstLoopingRecord>  
    <FieldA>A ball of string</FieldA>  
    <FieldB>12</FieldB>  
</DstLoopingRecord>  
```  
  
 <span data-ttu-id="303fb-129">出現回数、 **SrcLoopingRecord** (3) の入力インスタンス メッセージ内の要素の出現回数を決定する、 **DstLoopingRecord**出力インスタンス メッセージ内の要素。</span><span class="sxs-lookup"><span data-stu-id="303fb-129">The number of occurrences of the **SrcLoopingRecord** element in the input instance message (3) determines the number of occurrences of the **DstLoopingRecord** element in the output instance message.</span></span>  
  
 <span data-ttu-id="303fb-130">BizTalk マッパーでサポートされていないマッピングでは、複数のループ パスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="303fb-130">A type of mapping not supported by BizTalk Mapper is the use of multiple loop paths.</span></span> <span data-ttu-id="303fb-131">このようなマッピングでは、送信元スキーマの 2 つ以上のループ レコードに属するフィールドから、送信先スキーマの単一のルーピング レコードに属するフィールドへのマップ操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="303fb-131">This type of mapping involves fields from two or more looping records in the source schema being mapped to fields within a single looping record in the destination schema.</span></span> <span data-ttu-id="303fb-132">これは、問題など、出力インスタンス メッセージで生成される要素の数を決定する効果的な方法はありません。</span><span class="sxs-lookup"><span data-stu-id="303fb-132">This presents a problem—there is no effective way to determine the number of elements to produce in the output instance message.</span></span> <span data-ttu-id="303fb-133">複数のループ パスを使用すると、送信先ノードが複数の送信元ループ パスを持つことを示す、マップのコンパイル警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="303fb-133">Multiple loop paths result in a map compilation warning indicating that the destination node has multiple source loop paths.</span></span> <span data-ttu-id="303fb-134">ただし、これは単なる警告であり、最初の送信元ループ パスの繰り返し回数が使用されて、出力インスタンス メッセージに生成される要素の数が決定されます。</span><span class="sxs-lookup"><span data-stu-id="303fb-134">However, this is only a warning, and the number of iterations in the first source loop path is used to determine the number of elements produced in the output instance message.</span></span> <span data-ttu-id="303fb-135">ループを使用して動作の明示的な制御を行う、**ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="303fb-135">You can take explicit control of looping behavior by using the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="303fb-136">Microsoft BizTalk Server では、新しい種類のテーブルドリブン ループというループが導入されました。</span><span class="sxs-lookup"><span data-stu-id="303fb-136">Microsoft BizTalk Server introduced a new kind of looping called table-driven looping.</span></span> <span data-ttu-id="303fb-137">1 つ以上の定数、送信元スキーマからのリンク、または Functoid を組み合わせた入力インスタンス メッセージのデータに基づいて、出力インスタンス メッセージを使用する必要がある場合、テーブルドリブン ループは便利です。</span><span class="sxs-lookup"><span data-stu-id="303fb-137">Table-driven looping is useful when your output instance message needs to be based on data from the input instance message, combined with one or more constants, links from the source schema, or functoids.</span></span> <span data-ttu-id="303fb-138">この場合、出力インスタンス メッセージは、異なる定数を組み合わせた入力インスタンス メッセージの単一のレコードのデータに基づいて (または、入力インスタンス メッセージの複数のレコードのデータに基づいて)、複数のレコードを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="303fb-138">In such cases, the output instance message can have multiple records based on data from a single record in the input instance message that is combined with different constants, or based on data coming from multiple records in the input instance message.</span></span> <span data-ttu-id="303fb-139">テーブル ドリブンの詳細については、ループを使用して、**テーブル ループ**と**テーブル抽出**functoid を参照してください[テーブル ループ functoid およびテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)します。</span><span class="sxs-lookup"><span data-stu-id="303fb-139">For more information about table-driven looping using the **Table Looping** and **Table Extractor** functoids, see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303fb-140">参照</span><span class="sxs-lookup"><span data-stu-id="303fb-140">See Also</span></span>  
 <span data-ttu-id="303fb-141">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="303fb-141">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="303fb-142">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="303fb-142">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)
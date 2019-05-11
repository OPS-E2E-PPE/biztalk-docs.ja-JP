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
ms.openlocfilehash: e3ca1e0819de255e70d4f66064f52cdc70f7189c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529155"
---
# <a name="basic-and-complex-mapping-operations"></a><span data-ttu-id="223c5-102">基本的なと複雑なマッピング操作</span><span class="sxs-lookup"><span data-stu-id="223c5-102">Basic and Complex Mapping Operations</span></span>
<span data-ttu-id="223c5-103">BizTalk マッパーでは、マッピングのシナリオが単純な親子ツリー型の操作からループ レコードや階層に関連する詳細で複雑な操作に至るまでのさまざまなソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="223c5-103">BizTalk Mapper provides solutions for a variety of mapping scenarios ranging from simple parent-child tree-type operations to detailed, complex operations involving looping records and hierarchies.</span></span> <span data-ttu-id="223c5-104">マッピング シナリオの複雑さは、基本設定とビジネス ニーズによって異なります: XML Schema definition (XSD) 言語は、かなり柔軟に構造化された形式の定義を提供します。</span><span class="sxs-lookup"><span data-stu-id="223c5-104">The complexity of a mapping scenario depends on your preferences and business needs—XML Schema definition (XSD) language gives you considerable flexibility in defining structured formats.</span></span> <span data-ttu-id="223c5-105">ほぼすべてのマッピング シナリオが 2 つのカテゴリのいずれかに分類されます。 基本的なマッピングと複雑なマッピング。</span><span class="sxs-lookup"><span data-stu-id="223c5-105">Almost all mapping scenarios fall into one of two categories: basic mapping and complex mapping.</span></span>  
  
## <a name="basic-mapping"></a><span data-ttu-id="223c5-106">基本的なマッピング</span><span class="sxs-lookup"><span data-stu-id="223c5-106">Basic Mapping</span></span>  
 <span data-ttu-id="223c5-107">基本的なマッピングは、最も一般的な種類のマッピングを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="223c5-107">Basic mapping is the most common type of mapping you can create.</span></span> <span data-ttu-id="223c5-108">基本的なマップでは、入力と出力の項目は、一対一のリレーションシップを持ちます。</span><span class="sxs-lookup"><span data-stu-id="223c5-108">In a basic map, input and output items have a one-to-one relationship.</span></span> <span data-ttu-id="223c5-109">入力の項目は、1 つだけの出力項目にマップされます。</span><span class="sxs-lookup"><span data-stu-id="223c5-109">An input item maps to one and only one output item.</span></span> <span data-ttu-id="223c5-110">さまざまな種類の変換および変換が複数の使用などの基本的なマッピングで可能な*functoid*コピーされる値を操作する functoid を連鎖するには、基になるシナリオは比較的と簡単です。</span><span class="sxs-lookup"><span data-stu-id="223c5-110">Although many types of transformations and translations are possible with basic mapping, such as using multiple *functoids* and cascading functoids to manipulate the value being copied, the underlying scenario remains relatively simple.</span></span> <span data-ttu-id="223c5-111">基本的なマッピング操作では、(一度だけ発生する) 送信先スキーマの 1 つの親レコードの下のフィールドに 2 つの異なる親レコードからフィールドのマッピングも含まれます。</span><span class="sxs-lookup"><span data-stu-id="223c5-111">Basic mapping operations also include mapping fields from two different parent records (occurring only once) to fields under a single parent record in the destination schema.</span></span>  
  
## <a name="complex-mapping"></a><span data-ttu-id="223c5-112">複雑なマッピング</span><span class="sxs-lookup"><span data-stu-id="223c5-112">Complex Mapping</span></span>  
 <span data-ttu-id="223c5-113">複雑なマッピングには、1 つのインスタンスに対して複数回発生するレコードやフィールドが含まれます。、**レコード**または**フィールド要素**スキーマ ツリー内のノード。</span><span class="sxs-lookup"><span data-stu-id="223c5-113">Complex mapping involves records or fields that occur multiple times for a single instance of the **Record** or **Field Element** node in the schema tree.</span></span> <span data-ttu-id="223c5-114">このようなノードがその**Max Occurs** 1 つ以上の対応する要素にあります、インスタンス メッセージを示すプロパティを 1 (1) よりも大きい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="223c5-114">Such nodes have their **Max Occurs** property set to a value greater than one (1), indicating there may be more than one corresponding element in an instance message.</span></span> <span data-ttu-id="223c5-115">BizTalk マップが可変のマッピングには、この型を使用する場合 (とも呼ばれます*ループ*)、Extensible Stylesheet Language (XSL) スタイル シートのコンパイラで生成するために反復処理する対象となる適切なループ パスを決定できる必要があります、必要な出力。</span><span class="sxs-lookup"><span data-stu-id="223c5-115">When a BizTalk map uses this type of variable count mapping (also known as *looping*), the Extensible Stylesheet Language (XSL) style sheet compiler must be able to determine the proper loop path over which to iterate to produce the required output.</span></span>  
  
 <span data-ttu-id="223c5-116">一般に、送信先スキーマのループ レコード内のフィールドに、送信元スキーマのループ レコード内のフィールドをリンクできます。</span><span class="sxs-lookup"><span data-stu-id="223c5-116">In general, you can link a field in a looping record in the source schema to a field in a looping record in the destination schema.</span></span> <span data-ttu-id="223c5-117">入力インスタンス メッセージに対応する要素の数は、出力インスタンス メッセージで作成した要素の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="223c5-117">The number of corresponding elements in an input instance message determines the number of elements created in the output instance message.</span></span> <span data-ttu-id="223c5-118">元と送信先スキーマの例は、次の XSD フラグメントを検討してください。</span><span class="sxs-lookup"><span data-stu-id="223c5-118">Consider the following XSD fragments from example source and destination schemas.</span></span>  
  
### <a name="source-schema-fragment"></a><span data-ttu-id="223c5-119">ソース スキーマのフラグメント</span><span class="sxs-lookup"><span data-stu-id="223c5-119">Source Schema Fragment</span></span>  
  
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
  
### <a name="destination-schema-fragment"></a><span data-ttu-id="223c5-120">送信先スキーマのフラグメント</span><span class="sxs-lookup"><span data-stu-id="223c5-120">Destination Schema Fragment</span></span>  
  
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
  
 <span data-ttu-id="223c5-121">: これらのフラグメントで</span><span class="sxs-lookup"><span data-stu-id="223c5-121">In these fragments:</span></span>  
  
- <span data-ttu-id="223c5-122">**SrcLoopingRecord**、**レコード**、入力インスタンス メッセージ内のノードが 5 回に 1 つから発生することができます。</span><span class="sxs-lookup"><span data-stu-id="223c5-122">**SrcLoopingRecord**, a **Record** node in input instance messages, can occur from one to five times.</span></span> <span data-ttu-id="223c5-123">子も含まれています。**フィールド要素**ノード**Field1** (文字列) と**Field2** (整数)、親の各インスタンスに対して一度だけ発生します。</span><span class="sxs-lookup"><span data-stu-id="223c5-123">It also contains the child **Field Element** nodes **Field1** (a string) and **Field2** (an integer) that occur once for each instance of their parent.</span></span>  
  
- <span data-ttu-id="223c5-124">**DstLoopingRecord**、**レコード**、出力インスタンス メッセージ内のノードは、ゼロ (0) 回以上、無制限に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="223c5-124">**DstLoopingRecord**, a **Record** node in output instance messages, can occur zero (0) or more times, unbounded.</span></span> <span data-ttu-id="223c5-125">子も含まれています。**フィールド要素**ノード**FieldA** (文字列) と**FieldB** (整数)、親の各インスタンスに対して一度だけ発生します。</span><span class="sxs-lookup"><span data-stu-id="223c5-125">It also contains the child **Field Element** nodes **FieldA** (a string) and **FieldB** (an integer) that occur once for each instance of their parent.</span></span>  
  
  <span data-ttu-id="223c5-126">Field1 は FieldA にマップされ、Field2 がマップされていると仮定 FieldB に、入力インスタンス メッセージから次のフラグメントが、それらのマッピングを処理、出力インスタンス メッセージから次のフラグメントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="223c5-126">Assuming that Field1 is mapped to FieldA and Field2 is mapped to FieldB, and that the following fragment from an input instance message has processed those mappings, the following fragment from an output instance message would be produced.</span></span>  
  
### <a name="input-instance-message-fragment"></a><span data-ttu-id="223c5-127">入力インスタンス メッセージのフラグメント</span><span class="sxs-lookup"><span data-stu-id="223c5-127">Input Instance Message Fragment</span></span>  
  
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
  
### <a name="output-instance-message-fragment"></a><span data-ttu-id="223c5-128">出力インスタンス メッセージのフラグメント</span><span class="sxs-lookup"><span data-stu-id="223c5-128">Output Instance Message Fragment</span></span>  
  
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
  
 <span data-ttu-id="223c5-129">出現回数、 **SrcLoopingRecord** (3) の入力インスタンス メッセージ内の要素の出現回数を決定する、 **DstLoopingRecord**出力インスタンス メッセージ内の要素。</span><span class="sxs-lookup"><span data-stu-id="223c5-129">The number of occurrences of the **SrcLoopingRecord** element in the input instance message (3) determines the number of occurrences of the **DstLoopingRecord** element in the output instance message.</span></span>  
  
 <span data-ttu-id="223c5-130">BizTalk マッパーでサポートされていないマッピングの種類は、複数のループ パスの使用です。</span><span class="sxs-lookup"><span data-stu-id="223c5-130">A type of mapping not supported by BizTalk Mapper is the use of multiple loop paths.</span></span> <span data-ttu-id="223c5-131">この種類マッピングにはには、送信先スキーマの 1 つのループ レコード内のフィールドにマップされる送信元スキーマ内の 2 つまたは複数のループ レコードからフィールドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="223c5-131">This type of mapping involves fields from two or more looping records in the source schema being mapped to fields within a single looping record in the destination schema.</span></span> <span data-ttu-id="223c5-132">これは、問題など、出力インスタンス メッセージで生成される要素の数を決定する効果的な方法はありません。</span><span class="sxs-lookup"><span data-stu-id="223c5-132">This presents a problem—there is no effective way to determine the number of elements to produce in the output instance message.</span></span> <span data-ttu-id="223c5-133">マップのコンパイル警告を示すの宛先ノードが複数の送信元ループ パスを持つ複数のループ パスがあります。</span><span class="sxs-lookup"><span data-stu-id="223c5-133">Multiple loop paths result in a map compilation warning indicating that the destination node has multiple source loop paths.</span></span> <span data-ttu-id="223c5-134">ただし、これは、警告のみと、最初の送信元ループ パスでのイテレーションの数は、出力インスタンス メッセージに生成される要素の数を決定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="223c5-134">However, this is only a warning, and the number of iterations in the first source loop path is used to determine the number of elements produced in the output instance message.</span></span> <span data-ttu-id="223c5-135">ループを使用して動作の明示的な制御を行う、**ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="223c5-135">You can take explicit control of looping behavior by using the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="223c5-136">Microsoft BizTalk Server では、新しい種類のテーブルドリブン ループというループが導入されました。</span><span class="sxs-lookup"><span data-stu-id="223c5-136">Microsoft BizTalk Server introduced a new kind of looping called table-driven looping.</span></span> <span data-ttu-id="223c5-137">テーブルドリブン ループは、出力インスタンス メッセージは、入力インスタンス メッセージからデータに基づく、定数、送信元スキーマ、または functoid からのリンクの 1 つまたは複数を組み合わせる必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="223c5-137">Table-driven looping is useful when your output instance message needs to be based on data from the input instance message, combined with one or more constants, links from the source schema, or functoids.</span></span> <span data-ttu-id="223c5-138">このような場合は、出力インスタンス メッセージに複数のレコードが別の定数と組み合わせるか、入力インスタンス メッセージ内の複数レコードからのデータに基づく入力インスタンス メッセージ内の 1 つのレコードからデータに基づくことができます。</span><span class="sxs-lookup"><span data-stu-id="223c5-138">In such cases, the output instance message can have multiple records based on data from a single record in the input instance message that is combined with different constants, or based on data coming from multiple records in the input instance message.</span></span> <span data-ttu-id="223c5-139">テーブル ドリブンの詳細については、ループを使用して、**テーブル ループ**と**テーブル抽出**functoid を参照してください[テーブル ループ functoid およびテーブル抽出 Functoid](../core/table-looping-and-table-extractor-functoids.md)します。</span><span class="sxs-lookup"><span data-stu-id="223c5-139">For more information about table-driven looping using the **Table Looping** and **Table Extractor** functoids, see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223c5-140">参照</span><span class="sxs-lookup"><span data-stu-id="223c5-140">See Also</span></span>  
 <span data-ttu-id="223c5-141">[マップ](../core/maps.md) </span><span class="sxs-lookup"><span data-stu-id="223c5-141">[Maps](../core/maps.md) </span></span>  
 [<span data-ttu-id="223c5-142">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="223c5-142">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)
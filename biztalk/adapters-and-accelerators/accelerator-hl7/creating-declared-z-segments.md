---
title: 宣言されている Z セグメントを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae9148547f527d29238b6080cd499be8da7b7e6
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "22204746"
---
# <a name="creating-declared-z-segments"></a><span data-ttu-id="7501a-102">宣言されている Z セグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7501a-102">Creating Declared Z Segments</span></span>
<span data-ttu-id="7501a-103">(宣言されていない Z セグメント、ボディ部に続く、マルチパーティ メッセージの最後の部分をする必要があります) とは異なり、スキーマの任意のレベルで宣言されている Z セグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7501a-103">You can create declared Z segments at any level of a schema (unlike undeclared Z segments, which must be the last part of a multi-party message, following the body part).</span></span>  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a><span data-ttu-id="7501a-104">BizTalk エディターで Z セグメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="7501a-104">To create a Z segment in BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="7501a-105">ソリューション エクスプ ローラーの Visual Studio で、クリックして、Z セグメントを追加するスキーマを右クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="7501a-105">In Solution Explorer of Visual Studio, right-click the schema to which you want to add a Z segment, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="7501a-106">BizTalk エディターで、スキーマの名前を持つノードを右クリックし、**スキーマ ノードの挿入**、クリックして**子レコード**です。</span><span class="sxs-lookup"><span data-stu-id="7501a-106">In BizTalk Editor, right-click the node with the name of the schema, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  
  
3.  <span data-ttu-id="7501a-107">英数字を 3 桁で、英大文字の"Z"をされている最初の桁で、name の先頭レコードの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="7501a-107">Name the record starting the name with three alphanumeric digits, in capitals, with the first digit being "Z".</span></span> <span data-ttu-id="7501a-108">(Z セグメント タグは、次の 3 つの文字を含める必要があります)アンダー スコア (_) を挿入し、セグメントの簡単な説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="7501a-108">(The Z segment tag must include three characters.) Insert an underscore (_), and then add a short description of the segment.</span></span> <span data-ttu-id="7501a-109">説明には、1 つまたは一連のスペースを含めずの単語を大文字の各単語の最初の文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7501a-109">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="7501a-110">最後の単語は、「セグメント」にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7501a-110">The last word should be "Segment".</span></span> <span data-ttu-id="7501a-111">(例では"ZPP_PatientPreferencesSegment)**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7501a-111">(An example is "ZPP_PatientPreferencesSegment.) Press **Enter**.</span></span>  
  
4.  <span data-ttu-id="7501a-112">プロパティ ペインで、Z セグメントに必要なプロパティを入力を含む**Data Structure Type** (スキーマ名または xsd:anyType) **Max Occurs**、および**Min Occurs**です。</span><span class="sxs-lookup"><span data-stu-id="7501a-112">In the Properties pane, type the properties you want for the Z segment, including **Data Structure Type** (schema name or xsd:anyType), **Max Occurs**, and **Min Occurs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7501a-113">レコードのデータ構造体の型を入力すると、子フィールド要素を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="7501a-113">If you enter a data structure type for the record, you will not be able to add a child field element.</span></span>  
  
5.  <span data-ttu-id="7501a-114">BizTalk エディターでは、Z のセグメントの名前を右クリックし、**スキーマ ノードの挿入**をクリックし、**子フィールド要素**です。</span><span class="sxs-lookup"><span data-stu-id="7501a-114">In BizTalk Editor, right-click the name of the Z segment, point to **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
6.  <span data-ttu-id="7501a-115">名前から始まる、ピリオドと後にアンダー スコアと、フィールドの簡単な説明、フィールドの数が続くセグメント名の最初の 3 桁、フィールドの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7501a-115">Type the name of the field, starting the name with the first three digits of the segment name, followed by a period and the number of the field, followed by an underscore and then a short description of the field.</span></span> <span data-ttu-id="7501a-116">説明には、1 つまたは一連のスペースを含めずの単語を大文字の各単語の最初の文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7501a-116">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="7501a-117">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7501a-117">Press **Enter**.</span></span>  
  
7.  <span data-ttu-id="7501a-118">プロパティ ウィンドウで、入力、Z セグメントに必要なプロパティを含む**データ型**、 **Nillable**、**固定**、 **Max Occurs**、および**Min Occurs**です。</span><span class="sxs-lookup"><span data-stu-id="7501a-118">In the Properties pane, type the properties you want for the Z segment, including **Data Type**, **Nillable**, **Fixed**, **Max Occurs**, and **Min Occurs**.</span></span>  
  
8.  <span data-ttu-id="7501a-119">コンポーネントでフィールドを作成するには、レコードとしてフィールドを作成し、各コンポーネントについては、そのレコードの子要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="7501a-119">To create a field with components, create the field as a record, and then create a child element of that record for each component.</span></span> <span data-ttu-id="7501a-120">これらのサブコンポーネントに、フィールドを作成するには、要素を作成、フィールドとレコードとしてのコンポーネントのサブコンポーネントの子として。</span><span class="sxs-lookup"><span data-stu-id="7501a-120">To create a field with subcomponents, create the field and components as records, and the subcomponents as child elements.</span></span> <span data-ttu-id="7501a-121">これらのサブコンポーネントは複合データ型であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7501a-121">Note that subcomponents cannot be composite data types.</span></span> <span data-ttu-id="7501a-122">たとえば、ZPP_PatientPreferencesSegment をという名前のセグメントをする可能性があります ZPP.1_Dietary フィールドと作成 PD.1 性が高まりますコンポーネント PD.1.1_FoodGroupAllergy サブコンポーネントとします。</span><span class="sxs-lookup"><span data-stu-id="7501a-122">For example, for the segment named ZPP_PatientPreferencesSegment, you might create a ZPP.1_Dietary field and a PD.1 Allergies component with a PD.1.1_FoodGroupAllergy subcomponent.</span></span> <span data-ttu-id="7501a-123">PD.1.1_FoodGroupAllergy サブコンポーネントの情報は、単純なデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7501a-123">The PD.1.1_FoodGroupAllergy subcomponent would have to be a simple data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7501a-124">参照</span><span class="sxs-lookup"><span data-stu-id="7501a-124">See Also</span></span>  
 <span data-ttu-id="7501a-125">[Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="7501a-125">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="7501a-126">[スキーマでカスタム データ型を作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="7501a-126">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="7501a-127">[スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="7501a-127">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 <span data-ttu-id="7501a-128">[列挙型を拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="7501a-128">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="7501a-129">未宣言の Z セグメントの処理</span><span class="sxs-lookup"><span data-stu-id="7501a-129">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
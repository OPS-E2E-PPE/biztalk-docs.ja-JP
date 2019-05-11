---
title: 宣言された Z セグメントの作成 |Microsoft Docs
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
ms.openlocfilehash: 67b6469130173dbdc60d223f4f5c4f268699ce3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255637"
---
# <a name="creating-declared-z-segments"></a><span data-ttu-id="648d5-102">宣言された Z セグメントの作成</span><span class="sxs-lookup"><span data-stu-id="648d5-102">Creating Declared Z Segments</span></span>
<span data-ttu-id="648d5-103">(宣言されていない Z セグメント、マルチパーティ メッセージのボディ部を次の最後の部分である必要があります) とは異なり、スキーマの任意のレベルで宣言された Z セグメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="648d5-103">You can create declared Z segments at any level of a schema (unlike undeclared Z segments, which must be the last part of a multi-party message, following the body part).</span></span>  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a><span data-ttu-id="648d5-104">Z セグメントを BizTalk エディターで作成するには</span><span class="sxs-lookup"><span data-stu-id="648d5-104">To create a Z segment in BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="648d5-105">ソリューション エクスプ ローラーの Visual Studio で、クリックして Z セグメントを追加するスキーマを右クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="648d5-105">In Solution Explorer of Visual Studio, right-click the schema to which you want to add a Z segment, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="648d5-106">BizTalk エディターでスキーマの名前を持つノードを右クリックし、[**スキーマ ノードの挿入**、] をクリックし、**子レコード**します。</span><span class="sxs-lookup"><span data-stu-id="648d5-106">In BizTalk Editor, right-click the node with the name of the schema, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  
  
3.  <span data-ttu-id="648d5-107">名前を 3 桁の英数字、大文字で"Z"されている最初の桁で始まるレコードの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="648d5-107">Name the record starting the name with three alphanumeric digits, in capitals, with the first digit being "Z".</span></span> <span data-ttu-id="648d5-108">(Z セグメントのタグは、次の 3 つの文字を含める必要があります)アンダー スコア (_) を挿入し、セグメントの簡単な説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="648d5-108">(The Z segment tag must include three characters.) Insert an underscore (_), and then add a short description of the segment.</span></span> <span data-ttu-id="648d5-109">説明には、1 つまたは一連のスペースを含めずの単語を大文字で入力の各単語の最初の文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="648d5-109">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="648d5-110">最後の単語には、「セグメント」必要があります。</span><span class="sxs-lookup"><span data-stu-id="648d5-110">The last word should be "Segment".</span></span> <span data-ttu-id="648d5-111">(例では"ZPP_PatientPreferencesSegment)**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="648d5-111">(An example is "ZPP_PatientPreferencesSegment.) Press **Enter**.</span></span>  
  
4.  <span data-ttu-id="648d5-112">プロパティ ペインで、Z セグメントの必要なプロパティを入力を含む**Data Structure Type** (スキーマ名または xsd:anyType) **Max Occurs**、および**Min Occurs**します。</span><span class="sxs-lookup"><span data-stu-id="648d5-112">In the Properties pane, type the properties you want for the Z segment, including **Data Structure Type** (schema name or xsd:anyType), **Max Occurs**, and **Min Occurs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="648d5-113">レコードのデータ構造体の型を入力する場合、子フィールド要素を追加することができなきます。</span><span class="sxs-lookup"><span data-stu-id="648d5-113">If you enter a data structure type for the record, you will not be able to add a child field element.</span></span>  
  
5.  <span data-ttu-id="648d5-114">BizTalk エディターでは、Z セグメントの名前を右クリックし、[**スキーマ ノードの挿入**、] をクリックし、**子フィールド要素**します。</span><span class="sxs-lookup"><span data-stu-id="648d5-114">In BizTalk Editor, right-click the name of the Z segment, point to **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
6.  <span data-ttu-id="648d5-115">名前から始まる、ピリオド、アンダー スコアと、フィールドの簡単な説明が続く、フィールドの電話番号、セグメント名の最初の 3 つの数字、フィールドの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="648d5-115">Type the name of the field, starting the name with the first three digits of the segment name, followed by a period and the number of the field, followed by an underscore and then a short description of the field.</span></span> <span data-ttu-id="648d5-116">説明には、1 つまたは一連のスペースを含めずの単語を大文字で入力の各単語の最初の文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="648d5-116">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="648d5-117">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="648d5-117">Press **Enter**.</span></span>  
  
7.  <span data-ttu-id="648d5-118">プロパティ ペインで、Z セグメントの必要なプロパティを入力を含む**データ型**、 **Nillable**、**固定**、 **Max Occurs**、**Min Occurs**します。</span><span class="sxs-lookup"><span data-stu-id="648d5-118">In the Properties pane, type the properties you want for the Z segment, including **Data Type**, **Nillable**, **Fixed**, **Max Occurs**, and **Min Occurs**.</span></span>  
  
8.  <span data-ttu-id="648d5-119">コンポーネントと、フィールドを作成するには、レコードとフィールドを作成し、コンポーネントごとにそのレコードの子要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="648d5-119">To create a field with components, create the field as a record, and then create a child element of that record for each component.</span></span> <span data-ttu-id="648d5-120">サブコンポーネントのフィールドを作成するには、要素を作成、フィールドとレコードとしてコンポーネントとサブコンポーネントの子として。</span><span class="sxs-lookup"><span data-stu-id="648d5-120">To create a field with subcomponents, create the field and components as records, and the subcomponents as child elements.</span></span> <span data-ttu-id="648d5-121">サブコンポーネントの複合データ型であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="648d5-121">Note that subcomponents cannot be composite data types.</span></span> <span data-ttu-id="648d5-122">たとえば、ZPP_PatientPreferencesSegment という名前のセグメントの可能性がありますを作成 ZPP.1_Dietary フィールドと PD.1 アレルギー コンポーネント PD.1.1_FoodGroupAllergy サブコンポーネントとします。</span><span class="sxs-lookup"><span data-stu-id="648d5-122">For example, for the segment named ZPP_PatientPreferencesSegment, you might create a ZPP.1_Dietary field and a PD.1 Allergies component with a PD.1.1_FoodGroupAllergy subcomponent.</span></span> <span data-ttu-id="648d5-123">PD.1.1_FoodGroupAllergy サブコンポーネントには、単純なデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="648d5-123">The PD.1.1_FoodGroupAllergy subcomponent would have to be a simple data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648d5-124">参照</span><span class="sxs-lookup"><span data-stu-id="648d5-124">See Also</span></span>  
 <span data-ttu-id="648d5-125">[Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="648d5-125">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="648d5-126">[スキーマでカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="648d5-126">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="648d5-127">[スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="648d5-127">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 <span data-ttu-id="648d5-128">[列挙の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="648d5-128">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="648d5-129">未宣言の Z セグメントの処理</span><span class="sxs-lookup"><span data-stu-id="648d5-129">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
---
title: "スキーマでのカスタム データ型の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, creating Z data types [Z objects]
- data types, creating [Z objects]
- Z objects, creating Z data types
ms.assetid: e545c849-d414-4d5d-bb56-d3f9d5238c70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea38eb106b3554b72885355aaa9aef4928f4fda2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="creating-custom-data-types-in-schemas"></a><span data-ttu-id="7301f-102">スキーマでカスタム データ型を作成します。</span><span class="sxs-lookup"><span data-stu-id="7301f-102">Creating Custom Data Types in Schemas</span></span>
<span data-ttu-id="7301f-103">カスタム データ型を作成するには、datatypes_ で\<*バージョン*\>.xsd 共通のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="7301f-103">You can create a custom data type in the datatypes_\<*version*\>.xsd common schema.</span></span> <span data-ttu-id="7301f-104">既存のデータ型、基本データ型、またはテーブルで定義された列挙体のカスタム データ型を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7301f-104">You can base a custom data type on an existing data type, a base data type, or on an enumeration defined in a table.</span></span>  
  
### <a name="to-create-a-z-data-type"></a><span data-ttu-id="7301f-105">Z データ型を作成するには</span><span class="sxs-lookup"><span data-stu-id="7301f-105">To create a Z data type</span></span>  
  
1.  <span data-ttu-id="7301f-106">ソリューション エクスプ ローラーの Visual Studio で、共通のデータ型のスキーマ ファイルを開きます (**datatypes_\<*バージョン*\>.xsd * *)、をクリックして**を開く**.</span><span class="sxs-lookup"><span data-stu-id="7301f-106">In Solution Explorer of Visual Studio, open the common data-type schema file (**datatypes_\<*version*\>.xsd**), and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="7301f-107">BizTalk エディターを右クリックして**HL7DefinedDataTypes**、 をポイント**スキーマ ノードの挿入**、クリックして**子レコード**をコンポーネントのデータ型を作成またはをクリックするには**子要素**を単純なデータ型を作成します。</span><span class="sxs-lookup"><span data-stu-id="7301f-107">In BizTalk Editor, right-click **HL7DefinedDataTypes**, point to **Insert Schema Node**, and then click **Child Record** to create a component data type, or click **Child Element** to create a simple data type.</span></span>  
  
3.  <span data-ttu-id="7301f-108">"Z"で始まる 3 文字のタグを持つデータ型を名前します。</span><span class="sxs-lookup"><span data-stu-id="7301f-108">Name the data type with a three-character tag starting with "Z".</span></span>  
  
4.  <span data-ttu-id="7301f-109">プロパティ ウィンドウで、使用値を入力**Base Data Type**、**データ型**、および必要に応じて、他のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="7301f-109">In the Properties pane, type the values you want for **Base Data Type**, **Data Type**, and other properties, as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7301f-110">参照</span><span class="sxs-lookup"><span data-stu-id="7301f-110">See Also</span></span>  
 <span data-ttu-id="7301f-111">[Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="7301f-111">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="7301f-112">[宣言されている Z セグメントを作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="7301f-112">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="7301f-113">[スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="7301f-113">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 <span data-ttu-id="7301f-114">[列挙型を拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="7301f-114">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="7301f-115">未宣言の Z セグメントの処理</span><span class="sxs-lookup"><span data-stu-id="7301f-115">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
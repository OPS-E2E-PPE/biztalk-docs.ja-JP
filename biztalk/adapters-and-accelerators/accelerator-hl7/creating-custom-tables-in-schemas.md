---
title: スキーマのカスタム テーブルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Z tables [Z objects]
- Z objects, creating Z tables
- 2.X schemas, creating Z tables
ms.assetid: d6ab8ac9-a835-4ec0-9ddd-76ff267a3cbd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41efa501b1b937bcb179c61d6d21f1dd12deac88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255724"
---
# <a name="creating-custom-tables-in-schemas"></a><span data-ttu-id="dcac0-102">スキーマのカスタム テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="dcac0-102">Creating Custom Tables in Schemas</span></span>
<span data-ttu-id="dcac0-103">カスタムのテーブルを作成するには、tablevalues_ で\<*バージョン*\>.xsd 共通のスキーマ。</span><span class="sxs-lookup"><span data-stu-id="dcac0-103">You can create a custom table in the tablevalues_\<*version*\>.xsd common schema.</span></span> <span data-ttu-id="dcac0-104">カスタム テーブルは、既存のデータ型、基本データ型、またはテーブルで定義されている列挙体の基本ことができます。</span><span class="sxs-lookup"><span data-stu-id="dcac0-104">You can base a custom table on an existing data type, a base data type, or on an enumeration defined in a table.</span></span>  
  
### <a name="to-create-a-z-table"></a><span data-ttu-id="dcac0-105">Z テーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="dcac0-105">To create a Z table</span></span>  
  
1.  <span data-ttu-id="dcac0-106">ソリューション エクスプ ローラーで、一般的なデータ型のスキーマ ファイルを開く**tablevalues_\<*バージョン*\>.xsd**、 をクリックし、**開く**。</span><span class="sxs-lookup"><span data-stu-id="dcac0-106">In Solution Explorer, open the common data-type schema file **tablevalues_\<*version*\>.xsd**, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="dcac0-107">BizTalk エディターで、右クリックして**HL7DefinedTables**、 をポイント**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-107">In BizTalk Editor, right-click **HL7DefinedTables**, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
3.  <span data-ttu-id="dcac0-108">"Z"文字で始まるタグを持つテーブルを名前します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-108">Name the table with a tag starting with the letter "Z".</span></span>  
  
4.  <span data-ttu-id="dcac0-109">プロパティ ペインで、必要に応じて、固有のプロパティの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-109">In the Properties pane, type the values you want for specific properties, as needed.</span></span>  
  
5.  <span data-ttu-id="dcac0-110">列挙体を関連付けるプロパティ ペインで、テーブルに次のように設定します。 **Derived By**に**制限**、 をクリック**列挙**、の省略記号(...)ボタンをクリックします。**列挙体**、列挙エディタを格納する列挙値を入力します。</span><span class="sxs-lookup"><span data-stu-id="dcac0-110">To associate an enumeration with the table, in the Properties pane, set **Derived By** to **Restriction**, click **Enumeration**, click the ellipsis (…) button for **Enumeration**, and then type the values that you want the enumeration to contain in the Enumeration Editor.</span></span> <span data-ttu-id="dcac0-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcac0-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcac0-112">参照</span><span class="sxs-lookup"><span data-stu-id="dcac0-112">See Also</span></span>  
 <span data-ttu-id="dcac0-113">[Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="dcac0-113">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="dcac0-114">[宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="dcac0-114">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="dcac0-115">[スキーマでカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="dcac0-115">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="dcac0-116">[列挙の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="dcac0-116">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="dcac0-117">未宣言の Z セグメントの処理</span><span class="sxs-lookup"><span data-stu-id="dcac0-117">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
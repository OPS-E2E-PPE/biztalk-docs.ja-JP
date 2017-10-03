---
title: "スキーマにカスタムのテーブルを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Z tables [Z objects]
- Z objects, creating Z tables
- 2.X schemas, creating Z tables
ms.assetid: d6ab8ac9-a835-4ec0-9ddd-76ff267a3cbd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c3ce69e60517f90af4031bf76691a551afcbe2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-custom-tables-in-schemas"></a><span data-ttu-id="74740-102">スキーマのカスタム テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="74740-102">Creating Custom Tables in Schemas</span></span>
<span data-ttu-id="74740-103">カスタムのテーブルを作成するには、tablevalues_ で\<*バージョン*> .xsd 共通のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="74740-103">You can create a custom table in the tablevalues_\<*version*>.xsd common schema.</span></span> <span data-ttu-id="74740-104">既存のデータ型、基本データ型、またはテーブルで定義された列挙体のカスタムのテーブルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="74740-104">You can base a custom table on an existing data type, a base data type, or on an enumeration defined in a table.</span></span>  
  
### <a name="to-create-a-z-table"></a><span data-ttu-id="74740-105">Z テーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="74740-105">To create a Z table</span></span>  
  
1.  <span data-ttu-id="74740-106">ソリューション エクスプ ローラーで、共通のデータ型のスキーマ ファイルを開く **tablevalues_\<*バージョン*> * *、.xsd をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="74740-106">In Solution Explorer, open the common data-type schema file **tablevalues_\<*version*>.xsd**, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="74740-107">BizTalk エディターを右クリックして**HL7DefinedTables**、 をポイント**スキーマ ノードの挿入**、クリックして**子フィールド要素**です。</span><span class="sxs-lookup"><span data-stu-id="74740-107">In BizTalk Editor, right-click **HL7DefinedTables**, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
3.  <span data-ttu-id="74740-108">"Z"文字で始まるタグを持つテーブルを名前します。</span><span class="sxs-lookup"><span data-stu-id="74740-108">Name the table with a tag starting with the letter "Z".</span></span>  
  
4.  <span data-ttu-id="74740-109">プロパティ ウィンドウで、必要に応じて、特定のプロパティに対して使用値を入力します。</span><span class="sxs-lookup"><span data-stu-id="74740-109">In the Properties pane, type the values you want for specific properties, as needed.</span></span>  
  
5.  <span data-ttu-id="74740-110">プロパティ ペインで、テーブルに列挙体を関連付けるには次のように設定します**Derived By**に**制限**、をクリックして**列挙**、の省略記号(...)ボタンをクリック。**列挙体**、列挙エディタを格納する列挙を目的の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="74740-110">To associate an enumeration with the table, in the Properties pane, set **Derived By** to **Restriction**, click **Enumeration**, click the ellipsis (…) button for **Enumeration**, and then type the values that you want the enumeration to contain in the Enumeration Editor.</span></span> <span data-ttu-id="74740-111">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74740-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74740-112">参照</span><span class="sxs-lookup"><span data-stu-id="74740-112">See Also</span></span>  
 <span data-ttu-id="74740-113">[Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="74740-113">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="74740-114">[宣言されている Z セグメントを作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="74740-114">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="74740-115">[スキーマでカスタム データ型を作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="74740-115">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="74740-116">[列挙型を拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="74740-116">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="74740-117">宣言されていない Z セグメントの処理</span><span class="sxs-lookup"><span data-stu-id="74740-117">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)
---
title: テーブル値の一般的なスキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, table values
- common schemas
ms.assetid: 2421e150-1bae-43bd-aba3-6322c679b22b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f577b96f07daa6367a6e68550df441b9d355c5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286562"
---
# <a name="table-values-common-schemas"></a><span data-ttu-id="cf214-102">テーブル値の一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="cf214-102">Table Values Common Schemas</span></span>
<span data-ttu-id="cf214-103">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を生成、 **tablevalues_*\<バージョン\>*.xsd** HL7 バージョンごとに、ファイルし、のルートにあるファイルを見つけますHL7 バージョン固有のフォルダー。</span><span class="sxs-lookup"><span data-stu-id="cf214-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) generates the **tablevalues_*\<version\>*.xsd** file for each HL7 version, and locates the file at the root of the HL7 version-specific folder.</span></span> <span data-ttu-id="cf214-104">データ型の共通スキーマ ファイルでは、テーブル値の一般的なスキーマ ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="cf214-104">The data type common schema file references the table values common schema file.</span></span>  
  
 <span data-ttu-id="cf214-105">これらのテーブル内の値、列挙値の形式です。</span><span class="sxs-lookup"><span data-stu-id="cf214-105">Values in these tables are in the form of enumerations.</span></span> <span data-ttu-id="cf214-106">各列挙体は、メッセージ スキーマの 1 つまたは複数のフィールド内で許容される値を定義します。</span><span class="sxs-lookup"><span data-stu-id="cf214-106">Each enumeration defines the values that are acceptable within one or more fields of the message schemas.</span></span> <span data-ttu-id="cf214-107">テーブルは、スキーマを BizTalk エディターで開く、ノードをクリックし、確認メッセージのスキーマのノードに適用されますを参照してください、 **Base Data Type**プロパティ ペインでプロパティ。</span><span class="sxs-lookup"><span data-stu-id="cf214-107">You can see which table applies to a node of a message schema by opening the schema in BizTalk Editor, clicking a node, and looking at the **Base Data Type** property in the Properties pane.</span></span>  
  
 <span data-ttu-id="cf214-108">このノードに使用できる値は、ただし、メッセージ スキーマのノードのプロパティ ペインで、列挙型を表示して確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf214-108">You will not be able to see what the acceptable values for this node are, however, by viewing the enumeration in the Properties pane for the message-schema node.</span></span> <span data-ttu-id="cf214-109">テーブル値の一般的なスキーマ ファイルが列挙体を定義するためです。</span><span class="sxs-lookup"><span data-stu-id="cf214-109">This is because the table values common schema file defines the enumeration.</span></span> <span data-ttu-id="cf214-110">列挙体を表示する をクリックして**tablevalues_*\<バージョン\>*.xsd** 、スキーマ ツリーの BizTalk エディターとし、省略記号ボタンをクリックします (**.**)、プロパティ ペインで列挙型の行にボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf214-110">To view the enumerations, click **tablevalues_*\<version\>*.xsd** in the Schema tree in BizTalk Editor, and then click the ellipsis (**...**) button on the Enumeration row in the Properties pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf214-111">参照</span><span class="sxs-lookup"><span data-stu-id="cf214-111">See Also</span></span>  
 <span data-ttu-id="cf214-112">[HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="cf214-112">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="cf214-113">[データ型の一般的なスキーマ](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="cf214-113">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="cf214-114">セグメントの一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="cf214-114">Segments Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)
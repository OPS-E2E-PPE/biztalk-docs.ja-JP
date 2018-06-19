---
title: テーブルの一般的なスキーマ値 |Microsoft ドキュメント
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
ms.openlocfilehash: a55491f0a44bec6a5cd5eaf4fe120f693b3996c5
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25962040"
---
# <a name="table-values-common-schemas"></a><span data-ttu-id="e4cc3-102">テーブル値の一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="e4cc3-102">Table Values Common Schemas</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="e4cc3-103">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を生成、 **tablevalues_*\<バージョン\>*.xsd** HL7 バージョンごとに、ファイルを HL7 のルートにあるファイルを見つけますバージョン固有のフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e4cc3-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) generates the **tablevalues_*\<version\>*.xsd** file for each HL7 version, and locates the file at the root of the HL7 version-specific folder.</span></span> <span data-ttu-id="e4cc3-104">データ型の共通スキーマ ファイルは、テーブル値の共通スキーマ ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="e4cc3-104">The data type common schema file references the table values common schema file.</span></span>  
  
 <span data-ttu-id="e4cc3-105">これらのテーブル内の値、列挙値の形式です。</span><span class="sxs-lookup"><span data-stu-id="e4cc3-105">Values in these tables are in the form of enumerations.</span></span> <span data-ttu-id="e4cc3-106">列挙ごとでは、メッセージ スキーマの 1 つまたは複数のフィールドで許容される値を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4cc3-106">Each enumeration defines the values that are acceptable within one or more fields of the message schemas.</span></span> <span data-ttu-id="e4cc3-107">どのテーブルがスキーマを BizTalk エディターで開く、ノードをクリックしにあるメッセージ スキーマのノードに適用されますを参照してください、 **Base Data Type**プロパティ ペインでプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e4cc3-107">You can see which table applies to a node of a message schema by opening the schema in BizTalk Editor, clicking a node, and looking at the **Base Data Type** property in the Properties pane.</span></span>  
  
 <span data-ttu-id="e4cc3-108">このノードの使用可能な値は、ただし、メッセージ スキーマ ノードのプロパティ ペインで、列挙型を表示して表示できなきます。</span><span class="sxs-lookup"><span data-stu-id="e4cc3-108">You will not be able to see what the acceptable values for this node are, however, by viewing the enumeration in the Properties pane for the message-schema node.</span></span> <span data-ttu-id="e4cc3-109">これは、テーブル値の共通スキーマ ファイルには、列挙が定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="e4cc3-109">This is because the table values common schema file defines the enumeration.</span></span> <span data-ttu-id="e4cc3-110">列挙体を表示するクリックして**tablevalues_*\<バージョン\>*.xsd**スキーマ ツリーの BizTalk エディターで、クリックして、省略記号 (**.**) ボタン、プロパティ ウィンドウの行を列挙します。</span><span class="sxs-lookup"><span data-stu-id="e4cc3-110">To view the enumerations, click **tablevalues_*\<version\>*.xsd** in the Schema tree in BizTalk Editor, and then click the ellipsis (**...**) button on the Enumeration row in the Properties pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4cc3-111">参照</span><span class="sxs-lookup"><span data-stu-id="e4cc3-111">See Also</span></span>  
 <span data-ttu-id="e4cc3-112">[HL7 2.X の共通スキーマ ファイル](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="e4cc3-112">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="e4cc3-113">[一般的なスキーマのデータ型します。](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e4cc3-113">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="e4cc3-114">セグメントの一般的なスキーマ</span><span class="sxs-lookup"><span data-stu-id="e4cc3-114">Segments Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)
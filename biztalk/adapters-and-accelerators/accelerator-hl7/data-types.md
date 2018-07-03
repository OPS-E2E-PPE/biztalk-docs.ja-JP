---
title: データの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, messages
- messages, data types
ms.assetid: 7a758289-1629-48a0-843d-6f6773bd5ba6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a7b8d75be35be01e9c961d6bd054dcaed6d3aee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984675"
---
# <a name="data-types"></a><span data-ttu-id="061bd-102">データ型</span><span class="sxs-lookup"><span data-stu-id="061bd-102">Data Types</span></span>
<span data-ttu-id="061bd-103">データ型の仕様では、HL7 標準の複雑さをパーティション分割の重要なツール、HL7 フィールドのデータの内容を理解するため重要です。</span><span class="sxs-lookup"><span data-stu-id="061bd-103">The data type specification is an important tool for partitioning the complexity of the HL7 standard, and is critical to understanding the data contents of an HL7 field.</span></span> <span data-ttu-id="061bd-104">一部のデータ型は単純なと 1 つだけの要素を含んでいるし、一部は、多くのコンポーネントとサブコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="061bd-104">Some data types are simple and contain only one component, and some contain many components and subcomponents.</span></span> <span data-ttu-id="061bd-105">たとえば、PID.5 患者名では、バージョン 2.4 で XPN の入力データがあります。</span><span class="sxs-lookup"><span data-stu-id="061bd-105">For example, PID.5 Patient Name has the data type XPN in Version 2.4.</span></span> <span data-ttu-id="061bd-106">このデータ型には、英語の言語名の一般的な目盛り、たとえば、姓、名、ミドル ネーム、だけでなくサフィックス、プレフィックス、名前型コード、および名前の有効期間 (日) の範囲がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="061bd-106">This data type supports the common subdivisions of an English language name, for example, surname, first name, middle name, as well as suffix, prefix, name type code, and name validity (date) range.</span></span>  
  
 <span data-ttu-id="061bd-107">新しい HL7 のバージョンでは、追加できますがデータ型を削除できません。</span><span class="sxs-lookup"><span data-stu-id="061bd-107">In new HL7 versions, you can add but not remove data types.</span></span> <span data-ttu-id="061bd-108">新しいコンポーネントまたはサブコンポーネントを追加することで、データ型にコンテンツを追加する場合のみそれらをネストされている構造体の末尾に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="061bd-108">If you add content to a data type, by adding new components or subcomponents, you can only add them at the end of the structure within which they are nested.</span></span> <span data-ttu-id="061bd-109">場合によっては、HL7 組織は、既存のデータ型と新しいフォームをマージします。</span><span class="sxs-lookup"><span data-stu-id="061bd-109">In some cases, the HL7 organization merged existing data types to form new ones.</span></span> <span data-ttu-id="061bd-110">これが元のデータ型内のサブコンポーネントであった以前項目をサポートするために必要につながっています。</span><span class="sxs-lookup"><span data-stu-id="061bd-110">This led to the need to support items that were formerly subcomponents within the original data types.</span></span>  
  
 <span data-ttu-id="061bd-111">Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。</span><span class="sxs-lookup"><span data-stu-id="061bd-111">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="061bd-112"> 上のすべての HL7 バージョン V2.1 から標準のデータ型をサポートします。</span><span class="sxs-lookup"><span data-stu-id="061bd-112"> supports standard data types for all HL7 versions from V2.1 on.</span></span>  
  
- <span data-ttu-id="061bd-113">インターフェイスを開発するときに、適切な場所に、データ型を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="061bd-113">You can restrict data types where appropriate when developing interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="061bd-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="061bd-114">In This Section</span></span>  
  
-   [<span data-ttu-id="061bd-115">HL7 のデータ型 ID 2.1</span><span class="sxs-lookup"><span data-stu-id="061bd-115">Data Type ID in HL7 2.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)
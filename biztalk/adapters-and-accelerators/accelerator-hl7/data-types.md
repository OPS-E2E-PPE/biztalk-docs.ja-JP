---
title: データの種類 |Microsoft ドキュメント
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
ms.openlocfilehash: b8580b4f6c2a3f1a9f461b112bb4125f1a11ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204946"
---
# <a name="data-types"></a><span data-ttu-id="13daa-102">データ型</span><span class="sxs-lookup"><span data-stu-id="13daa-102">Data Types</span></span>
<span data-ttu-id="13daa-103">データ型の仕様では、HL7 標準の複雑さをパーティション分割に関する重要なツール、HL7 フィールドのデータの内容を理解するため重要です。</span><span class="sxs-lookup"><span data-stu-id="13daa-103">The data type specification is an important tool for partitioning the complexity of the HL7 standard, and is critical to understanding the data contents of an HL7 field.</span></span> <span data-ttu-id="13daa-104">一部のデータ型は、シンプルで、1 つだけの要素を含んでいるし、一部は、多くのコンポーネントとサブコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="13daa-104">Some data types are simple and contain only one component, and some contain many components and subcomponents.</span></span> <span data-ttu-id="13daa-105">たとえば、PID.5 患者の名前には、バージョン 2.4 で XPN を入力データがあります。</span><span class="sxs-lookup"><span data-stu-id="13daa-105">For example, PID.5 Patient Name has the data type XPN in Version 2.4.</span></span> <span data-ttu-id="13daa-106">このデータ型には、英語の言語名では、一般的な目盛り、たとえば、姓、名、ミドル ネーム、だけでなくサフィックス、プレフィックス、名の種類のコードおよび名の有効期間 (日) の範囲がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="13daa-106">This data type supports the common subdivisions of an English language name, for example, surname, first name, middle name, as well as suffix, prefix, name type code, and name validity (date) range.</span></span>  
  
 <span data-ttu-id="13daa-107">新しい HL7 バージョンを追加できますが、データ型を削除できません。</span><span class="sxs-lookup"><span data-stu-id="13daa-107">In new HL7 versions, you can add but not remove data types.</span></span> <span data-ttu-id="13daa-108">新しいコンポーネントまたはサブコンポーネントを追加することで、データ型にコンテンツを追加する場合のみそれらをネストされている構造体の末尾に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="13daa-108">If you add content to a data type, by adding new components or subcomponents, you can only add them at the end of the structure within which they are nested.</span></span> <span data-ttu-id="13daa-109">場合によってでは、HL7 組織は、既存のデータ型を新しいものを形成をマージします。</span><span class="sxs-lookup"><span data-stu-id="13daa-109">In some cases, the HL7 organization merged existing data types to form new ones.</span></span> <span data-ttu-id="13daa-110">元のデータ型内でこれらのサブコンポーネント以前なった項目をサポートするために必要に生じていました。</span><span class="sxs-lookup"><span data-stu-id="13daa-110">This led to the need to support items that were formerly subcomponents within the original data types.</span></span>  
  
 <span data-ttu-id="13daa-111">次の関数の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。</span><span class="sxs-lookup"><span data-stu-id="13daa-111">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="13daa-112">上のすべての HL7 バージョン V2.1 から標準のデータ型をサポートします。</span><span class="sxs-lookup"><span data-stu-id="13daa-112"> supports standard data types for all HL7 versions from V2.1 on.</span></span>  
  
-   <span data-ttu-id="13daa-113">インターフェイスを開発するときに、適切な場所に、データ型を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="13daa-113">You can restrict data types where appropriate when developing interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13daa-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="13daa-114">In This Section</span></span>  
  
-   [<span data-ttu-id="13daa-115">HL7 のデータ型の ID 2.1</span><span class="sxs-lookup"><span data-stu-id="13daa-115">Data Type ID in HL7 2.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/data-type-id-in-hl7.md)
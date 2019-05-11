---
title: HL7 のデータ型 ID |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data types, data type ID
- data types, messages
- messages, data types
ms.assetid: d1412886-ff0b-4333-b01e-1c3ae45240e2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f90b215857f0d0fea5e1bd899e1101b117b8ecbe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255597"
---
# <a name="data-type-id-in-hl7"></a><span data-ttu-id="0f2ad-102">HL7 のデータ型の ID</span><span class="sxs-lookup"><span data-stu-id="0f2ad-102">Data Type ID in HL7</span></span>
<span data-ttu-id="0f2ad-103">HL7 の V2.1 の場合は、データ型の ID は、未定義のデータ型のプレース ホルダーは。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-103">In the case of HL7 V2.1, the data type ID is a placeholder for undefined data types.</span></span> <span data-ttu-id="0f2ad-104">その使用法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-104">The following are examples of its usage:</span></span>  
  
- <span data-ttu-id="0f2ad-105">ST フィールドの形式でのデータ型は、SI (シーケンス ID) です。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-105">The data type in the form of an ST field is SI (Sequence ID).</span></span>  
  
- <span data-ttu-id="0f2ad-106">NM フィールドの形式でのデータ型は、複合フィールドです。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-106">The data type in the form of an NM field is composite fields.</span></span>  
  
  <span data-ttu-id="0f2ad-107">具体的には定義された複合データ型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-107">The following are examples of specifically defined composite data types:</span></span>  
  
- <span data-ttu-id="0f2ad-108">CK:チェック ディジット複合 ID。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-108">CK: Composite ID with check digit.</span></span> <span data-ttu-id="0f2ad-109">例 :</span><span class="sxs-lookup"><span data-stu-id="0f2ad-109">For example:</span></span>  
  
  ```  
  |128952^6^M11|  
  ```  
  
- <span data-ttu-id="0f2ad-110">CN:複合の ID 番号と名前です。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-110">CN: Composite ID number and name.</span></span> <span data-ttu-id="0f2ad-111">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-111">For example:</span></span>  
  
  ```  
  |12372^RIGGINS^JOHN^""^MD|  
  |12372|  
  |^RIGGINS^JOHN^""^MD|  
  ```  
  
- <span data-ttu-id="0f2ad-112">CQ:単位付きの複合数量です。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-112">CQ: Composite quantity with units.</span></span> <span data-ttu-id="0f2ad-113">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-113">For example:</span></span>  
  
  ```  
  |123.7^ML|  
  ```  
  
- <span data-ttu-id="0f2ad-114">CE:コード化された要素。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-114">CE: Coded element.</span></span> <span data-ttu-id="0f2ad-115">例 :</span><span class="sxs-lookup"><span data-stu-id="0f2ad-115">For example:</span></span>  
  
  ```  
  |54.21^Laparoscopy^I9C^42112^^AS4|  
  ```  
  
  <span data-ttu-id="0f2ad-116">このデータ型はローカライズし、サイト定義します。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-116">This data type is localized and site-defined.</span></span> <span data-ttu-id="0f2ad-117">さらに、HL7 V2.1 は提供されません、カバレッジの HL7 Access データベースでは、このデータ型。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-117">Additionally, HL7 V2.1 does not provide the coverage for this data type in the HL7 Access database.</span></span> <span data-ttu-id="0f2ad-118">Microsoft BizTalk Accelerator 用 HL7 スキーマを生成するため ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 V2.2 のデータ型が有効で、この情報を使用して、スキーマをビルドするいると見なします。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-118">For generating your schemas, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) assumes that the HL7 V2.2 data types are valid, and uses this information to build the schemas.</span></span> <span data-ttu-id="0f2ad-119">スキーマの使用量によって、適切なデータ型を使用する、CK、CQ、CE、ST、データ型を置き換える必要があることを意味 ^ SI、という具合です。</span><span class="sxs-lookup"><span data-stu-id="0f2ad-119">Depending on the usage in the schema, an appropriate data type must be used, meaning that the data type must be replaced with CK, CQ, CE, ST^SI, and so on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2ad-120">参照</span><span class="sxs-lookup"><span data-stu-id="0f2ad-120">See Also</span></span>  
 <span data-ttu-id="0f2ad-121">[データ型](../../adapters-and-accelerators/accelerator-hl7/data-types.md) </span><span class="sxs-lookup"><span data-stu-id="0f2ad-121">[Data Types](../../adapters-and-accelerators/accelerator-hl7/data-types.md) </span></span>  
 <span data-ttu-id="0f2ad-122">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0f2ad-122">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="0f2ad-123">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="0f2ad-123">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="0f2ad-124">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="0f2ad-124">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
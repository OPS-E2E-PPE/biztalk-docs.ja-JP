---
title: 反復可能なフィールド セグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, repeatable fields
- QPD
- Table Row Data (RDT)
- Query Parameter Definition (QPD)
- Segments table
- RDT
ms.assetid: 4c31cb56-21e5-4918-aaf6-67e8ceddd74f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5121952269715a27dcf7981e2ba44204fc5c856
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289910"
---
# <a name="repeatable-field-segments"></a><span data-ttu-id="d6598-102">反復可能なフィールド セグメント</span><span class="sxs-lookup"><span data-stu-id="d6598-102">Repeatable Field Segments</span></span>
<span data-ttu-id="d6598-103">HL7 の Access データベース内のセグメント テーブルの列が格納 (ADD、RDT、および QPD) セグメントの最後のフィールドを Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 反復可能として定義されています (**Last_field_repeatable**  =  **True**)。</span><span class="sxs-lookup"><span data-stu-id="d6598-103">The Segments table in the HL7 Access database contains a column for the last field of segments (ADD, RDT, and QPD) that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) defines as repeatable (**Last_field_repeatable** = **True**).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="d6598-104">追加はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d6598-104">does not support ADD.</span></span> <span data-ttu-id="d6598-105">ただし、RDT と QPD の両方がクエリのテーブルに存在して、テーブルの値で応答します。</span><span class="sxs-lookup"><span data-stu-id="d6598-105">However, both RDT and QPD are present to query tables and respond with table values.</span></span> <span data-ttu-id="d6598-106">次のサンプルではどのように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]これらの列を処理します。</span><span class="sxs-lookup"><span data-stu-id="d6598-106">The following sample demonstrates how [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] handles these columns.</span></span>  
  
 <span data-ttu-id="d6598-107">クライアントは、次のクエリを送信して、クライアントが設定して、即座に応答を要求することを示します**RCP-1-応答の優先順位**に"**は**"。</span><span class="sxs-lookup"><span data-stu-id="d6598-107">A client submits the following query and indicates that the client wants an immediate response by setting **RCP-1-Response priority** to "**I**":</span></span>  
  
```  
MSH|^&~\|PCR|Gen Hosp|PIMS||199811201400-0800||QBP^Q42^QBP_Q13|ACK9901|P|2.4||||||||  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR| |19980531|19990531|  
RCP|I|999^RD|  
RDF|3|PatientList^ST^20~PatientName^XPN^48~MedicationDispensed^ST^40~RXD.3^TS^26  
```  
  
 <span data-ttu-id="d6598-108">1 分後、次のメッセージで応答します。</span><span class="sxs-lookup"><span data-stu-id="d6598-108">The server responds one minute later with the following message:</span></span>  
  
```  
MSH|^&~\|PIMS|Gen Hosp|PCR||199811201401-0800||RTB^K42^RTB_K13|8858|P|2.3||||||||  
MSA|AA|8699|  
QAK|Q010|OK|Q42^Tabular Dispense History^HL7nnn|4  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR||19980531|19990531|  
RDF|7|PatientId^CX^20~PatientName^XPN^48~OrderControlCode^ID^2~ MedicationDispensed^CE^100~DispenseDate^TS^26~QuantityDispensed^NM^20~ OrderingProvider^XCN^120  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|525440345^Verapamil Hydrochloride 120 mg TAB^NDC |199805291115-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00182196901^VERAPAMIL HCL ER TAB 180MG ER^NDC |19980821-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00172409660^BACLOFEN 10MG TABS^NDC |199809221415-0700|10|88^Semmelweis^Samuel^^^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00054384163^THEOPHYLLINE 80MG/15ML SOLN^NDC|199810121145-0700|10|99^Lister^Lenora^^^DR^MD  
```  
  
 <span data-ttu-id="d6598-109">例から QPD と RDT が定義されているカスタム サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6598-109">From the example, you see that QPD and RDT are custom/site defined.</span></span> <span data-ttu-id="d6598-110">HL7 仕様では、次のように QPD と RDT のセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="d6598-110">The HL7 specification defines QPD and RDT segments as follows.</span></span>  
  
## <a name="qpd---query-parameter-definition"></a><span data-ttu-id="d6598-111">QPD - クエリ パラメーターの定義</span><span class="sxs-lookup"><span data-stu-id="d6598-111">QPD - Query Parameter Definition</span></span>  
 <span data-ttu-id="d6598-112">次の表では、HL7 仕様が QPD を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6598-112">The following table shows how the HL7 specification defines QPD.</span></span>  
  
|<span data-ttu-id="d6598-113">SEQ</span><span class="sxs-lookup"><span data-stu-id="d6598-113">SEQ</span></span>|<span data-ttu-id="d6598-114">LEN</span><span class="sxs-lookup"><span data-stu-id="d6598-114">LEN</span></span>|<span data-ttu-id="d6598-115">DT</span><span class="sxs-lookup"><span data-stu-id="d6598-115">DT</span></span>|<span data-ttu-id="d6598-116">オプトイン</span><span class="sxs-lookup"><span data-stu-id="d6598-116">OPT</span></span>|<span data-ttu-id="d6598-117">RP/#</span><span class="sxs-lookup"><span data-stu-id="d6598-117">RP/#</span></span>|<span data-ttu-id="d6598-118">TBL #</span><span class="sxs-lookup"><span data-stu-id="d6598-118">TBL#</span></span>|<span data-ttu-id="d6598-119">項目番号</span><span class="sxs-lookup"><span data-stu-id="d6598-119">ITEM#</span></span>|<span data-ttu-id="d6598-120">要素名</span><span class="sxs-lookup"><span data-stu-id="d6598-120">ELEMENT NAME</span></span>|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|<span data-ttu-id="d6598-121">1</span><span class="sxs-lookup"><span data-stu-id="d6598-121">1</span></span>|<span data-ttu-id="d6598-122">250</span><span class="sxs-lookup"><span data-stu-id="d6598-122">250</span></span>|<span data-ttu-id="d6598-123">CE</span><span class="sxs-lookup"><span data-stu-id="d6598-123">CE</span></span>|<span data-ttu-id="d6598-124">R</span><span class="sxs-lookup"><span data-stu-id="d6598-124">R</span></span>||<span data-ttu-id="d6598-125">0471</span><span class="sxs-lookup"><span data-stu-id="d6598-125">0471</span></span>|<span data-ttu-id="d6598-126">01375</span><span class="sxs-lookup"><span data-stu-id="d6598-126">01375</span></span>|<span data-ttu-id="d6598-127">メッセージ クエリ名</span><span class="sxs-lookup"><span data-stu-id="d6598-127">Message Query Name</span></span>|  
|<span data-ttu-id="d6598-128">2</span><span class="sxs-lookup"><span data-stu-id="d6598-128">2</span></span>|<span data-ttu-id="d6598-129">32</span><span class="sxs-lookup"><span data-stu-id="d6598-129">32</span></span>|<span data-ttu-id="d6598-130">ST</span><span class="sxs-lookup"><span data-stu-id="d6598-130">ST</span></span>|<span data-ttu-id="d6598-131">c</span><span class="sxs-lookup"><span data-stu-id="d6598-131">C</span></span>|||<span data-ttu-id="d6598-132">00696</span><span class="sxs-lookup"><span data-stu-id="d6598-132">00696</span></span>|<span data-ttu-id="d6598-133">クエリのタグ</span><span class="sxs-lookup"><span data-stu-id="d6598-133">Query Tag</span></span>|  
|<span data-ttu-id="d6598-134">3-n</span><span class="sxs-lookup"><span data-stu-id="d6598-134">3-n</span></span>|<span data-ttu-id="d6598-135">256</span><span class="sxs-lookup"><span data-stu-id="d6598-135">256</span></span>|<span data-ttu-id="d6598-136">不定</span><span class="sxs-lookup"><span data-stu-id="d6598-136">Varies</span></span>||||<span data-ttu-id="d6598-137">01435</span><span class="sxs-lookup"><span data-stu-id="d6598-137">01435</span></span>|<span data-ttu-id="d6598-138">ユーザーのパラメーターを連続するフィールド</span><span class="sxs-lookup"><span data-stu-id="d6598-138">User parameters in successive fields</span></span>|  
  
## <a name="rdt---table-row-data"></a><span data-ttu-id="d6598-139">RDT - テーブルの行データ</span><span class="sxs-lookup"><span data-stu-id="d6598-139">RDT - Table Row Data</span></span>  
 <span data-ttu-id="d6598-140">次の表では、HL7 仕様が RDT を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d6598-140">The following table shows how the HL7 specification defines RDT.</span></span>  
  
|<span data-ttu-id="d6598-141">SEQ</span><span class="sxs-lookup"><span data-stu-id="d6598-141">SEQ</span></span>|<span data-ttu-id="d6598-142">LEN</span><span class="sxs-lookup"><span data-stu-id="d6598-142">LEN</span></span>|<span data-ttu-id="d6598-143">DT</span><span class="sxs-lookup"><span data-stu-id="d6598-143">DT</span></span>|<span data-ttu-id="d6598-144">オプトイン</span><span class="sxs-lookup"><span data-stu-id="d6598-144">OPT</span></span>|<span data-ttu-id="d6598-145">RP/#</span><span class="sxs-lookup"><span data-stu-id="d6598-145">RP/#</span></span>|<span data-ttu-id="d6598-146">TBL #</span><span class="sxs-lookup"><span data-stu-id="d6598-146">TBL#</span></span>|<span data-ttu-id="d6598-147">項目番号</span><span class="sxs-lookup"><span data-stu-id="d6598-147">ITEM#</span></span>|<span data-ttu-id="d6598-148">要素名</span><span class="sxs-lookup"><span data-stu-id="d6598-148">ELEMENT NAME</span></span>|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|<span data-ttu-id="d6598-149">1 ~ n</span><span class="sxs-lookup"><span data-stu-id="d6598-149">1-n</span></span>|<span data-ttu-id="d6598-150">変数</span><span class="sxs-lookup"><span data-stu-id="d6598-150">Variable</span></span>|<span data-ttu-id="d6598-151">変数</span><span class="sxs-lookup"><span data-stu-id="d6598-151">Variable</span></span>|<span data-ttu-id="d6598-152">R</span><span class="sxs-lookup"><span data-stu-id="d6598-152">R</span></span>|||<span data-ttu-id="d6598-153">00703</span><span class="sxs-lookup"><span data-stu-id="d6598-153">00703</span></span>|<span data-ttu-id="d6598-154">列の値</span><span class="sxs-lookup"><span data-stu-id="d6598-154">Column Value</span></span>|  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="d6598-155">QPD と RDT を繰り返すことができるサイト定義の値として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="d6598-155">interprets QPD and RDT as site-defined values that can repeat.</span></span> <span data-ttu-id="d6598-156">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データ型およびその他の詳細が解決しない[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]QPD.3 および RDT.1、スキーマ内の文字列データ型として扱われます。</span><span class="sxs-lookup"><span data-stu-id="d6598-156">Since [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not fix the data types and other details, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] treats QPD.3 and RDT.1 as String data types in the schemas.</span></span> <span data-ttu-id="d6598-157">サイトの条件によってこれらのスキーマを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6598-157">You may have to modify these schemas depending on your own site conditions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6598-158">参照</span><span class="sxs-lookup"><span data-stu-id="d6598-158">See Also</span></span>  
 [<span data-ttu-id="d6598-159">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="d6598-159">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
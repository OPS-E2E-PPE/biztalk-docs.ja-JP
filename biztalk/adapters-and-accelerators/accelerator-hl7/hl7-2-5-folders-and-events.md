---
title: HL7 2.5 のフォルダーとイベント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 662ef767-5504-4ff5-8820-994e9cf674ea
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90f26c4506392d8ae0543fa140d8b1791dea0a29
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278033"
---
# <a name="hl7-25-folders-and-events"></a><span data-ttu-id="ab3be-102">HL7 2.5 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="ab3be-102">HL7 2.5 Folders and Events</span></span>
<span data-ttu-id="ab3be-103">次の表は、HL7 でエンコードされたメッセージの HL7 バージョン 2.5 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ab3be-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.5 folder for HL7-encoded messages.</span></span> <span data-ttu-id="ab3be-104">これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="ab3be-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="ab3be-105">サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab3be-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="ab3be-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="ab3be-106">Subfolder</span></span>|<span data-ttu-id="ab3be-107">イベント</span><span class="sxs-lookup"><span data-stu-id="ab3be-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="ab3be-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="ab3be-108">Patient Administration</span></span>|<span data-ttu-id="ab3be-109">A01 A62 K21 K24、Q21-Q24</span><span class="sxs-lookup"><span data-stu-id="ab3be-109">A01-A62,K21-K24,Q21-Q24</span></span>|  
|<span data-ttu-id="ab3be-110">人事管理</span><span class="sxs-lookup"><span data-stu-id="ab3be-110">Personnel Management</span></span>|<span data-ttu-id="ab3be-111">B01-B08,K25,Q25</span><span class="sxs-lookup"><span data-stu-id="ab3be-111">B01-B08,K25,Q25</span></span>|  
|<span data-ttu-id="ab3be-112">監視レポート</span><span class="sxs-lookup"><span data-stu-id="ab3be-112">Observation Reporting</span></span>|<span data-ttu-id="ab3be-113">C01-C12,P07-P09,R01-R02,R04,R21-R24,R30-R32</span><span class="sxs-lookup"><span data-stu-id="ab3be-113">C01-C12,P07-P09,R01-R02,R04,R21-R24,R30-R32</span></span>|  
|<span data-ttu-id="ab3be-114">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="ab3be-114">Patient Referral</span></span>|<span data-ttu-id="ab3be-115">I01 I15</span><span class="sxs-lookup"><span data-stu-id="ab3be-115">I01-I15</span></span>|  
|<span data-ttu-id="ab3be-116">Query</span><span class="sxs-lookup"><span data-stu-id="ab3be-116">Query</span></span>|<span data-ttu-id="ab3be-117">J01、J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09、Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="ab3be-117">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09,Q11,Q13,Q15-Q17, R07-R09,Z75-Z99</span></span>|  
|<span data-ttu-id="ab3be-118">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="ab3be-118">Master Files</span></span>|<span data-ttu-id="ab3be-119">M01 M12</span><span class="sxs-lookup"><span data-stu-id="ab3be-119">M01-M12</span></span>|  
|<span data-ttu-id="ab3be-120">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="ab3be-120">Order Entry</span></span>|<span data-ttu-id="ab3be-121">O01 O36、Q06、Q26 Q31、RAR、RDR、RER、RGR、権限が必要です、V01 V04、Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="ab3be-121">O01-O36,Q06,Q26-Q31,RAR,RDR,RER,RGR,ROR,V01-V04,Z73-Z74</span></span>|  
|<span data-ttu-id="ab3be-122">アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="ab3be-122">Application Management</span></span>|<span data-ttu-id="ab3be-123">N01 N02</span><span class="sxs-lookup"><span data-stu-id="ab3be-123">N01-N02</span></span>|  
|<span data-ttu-id="ab3be-124">財務管理</span><span class="sxs-lookup"><span data-stu-id="ab3be-124">Financial Management</span></span>|<span data-ttu-id="ab3be-125">P01 P03、P05-06、P10 P12</span><span class="sxs-lookup"><span data-stu-id="ab3be-125">P01-P03,P05-06,P10-P12</span></span>|  
|<span data-ttu-id="ab3be-126">患者のケア</span><span class="sxs-lookup"><span data-stu-id="ab3be-126">Patient Care</span></span>|<span data-ttu-id="ab3be-127">PC1 PC9 PCA PCH PCJ、PCL</span><span class="sxs-lookup"><span data-stu-id="ab3be-127">PC1-PC9,PCA-PCH,PCJ,PCL</span></span>|  
|<span data-ttu-id="ab3be-128">スケジューリング</span><span class="sxs-lookup"><span data-stu-id="ab3be-128">Scheduling</span></span>|<span data-ttu-id="ab3be-129">S01 S26</span><span class="sxs-lookup"><span data-stu-id="ab3be-129">S01-S26</span></span>|  
|<span data-ttu-id="ab3be-130">医療記録の管理</span><span class="sxs-lookup"><span data-stu-id="ab3be-130">Medical Records/Information Management</span></span>|<span data-ttu-id="ab3be-131">T01 T12</span><span class="sxs-lookup"><span data-stu-id="ab3be-131">T01-T12</span></span>|  
|<span data-ttu-id="ab3be-132">臨床試験の自動化</span><span class="sxs-lookup"><span data-stu-id="ab3be-132">Clinical Laboratory Automation</span></span>|<span data-ttu-id="ab3be-133">U01 U13</span><span class="sxs-lookup"><span data-stu-id="ab3be-133">U01-U13</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab3be-134">参照</span><span class="sxs-lookup"><span data-stu-id="ab3be-134">See Also</span></span>  
 <span data-ttu-id="ab3be-135">[HL7 2.X のサブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="ab3be-135">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="ab3be-136">[HL7 2.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="ab3be-136">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="ab3be-137">[HL7 2.2 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="ab3be-137">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="ab3be-138">[HL7 2.3 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="ab3be-138">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="ab3be-139">[HL7 2.3.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="ab3be-139">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="ab3be-140">[HL7 2.4 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="ab3be-140">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="ab3be-141">HL7 2.5 のフォルダーとイベント&#91;hl7&#93;</span><span class="sxs-lookup"><span data-stu-id="ab3be-141">HL7 2.5 Folders and Events &#91;hl7&#93;</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
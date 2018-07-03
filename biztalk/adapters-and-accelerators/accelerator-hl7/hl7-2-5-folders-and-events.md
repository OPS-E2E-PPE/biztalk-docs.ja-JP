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
ms.openlocfilehash: 66bcd4c6dd5acbe8a6d2f649e387da8177c9618c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992803"
---
# <a name="hl7-25-folders-and-events"></a><span data-ttu-id="f1db5-102">HL7 2.5 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="f1db5-102">HL7 2.5 Folders and Events</span></span>
<span data-ttu-id="f1db5-103">次の表は、HL7 でエンコードされたメッセージの HL7 バージョン 2.5 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f1db5-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.5 folder for HL7-encoded messages.</span></span> <span data-ttu-id="f1db5-104">これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="f1db5-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="f1db5-105">サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1db5-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="f1db5-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="f1db5-106">Subfolder</span></span>|<span data-ttu-id="f1db5-107">イベント</span><span class="sxs-lookup"><span data-stu-id="f1db5-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="f1db5-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="f1db5-108">Patient Administration</span></span>|<span data-ttu-id="f1db5-109">A01 A62 K21 K24、Q21-Q24</span><span class="sxs-lookup"><span data-stu-id="f1db5-109">A01-A62,K21-K24,Q21-Q24</span></span>|  
|<span data-ttu-id="f1db5-110">人事管理</span><span class="sxs-lookup"><span data-stu-id="f1db5-110">Personnel Management</span></span>|<span data-ttu-id="f1db5-111">B01 B08 K25、Q25</span><span class="sxs-lookup"><span data-stu-id="f1db5-111">B01-B08,K25,Q25</span></span>|  
|<span data-ttu-id="f1db5-112">監視レポート</span><span class="sxs-lookup"><span data-stu-id="f1db5-112">Observation Reporting</span></span>|<span data-ttu-id="f1db5-113">C01-C12,P07-P09,R01-R02,R04,R21-R24,R30-R32</span><span class="sxs-lookup"><span data-stu-id="f1db5-113">C01-C12,P07-P09,R01-R02,R04,R21-R24,R30-R32</span></span>|  
|<span data-ttu-id="f1db5-114">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="f1db5-114">Patient Referral</span></span>|<span data-ttu-id="f1db5-115">I01 I15</span><span class="sxs-lookup"><span data-stu-id="f1db5-115">I01-I15</span></span>|  
|<span data-ttu-id="f1db5-116">Query</span><span class="sxs-lookup"><span data-stu-id="f1db5-116">Query</span></span>|<span data-ttu-id="f1db5-117">J01、J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09、Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="f1db5-117">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09,Q11,Q13,Q15-Q17, R07-R09,Z75-Z99</span></span>|  
|<span data-ttu-id="f1db5-118">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="f1db5-118">Master Files</span></span>|<span data-ttu-id="f1db5-119">M01 M12</span><span class="sxs-lookup"><span data-stu-id="f1db5-119">M01-M12</span></span>|  
|<span data-ttu-id="f1db5-120">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="f1db5-120">Order Entry</span></span>|<span data-ttu-id="f1db5-121">O01 O36、Q06、Q26 Q31、RAR、RDR、RER、RGR、権限が必要です、V01 V04、Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="f1db5-121">O01-O36,Q06,Q26-Q31,RAR,RDR,RER,RGR,ROR,V01-V04,Z73-Z74</span></span>|  
|<span data-ttu-id="f1db5-122">アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="f1db5-122">Application Management</span></span>|<span data-ttu-id="f1db5-123">N01 N02</span><span class="sxs-lookup"><span data-stu-id="f1db5-123">N01-N02</span></span>|  
|<span data-ttu-id="f1db5-124">財務管理</span><span class="sxs-lookup"><span data-stu-id="f1db5-124">Financial Management</span></span>|<span data-ttu-id="f1db5-125">P01 P03、P05-06、P10 P12</span><span class="sxs-lookup"><span data-stu-id="f1db5-125">P01-P03,P05-06,P10-P12</span></span>|  
|<span data-ttu-id="f1db5-126">患者のケア</span><span class="sxs-lookup"><span data-stu-id="f1db5-126">Patient Care</span></span>|<span data-ttu-id="f1db5-127">PC1 PC9 PCA PCH PCJ、PCL</span><span class="sxs-lookup"><span data-stu-id="f1db5-127">PC1-PC9,PCA-PCH,PCJ,PCL</span></span>|  
|<span data-ttu-id="f1db5-128">スケジューリング</span><span class="sxs-lookup"><span data-stu-id="f1db5-128">Scheduling</span></span>|<span data-ttu-id="f1db5-129">S01 S26</span><span class="sxs-lookup"><span data-stu-id="f1db5-129">S01-S26</span></span>|  
|<span data-ttu-id="f1db5-130">医療記録の管理</span><span class="sxs-lookup"><span data-stu-id="f1db5-130">Medical Records/Information Management</span></span>|<span data-ttu-id="f1db5-131">T01 T12</span><span class="sxs-lookup"><span data-stu-id="f1db5-131">T01-T12</span></span>|  
|<span data-ttu-id="f1db5-132">臨床試験の自動化</span><span class="sxs-lookup"><span data-stu-id="f1db5-132">Clinical Laboratory Automation</span></span>|<span data-ttu-id="f1db5-133">U01 U13</span><span class="sxs-lookup"><span data-stu-id="f1db5-133">U01-U13</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1db5-134">参照</span><span class="sxs-lookup"><span data-stu-id="f1db5-134">See Also</span></span>  
 <span data-ttu-id="f1db5-135">[HL7 2.X のサブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f1db5-135">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="f1db5-136">[HL7 2.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f1db5-136">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="f1db5-137">[HL7 2.2 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f1db5-137">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="f1db5-138">[HL7 2.3 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f1db5-138">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="f1db5-139">[HL7 2.3.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f1db5-139">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="f1db5-140">[HL7 2.4 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f1db5-140">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="f1db5-141">HL7 2.5 のフォルダーとイベント&#91;hl7&#93;</span><span class="sxs-lookup"><span data-stu-id="f1db5-141">HL7 2.5 Folders and Events &#91;hl7&#93;</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
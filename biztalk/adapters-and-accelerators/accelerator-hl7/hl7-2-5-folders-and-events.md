---
title: "HL7 2.5 フォルダーとイベント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 662ef767-5504-4ff5-8820-994e9cf674ea
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdb229e2f8adf58397babf637a696bc2437ab626
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-25-folders-and-events"></a><span data-ttu-id="b1cd3-102">HL7 2.5 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="b1cd3-102">HL7 2.5 Folders and Events</span></span>
<span data-ttu-id="b1cd3-103">次の表は、HL7 でエンコードされたメッセージ HL7 バージョン 2.5 フォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b1cd3-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.5 folder for HL7-encoded messages.</span></span> <span data-ttu-id="b1cd3-104">これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="b1cd3-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="b1cd3-105">サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1cd3-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="b1cd3-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="b1cd3-106">Subfolder</span></span>|<span data-ttu-id="b1cd3-107">イベント</span><span class="sxs-lookup"><span data-stu-id="b1cd3-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="b1cd3-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="b1cd3-108">Patient Administration</span></span>|<span data-ttu-id="b1cd3-109">A01 A62、K21 K24、Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="b1cd3-109">A01-A62,K21-K24,Q21-Q24</span></span>|  
|<span data-ttu-id="b1cd3-110">人事管理</span><span class="sxs-lookup"><span data-stu-id="b1cd3-110">Personnel Management</span></span>|<span data-ttu-id="b1cd3-111">B01 B08、K25、Q25</span><span class="sxs-lookup"><span data-stu-id="b1cd3-111">B01-B08,K25,Q25</span></span>|  
|<span data-ttu-id="b1cd3-112">監視レポート</span><span class="sxs-lookup"><span data-stu-id="b1cd3-112">Observation Reporting</span></span>|<span data-ttu-id="b1cd3-113">C01-C12,P07-P09,R01-R02,R04,R21-R24,R30-R32</span><span class="sxs-lookup"><span data-stu-id="b1cd3-113">C01-C12,P07-P09,R01-R02,R04,R21-R24,R30-R32</span></span>|  
|<span data-ttu-id="b1cd3-114">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="b1cd3-114">Patient Referral</span></span>|<span data-ttu-id="b1cd3-115">I01 I15</span><span class="sxs-lookup"><span data-stu-id="b1cd3-115">I01-I15</span></span>|  
|<span data-ttu-id="b1cd3-116">Query</span><span class="sxs-lookup"><span data-stu-id="b1cd3-116">Query</span></span>|<span data-ttu-id="b1cd3-117">J01 J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09 Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="b1cd3-117">J01,J02,K11,K13,K15, Q01-Q05, Q07-Q09,Q11,Q13,Q15-Q17, R07-R09,Z75-Z99</span></span>|  
|<span data-ttu-id="b1cd3-118">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="b1cd3-118">Master Files</span></span>|<span data-ttu-id="b1cd3-119">M01 M12</span><span class="sxs-lookup"><span data-stu-id="b1cd3-119">M01-M12</span></span>|  
|<span data-ttu-id="b1cd3-120">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="b1cd3-120">Order Entry</span></span>|<span data-ttu-id="b1cd3-121">O01 O36 Q06、Q26 Q31、RAR、RDR、RER、RGR、権限が必要です、V01 V04 Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="b1cd3-121">O01-O36,Q06,Q26-Q31,RAR,RDR,RER,RGR,ROR,V01-V04,Z73-Z74</span></span>|  
|<span data-ttu-id="b1cd3-122">アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="b1cd3-122">Application Management</span></span>|<span data-ttu-id="b1cd3-123">N01 N02</span><span class="sxs-lookup"><span data-stu-id="b1cd3-123">N01-N02</span></span>|  
|<span data-ttu-id="b1cd3-124">財務管理</span><span class="sxs-lookup"><span data-stu-id="b1cd3-124">Financial Management</span></span>|<span data-ttu-id="b1cd3-125">P01 P03、P05-06、P10 P12</span><span class="sxs-lookup"><span data-stu-id="b1cd3-125">P01-P03,P05-06,P10-P12</span></span>|  
|<span data-ttu-id="b1cd3-126">治療</span><span class="sxs-lookup"><span data-stu-id="b1cd3-126">Patient Care</span></span>|<span data-ttu-id="b1cd3-127">PC1 PC9、PCA PCH、PCJ、PCL</span><span class="sxs-lookup"><span data-stu-id="b1cd3-127">PC1-PC9,PCA-PCH,PCJ,PCL</span></span>|  
|<span data-ttu-id="b1cd3-128">スケジューリング</span><span class="sxs-lookup"><span data-stu-id="b1cd3-128">Scheduling</span></span>|<span data-ttu-id="b1cd3-129">S01 S26</span><span class="sxs-lookup"><span data-stu-id="b1cd3-129">S01-S26</span></span>|  
|<span data-ttu-id="b1cd3-130">医療レコード/Information Management</span><span class="sxs-lookup"><span data-stu-id="b1cd3-130">Medical Records/Information Management</span></span>|<span data-ttu-id="b1cd3-131">T01 T12 が同時</span><span class="sxs-lookup"><span data-stu-id="b1cd3-131">T01-T12</span></span>|  
|<span data-ttu-id="b1cd3-132">医療研究所のオートメーション</span><span class="sxs-lookup"><span data-stu-id="b1cd3-132">Clinical Laboratory Automation</span></span>|<span data-ttu-id="b1cd3-133">U01 U13</span><span class="sxs-lookup"><span data-stu-id="b1cd3-133">U01-U13</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1cd3-134">参照</span><span class="sxs-lookup"><span data-stu-id="b1cd3-134">See Also</span></span>  
 <span data-ttu-id="b1cd3-135">[HL7 2.X サブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd3-135">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="b1cd3-136">[HL7 2.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd3-136">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="b1cd3-137">[HL7 2.2 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd3-137">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="b1cd3-138">[HL7 2.3 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd3-138">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="b1cd3-139">[HL7 2.3.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd3-139">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="b1cd3-140">[HL7 2.4 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b1cd3-140">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="b1cd3-141">HL7 2.5 フォルダーとイベント &#91; hl7 &#93;</span><span class="sxs-lookup"><span data-stu-id="b1cd3-141">HL7 2.5 Folders and Events &#91;hl7&#93;</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
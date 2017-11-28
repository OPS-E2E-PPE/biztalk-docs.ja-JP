---
title: "HL7 2.4 フォルダーとイベント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HL7, default sub-folders
- events, 2.X versions
- HL7, events
ms.assetid: c8855311-40c7-4338-ba07-5112c253fafd
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9196b0b69eb3730de8ad3ef383a1cde8564e5002
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-24-folders-and-events"></a><span data-ttu-id="09358-102">HL7 2.4 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="09358-102">HL7 2.4 Folders and Events</span></span>
<span data-ttu-id="09358-103">次の表は、HL7 でエンコードされたメッセージ HL7 バージョン 2.4 フォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="09358-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.4 folder for HL7-encoded messages.</span></span> <span data-ttu-id="09358-104">これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="09358-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="09358-105">サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="09358-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="09358-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="09358-106">Subfolder</span></span>|<span data-ttu-id="09358-107">イベント</span><span class="sxs-lookup"><span data-stu-id="09358-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="09358-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="09358-108">Patient Administration</span></span>|<span data-ttu-id="09358-109">A01 A62、K21 K24、Q21 Q24</span><span class="sxs-lookup"><span data-stu-id="09358-109">A01-A62, K21-K24,Q21-Q24</span></span>|  
|<span data-ttu-id="09358-110">人事管理</span><span class="sxs-lookup"><span data-stu-id="09358-110">Personnel Management</span></span>|<span data-ttu-id="09358-111">B01 B06、K25、Q25</span><span class="sxs-lookup"><span data-stu-id="09358-111">B01-B06, K25,Q25</span></span>|  
|<span data-ttu-id="09358-112">監視レポート</span><span class="sxs-lookup"><span data-stu-id="09358-112">Observation Reporting</span></span>|<span data-ttu-id="09358-113">C01 C12、P07 P09、R01 R02、R04、R21、W01 W02</span><span class="sxs-lookup"><span data-stu-id="09358-113">C01-C12, P07-P09, R01-R02,R04, R21, W01-W02</span></span>|  
|<span data-ttu-id="09358-114">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="09358-114">Patient Referral</span></span>|<span data-ttu-id="09358-115">I01 I15</span><span class="sxs-lookup"><span data-stu-id="09358-115">I01-I15</span></span>|  
|<span data-ttu-id="09358-116">Query</span><span class="sxs-lookup"><span data-stu-id="09358-116">Query</span></span>|<span data-ttu-id="09358-117">J01 J02、K11、K13、K15、Q01 Q05、Q07 Q09、Q11、Q13、Q15 Q17、R07 R09 Z75 Z99</span><span class="sxs-lookup"><span data-stu-id="09358-117">J01,J02,K11,K13,K15,  Q01-Q05, Q07-Q09, Q11,Q13,Q15-Q17, R07-R09, Z75-Z99</span></span>|  
|<span data-ttu-id="09358-118">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="09358-118">Master Files</span></span>|<span data-ttu-id="09358-119">M01 M12 の MFA</span><span class="sxs-lookup"><span data-stu-id="09358-119">M01-M12, MFA</span></span>|  
|<span data-ttu-id="09358-120">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="09358-120">Order Entry</span></span>|<span data-ttu-id="09358-121">O01 O22 Q06、Q26 Q30、RAR、RDR、RER、RGR、権限が必要です、V01 V04 Z73 Z74</span><span class="sxs-lookup"><span data-stu-id="09358-121">O01-O22, Q06, Q26-Q30, RAR,RDR,RER,RGR,ROR, V01-V04, Z73- Z74</span></span>|  
|<span data-ttu-id="09358-122">アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="09358-122">Application Management</span></span>|<span data-ttu-id="09358-123">N01 N02</span><span class="sxs-lookup"><span data-stu-id="09358-123">N01-N02</span></span>|  
|<span data-ttu-id="09358-124">財務管理</span><span class="sxs-lookup"><span data-stu-id="09358-124">Financial Management</span></span>|<span data-ttu-id="09358-125">P01 P06、P10</span><span class="sxs-lookup"><span data-stu-id="09358-125">P01-P06, P10</span></span>|  
|<span data-ttu-id="09358-126">治療</span><span class="sxs-lookup"><span data-stu-id="09358-126">Patient Care</span></span>|<span data-ttu-id="09358-127">PC1 PCH、PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="09358-127">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="09358-128">スケジューリング</span><span class="sxs-lookup"><span data-stu-id="09358-128">Scheduling</span></span>|<span data-ttu-id="09358-129">S01 S26</span><span class="sxs-lookup"><span data-stu-id="09358-129">S01-S26</span></span>|  
|<span data-ttu-id="09358-130">医療レコード/Information Management</span><span class="sxs-lookup"><span data-stu-id="09358-130">Medical Records/Information Management</span></span>|<span data-ttu-id="09358-131">T01 T12 が同時</span><span class="sxs-lookup"><span data-stu-id="09358-131">T01-T12</span></span>|  
|<span data-ttu-id="09358-132">医療研究所のオートメーション</span><span class="sxs-lookup"><span data-stu-id="09358-132">Clinical Laboratory Automation</span></span>|<span data-ttu-id="09358-133">U01 U13</span><span class="sxs-lookup"><span data-stu-id="09358-133">U01-U13</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09358-134">参照</span><span class="sxs-lookup"><span data-stu-id="09358-134">See Also</span></span>  
 <span data-ttu-id="09358-135">[HL7 2.X サブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="09358-135">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="09358-136">[HL7 2.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="09358-136">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="09358-137">[HL7 2.2 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="09358-137">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="09358-138">[HL7 2.3 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="09358-138">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="09358-139">[HL7 2.3.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="09358-139">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 [<span data-ttu-id="09358-140">HL7 2.5 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="09358-140">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
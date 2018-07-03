---
title: HL7 2.3 のフォルダーとイベント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, default sub-folders
- events, 2.X versions
- HL7, events
ms.assetid: 555a8620-a714-4102-80ba-1424d60387bf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f5df624fa1de08844fb1076adbc5e6d2ff08720
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992051"
---
# <a name="hl7-23-folders-and-events"></a><span data-ttu-id="0968b-102">HL7 2.3 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="0968b-102">HL7 2.3 Folders and Events</span></span>
<span data-ttu-id="0968b-103">次の表は、HL7 でエンコードされたメッセージの HL7 バージョン 2.3 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0968b-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3 folder for HL7-encoded messages.</span></span> <span data-ttu-id="0968b-104">これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="0968b-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="0968b-105">サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="0968b-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="0968b-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="0968b-106">Subfolder</span></span>|<span data-ttu-id="0968b-107">イベント</span><span class="sxs-lookup"><span data-stu-id="0968b-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="0968b-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="0968b-108">Patient Administration</span></span>|<span data-ttu-id="0968b-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="0968b-109">A01-A51</span></span>|  
|<span data-ttu-id="0968b-110">監視レポート</span><span class="sxs-lookup"><span data-stu-id="0968b-110">Observation Reporting</span></span>|<span data-ttu-id="0968b-111">C01 C12 P07 P09、R01-R06、W01 W02</span><span class="sxs-lookup"><span data-stu-id="0968b-111">C01-C12, P07-P09, R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="0968b-112">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="0968b-112">Patient Referral</span></span>|<span data-ttu-id="0968b-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="0968b-113">I01-I15</span></span>|  
|<span data-ttu-id="0968b-114">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="0968b-114">Master File</span></span>|<span data-ttu-id="0968b-115">M01 M11</span><span class="sxs-lookup"><span data-stu-id="0968b-115">M01-M11</span></span>|  
|<span data-ttu-id="0968b-116">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="0968b-116">Order Entry</span></span>|<span data-ttu-id="0968b-117">O01 O02、Q06、RAR、RDR、RER、RGR、権限が必要です、V01 V04</span><span class="sxs-lookup"><span data-stu-id="0968b-117">O01-O02,Q06, RAR,RDR,RER,RGR,ROR, V01-V04</span></span>|  
|<span data-ttu-id="0968b-118">財務管理</span><span class="sxs-lookup"><span data-stu-id="0968b-118">Financial Management</span></span>|<span data-ttu-id="0968b-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="0968b-119">P01-P06</span></span>|  
|<span data-ttu-id="0968b-120">患者のケア</span><span class="sxs-lookup"><span data-stu-id="0968b-120">Patient Care</span></span>|<span data-ttu-id="0968b-121">PC1 PCH PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="0968b-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="0968b-122">Query</span><span class="sxs-lookup"><span data-stu-id="0968b-122">Query</span></span>|<span data-ttu-id="0968b-123">CNQ、Q01 Q03、Q05</span><span class="sxs-lookup"><span data-stu-id="0968b-123">CNQ, Q01-Q03, Q05</span></span>|  
|<span data-ttu-id="0968b-124">スケジューリング</span><span class="sxs-lookup"><span data-stu-id="0968b-124">Scheduling</span></span>|<span data-ttu-id="0968b-125">S01 S26</span><span class="sxs-lookup"><span data-stu-id="0968b-125">S01-S26</span></span>|  
|<span data-ttu-id="0968b-126">医療記録、および情報の管理</span><span class="sxs-lookup"><span data-stu-id="0968b-126">Medical Records and Information Management</span></span>|<span data-ttu-id="0968b-127">T01 T12</span><span class="sxs-lookup"><span data-stu-id="0968b-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0968b-128">参照</span><span class="sxs-lookup"><span data-stu-id="0968b-128">See Also</span></span>  
 <span data-ttu-id="0968b-129">[HL7 2.X のサブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="0968b-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="0968b-130">[HL7 2.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="0968b-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="0968b-131">[HL7 2.2 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="0968b-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="0968b-132">[HL7 2.3.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="0968b-132">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="0968b-133">[HL7 2.4 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="0968b-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="0968b-134">HL7 2.5 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="0968b-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
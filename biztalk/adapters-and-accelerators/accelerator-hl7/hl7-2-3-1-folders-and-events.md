---
title: HL7 2.3.1 のフォルダーとイベント |Microsoft Docs
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
ms.assetid: 5cab1b7e-fdce-4b4b-bbd6-1da67fcf6a74
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c827cf38af1d12d2e8b0a1f7ee3521e1fd894029
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65269064"
---
# <a name="hl7-231-folders-and-events"></a><span data-ttu-id="bbf5a-102">HL7 2.3.1 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="bbf5a-102">HL7 2.3.1 Folders and Events</span></span>
<span data-ttu-id="bbf5a-103">次の表は、HL7 でエンコードされたメッセージの HL7 version 2.3.1 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="bbf5a-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for HL7-encoded messages.</span></span> <span data-ttu-id="bbf5a-104">これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="bbf5a-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="bbf5a-105">サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbf5a-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="bbf5a-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="bbf5a-106">Subfolder</span></span>|<span data-ttu-id="bbf5a-107">イベント</span><span class="sxs-lookup"><span data-stu-id="bbf5a-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="bbf5a-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="bbf5a-108">Patient Administration</span></span>|<span data-ttu-id="bbf5a-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="bbf5a-109">A01-A51</span></span>|  
|<span data-ttu-id="bbf5a-110">監視レポート</span><span class="sxs-lookup"><span data-stu-id="bbf5a-110">Observation Reporting</span></span>|<span data-ttu-id="bbf5a-111">C01 C12 P06 P09、R01-R06、W01 W02</span><span class="sxs-lookup"><span data-stu-id="bbf5a-111">C01-C12,P06-P09,R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="bbf5a-112">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="bbf5a-112">Patient Referral</span></span>|<span data-ttu-id="bbf5a-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="bbf5a-113">I01-I15</span></span>|  
|<span data-ttu-id="bbf5a-114">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="bbf5a-114">Master Files</span></span>|<span data-ttu-id="bbf5a-115">M01 M11、MFA</span><span class="sxs-lookup"><span data-stu-id="bbf5a-115">M01-M11, MFA</span></span>|  
|<span data-ttu-id="bbf5a-116">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="bbf5a-116">Order Entry</span></span>|<span data-ttu-id="bbf5a-117">O01 O02、Q06、R0R、RAR、RDR、RER、RGR、V01 V04</span><span class="sxs-lookup"><span data-stu-id="bbf5a-117">O01-O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="bbf5a-118">財務管理</span><span class="sxs-lookup"><span data-stu-id="bbf5a-118">Financial Management</span></span>|<span data-ttu-id="bbf5a-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="bbf5a-119">P01-P06</span></span>|  
|<span data-ttu-id="bbf5a-120">患者のケア</span><span class="sxs-lookup"><span data-stu-id="bbf5a-120">Patient Care</span></span>|<span data-ttu-id="bbf5a-121">PC1 PCH PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="bbf5a-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="bbf5a-122">Query</span><span class="sxs-lookup"><span data-stu-id="bbf5a-122">Query</span></span>|<span data-ttu-id="bbf5a-123">CNQ、Q01 Q05、Q07-Q09、R07 R09</span><span class="sxs-lookup"><span data-stu-id="bbf5a-123">CNQ, Q01-Q05, Q07-Q09, R07-R09</span></span>|  
|<span data-ttu-id="bbf5a-124">[スケジュール]</span><span class="sxs-lookup"><span data-stu-id="bbf5a-124">Schedule</span></span>|<span data-ttu-id="bbf5a-125">S01 S26</span><span class="sxs-lookup"><span data-stu-id="bbf5a-125">S01-S26</span></span>|  
|<span data-ttu-id="bbf5a-126">医療記録の管理</span><span class="sxs-lookup"><span data-stu-id="bbf5a-126">Medical Records/Information Management</span></span>|<span data-ttu-id="bbf5a-127">T01 T12</span><span class="sxs-lookup"><span data-stu-id="bbf5a-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbf5a-128">参照</span><span class="sxs-lookup"><span data-stu-id="bbf5a-128">See Also</span></span>  
 <span data-ttu-id="bbf5a-129">[HL7 2.X のサブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="bbf5a-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="bbf5a-130">[HL7 2.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="bbf5a-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="bbf5a-131">[HL7 2.2 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="bbf5a-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="bbf5a-132">[HL7 2.3 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="bbf5a-132">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="bbf5a-133">[HL7 2.4 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="bbf5a-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="bbf5a-134">HL7 2.5 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="bbf5a-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
---
title: "HL7 2.3.1 フォルダーとイベント |Microsoft ドキュメント"
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
ms.assetid: 5cab1b7e-fdce-4b4b-bbd6-1da67fcf6a74
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad51a024348c12c4097af29419698ced7c9c0c85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-231-folders-and-events"></a><span data-ttu-id="36e23-102">HL7 2.3.1 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="36e23-102">HL7 2.3.1 Folders and Events</span></span>
<span data-ttu-id="36e23-103">次の表は、HL7 でエンコードされたメッセージ HL7 version 2.3.1 フォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="36e23-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3.1 folder for HL7-encoded messages.</span></span> <span data-ttu-id="36e23-104">これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="36e23-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="36e23-105">サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="36e23-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="36e23-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="36e23-106">Subfolder</span></span>|<span data-ttu-id="36e23-107">イベント</span><span class="sxs-lookup"><span data-stu-id="36e23-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="36e23-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="36e23-108">Patient Administration</span></span>|<span data-ttu-id="36e23-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="36e23-109">A01-A51</span></span>|  
|<span data-ttu-id="36e23-110">監視レポート</span><span class="sxs-lookup"><span data-stu-id="36e23-110">Observation Reporting</span></span>|<span data-ttu-id="36e23-111">C01 C12、P06 P09、R01-R06、W01 W02</span><span class="sxs-lookup"><span data-stu-id="36e23-111">C01-C12,P06-P09,R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="36e23-112">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="36e23-112">Patient Referral</span></span>|<span data-ttu-id="36e23-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="36e23-113">I01-I15</span></span>|  
|<span data-ttu-id="36e23-114">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="36e23-114">Master Files</span></span>|<span data-ttu-id="36e23-115">M01 M11 の MFA</span><span class="sxs-lookup"><span data-stu-id="36e23-115">M01-M11, MFA</span></span>|  
|<span data-ttu-id="36e23-116">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="36e23-116">Order Entry</span></span>|<span data-ttu-id="36e23-117">O01 O02 Q06、R0R、RAR、RDR、RER、RGR V01 V04</span><span class="sxs-lookup"><span data-stu-id="36e23-117">O01-O02,Q06,R0R,RAR,RDR,RER,RGR, V01-V04</span></span>|  
|<span data-ttu-id="36e23-118">財務管理</span><span class="sxs-lookup"><span data-stu-id="36e23-118">Financial Management</span></span>|<span data-ttu-id="36e23-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="36e23-119">P01-P06</span></span>|  
|<span data-ttu-id="36e23-120">治療</span><span class="sxs-lookup"><span data-stu-id="36e23-120">Patient Care</span></span>|<span data-ttu-id="36e23-121">PC1 PCH、PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="36e23-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="36e23-122">Query</span><span class="sxs-lookup"><span data-stu-id="36e23-122">Query</span></span>|<span data-ttu-id="36e23-123">CNQ、Q01 Q05、Q07-Q09、R07 R09</span><span class="sxs-lookup"><span data-stu-id="36e23-123">CNQ, Q01-Q05, Q07-Q09, R07-R09</span></span>|  
|<span data-ttu-id="36e23-124">スケジュール</span><span class="sxs-lookup"><span data-stu-id="36e23-124">Schedule</span></span>|<span data-ttu-id="36e23-125">S01 S26</span><span class="sxs-lookup"><span data-stu-id="36e23-125">S01-S26</span></span>|  
|<span data-ttu-id="36e23-126">医療レコード/Information Management</span><span class="sxs-lookup"><span data-stu-id="36e23-126">Medical Records/Information Management</span></span>|<span data-ttu-id="36e23-127">T01 T12 が同時</span><span class="sxs-lookup"><span data-stu-id="36e23-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36e23-128">参照</span><span class="sxs-lookup"><span data-stu-id="36e23-128">See Also</span></span>  
 <span data-ttu-id="36e23-129">[HL7 2.X サブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="36e23-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="36e23-130">[HL7 2.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="36e23-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="36e23-131">[HL7 2.2 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="36e23-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="36e23-132">[HL7 2.3 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="36e23-132">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="36e23-133">[HL7 2.4 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="36e23-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="36e23-134">HL7 2.5 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="36e23-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
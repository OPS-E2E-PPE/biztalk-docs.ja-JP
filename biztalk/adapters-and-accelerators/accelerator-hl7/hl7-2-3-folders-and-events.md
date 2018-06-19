---
title: HL7 2.3 フォルダーとイベント |Microsoft ドキュメント
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
ms.openlocfilehash: a396fca582defb8601bdda23280f92d0acbd90be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205210"
---
# <a name="hl7-23-folders-and-events"></a><span data-ttu-id="c0b56-102">HL7 2.3 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="c0b56-102">HL7 2.3 Folders and Events</span></span>
<span data-ttu-id="c0b56-103">次の表は、HL7 でエンコードされたメッセージ HL7 バージョン 2.3 フォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c0b56-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.3 folder for HL7-encoded messages.</span></span> <span data-ttu-id="c0b56-104">これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="c0b56-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="c0b56-105">サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0b56-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="c0b56-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="c0b56-106">Subfolder</span></span>|<span data-ttu-id="c0b56-107">イベント</span><span class="sxs-lookup"><span data-stu-id="c0b56-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="c0b56-108">患者の管理</span><span class="sxs-lookup"><span data-stu-id="c0b56-108">Patient Administration</span></span>|<span data-ttu-id="c0b56-109">A01 A51</span><span class="sxs-lookup"><span data-stu-id="c0b56-109">A01-A51</span></span>|  
|<span data-ttu-id="c0b56-110">監視レポート</span><span class="sxs-lookup"><span data-stu-id="c0b56-110">Observation Reporting</span></span>|<span data-ttu-id="c0b56-111">C01 C12、P07 P09、R01-R06、W01 W02</span><span class="sxs-lookup"><span data-stu-id="c0b56-111">C01-C12, P07-P09, R01-R06, W01-W02</span></span>|  
|<span data-ttu-id="c0b56-112">患者の紹介</span><span class="sxs-lookup"><span data-stu-id="c0b56-112">Patient Referral</span></span>|<span data-ttu-id="c0b56-113">I01 I15</span><span class="sxs-lookup"><span data-stu-id="c0b56-113">I01-I15</span></span>|  
|<span data-ttu-id="c0b56-114">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="c0b56-114">Master File</span></span>|<span data-ttu-id="c0b56-115">M01 M11</span><span class="sxs-lookup"><span data-stu-id="c0b56-115">M01-M11</span></span>|  
|<span data-ttu-id="c0b56-116">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="c0b56-116">Order Entry</span></span>|<span data-ttu-id="c0b56-117">O01 O02、Q06、RAR、RDR、RER、RGR、権限が必要です、V01 V04</span><span class="sxs-lookup"><span data-stu-id="c0b56-117">O01-O02,Q06, RAR,RDR,RER,RGR,ROR, V01-V04</span></span>|  
|<span data-ttu-id="c0b56-118">財務管理</span><span class="sxs-lookup"><span data-stu-id="c0b56-118">Financial Management</span></span>|<span data-ttu-id="c0b56-119">P01 P06</span><span class="sxs-lookup"><span data-stu-id="c0b56-119">P01-P06</span></span>|  
|<span data-ttu-id="c0b56-120">治療</span><span class="sxs-lookup"><span data-stu-id="c0b56-120">Patient Care</span></span>|<span data-ttu-id="c0b56-121">PC1 PCH、PCJ PCL</span><span class="sxs-lookup"><span data-stu-id="c0b56-121">PC1-PCH, PCJ-PCL</span></span>|  
|<span data-ttu-id="c0b56-122">Query</span><span class="sxs-lookup"><span data-stu-id="c0b56-122">Query</span></span>|<span data-ttu-id="c0b56-123">CNQ、Q01 Q03、Q05</span><span class="sxs-lookup"><span data-stu-id="c0b56-123">CNQ, Q01-Q03, Q05</span></span>|  
|<span data-ttu-id="c0b56-124">スケジューリング</span><span class="sxs-lookup"><span data-stu-id="c0b56-124">Scheduling</span></span>|<span data-ttu-id="c0b56-125">S01 S26</span><span class="sxs-lookup"><span data-stu-id="c0b56-125">S01-S26</span></span>|  
|<span data-ttu-id="c0b56-126">医療記録および情報の管理</span><span class="sxs-lookup"><span data-stu-id="c0b56-126">Medical Records and Information Management</span></span>|<span data-ttu-id="c0b56-127">T01 T12 が同時</span><span class="sxs-lookup"><span data-stu-id="c0b56-127">T01-T12</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0b56-128">参照</span><span class="sxs-lookup"><span data-stu-id="c0b56-128">See Also</span></span>  
 <span data-ttu-id="c0b56-129">[HL7 2.X サブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c0b56-129">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="c0b56-130">[HL7 2.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c0b56-130">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="c0b56-131">[HL7 2.2 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c0b56-131">[HL7 2.2 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-2-folders-and-events.md) </span></span>  
 <span data-ttu-id="c0b56-132">[HL7 2.3.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c0b56-132">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="c0b56-133">[HL7 2.4 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="c0b56-133">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="c0b56-134">HL7 2.5 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="c0b56-134">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
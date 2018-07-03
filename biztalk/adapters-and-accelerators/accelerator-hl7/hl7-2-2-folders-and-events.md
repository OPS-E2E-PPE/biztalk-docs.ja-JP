---
title: HL7 2.2 のフォルダーとイベント |Microsoft Docs
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
ms.assetid: 3811dfed-21c6-4bee-bd01-7c910a1a581f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 144940331c8f0917a372dddf0e906cfa4472562d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991139"
---
# <a name="hl7-22-folders-and-events"></a><span data-ttu-id="101dd-102">HL7 2.2 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="101dd-102">HL7 2.2 Folders and Events</span></span>
<span data-ttu-id="101dd-103">次の表は、HL7 でエンコードされたメッセージ HL7 2.2 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="101dd-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.2 folder for HL7-encoded messages.</span></span> <span data-ttu-id="101dd-104">これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="101dd-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="101dd-105">サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="101dd-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="101dd-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="101dd-106">Subfolder</span></span>|<span data-ttu-id="101dd-107">イベント</span><span class="sxs-lookup"><span data-stu-id="101dd-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="101dd-108">正直、放電し、転送</span><span class="sxs-lookup"><span data-stu-id="101dd-108">Admit, Discharge and Transfer</span></span>|<span data-ttu-id="101dd-109">A01 A37</span><span class="sxs-lookup"><span data-stu-id="101dd-109">A01-A37</span></span>|  
|<span data-ttu-id="101dd-110">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="101dd-110">Master Files</span></span>|<span data-ttu-id="101dd-111">M01 M03</span><span class="sxs-lookup"><span data-stu-id="101dd-111">M01-M03</span></span>|  
|<span data-ttu-id="101dd-112">ネットワークの管理</span><span class="sxs-lookup"><span data-stu-id="101dd-112">Network Management</span></span>|<span data-ttu-id="101dd-113">N01 N02</span><span class="sxs-lookup"><span data-stu-id="101dd-113">N01-N02</span></span>|  
|<span data-ttu-id="101dd-114">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="101dd-114">Order Entry</span></span>|<span data-ttu-id="101dd-115">O01 O02</span><span class="sxs-lookup"><span data-stu-id="101dd-115">O01-O02</span></span>|  
|<span data-ttu-id="101dd-116">患者のアカウンティング</span><span class="sxs-lookup"><span data-stu-id="101dd-116">Patient Accounting</span></span>|<span data-ttu-id="101dd-117">P01 P04</span><span class="sxs-lookup"><span data-stu-id="101dd-117">P01-P04</span></span>|  
|<span data-ttu-id="101dd-118">Query</span><span class="sxs-lookup"><span data-stu-id="101dd-118">Query</span></span>|<span data-ttu-id="101dd-119">Q01 Q03 Q05</span><span class="sxs-lookup"><span data-stu-id="101dd-119">Q01-Q03,Q05</span></span>|  
|<span data-ttu-id="101dd-120">監視レポート</span><span class="sxs-lookup"><span data-stu-id="101dd-120">Observation Reporting</span></span>|<span data-ttu-id="101dd-121">R01 R04</span><span class="sxs-lookup"><span data-stu-id="101dd-121">R01-R04</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="101dd-122">参照</span><span class="sxs-lookup"><span data-stu-id="101dd-122">See Also</span></span>  
 <span data-ttu-id="101dd-123">[HL7 2.X のサブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="101dd-123">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="101dd-124">[HL7 2.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="101dd-124">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="101dd-125">[HL7 2.3 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="101dd-125">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="101dd-126">[HL7 2.3.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="101dd-126">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="101dd-127">[HL7 2.4 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="101dd-127">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="101dd-128">HL7 2.5 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="101dd-128">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
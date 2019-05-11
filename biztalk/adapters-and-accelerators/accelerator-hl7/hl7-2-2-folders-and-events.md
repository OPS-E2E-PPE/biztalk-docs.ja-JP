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
ms.openlocfilehash: fadcf32983b9eb7975770627606c165e7b832969
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255214"
---
# <a name="hl7-22-folders-and-events"></a><span data-ttu-id="f8aae-102">HL7 2.2 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="f8aae-102">HL7 2.2 Folders and Events</span></span>
<span data-ttu-id="f8aae-103">次の表は、HL7 でエンコードされたメッセージ HL7 2.2 のフォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f8aae-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.2 folder for HL7-encoded messages.</span></span> <span data-ttu-id="f8aae-104">これらのサブフォルダーは、Microsoft BizTalk Accelerator for HL7 のために使用するスキーマを含めることが ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証する、解析し、このテーブルの [イベント] 列に表示されるイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="f8aae-104">These subfolders contain the schemas used by Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="f8aae-105">サブフォルダー名には、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8aae-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="f8aae-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="f8aae-106">Subfolder</span></span>|<span data-ttu-id="f8aae-107">イベント</span><span class="sxs-lookup"><span data-stu-id="f8aae-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="f8aae-108">正直、放電し、転送</span><span class="sxs-lookup"><span data-stu-id="f8aae-108">Admit, Discharge and Transfer</span></span>|<span data-ttu-id="f8aae-109">A01 A37</span><span class="sxs-lookup"><span data-stu-id="f8aae-109">A01-A37</span></span>|  
|<span data-ttu-id="f8aae-110">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="f8aae-110">Master Files</span></span>|<span data-ttu-id="f8aae-111">M01 M03</span><span class="sxs-lookup"><span data-stu-id="f8aae-111">M01-M03</span></span>|  
|<span data-ttu-id="f8aae-112">ネットワークの管理</span><span class="sxs-lookup"><span data-stu-id="f8aae-112">Network Management</span></span>|<span data-ttu-id="f8aae-113">N01 N02</span><span class="sxs-lookup"><span data-stu-id="f8aae-113">N01-N02</span></span>|  
|<span data-ttu-id="f8aae-114">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="f8aae-114">Order Entry</span></span>|<span data-ttu-id="f8aae-115">O01 O02</span><span class="sxs-lookup"><span data-stu-id="f8aae-115">O01-O02</span></span>|  
|<span data-ttu-id="f8aae-116">患者のアカウンティング</span><span class="sxs-lookup"><span data-stu-id="f8aae-116">Patient Accounting</span></span>|<span data-ttu-id="f8aae-117">P01 P04</span><span class="sxs-lookup"><span data-stu-id="f8aae-117">P01-P04</span></span>|  
|<span data-ttu-id="f8aae-118">Query</span><span class="sxs-lookup"><span data-stu-id="f8aae-118">Query</span></span>|<span data-ttu-id="f8aae-119">Q01 Q03 Q05</span><span class="sxs-lookup"><span data-stu-id="f8aae-119">Q01-Q03,Q05</span></span>|  
|<span data-ttu-id="f8aae-120">監視レポート</span><span class="sxs-lookup"><span data-stu-id="f8aae-120">Observation Reporting</span></span>|<span data-ttu-id="f8aae-121">R01 R04</span><span class="sxs-lookup"><span data-stu-id="f8aae-121">R01-R04</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8aae-122">参照</span><span class="sxs-lookup"><span data-stu-id="f8aae-122">See Also</span></span>  
 <span data-ttu-id="f8aae-123">[HL7 2.X のサブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f8aae-123">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="f8aae-124">[HL7 2.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f8aae-124">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="f8aae-125">[HL7 2.3 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f8aae-125">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="f8aae-126">[HL7 2.3.1 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f8aae-126">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="f8aae-127">[HL7 2.4 のフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="f8aae-127">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="f8aae-128">HL7 2.5 のフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="f8aae-128">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
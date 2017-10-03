---
title: "HL7 2.2 フォルダーとイベント |Microsoft ドキュメント"
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
ms.assetid: 3811dfed-21c6-4bee-bd01-7c910a1a581f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84d807452532b7d4e3e063fde841b9bed84f5e6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-22-folders-and-events"></a><span data-ttu-id="e61f6-102">HL7 2.2 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="e61f6-102">HL7 2.2 Folders and Events</span></span>
<span data-ttu-id="e61f6-103">次の表は、HL7 でエンコードされたメッセージ HL7 バージョン 2.2 フォルダー内のセットアップ ウィザードによって作成されるサブフォルダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e61f6-103">The following table lists the subfolders created by the setup wizard within the HL7 version 2.2 folder for HL7-encoded messages.</span></span> <span data-ttu-id="e61f6-104">これらのサブフォルダーがによって使用されるスキーマを含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を検証、解析、およびこのテーブルの [イベント] 列に示されているイベントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="e61f6-104">These subfolders contain the schemas used by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) to validate, parse, and serialize the events listed in the Events column of this table.</span></span> <span data-ttu-id="e61f6-105">サブフォルダー名では、これらのスキーマをサポートするイベントの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="e61f6-105">The subfolder names describe the types of events these schemas support.</span></span>  
  
|<span data-ttu-id="e61f6-106">サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="e61f6-106">Subfolder</span></span>|<span data-ttu-id="e61f6-107">イベント</span><span class="sxs-lookup"><span data-stu-id="e61f6-107">Events</span></span>|  
|---------------|------------|  
|<span data-ttu-id="e61f6-108">許可、放電し、転送</span><span class="sxs-lookup"><span data-stu-id="e61f6-108">Admit, Discharge and Transfer</span></span>|<span data-ttu-id="e61f6-109">A01 A37</span><span class="sxs-lookup"><span data-stu-id="e61f6-109">A01-A37</span></span>|  
|<span data-ttu-id="e61f6-110">Master ファイル</span><span class="sxs-lookup"><span data-stu-id="e61f6-110">Master Files</span></span>|<span data-ttu-id="e61f6-111">M01 M03</span><span class="sxs-lookup"><span data-stu-id="e61f6-111">M01-M03</span></span>|  
|<span data-ttu-id="e61f6-112">ネットワークの管理</span><span class="sxs-lookup"><span data-stu-id="e61f6-112">Network Management</span></span>|<span data-ttu-id="e61f6-113">N01 N02</span><span class="sxs-lookup"><span data-stu-id="e61f6-113">N01-N02</span></span>|  
|<span data-ttu-id="e61f6-114">注文エントリ</span><span class="sxs-lookup"><span data-stu-id="e61f6-114">Order Entry</span></span>|<span data-ttu-id="e61f6-115">O01 O02</span><span class="sxs-lookup"><span data-stu-id="e61f6-115">O01-O02</span></span>|  
|<span data-ttu-id="e61f6-116">患者のアカウンティング</span><span class="sxs-lookup"><span data-stu-id="e61f6-116">Patient Accounting</span></span>|<span data-ttu-id="e61f6-117">P01 P04</span><span class="sxs-lookup"><span data-stu-id="e61f6-117">P01-P04</span></span>|  
|<span data-ttu-id="e61f6-118">Query</span><span class="sxs-lookup"><span data-stu-id="e61f6-118">Query</span></span>|<span data-ttu-id="e61f6-119">Q01 Q03、Q05</span><span class="sxs-lookup"><span data-stu-id="e61f6-119">Q01-Q03,Q05</span></span>|  
|<span data-ttu-id="e61f6-120">監視レポート</span><span class="sxs-lookup"><span data-stu-id="e61f6-120">Observation Reporting</span></span>|<span data-ttu-id="e61f6-121">R01 R04</span><span class="sxs-lookup"><span data-stu-id="e61f6-121">R01-R04</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e61f6-122">参照</span><span class="sxs-lookup"><span data-stu-id="e61f6-122">See Also</span></span>  
 <span data-ttu-id="e61f6-123">[HL7 2.X サブフォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="e61f6-123">[HL7 2.X Subfolders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md) </span></span>  
 <span data-ttu-id="e61f6-124">[HL7 2.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="e61f6-124">[HL7 2.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="e61f6-125">[HL7 2.3 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="e61f6-125">[HL7 2.3 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-folders-and-events.md) </span></span>  
 <span data-ttu-id="e61f6-126">[HL7 2.3.1 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="e61f6-126">[HL7 2.3.1 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-3-1-folders-and-events.md) </span></span>  
 <span data-ttu-id="e61f6-127">[HL7 2.4 フォルダーとイベント](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="e61f6-127">[HL7 2.4 Folders and Events](../../adapters-and-accelerators/accelerator-hl7/hl7-2-4-folders-and-events.md) </span></span>  
 [<span data-ttu-id="e61f6-128">HL7 2.5 フォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="e61f6-128">HL7 2.5 Folders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-5-folders-and-events.md)
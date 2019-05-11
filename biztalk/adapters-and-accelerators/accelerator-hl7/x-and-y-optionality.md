---
title: '&#39;X&#39;と&#39;Y&#39; Optionality |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, Y optionality
- segments, SegmentDataElements table
- SegmentDataElements table
- segments, X optionality
ms.assetid: 8a59b407-95a2-45ba-a8d6-db4154c91d7b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82507c8c6d6f57c4fa85c4e20599b4fc79802e76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285284"
---
# <a name="39x39-and-39y39-optionality"></a><span data-ttu-id="a8b0a-102">&#39;X&#39;と&#39;Y&#39; Optionality</span><span class="sxs-lookup"><span data-stu-id="a8b0a-102">&#39;X&#39; and &#39;Y&#39; Optionality</span></span>
<span data-ttu-id="a8b0a-103">HL7 Access データベースに SegmentDataElements テーブルにはとして設定されているいくつかのデータ項目 (フィールド) が含まれています**Req/Opt X =**、ように、このトリガー イベントにこのフィールドは、HL7 標準によって関連付けるしないことを意味します次の表にします。</span><span class="sxs-lookup"><span data-stu-id="a8b0a-103">The SegmentDataElements table in the HL7 Access database contains several Data Items (fields) that have been set as **Req/Opt = X**, meaning that the HL7 standard does not associate this field with this trigger event, as shown in the following table.</span></span>  
  
|<span data-ttu-id="a8b0a-104">Segment</span><span class="sxs-lookup"><span data-stu-id="a8b0a-104">Segment</span></span>|<span data-ttu-id="a8b0a-105">バージョン</span><span class="sxs-lookup"><span data-stu-id="a8b0a-105">Version</span></span>|<span data-ttu-id="a8b0a-106">」の章</span><span class="sxs-lookup"><span data-stu-id="a8b0a-106">Chapter</span></span>|<span data-ttu-id="a8b0a-107">データ項目</span><span class="sxs-lookup"><span data-stu-id="a8b0a-107">Data Item</span></span>|<span data-ttu-id="a8b0a-108">必要な/</span><span class="sxs-lookup"><span data-stu-id="a8b0a-108">Required/</span></span><br /><br /> <span data-ttu-id="a8b0a-109">省略可</span><span class="sxs-lookup"><span data-stu-id="a8b0a-109">Optional</span></span>|<span data-ttu-id="a8b0a-110">レポート</span><span class="sxs-lookup"><span data-stu-id="a8b0a-110">Report</span></span>|<span data-ttu-id="a8b0a-111">数値</span><span class="sxs-lookup"><span data-stu-id="a8b0a-111">Number</span></span>|<span data-ttu-id="a8b0a-112">HTML 標準</span><span class="sxs-lookup"><span data-stu-id="a8b0a-112">HTML Standard</span></span>|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|<span data-ttu-id="a8b0a-113">OBX</span><span class="sxs-lookup"><span data-stu-id="a8b0a-113">OBX</span></span>|<span data-ttu-id="a8b0a-114">2.4</span><span class="sxs-lookup"><span data-stu-id="a8b0a-114">2.4</span></span>|<span data-ttu-id="a8b0a-115">7.4.2.9</span><span class="sxs-lookup"><span data-stu-id="a8b0a-115">7.4.2.9</span></span>|<span data-ttu-id="a8b0a-116">00577</span><span class="sxs-lookup"><span data-stu-id="a8b0a-116">00577</span></span>|<span data-ttu-id="a8b0a-117">x</span><span class="sxs-lookup"><span data-stu-id="a8b0a-117">X</span></span>|<span data-ttu-id="a8b0a-118">Y</span><span class="sxs-lookup"><span data-stu-id="a8b0a-118">Y</span></span>|<span data-ttu-id="a8b0a-119">5</span><span class="sxs-lookup"><span data-stu-id="a8b0a-119">5</span></span>|<span data-ttu-id="a8b0a-120">ch07.htm#Heading113</span><span class="sxs-lookup"><span data-stu-id="a8b0a-120">ch07.htm#Heading113</span></span>|  
|<span data-ttu-id="a8b0a-121">OBX</span><span class="sxs-lookup"><span data-stu-id="a8b0a-121">OBX</span></span>|<span data-ttu-id="a8b0a-122">2.4</span><span class="sxs-lookup"><span data-stu-id="a8b0a-122">2.4</span></span>|<span data-ttu-id="a8b0a-123">7.4.2.8</span><span class="sxs-lookup"><span data-stu-id="a8b0a-123">7.4.2.8</span></span>|<span data-ttu-id="a8b0a-124">00576</span><span class="sxs-lookup"><span data-stu-id="a8b0a-124">00576</span></span>|<span data-ttu-id="a8b0a-125">x</span><span class="sxs-lookup"><span data-stu-id="a8b0a-125">X</span></span>||<span data-ttu-id="a8b0a-126">0</span><span class="sxs-lookup"><span data-stu-id="a8b0a-126">0</span></span>|<span data-ttu-id="a8b0a-127">ch07.htm#Heading112</span><span class="sxs-lookup"><span data-stu-id="a8b0a-127">ch07.htm#Heading112</span></span>|  
|<span data-ttu-id="a8b0a-128">OBX</span><span class="sxs-lookup"><span data-stu-id="a8b0a-128">OBX</span></span>|<span data-ttu-id="a8b0a-129">2.4</span><span class="sxs-lookup"><span data-stu-id="a8b0a-129">2.4</span></span>|<span data-ttu-id="a8b0a-130">7.4.2.6</span><span class="sxs-lookup"><span data-stu-id="a8b0a-130">7.4.2.6</span></span>|<span data-ttu-id="a8b0a-131">00574</span><span class="sxs-lookup"><span data-stu-id="a8b0a-131">00574</span></span>|<span data-ttu-id="a8b0a-132">x</span><span class="sxs-lookup"><span data-stu-id="a8b0a-132">X</span></span>||<span data-ttu-id="a8b0a-133">0</span><span class="sxs-lookup"><span data-stu-id="a8b0a-133">0</span></span>|<span data-ttu-id="a8b0a-134">ch07.htm#Heading107</span><span class="sxs-lookup"><span data-stu-id="a8b0a-134">ch07.htm#Heading107</span></span>|  
|<span data-ttu-id="a8b0a-135">OBX</span><span class="sxs-lookup"><span data-stu-id="a8b0a-135">OBX</span></span>|<span data-ttu-id="a8b0a-136">2.4</span><span class="sxs-lookup"><span data-stu-id="a8b0a-136">2.4</span></span>|<span data-ttu-id="a8b0a-137">7.4.2.17</span><span class="sxs-lookup"><span data-stu-id="a8b0a-137">7.4.2.17</span></span>|<span data-ttu-id="a8b0a-138">00936</span><span class="sxs-lookup"><span data-stu-id="a8b0a-138">00936</span></span>|<span data-ttu-id="a8b0a-139">x</span><span class="sxs-lookup"><span data-stu-id="a8b0a-139">X</span></span>|<span data-ttu-id="a8b0a-140">Y</span><span class="sxs-lookup"><span data-stu-id="a8b0a-140">Y</span></span>|<span data-ttu-id="a8b0a-141">0</span><span class="sxs-lookup"><span data-stu-id="a8b0a-141">0</span></span>|<span data-ttu-id="a8b0a-142">ch07.htm#Heading121</span><span class="sxs-lookup"><span data-stu-id="a8b0a-142">ch07.htm#Heading121</span></span>|  
  
 <span data-ttu-id="a8b0a-143">Microsoft から[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]イベントをトリガーで指定されていないことにどのような必須/任意の規則またはオプションかどうかにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b0a-143">Since Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] does not specify trigger events, you decide what the required/optional rules, or optionality should be.</span></span> <span data-ttu-id="a8b0a-144">ローカル サイトの条件に基づく、optionality ルールを適用する決定可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8b0a-144">Based on local site conditions, you may decide to enforce optionality rules.</span></span> <span data-ttu-id="a8b0a-145">既定では、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]として示されている 23 フィールドを提供します。 省略可能なフィールドとして"X"です。</span><span class="sxs-lookup"><span data-stu-id="a8b0a-145">By default, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provides the 23 fields listed as "X" as optional fields.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8b0a-146">値"Y"はエラーです、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Access データベース。</span><span class="sxs-lookup"><span data-stu-id="a8b0a-146">Value "Y" is an error in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Access database.</span></span> [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] <span data-ttu-id="a8b0a-147">想定されるすべての値**Y**と**空白**は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a8b0a-147">assumes that all the values of **Y** and **Blank** are optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b0a-148">参照</span><span class="sxs-lookup"><span data-stu-id="a8b0a-148">See Also</span></span>  
 [<span data-ttu-id="a8b0a-149">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="a8b0a-149">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
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
ms.openlocfilehash: aed5b87216bd2d8e127ff032e3773b3f740835c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981523"
---
# <a name="39x39-and-39y39-optionality"></a><span data-ttu-id="23ef8-102">&#39;X&#39;と&#39;Y&#39; Optionality</span><span class="sxs-lookup"><span data-stu-id="23ef8-102">&#39;X&#39; and &#39;Y&#39; Optionality</span></span>
<span data-ttu-id="23ef8-103">HL7 Access データベースに SegmentDataElements テーブルにはとして設定されているいくつかのデータ項目 (フィールド) が含まれています**Req/Opt X =**、ように、このトリガー イベントにこのフィールドは、HL7 標準によって関連付けるしないことを意味します次の表にします。</span><span class="sxs-lookup"><span data-stu-id="23ef8-103">The SegmentDataElements table in the HL7 Access database contains several Data Items (fields) that have been set as **Req/Opt = X**, meaning that the HL7 standard does not associate this field with this trigger event, as shown in the following table.</span></span>  
  
|<span data-ttu-id="23ef8-104">Segment</span><span class="sxs-lookup"><span data-stu-id="23ef8-104">Segment</span></span>|<span data-ttu-id="23ef8-105">バージョン</span><span class="sxs-lookup"><span data-stu-id="23ef8-105">Version</span></span>|<span data-ttu-id="23ef8-106">章</span><span class="sxs-lookup"><span data-stu-id="23ef8-106">Chapter</span></span>|<span data-ttu-id="23ef8-107">データ項目</span><span class="sxs-lookup"><span data-stu-id="23ef8-107">Data Item</span></span>|<span data-ttu-id="23ef8-108">必要な/</span><span class="sxs-lookup"><span data-stu-id="23ef8-108">Required/</span></span><br /><br /> <span data-ttu-id="23ef8-109">省略可</span><span class="sxs-lookup"><span data-stu-id="23ef8-109">Optional</span></span>|<span data-ttu-id="23ef8-110">レポート</span><span class="sxs-lookup"><span data-stu-id="23ef8-110">Report</span></span>|<span data-ttu-id="23ef8-111">数値</span><span class="sxs-lookup"><span data-stu-id="23ef8-111">Number</span></span>|<span data-ttu-id="23ef8-112">HTML 標準</span><span class="sxs-lookup"><span data-stu-id="23ef8-112">HTML Standard</span></span>|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|<span data-ttu-id="23ef8-113">OBX</span><span class="sxs-lookup"><span data-stu-id="23ef8-113">OBX</span></span>|<span data-ttu-id="23ef8-114">2.4</span><span class="sxs-lookup"><span data-stu-id="23ef8-114">2.4</span></span>|<span data-ttu-id="23ef8-115">7.4.2.9</span><span class="sxs-lookup"><span data-stu-id="23ef8-115">7.4.2.9</span></span>|<span data-ttu-id="23ef8-116">00577</span><span class="sxs-lookup"><span data-stu-id="23ef8-116">00577</span></span>|<span data-ttu-id="23ef8-117">×</span><span class="sxs-lookup"><span data-stu-id="23ef8-117">X</span></span>|<span data-ttu-id="23ef8-118">Y</span><span class="sxs-lookup"><span data-stu-id="23ef8-118">Y</span></span>|<span data-ttu-id="23ef8-119">5</span><span class="sxs-lookup"><span data-stu-id="23ef8-119">5</span></span>|<span data-ttu-id="23ef8-120">ch07.htm#Heading113</span><span class="sxs-lookup"><span data-stu-id="23ef8-120">ch07.htm#Heading113</span></span>|  
|<span data-ttu-id="23ef8-121">OBX</span><span class="sxs-lookup"><span data-stu-id="23ef8-121">OBX</span></span>|<span data-ttu-id="23ef8-122">2.4</span><span class="sxs-lookup"><span data-stu-id="23ef8-122">2.4</span></span>|<span data-ttu-id="23ef8-123">7.4.2.8</span><span class="sxs-lookup"><span data-stu-id="23ef8-123">7.4.2.8</span></span>|<span data-ttu-id="23ef8-124">00576</span><span class="sxs-lookup"><span data-stu-id="23ef8-124">00576</span></span>|<span data-ttu-id="23ef8-125">×</span><span class="sxs-lookup"><span data-stu-id="23ef8-125">X</span></span>||<span data-ttu-id="23ef8-126">0</span><span class="sxs-lookup"><span data-stu-id="23ef8-126">0</span></span>|<span data-ttu-id="23ef8-127">ch07.htm#Heading112</span><span class="sxs-lookup"><span data-stu-id="23ef8-127">ch07.htm#Heading112</span></span>|  
|<span data-ttu-id="23ef8-128">OBX</span><span class="sxs-lookup"><span data-stu-id="23ef8-128">OBX</span></span>|<span data-ttu-id="23ef8-129">2.4</span><span class="sxs-lookup"><span data-stu-id="23ef8-129">2.4</span></span>|<span data-ttu-id="23ef8-130">7.4.2.6</span><span class="sxs-lookup"><span data-stu-id="23ef8-130">7.4.2.6</span></span>|<span data-ttu-id="23ef8-131">00574</span><span class="sxs-lookup"><span data-stu-id="23ef8-131">00574</span></span>|<span data-ttu-id="23ef8-132">×</span><span class="sxs-lookup"><span data-stu-id="23ef8-132">X</span></span>||<span data-ttu-id="23ef8-133">0</span><span class="sxs-lookup"><span data-stu-id="23ef8-133">0</span></span>|<span data-ttu-id="23ef8-134">ch07.htm#Heading107</span><span class="sxs-lookup"><span data-stu-id="23ef8-134">ch07.htm#Heading107</span></span>|  
|<span data-ttu-id="23ef8-135">OBX</span><span class="sxs-lookup"><span data-stu-id="23ef8-135">OBX</span></span>|<span data-ttu-id="23ef8-136">2.4</span><span class="sxs-lookup"><span data-stu-id="23ef8-136">2.4</span></span>|<span data-ttu-id="23ef8-137">7.4.2.17</span><span class="sxs-lookup"><span data-stu-id="23ef8-137">7.4.2.17</span></span>|<span data-ttu-id="23ef8-138">00936</span><span class="sxs-lookup"><span data-stu-id="23ef8-138">00936</span></span>|<span data-ttu-id="23ef8-139">×</span><span class="sxs-lookup"><span data-stu-id="23ef8-139">X</span></span>|<span data-ttu-id="23ef8-140">Y</span><span class="sxs-lookup"><span data-stu-id="23ef8-140">Y</span></span>|<span data-ttu-id="23ef8-141">0</span><span class="sxs-lookup"><span data-stu-id="23ef8-141">0</span></span>|<span data-ttu-id="23ef8-142">ch07.htm#Heading121</span><span class="sxs-lookup"><span data-stu-id="23ef8-142">ch07.htm#Heading121</span></span>|  
  
 <span data-ttu-id="23ef8-143">Microsoft から[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]イベントをトリガーで指定されていないことにどのような必須/任意の規則またはオプションかどうかにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23ef8-143">Since Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] does not specify trigger events, you decide what the required/optional rules, or optionality should be.</span></span> <span data-ttu-id="23ef8-144">ローカル サイトの条件に基づく、optionality ルールを適用する決定可能性があります。</span><span class="sxs-lookup"><span data-stu-id="23ef8-144">Based on local site conditions, you may decide to enforce optionality rules.</span></span> <span data-ttu-id="23ef8-145">既定では、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]として示されている 23 フィールドを提供します。 省略可能なフィールドとして"X"です。</span><span class="sxs-lookup"><span data-stu-id="23ef8-145">By default, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provides the 23 fields listed as "X" as optional fields.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23ef8-146">値"Y"はエラーです、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Access データベース。</span><span class="sxs-lookup"><span data-stu-id="23ef8-146">Value "Y" is an error in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Access database.</span></span> [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="23ef8-147"> 想定されるすべての値**Y**と**空白**は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="23ef8-147"> assumes that all the values of **Y** and **Blank** are optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ef8-148">参照</span><span class="sxs-lookup"><span data-stu-id="23ef8-148">See Also</span></span>  
 [<span data-ttu-id="23ef8-149">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="23ef8-149">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)
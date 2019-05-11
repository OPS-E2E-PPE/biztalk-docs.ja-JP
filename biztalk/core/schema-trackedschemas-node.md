---
title: Schema (TrackedSchemas ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Schema node
ms.assetid: a503aad6-07f8-4650-a214-4d2f6650cb80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe27ed2ce631fe27cb34ec44bb792349737dbe01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396887"
---
# <a name="schema-trackedschemas-node"></a><span data-ttu-id="8d5e7-102">Schema (TrackedSchemas ノード)</span><span class="sxs-lookup"><span data-stu-id="8d5e7-102">Schema (TrackedSchemas Node)</span></span>
<span data-ttu-id="8d5e7-103">バインド ファイルの TrackedSchemas ノードのスキーマのノードは、バインド ファイルと共にエクスポートされるサービスにバインドされるスキーマについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8d5e7-103">The Schema node of the TrackedSchemas node of a binding file describes a schema bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-schema-node"></a><span data-ttu-id="8d5e7-104">ノード内のスキーマ ノード</span><span class="sxs-lookup"><span data-stu-id="8d5e7-104">Nodes in the Schema node</span></span>  
 <span data-ttu-id="8d5e7-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="8d5e7-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="8d5e7-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="8d5e7-106">**Name**</span></span>|<span data-ttu-id="8d5e7-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="8d5e7-107">**Node Type**</span></span>|<span data-ttu-id="8d5e7-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="8d5e7-108">**Data Type**</span></span>|<span data-ttu-id="8d5e7-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="8d5e7-109">**Description**</span></span>|<span data-ttu-id="8d5e7-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="8d5e7-110">**Restrictions**</span></span>|<span data-ttu-id="8d5e7-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="8d5e7-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="8d5e7-112">FullName</span><span class="sxs-lookup"><span data-stu-id="8d5e7-112">FullName</span></span>|<span data-ttu-id="8d5e7-113">属性</span><span class="sxs-lookup"><span data-stu-id="8d5e7-113">Attribute</span></span>|<span data-ttu-id="8d5e7-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5e7-114">xs:string</span></span>|<span data-ttu-id="8d5e7-115">スキーマの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d5e7-115">Specifies the full name for the schema.</span></span>|<span data-ttu-id="8d5e7-116">任意</span><span class="sxs-lookup"><span data-stu-id="8d5e7-116">Not required</span></span>|<span data-ttu-id="8d5e7-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="8d5e7-117">Default value: empty</span></span>|  
|<span data-ttu-id="8d5e7-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8d5e7-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="8d5e7-119">属性</span><span class="sxs-lookup"><span data-stu-id="8d5e7-119">Attribute</span></span>|<span data-ttu-id="8d5e7-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5e7-120">xs:string</span></span>|<span data-ttu-id="8d5e7-121">このスキーマを含むアセンブリの修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d5e7-121">Specifies the qualified name for the assembly containing this schema.</span></span>|<span data-ttu-id="8d5e7-122">任意</span><span class="sxs-lookup"><span data-stu-id="8d5e7-122">Not required</span></span>|<span data-ttu-id="8d5e7-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="8d5e7-123">Default value: empty</span></span>|  
|<span data-ttu-id="8d5e7-124">AlwaysTrackAllProperties</span><span class="sxs-lookup"><span data-stu-id="8d5e7-124">AlwaysTrackAllProperties</span></span>|<span data-ttu-id="8d5e7-125">属性</span><span class="sxs-lookup"><span data-stu-id="8d5e7-125">Attribute</span></span>|<span data-ttu-id="8d5e7-126">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="8d5e7-126">xs:boolean</span></span>|<span data-ttu-id="8d5e7-127">指定されたアセンブリのすべてのプロパティを追跡するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d5e7-127">Specifies whether to track all properties for the specified assembly.</span></span>|<span data-ttu-id="8d5e7-128">必須</span><span class="sxs-lookup"><span data-stu-id="8d5e7-128">Required</span></span>|<span data-ttu-id="8d5e7-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="8d5e7-129">Default value: none</span></span><br /><br /> <span data-ttu-id="8d5e7-130">設定**true**をすべてのプロパティを追跡するには、それ以外の場合は、設定**false**します。</span><span class="sxs-lookup"><span data-stu-id="8d5e7-130">Set to **true** to track all properties, otherwise set to **false**.</span></span>|  
|<span data-ttu-id="8d5e7-131">説明</span><span class="sxs-lookup"><span data-stu-id="8d5e7-131">Description</span></span>|<span data-ttu-id="8d5e7-132">属性</span><span class="sxs-lookup"><span data-stu-id="8d5e7-132">Attribute</span></span>|<span data-ttu-id="8d5e7-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="8d5e7-133">xs:string</span></span>|<span data-ttu-id="8d5e7-134">スキーマの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d5e7-134">Specifies a description for the schema.</span></span>|<span data-ttu-id="8d5e7-135">任意</span><span class="sxs-lookup"><span data-stu-id="8d5e7-135">Not required</span></span>|<span data-ttu-id="8d5e7-136">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="8d5e7-136">Default value: empty</span></span>|  
|[<span data-ttu-id="8d5e7-137">TrackedPropertyNames (Schema ノード)</span><span class="sxs-lookup"><span data-stu-id="8d5e7-137">TrackedPropertyNames (Schema Node)</span></span>](../core/trackedpropertynames-schema-node.md)|<span data-ttu-id="8d5e7-138">レコード</span><span class="sxs-lookup"><span data-stu-id="8d5e7-138">Record</span></span>|<span data-ttu-id="8d5e7-139">(ComplexType)</span><span class="sxs-lookup"><span data-stu-id="8d5e7-139">ArrayOfString (ComplexType)</span></span>|<span data-ttu-id="8d5e7-140">追跡対象プロパティを指定する要素のコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="8d5e7-140">Container for the elements that specify the properties to be tracked.</span></span>|<span data-ttu-id="8d5e7-141">任意</span><span class="sxs-lookup"><span data-stu-id="8d5e7-141">Not required</span></span>|<span data-ttu-id="8d5e7-142">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="8d5e7-142">Default value: none</span></span>|
---
title: DistributionList (DistributionListCollection ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionList node [binding file]
ms.assetid: 51864a5c-1697-4804-ac18-8211494f3ff0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 732ffa00a2147212e688e9add579044c570faf6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350835"
---
# <a name="distributionlist-distributionlistcollection-node"></a><span data-ttu-id="d77f6-102">DistributionList (DistributionListCollection ノード)</span><span class="sxs-lookup"><span data-stu-id="d77f6-102">DistributionList (DistributionListCollection Node)</span></span>
<span data-ttu-id="d77f6-103">バインド ファイルの DistributionList ノードには、バインド ファイルと共にエクスポートされる同報リストに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d77f6-103">The DistributionList node of a binding file contains specific information about a distribution list that is exported with the binding file.</span></span> <span data-ttu-id="d77f6-104">同報リストは、送信ポート グループ、BizTalk Server 管理者と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d77f6-104">A distribution list is referred to as a send port group in the BizTalk Server Administrator.</span></span>  
  
## <a name="nodes-in-the-distributionlist-node"></a><span data-ttu-id="d77f6-105">DistributionList ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="d77f6-105">Nodes in the DistributionList node</span></span>  
 <span data-ttu-id="d77f6-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="d77f6-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="d77f6-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="d77f6-107">**Name**</span></span>|<span data-ttu-id="d77f6-108">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="d77f6-108">**Node Type**</span></span>|<span data-ttu-id="d77f6-109">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="d77f6-109">**Data Type**</span></span>|<span data-ttu-id="d77f6-110">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="d77f6-110">**Description**</span></span>|<span data-ttu-id="d77f6-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="d77f6-111">**Restrictions**</span></span>|<span data-ttu-id="d77f6-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="d77f6-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="d77f6-113">名前</span><span class="sxs-lookup"><span data-stu-id="d77f6-113">Name</span></span>|<span data-ttu-id="d77f6-114">属性</span><span class="sxs-lookup"><span data-stu-id="d77f6-114">Attribute</span></span>|<span data-ttu-id="d77f6-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="d77f6-115">xs:string</span></span>|<span data-ttu-id="d77f6-116">配布リストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d77f6-116">Specifies the name of the distribution list.</span></span>|<span data-ttu-id="d77f6-117">任意</span><span class="sxs-lookup"><span data-stu-id="d77f6-117">Not required</span></span>|<span data-ttu-id="d77f6-118">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="d77f6-118">Default value: empty</span></span>|  
|[<span data-ttu-id="d77f6-119">SendPorts</span><span class="sxs-lookup"><span data-stu-id="d77f6-119">SendPorts</span></span>](../core/sendports-distributionlist-node.md)|<span data-ttu-id="d77f6-120">レコード</span><span class="sxs-lookup"><span data-stu-id="d77f6-120">Record</span></span>|<span data-ttu-id="d77f6-121">ArrayOfSendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="d77f6-121">ArrayOfSendPortRef (ComplexType)</span></span>|<span data-ttu-id="d77f6-122">送信ポートまたは同報リストに含まれる送信ポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="d77f6-122">Specifies the send port or send ports included in the distribution list.</span></span>|<span data-ttu-id="d77f6-123">任意</span><span class="sxs-lookup"><span data-stu-id="d77f6-123">Not required</span></span>|<span data-ttu-id="d77f6-124">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="d77f6-124">Default value: none</span></span>|  
|<span data-ttu-id="d77f6-125">Assert</span><span class="sxs-lookup"><span data-stu-id="d77f6-125">Filter</span></span>|<span data-ttu-id="d77f6-126">要素</span><span class="sxs-lookup"><span data-stu-id="d77f6-126">Element</span></span>|<span data-ttu-id="d77f6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d77f6-127">xs:string</span></span>|<span data-ttu-id="d77f6-128">この同報リストで使用される省略可能なフィルター式の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d77f6-128">Specifies the name of the optional filter expression used on this distribution list.</span></span>|<span data-ttu-id="d77f6-129">必須</span><span class="sxs-lookup"><span data-stu-id="d77f6-129">Required</span></span>|<span data-ttu-id="d77f6-130">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="d77f6-130">Default value: empty</span></span>|  
|<span data-ttu-id="d77f6-131">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d77f6-131">ApplicationName</span></span>|<span data-ttu-id="d77f6-132">要素</span><span class="sxs-lookup"><span data-stu-id="d77f6-132">Element</span></span>|<span data-ttu-id="d77f6-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="d77f6-133">xs:string</span></span>|<span data-ttu-id="d77f6-134">同報リストが関連付けられているアプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d77f6-134">Specifies the name of the application that the distribution list is associated with.</span></span>|<span data-ttu-id="d77f6-135">必須</span><span class="sxs-lookup"><span data-stu-id="d77f6-135">Required</span></span>|<span data-ttu-id="d77f6-136">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="d77f6-136">Default value: empty</span></span>|  
|<span data-ttu-id="d77f6-137">説明</span><span class="sxs-lookup"><span data-stu-id="d77f6-137">Description</span></span>|<span data-ttu-id="d77f6-138">要素</span><span class="sxs-lookup"><span data-stu-id="d77f6-138">Element</span></span>|<span data-ttu-id="d77f6-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="d77f6-139">xs:string</span></span>|<span data-ttu-id="d77f6-140">配布リストの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="d77f6-140">Specifies a description for the distribution list.</span></span>|<span data-ttu-id="d77f6-141">必須</span><span class="sxs-lookup"><span data-stu-id="d77f6-141">Required</span></span>|<span data-ttu-id="d77f6-142">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="d77f6-142">Default value: empty</span></span>|
---
title: ホスト (Service ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Host node [binding file]
ms.assetid: 597522db-0336-43b1-b464-d17cffbf25be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a408b8f1bd269ff45881b31cd8a75d26bbc89a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387517"
---
# <a name="host-service-node"></a><span data-ttu-id="2a7e1-102">ホスト (Service ノード)</span><span class="sxs-lookup"><span data-stu-id="2a7e1-102">Host (Service Node)</span></span>
<span data-ttu-id="2a7e1-103">バインド ファイルのサービス ノードのホスト ノードでは、バインド ファイルと共にエクスポートされるサービスに関連付けられているホストについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-103">The Host node of the Service node of a binding file describes the host associated with the service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-host-node"></a><span data-ttu-id="2a7e1-104">ノード内のホスト ノード</span><span class="sxs-lookup"><span data-stu-id="2a7e1-104">Nodes in the Host node</span></span>  
 <span data-ttu-id="2a7e1-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="2a7e1-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="2a7e1-106">**Name**</span></span>|<span data-ttu-id="2a7e1-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="2a7e1-107">**Node Type**</span></span>|<span data-ttu-id="2a7e1-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="2a7e1-108">**Data Type**</span></span>|<span data-ttu-id="2a7e1-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="2a7e1-109">**Description**</span></span>|<span data-ttu-id="2a7e1-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="2a7e1-110">**Restrictions**</span></span>|<span data-ttu-id="2a7e1-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="2a7e1-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="2a7e1-112">名前</span><span class="sxs-lookup"><span data-stu-id="2a7e1-112">Name</span></span>|<span data-ttu-id="2a7e1-113">属性</span><span class="sxs-lookup"><span data-stu-id="2a7e1-113">Attribute</span></span>|<span data-ttu-id="2a7e1-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a7e1-114">xs:string</span></span>|<span data-ttu-id="2a7e1-115">ホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-115">Specifies the name of the host.</span></span>|<span data-ttu-id="2a7e1-116">任意</span><span class="sxs-lookup"><span data-stu-id="2a7e1-116">Not required</span></span>|<span data-ttu-id="2a7e1-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="2a7e1-117">Default value: empty</span></span>|  
|<span data-ttu-id="2a7e1-118">Nt グループ名</span><span class="sxs-lookup"><span data-stu-id="2a7e1-118">NTGroupName</span></span>|<span data-ttu-id="2a7e1-119">属性</span><span class="sxs-lookup"><span data-stu-id="2a7e1-119">Attribute</span></span>|<span data-ttu-id="2a7e1-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a7e1-120">xs:string</span></span>|<span data-ttu-id="2a7e1-121">ホストに関連付けられた Windows NT グループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-121">Specifies the Windows NT Group name associated with the host.</span></span>|<span data-ttu-id="2a7e1-122">任意</span><span class="sxs-lookup"><span data-stu-id="2a7e1-122">Not required</span></span>|<span data-ttu-id="2a7e1-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="2a7e1-123">Default value: empty</span></span>|  
|<span data-ttu-id="2a7e1-124">型</span><span class="sxs-lookup"><span data-stu-id="2a7e1-124">Type</span></span>|<span data-ttu-id="2a7e1-125">属性</span><span class="sxs-lookup"><span data-stu-id="2a7e1-125">Attribute</span></span>|<span data-ttu-id="2a7e1-126">xs:int</span><span class="sxs-lookup"><span data-stu-id="2a7e1-126">xs:int</span></span>|<span data-ttu-id="2a7e1-127">インプロセスまたは分離ホストの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-127">Specifies the host type as in process or isolated.</span></span>|<span data-ttu-id="2a7e1-128">必須</span><span class="sxs-lookup"><span data-stu-id="2a7e1-128">Required</span></span>|<span data-ttu-id="2a7e1-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="2a7e1-129">Default value: none</span></span><br /><br /> <span data-ttu-id="2a7e1-130">使用可能な値が記載されて、 [Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx)列挙体。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-130">Possible values are described in the [Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx) enumeration.</span></span>|  
|<span data-ttu-id="2a7e1-131">信頼されています。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-131">Trusted</span></span>|<span data-ttu-id="2a7e1-132">属性</span><span class="sxs-lookup"><span data-stu-id="2a7e1-132">Attribute</span></span>|<span data-ttu-id="2a7e1-133">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="2a7e1-133">xs:boolean</span></span>|<span data-ttu-id="2a7e1-134">BizTalk ホストが認証情報を収集するために信頼できるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-134">Specifies whether the BizTalk host can be trusted to collect authentication information.</span></span>|<span data-ttu-id="2a7e1-135">必須</span><span class="sxs-lookup"><span data-stu-id="2a7e1-135">Required</span></span>|<span data-ttu-id="2a7e1-136">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="2a7e1-136">Default value: none</span></span><br /><br /> <span data-ttu-id="2a7e1-137">設定**true**ホストが信頼されている場合がそれ以外の場合に設定**false**します。</span><span class="sxs-lookup"><span data-stu-id="2a7e1-137">Set to **true** if the host is trusted, otherwise set to **false**.</span></span>|
---
title: TransportType (SecondaryTransport ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: ed66c7ef-32b6-4110-b932-f96a45a29618
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e3816287f975370bc411bec593da4f8166481c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243343"
---
# <a name="transporttype-secondarytransport-node"></a><span data-ttu-id="c1c7e-102">TransportType (SecondaryTransport ノード)</span><span class="sxs-lookup"><span data-stu-id="c1c7e-102">TransportType (SecondaryTransport Node)</span></span>
<span data-ttu-id="c1c7e-103">バインド ファイルの SecondaryTransport ノードの TransportType ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられているアダプターに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1c7e-103">The TransportType node of the SecondaryTransport node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="c1c7e-104">TransportType ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="c1c7e-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="c1c7e-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="c1c7e-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c1c7e-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="c1c7e-106">**Name**</span></span>|<span data-ttu-id="c1c7e-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="c1c7e-107">**Node Type**</span></span>|<span data-ttu-id="c1c7e-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="c1c7e-108">**Data Type**</span></span>|<span data-ttu-id="c1c7e-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="c1c7e-109">**Description**</span></span>|<span data-ttu-id="c1c7e-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="c1c7e-110">**Restrictions**</span></span>|<span data-ttu-id="c1c7e-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="c1c7e-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="c1c7e-112">名前</span><span class="sxs-lookup"><span data-stu-id="c1c7e-112">Name</span></span>|<span data-ttu-id="c1c7e-113">属性</span><span class="sxs-lookup"><span data-stu-id="c1c7e-113">Attribute</span></span>|<span data-ttu-id="c1c7e-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c7e-114">xs:string</span></span>|<span data-ttu-id="c1c7e-115">トランスポートに関連付けられているアダプターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1c7e-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="c1c7e-116">任意</span><span class="sxs-lookup"><span data-stu-id="c1c7e-116">Not required</span></span>|<span data-ttu-id="c1c7e-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="c1c7e-117">Default value: empty</span></span>|  
|<span data-ttu-id="c1c7e-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="c1c7e-118">Capabilities</span></span>|<span data-ttu-id="c1c7e-119">属性</span><span class="sxs-lookup"><span data-stu-id="c1c7e-119">Attribute</span></span>|<span data-ttu-id="c1c7e-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="c1c7e-120">xs:int</span></span>|<span data-ttu-id="c1c7e-121">トランスポートに関連付けられているアダプターの機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1c7e-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="c1c7e-122">必須</span><span class="sxs-lookup"><span data-stu-id="c1c7e-122">Required</span></span>|<span data-ttu-id="c1c7e-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="c1c7e-123">Default value: none</span></span><br /><br /> <span data-ttu-id="c1c7e-124">設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1c7e-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="c1c7e-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="c1c7e-125">ConfigurationClsid</span></span>|<span data-ttu-id="c1c7e-126">属性</span><span class="sxs-lookup"><span data-stu-id="c1c7e-126">Attribute</span></span>|<span data-ttu-id="c1c7e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c7e-127">xs:string</span></span>|<span data-ttu-id="c1c7e-128">トランスポートに関連付けられているアダプターの構成 GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1c7e-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="c1c7e-129">任意</span><span class="sxs-lookup"><span data-stu-id="c1c7e-129">Not required</span></span>|<span data-ttu-id="c1c7e-130">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="c1c7e-130">Default value: empty</span></span>|
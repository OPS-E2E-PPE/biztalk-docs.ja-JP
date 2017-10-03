---
title: "TransportType (PrimaryTransport ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransportType node [binding file]
ms.assetid: 9eb377ec-35d8-4b72-85f9-f264f6553c5a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40e0f005e7279541a2cdcb5c2bf205b7731e5263
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype-primarytransport-node"></a><span data-ttu-id="2ada7-102">TransportType (PrimaryTransport ノード)</span><span class="sxs-lookup"><span data-stu-id="2ada7-102">TransportType (PrimaryTransport Node)</span></span>
<span data-ttu-id="2ada7-103">バインド ファイルの PrimaryTransport ノードの TransportType ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられているアダプターに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ada7-103">The TransportType node of the PrimaryTransport node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="2ada7-104">TransportType ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="2ada7-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="2ada7-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="2ada7-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="2ada7-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="2ada7-106">**Name**</span></span>|<span data-ttu-id="2ada7-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="2ada7-107">**Node Type**</span></span>|<span data-ttu-id="2ada7-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2ada7-108">**Data Type**</span></span>|<span data-ttu-id="2ada7-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="2ada7-109">**Description**</span></span>|<span data-ttu-id="2ada7-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="2ada7-110">**Restrictions**</span></span>|<span data-ttu-id="2ada7-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="2ada7-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="2ada7-112">名前</span><span class="sxs-lookup"><span data-stu-id="2ada7-112">Name</span></span>|<span data-ttu-id="2ada7-113">属性</span><span class="sxs-lookup"><span data-stu-id="2ada7-113">Attribute</span></span>|<span data-ttu-id="2ada7-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ada7-114">xs:string</span></span>|<span data-ttu-id="2ada7-115">トランスポートに関連付けられているアダプターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ada7-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="2ada7-116">任意</span><span class="sxs-lookup"><span data-stu-id="2ada7-116">Not required</span></span>|<span data-ttu-id="2ada7-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="2ada7-117">Default value: empty</span></span>|  
|<span data-ttu-id="2ada7-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="2ada7-118">Capabilities</span></span>|<span data-ttu-id="2ada7-119">属性</span><span class="sxs-lookup"><span data-stu-id="2ada7-119">Attribute</span></span>|<span data-ttu-id="2ada7-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="2ada7-120">xs:int</span></span>|<span data-ttu-id="2ada7-121">トランスポートに関連付けられているアダプターの機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ada7-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="2ada7-122">Required</span><span class="sxs-lookup"><span data-stu-id="2ada7-122">Required</span></span>|<span data-ttu-id="2ada7-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="2ada7-123">Default value: none</span></span><br /><br /> <span data-ttu-id="2ada7-124">設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ada7-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="2ada7-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="2ada7-125">ConfigurationClsid</span></span>|<span data-ttu-id="2ada7-126">属性</span><span class="sxs-lookup"><span data-stu-id="2ada7-126">Attribute</span></span>|<span data-ttu-id="2ada7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2ada7-127">xs:string</span></span>|<span data-ttu-id="2ada7-128">トランスポートに関連付けられているアダプターの構成 GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ada7-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="2ada7-129">任意</span><span class="sxs-lookup"><span data-stu-id="2ada7-129">Not required</span></span>|<span data-ttu-id="2ada7-130">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="2ada7-130">Default value: empty</span></span>|
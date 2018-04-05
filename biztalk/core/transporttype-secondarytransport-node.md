---
title: TransportType (SecondaryTransport ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: 7bb0b9460e6c4689dab169a37a9d6b6c51753598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype-secondarytransport-node"></a><span data-ttu-id="aadad-102">TransportType (SecondaryTransport ノード)</span><span class="sxs-lookup"><span data-stu-id="aadad-102">TransportType (SecondaryTransport Node)</span></span>
<span data-ttu-id="aadad-103">バインド ファイルの SecondaryTransport ノードの TransportType ノードには、バインド ファイルと共にエクスポートされるトランスポートに関連付けられているアダプターに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aadad-103">The TransportType node of the SecondaryTransport node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="aadad-104">TransportType ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="aadad-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="aadad-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="aadad-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="aadad-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="aadad-106">**Name**</span></span>|<span data-ttu-id="aadad-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="aadad-107">**Node Type**</span></span>|<span data-ttu-id="aadad-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="aadad-108">**Data Type**</span></span>|<span data-ttu-id="aadad-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="aadad-109">**Description**</span></span>|<span data-ttu-id="aadad-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="aadad-110">**Restrictions**</span></span>|<span data-ttu-id="aadad-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="aadad-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="aadad-112">名前</span><span class="sxs-lookup"><span data-stu-id="aadad-112">Name</span></span>|<span data-ttu-id="aadad-113">属性</span><span class="sxs-lookup"><span data-stu-id="aadad-113">Attribute</span></span>|<span data-ttu-id="aadad-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="aadad-114">xs:string</span></span>|<span data-ttu-id="aadad-115">トランスポートに関連付けられているアダプターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aadad-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="aadad-116">任意</span><span class="sxs-lookup"><span data-stu-id="aadad-116">Not required</span></span>|<span data-ttu-id="aadad-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="aadad-117">Default value: empty</span></span>|  
|<span data-ttu-id="aadad-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="aadad-118">Capabilities</span></span>|<span data-ttu-id="aadad-119">属性</span><span class="sxs-lookup"><span data-stu-id="aadad-119">Attribute</span></span>|<span data-ttu-id="aadad-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="aadad-120">xs:int</span></span>|<span data-ttu-id="aadad-121">トランスポートに関連付けられているアダプターの機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="aadad-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="aadad-122">Required</span><span class="sxs-lookup"><span data-stu-id="aadad-122">Required</span></span>|<span data-ttu-id="aadad-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="aadad-123">Default value: none</span></span><br /><br /> <span data-ttu-id="aadad-124">設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aadad-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="aadad-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="aadad-125">ConfigurationClsid</span></span>|<span data-ttu-id="aadad-126">属性</span><span class="sxs-lookup"><span data-stu-id="aadad-126">Attribute</span></span>|<span data-ttu-id="aadad-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="aadad-127">xs:string</span></span>|<span data-ttu-id="aadad-128">トランスポートに関連付けられているアダプターの構成 GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="aadad-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="aadad-129">任意</span><span class="sxs-lookup"><span data-stu-id="aadad-129">Not required</span></span>|<span data-ttu-id="aadad-130">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="aadad-130">Default value: empty</span></span>|
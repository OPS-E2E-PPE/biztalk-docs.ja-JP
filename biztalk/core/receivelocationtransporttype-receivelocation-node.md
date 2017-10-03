---
title: "ReceiveLocationTransportType (ReceiveLocation ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ReceiveLocationTransportType node [binding file]
ms.assetid: 375076c3-d5e6-4c25-b054-b452e29717e0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0eae3e2c4fd9f5f668cb12ffd630640b1b63c74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receivelocationtransporttype-receivelocation-node"></a><span data-ttu-id="7daf4-102">ReceiveLocationTransportType (ReceiveLocation ノード)</span><span class="sxs-lookup"><span data-stu-id="7daf4-102">ReceiveLocationTransportType (ReceiveLocation Node)</span></span>
<span data-ttu-id="7daf4-103">バインド ファイルの ReceiveLocation ノードの ReceiveLocationTransportType ノードには、そのバインド ファイルと共にエクスポートされるトランスポートに関連付けられているアダプターに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7daf4-103">The ReceiveLocationTransportType node of the ReceiveLocation node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a><span data-ttu-id="7daf4-104">ReceiveLocationTransportType ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="7daf4-104">Nodes in the ReceiveLocationTransportType node</span></span>  
 <span data-ttu-id="7daf4-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="7daf4-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="7daf4-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="7daf4-106">**Name**</span></span>|<span data-ttu-id="7daf4-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="7daf4-107">**Node Type**</span></span>|<span data-ttu-id="7daf4-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="7daf4-108">**Data Type**</span></span>|<span data-ttu-id="7daf4-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="7daf4-109">**Description**</span></span>|<span data-ttu-id="7daf4-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="7daf4-110">**Restrictions**</span></span>|<span data-ttu-id="7daf4-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="7daf4-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="7daf4-112">名前</span><span class="sxs-lookup"><span data-stu-id="7daf4-112">Name</span></span>|<span data-ttu-id="7daf4-113">属性</span><span class="sxs-lookup"><span data-stu-id="7daf4-113">Attribute</span></span>|<span data-ttu-id="7daf4-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="7daf4-114">xs:string</span></span>|<span data-ttu-id="7daf4-115">トランスポートに関連付けられているアダプターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7daf4-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="7daf4-116">任意</span><span class="sxs-lookup"><span data-stu-id="7daf4-116">Not required</span></span>|<span data-ttu-id="7daf4-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="7daf4-117">Default value: empty</span></span>|  
|<span data-ttu-id="7daf4-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="7daf4-118">Capabilities</span></span>|<span data-ttu-id="7daf4-119">属性</span><span class="sxs-lookup"><span data-stu-id="7daf4-119">Attribute</span></span>|<span data-ttu-id="7daf4-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="7daf4-120">xs:int</span></span>|<span data-ttu-id="7daf4-121">トランスポートに関連付けられているアダプターの機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="7daf4-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="7daf4-122">Required</span><span class="sxs-lookup"><span data-stu-id="7daf4-122">Required</span></span>|<span data-ttu-id="7daf4-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="7daf4-123">Default value: none</span></span><br /><br /> <span data-ttu-id="7daf4-124">設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7daf4-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="7daf4-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="7daf4-125">ConfigurationClsid</span></span>|<span data-ttu-id="7daf4-126">属性</span><span class="sxs-lookup"><span data-stu-id="7daf4-126">Attribute</span></span>|<span data-ttu-id="7daf4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7daf4-127">xs:string</span></span>|<span data-ttu-id="7daf4-128">トランスポートに関連付けられているアダプターの構成 GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="7daf4-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="7daf4-129">任意</span><span class="sxs-lookup"><span data-stu-id="7daf4-129">Not required</span></span>|<span data-ttu-id="7daf4-130">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="7daf4-130">Default value: empty</span></span>|
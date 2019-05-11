---
title: TransportType (SendHandler ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: ee87a409-33dd-4111-ba6a-ead3bacc80aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd31acc6cd31e359c1fc448d3468918675553d84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401854"
---
# <a name="transporttype-sendhandler-node"></a><span data-ttu-id="9d832-102">TransportType (SendHandler ノード)</span><span class="sxs-lookup"><span data-stu-id="9d832-102">TransportType (SendHandler Node)</span></span>
<span data-ttu-id="9d832-103">バインド ファイルの SendHandler ノードの TransportType ノードには、バインド ファイルと共にエクスポートされる送信ハンドラーに関連付けられたアダプターに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d832-103">The TransportType node of the SendHandler node of a binding file contains specific information about the adapter associated with a send handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="9d832-104">TransportType ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="9d832-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="9d832-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="9d832-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="9d832-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="9d832-106">**Name**</span></span>|<span data-ttu-id="9d832-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="9d832-107">**Node Type**</span></span>|<span data-ttu-id="9d832-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="9d832-108">**Data Type**</span></span>|<span data-ttu-id="9d832-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="9d832-109">**Description**</span></span>|<span data-ttu-id="9d832-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="9d832-110">**Restrictions**</span></span>|<span data-ttu-id="9d832-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="9d832-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="9d832-112">名前</span><span class="sxs-lookup"><span data-stu-id="9d832-112">Name</span></span>|<span data-ttu-id="9d832-113">属性</span><span class="sxs-lookup"><span data-stu-id="9d832-113">Attribute</span></span>|<span data-ttu-id="9d832-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d832-114">xs:string</span></span>|<span data-ttu-id="9d832-115">送信ハンドラーに関連付けられているアダプターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d832-115">Specifies the name of the adapter associated with the send handler.</span></span>|<span data-ttu-id="9d832-116">任意</span><span class="sxs-lookup"><span data-stu-id="9d832-116">Not required</span></span>|<span data-ttu-id="9d832-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="9d832-117">Default value: empty</span></span>|  
|<span data-ttu-id="9d832-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="9d832-118">Capabilities</span></span>|<span data-ttu-id="9d832-119">属性</span><span class="sxs-lookup"><span data-stu-id="9d832-119">Attribute</span></span>|<span data-ttu-id="9d832-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="9d832-120">xs:int</span></span>|<span data-ttu-id="9d832-121">送信ハンドラーに関連付けられているアダプターの機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d832-121">Specifies the capabilities of the adapter associated with the send handler.</span></span>|<span data-ttu-id="9d832-122">必須</span><span class="sxs-lookup"><span data-stu-id="9d832-122">Required</span></span>|<span data-ttu-id="9d832-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="9d832-123">Default value: none</span></span><br /><br /> <span data-ttu-id="9d832-124">設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d832-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="9d832-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="9d832-125">ConfigurationClsid</span></span>|<span data-ttu-id="9d832-126">属性</span><span class="sxs-lookup"><span data-stu-id="9d832-126">Attribute</span></span>|<span data-ttu-id="9d832-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d832-127">xs:string</span></span>|<span data-ttu-id="9d832-128">送信ハンドラーに関連付けられているアダプターの構成 GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d832-128">Specifies the configuration GUID of the adapter associated with the send handler.</span></span>|<span data-ttu-id="9d832-129">任意</span><span class="sxs-lookup"><span data-stu-id="9d832-129">Not required</span></span>|<span data-ttu-id="9d832-130">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="9d832-130">Default value: empty</span></span>|
---
title: TransportType |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: 64eb00be-47c9-473f-aec6-03cb7f948e3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e2c47dc4b4851cad5f0daf1f995c4cd2a1bc0a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398693"
---
# <a name="transporttype"></a><span data-ttu-id="81a92-102">TransportType</span><span class="sxs-lookup"><span data-stu-id="81a92-102">TransportType</span></span>
<span data-ttu-id="81a92-103">バインド ファイルの SendHandler ノードの TransportType ノードには、バインド ファイルと共にエクスポートされる送信ハンドラーに関連付けられたアダプターに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="81a92-103">The TransportType node of the SendHandler node of a binding file contains specific information about the adapter associated with a send handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="81a92-104">TransportType ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="81a92-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="81a92-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="81a92-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="81a92-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="81a92-106">**Name**</span></span>|<span data-ttu-id="81a92-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="81a92-107">**Node Type**</span></span>|<span data-ttu-id="81a92-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="81a92-108">**Data Type**</span></span>|<span data-ttu-id="81a92-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="81a92-109">**Description**</span></span>|<span data-ttu-id="81a92-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="81a92-110">**Restrictions**</span></span>|<span data-ttu-id="81a92-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="81a92-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="81a92-112">名前</span><span class="sxs-lookup"><span data-stu-id="81a92-112">Name</span></span>|<span data-ttu-id="81a92-113">属性</span><span class="sxs-lookup"><span data-stu-id="81a92-113">Attribute</span></span>|<span data-ttu-id="81a92-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="81a92-114">xs:string</span></span>|<span data-ttu-id="81a92-115">送信ハンドラーに関連付けられているアダプターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="81a92-115">Specifies the name of the adapter associated with the send handler.</span></span>|<span data-ttu-id="81a92-116">任意</span><span class="sxs-lookup"><span data-stu-id="81a92-116">Not required</span></span>|<span data-ttu-id="81a92-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="81a92-117">Default value: empty</span></span>|  
|<span data-ttu-id="81a92-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="81a92-118">Capabilities</span></span>|<span data-ttu-id="81a92-119">属性</span><span class="sxs-lookup"><span data-stu-id="81a92-119">Attribute</span></span>|<span data-ttu-id="81a92-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="81a92-120">xs:int</span></span>|<span data-ttu-id="81a92-121">送信ハンドラーに関連付けられているアダプターの機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="81a92-121">Specifies the capabilities of the adapter associated with the send handler.</span></span>|<span data-ttu-id="81a92-122">必須</span><span class="sxs-lookup"><span data-stu-id="81a92-122">Required</span></span>|<span data-ttu-id="81a92-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="81a92-123">Default value: none</span></span><br /><br /> <span data-ttu-id="81a92-124">設定可能な値には、 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 列挙体に使用できる値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="81a92-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="81a92-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="81a92-125">ConfigurationClsid</span></span>|<span data-ttu-id="81a92-126">属性</span><span class="sxs-lookup"><span data-stu-id="81a92-126">Attribute</span></span>|<span data-ttu-id="81a92-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="81a92-127">xs:string</span></span>|<span data-ttu-id="81a92-128">送信ハンドラーに関連付けられているアダプターの構成 GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="81a92-128">Specifies the configuration GUID of the adapter associated with the send handler.</span></span>|<span data-ttu-id="81a92-129">任意</span><span class="sxs-lookup"><span data-stu-id="81a92-129">Not required</span></span>|<span data-ttu-id="81a92-130">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="81a92-130">Default value: empty</span></span>|
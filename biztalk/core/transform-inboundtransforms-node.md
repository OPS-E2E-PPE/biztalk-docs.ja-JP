---
title: Transform (InboundTransforms ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: c1bad23e-78a4-4fd4-95ef-30601393d53c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93ae620e3f9f40e2f76b814dbfde4b45910c63c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399190"
---
# <a name="transform-inboundtransforms-node"></a><span data-ttu-id="1d4be-102">Transform (InboundTransforms ノード)</span><span class="sxs-lookup"><span data-stu-id="1d4be-102">Transform (InboundTransforms Node)</span></span>
<span data-ttu-id="1d4be-103">バインド ファイルの InboundTransforms ノードの Transform ノードには、バインド ファイルと共にエクスポートされる BizTalk Server マップに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d4be-103">The Transform node of the InboundTransforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="1d4be-104">Transform ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="1d4be-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="1d4be-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="1d4be-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="1d4be-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="1d4be-106">**Name**</span></span>|<span data-ttu-id="1d4be-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="1d4be-107">**Node Type**</span></span>|<span data-ttu-id="1d4be-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="1d4be-108">**Data Type**</span></span>|<span data-ttu-id="1d4be-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="1d4be-109">**Description**</span></span>|<span data-ttu-id="1d4be-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="1d4be-110">**Restrictions**</span></span>|<span data-ttu-id="1d4be-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="1d4be-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="1d4be-112">FullName</span><span class="sxs-lookup"><span data-stu-id="1d4be-112">FullName</span></span>|<span data-ttu-id="1d4be-113">属性</span><span class="sxs-lookup"><span data-stu-id="1d4be-113">Attribute</span></span>|<span data-ttu-id="1d4be-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d4be-114">xs:string</span></span>|<span data-ttu-id="1d4be-115">マップの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d4be-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="1d4be-116">任意</span><span class="sxs-lookup"><span data-stu-id="1d4be-116">Not required</span></span>|<span data-ttu-id="1d4be-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="1d4be-117">Default value: empty</span></span>|  
|<span data-ttu-id="1d4be-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1d4be-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="1d4be-119">属性</span><span class="sxs-lookup"><span data-stu-id="1d4be-119">Attribute</span></span>|<span data-ttu-id="1d4be-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d4be-120">xs:string</span></span>|<span data-ttu-id="1d4be-121">マップのアセンブリ修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d4be-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="1d4be-122">任意</span><span class="sxs-lookup"><span data-stu-id="1d4be-122">Not required</span></span>|<span data-ttu-id="1d4be-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="1d4be-123">Default value: empty</span></span>|
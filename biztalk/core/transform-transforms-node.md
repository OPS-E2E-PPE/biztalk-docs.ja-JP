---
title: Transform (Transforms ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: 2d1387f1-1668-4982-a717-52478e2a91f9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16eaf34e34c51c48a926b5f4c38daa1adbf9e1f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243072"
---
# <a name="transform-transforms-node"></a><span data-ttu-id="3c5f0-102">Transform (Transforms ノード)</span><span class="sxs-lookup"><span data-stu-id="3c5f0-102">Transform (Transforms Node)</span></span>
<span data-ttu-id="3c5f0-103">バインド ファイルの Transforms ノードの Transform ノードには、バインド ファイルと共にエクスポートされる BizTalk Server マップに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c5f0-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="3c5f0-104">Transform ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="3c5f0-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="3c5f0-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="3c5f0-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="3c5f0-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="3c5f0-106">**Name**</span></span>|<span data-ttu-id="3c5f0-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="3c5f0-107">**Node Type**</span></span>|<span data-ttu-id="3c5f0-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="3c5f0-108">**Data Type**</span></span>|<span data-ttu-id="3c5f0-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="3c5f0-109">**Description**</span></span>|<span data-ttu-id="3c5f0-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="3c5f0-110">**Restrictions**</span></span>|<span data-ttu-id="3c5f0-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="3c5f0-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="3c5f0-112">FullName</span><span class="sxs-lookup"><span data-stu-id="3c5f0-112">FullName</span></span>|<span data-ttu-id="3c5f0-113">属性</span><span class="sxs-lookup"><span data-stu-id="3c5f0-113">Attribute</span></span>|<span data-ttu-id="3c5f0-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c5f0-114">xs:string</span></span>|<span data-ttu-id="3c5f0-115">マップの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c5f0-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="3c5f0-116">任意</span><span class="sxs-lookup"><span data-stu-id="3c5f0-116">Not required</span></span>|<span data-ttu-id="3c5f0-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="3c5f0-117">Default value: empty</span></span>|  
|<span data-ttu-id="3c5f0-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="3c5f0-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="3c5f0-119">属性</span><span class="sxs-lookup"><span data-stu-id="3c5f0-119">Attribute</span></span>|<span data-ttu-id="3c5f0-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c5f0-120">xs:string</span></span>|<span data-ttu-id="3c5f0-121">マップのアセンブリ修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c5f0-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="3c5f0-122">任意</span><span class="sxs-lookup"><span data-stu-id="3c5f0-122">Not required</span></span>|<span data-ttu-id="3c5f0-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="3c5f0-123">Default value: empty</span></span>|
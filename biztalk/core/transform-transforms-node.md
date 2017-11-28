---
title: "Transform (Transforms ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transform node [binding file]
ms.assetid: 2d1387f1-1668-4982-a717-52478e2a91f9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33e70e5a2bcba2925941e727034b90c9fe4b1418
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transform-transforms-node"></a><span data-ttu-id="dfd6c-102">Transform (Transforms ノード)</span><span class="sxs-lookup"><span data-stu-id="dfd6c-102">Transform (Transforms Node)</span></span>
<span data-ttu-id="dfd6c-103">バインド ファイルの Transforms ノードの Transform ノードには、バインド ファイルと共にエクスポートされる BizTalk Server マップに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dfd6c-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="dfd6c-104">Transform ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="dfd6c-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="dfd6c-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="dfd6c-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="dfd6c-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="dfd6c-106">**Name**</span></span>|<span data-ttu-id="dfd6c-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="dfd6c-107">**Node Type**</span></span>|<span data-ttu-id="dfd6c-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="dfd6c-108">**Data Type**</span></span>|<span data-ttu-id="dfd6c-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="dfd6c-109">**Description**</span></span>|<span data-ttu-id="dfd6c-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="dfd6c-110">**Restrictions**</span></span>|<span data-ttu-id="dfd6c-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="dfd6c-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="dfd6c-112">FullName</span><span class="sxs-lookup"><span data-stu-id="dfd6c-112">FullName</span></span>|<span data-ttu-id="dfd6c-113">属性</span><span class="sxs-lookup"><span data-stu-id="dfd6c-113">Attribute</span></span>|<span data-ttu-id="dfd6c-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="dfd6c-114">xs:string</span></span>|<span data-ttu-id="dfd6c-115">マップの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfd6c-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="dfd6c-116">任意</span><span class="sxs-lookup"><span data-stu-id="dfd6c-116">Not required</span></span>|<span data-ttu-id="dfd6c-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="dfd6c-117">Default value: empty</span></span>|  
|<span data-ttu-id="dfd6c-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="dfd6c-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="dfd6c-119">属性</span><span class="sxs-lookup"><span data-stu-id="dfd6c-119">Attribute</span></span>|<span data-ttu-id="dfd6c-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="dfd6c-120">xs:string</span></span>|<span data-ttu-id="dfd6c-121">マップのアセンブリ修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dfd6c-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="dfd6c-122">任意</span><span class="sxs-lookup"><span data-stu-id="dfd6c-122">Not required</span></span>|<span data-ttu-id="dfd6c-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="dfd6c-123">Default value: empty</span></span>|
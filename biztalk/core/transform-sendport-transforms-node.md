---
title: Transform (Sendport-transforms ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: db9a82b2-9bc1-4bd8-8d98-a708a8d25b35
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca25040f9f462b35e1fd91f9afc6b1758c6559f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303029"
---
# <a name="transform-sendport-transforms-node"></a><span data-ttu-id="b7519-102">Transform (Sendport-transforms ノード)</span><span class="sxs-lookup"><span data-stu-id="b7519-102">Transform (SendPort-Transforms Node)</span></span>
<span data-ttu-id="b7519-103">バインド ファイルの Transforms ノードの Transform ノードには、バインド ファイルと共にエクスポートされる BizTalk Server マップに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7519-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="b7519-104">Transform ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="b7519-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="b7519-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="b7519-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="b7519-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="b7519-106">**Name**</span></span>|<span data-ttu-id="b7519-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="b7519-107">**Node Type**</span></span>|<span data-ttu-id="b7519-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="b7519-108">**Data Type**</span></span>|<span data-ttu-id="b7519-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="b7519-109">**Description**</span></span>|<span data-ttu-id="b7519-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="b7519-110">**Restrictions**</span></span>|<span data-ttu-id="b7519-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="b7519-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="b7519-112">FullName</span><span class="sxs-lookup"><span data-stu-id="b7519-112">FullName</span></span>|<span data-ttu-id="b7519-113">属性</span><span class="sxs-lookup"><span data-stu-id="b7519-113">Attribute</span></span>|<span data-ttu-id="b7519-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7519-114">xs:string</span></span>|<span data-ttu-id="b7519-115">マップの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7519-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="b7519-116">任意</span><span class="sxs-lookup"><span data-stu-id="b7519-116">Not required</span></span>|<span data-ttu-id="b7519-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="b7519-117">Default value: empty</span></span>|  
|<span data-ttu-id="b7519-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="b7519-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="b7519-119">属性</span><span class="sxs-lookup"><span data-stu-id="b7519-119">Attribute</span></span>|<span data-ttu-id="b7519-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7519-120">xs:string</span></span>|<span data-ttu-id="b7519-121">マップのアセンブリ修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7519-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="b7519-122">任意</span><span class="sxs-lookup"><span data-stu-id="b7519-122">Not required</span></span>|<span data-ttu-id="b7519-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="b7519-123">Default value: empty</span></span>|
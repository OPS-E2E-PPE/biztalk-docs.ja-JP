---
title: Transform (InboundTransforms ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: 705b1b04b8305330ab1d5ff705c5025f24b0685c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279114"
---
# <a name="transform-inboundtransforms-node"></a><span data-ttu-id="5f4e4-102">Transform (InboundTransforms ノード)</span><span class="sxs-lookup"><span data-stu-id="5f4e4-102">Transform (InboundTransforms Node)</span></span>
<span data-ttu-id="5f4e4-103">バインド ファイルの InboundTransforms ノードの Transform ノードには、バインド ファイルと共にエクスポートされる BizTalk Server マップに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-103">The Transform node of the InboundTransforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="5f4e4-104">Transform ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="5f4e4-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="5f4e4-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="5f4e4-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="5f4e4-106">**Name**</span></span>|<span data-ttu-id="5f4e4-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="5f4e4-107">**Node Type**</span></span>|<span data-ttu-id="5f4e4-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5f4e4-108">**Data Type**</span></span>|<span data-ttu-id="5f4e4-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="5f4e4-109">**Description**</span></span>|<span data-ttu-id="5f4e4-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="5f4e4-110">**Restrictions**</span></span>|<span data-ttu-id="5f4e4-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="5f4e4-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="5f4e4-112">FullName</span><span class="sxs-lookup"><span data-stu-id="5f4e4-112">FullName</span></span>|<span data-ttu-id="5f4e4-113">属性</span><span class="sxs-lookup"><span data-stu-id="5f4e4-113">Attribute</span></span>|<span data-ttu-id="5f4e4-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f4e4-114">xs:string</span></span>|<span data-ttu-id="5f4e4-115">マップの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="5f4e4-116">任意</span><span class="sxs-lookup"><span data-stu-id="5f4e4-116">Not required</span></span>|<span data-ttu-id="5f4e4-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="5f4e4-117">Default value: empty</span></span>|  
|<span data-ttu-id="5f4e4-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="5f4e4-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="5f4e4-119">属性</span><span class="sxs-lookup"><span data-stu-id="5f4e4-119">Attribute</span></span>|<span data-ttu-id="5f4e4-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f4e4-120">xs:string</span></span>|<span data-ttu-id="5f4e4-121">マップのアセンブリ修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f4e4-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="5f4e4-122">任意</span><span class="sxs-lookup"><span data-stu-id="5f4e4-122">Not required</span></span>|<span data-ttu-id="5f4e4-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="5f4e4-123">Default value: empty</span></span>|
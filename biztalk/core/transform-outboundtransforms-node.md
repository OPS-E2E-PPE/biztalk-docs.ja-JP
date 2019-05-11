---
title: Transform (OutboundTransforms ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: 928a93cd-7a26-4148-b1af-dc0bc316f8c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19c2940dd7700f7d3da63d0e9d897429d154d8e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302952"
---
# <a name="transform-outboundtransforms-node"></a><span data-ttu-id="4966a-102">Transform (OutboundTransforms ノード)</span><span class="sxs-lookup"><span data-stu-id="4966a-102">Transform (OutboundTransforms Node)</span></span>
<span data-ttu-id="4966a-103">バインド ファイルの OutboundTransforms ノードの Transform ノードには、バインド ファイルと共にエクスポートされる BizTalk Server マップに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4966a-103">The Transform node of the OutboundTransforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="4966a-104">Transform ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="4966a-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="4966a-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="4966a-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="4966a-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="4966a-106">**Name**</span></span>|<span data-ttu-id="4966a-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="4966a-107">**Node Type**</span></span>|<span data-ttu-id="4966a-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="4966a-108">**Data Type**</span></span>|<span data-ttu-id="4966a-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="4966a-109">**Description**</span></span>|<span data-ttu-id="4966a-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="4966a-110">**Restrictions**</span></span>|<span data-ttu-id="4966a-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="4966a-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="4966a-112">FullName</span><span class="sxs-lookup"><span data-stu-id="4966a-112">FullName</span></span>|<span data-ttu-id="4966a-113">属性</span><span class="sxs-lookup"><span data-stu-id="4966a-113">Attribute</span></span>|<span data-ttu-id="4966a-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="4966a-114">xs:string</span></span>|<span data-ttu-id="4966a-115">マップの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4966a-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="4966a-116">任意</span><span class="sxs-lookup"><span data-stu-id="4966a-116">Not required</span></span>|<span data-ttu-id="4966a-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="4966a-117">Default value: empty</span></span>|  
|<span data-ttu-id="4966a-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="4966a-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="4966a-119">属性</span><span class="sxs-lookup"><span data-stu-id="4966a-119">Attribute</span></span>|<span data-ttu-id="4966a-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="4966a-120">xs:string</span></span>|<span data-ttu-id="4966a-121">マップのアセンブリ修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4966a-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="4966a-122">任意</span><span class="sxs-lookup"><span data-stu-id="4966a-122">Not required</span></span>|<span data-ttu-id="4966a-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="4966a-123">Default value: empty</span></span>|
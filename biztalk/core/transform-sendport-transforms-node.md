---
title: "Transform (SendPort Transforms ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transform node [binding file]
ms.assetid: db9a82b2-9bc1-4bd8-8d98-a708a8d25b35
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a54ed1f25b762d12f598bca84da9b9c3ddd26a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transform-sendport-transforms-node"></a><span data-ttu-id="8633a-102">Transform (SendPort Transforms ノード)</span><span class="sxs-lookup"><span data-stu-id="8633a-102">Transform (SendPort-Transforms Node)</span></span>
<span data-ttu-id="8633a-103">バインド ファイルの Transforms ノードの Transform ノードには、バインド ファイルと共にエクスポートされる BizTalk Server マップに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8633a-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="8633a-104">Transform ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="8633a-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="8633a-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="8633a-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="8633a-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="8633a-106">**Name**</span></span>|<span data-ttu-id="8633a-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="8633a-107">**Node Type**</span></span>|<span data-ttu-id="8633a-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="8633a-108">**Data Type**</span></span>|<span data-ttu-id="8633a-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="8633a-109">**Description**</span></span>|<span data-ttu-id="8633a-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="8633a-110">**Restrictions**</span></span>|<span data-ttu-id="8633a-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="8633a-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="8633a-112">FullName</span><span class="sxs-lookup"><span data-stu-id="8633a-112">FullName</span></span>|<span data-ttu-id="8633a-113">属性</span><span class="sxs-lookup"><span data-stu-id="8633a-113">Attribute</span></span>|<span data-ttu-id="8633a-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="8633a-114">xs:string</span></span>|<span data-ttu-id="8633a-115">マップの完全な名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8633a-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="8633a-116">任意</span><span class="sxs-lookup"><span data-stu-id="8633a-116">Not required</span></span>|<span data-ttu-id="8633a-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="8633a-117">Default value: empty</span></span>|  
|<span data-ttu-id="8633a-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="8633a-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="8633a-119">属性</span><span class="sxs-lookup"><span data-stu-id="8633a-119">Attribute</span></span>|<span data-ttu-id="8633a-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="8633a-120">xs:string</span></span>|<span data-ttu-id="8633a-121">マップのアセンブリ修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8633a-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="8633a-122">任意</span><span class="sxs-lookup"><span data-stu-id="8633a-122">Not required</span></span>|<span data-ttu-id="8633a-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="8633a-123">Default value: empty</span></span>|
---
title: "Mapping (Mappings ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2c62d46e4d5c2b73eee5094ecda0e20c039798a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mapping-mappings-node"></a><span data-ttu-id="8e32a-102">Mapping (Mappings ノード)</span><span class="sxs-lookup"><span data-stu-id="8e32a-102">Mapping (Mappings Node)</span></span>
<span data-ttu-id="8e32a-103">バインド ファイルの Mapping ノードでは、参加しているパーティのパーティ ポートとロール ポートの操作の間のマッピングを記述します。</span><span class="sxs-lookup"><span data-stu-id="8e32a-103">The Mapping node of a binding file describes the mapping between a party port and role port type operation for the enlisted party.</span></span>  
  
## <a name="nodes-in-the-mapping-node"></a><span data-ttu-id="8e32a-104">Mapping ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="8e32a-104">Nodes in the Mapping node</span></span>  
 <span data-ttu-id="8e32a-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="8e32a-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="8e32a-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="8e32a-106">**Name**</span></span>|<span data-ttu-id="8e32a-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="8e32a-107">**Node Type**</span></span>|<span data-ttu-id="8e32a-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="8e32a-108">**Data Type**</span></span>|<span data-ttu-id="8e32a-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="8e32a-109">**Description**</span></span>|<span data-ttu-id="8e32a-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="8e32a-110">**Restrictions**</span></span>|<span data-ttu-id="8e32a-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="8e32a-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="8e32a-112">PortTypeName</span><span class="sxs-lookup"><span data-stu-id="8e32a-112">PortTypeName</span></span>|<span data-ttu-id="8e32a-113">属性</span><span class="sxs-lookup"><span data-stu-id="8e32a-113">Attribute</span></span>|<span data-ttu-id="8e32a-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="8e32a-114">xs:string</span></span>|<span data-ttu-id="8e32a-115">ポートの種類の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e32a-115">Specifies the name of the port type.</span></span>|<span data-ttu-id="8e32a-116">任意</span><span class="sxs-lookup"><span data-stu-id="8e32a-116">Not required</span></span>|<span data-ttu-id="8e32a-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="8e32a-117">Default value: empty</span></span>|  
|<span data-ttu-id="8e32a-118">OperationName</span><span class="sxs-lookup"><span data-stu-id="8e32a-118">OperationName</span></span>|<span data-ttu-id="8e32a-119">属性</span><span class="sxs-lookup"><span data-stu-id="8e32a-119">Attribute</span></span>|<span data-ttu-id="8e32a-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="8e32a-120">xs:string</span></span>|<span data-ttu-id="8e32a-121">このポートの種類に属する操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e32a-121">Specifies the operation belonging to this port type.</span></span>|<span data-ttu-id="8e32a-122">任意</span><span class="sxs-lookup"><span data-stu-id="8e32a-122">Not required</span></span>|<span data-ttu-id="8e32a-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="8e32a-123">Default value: empty</span></span>|  
|[<span data-ttu-id="8e32a-124">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="8e32a-124">SendPortRef</span></span>](../core/sendportref-mapping-node.md)|<span data-ttu-id="8e32a-125">レコード</span><span class="sxs-lookup"><span data-stu-id="8e32a-125">Record</span></span>|<span data-ttu-id="8e32a-126">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="8e32a-126">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="8e32a-127">マッピングに関連付けられている送信ポートの一覧のコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="8e32a-127">Container node for the list of send ports associated with a mapping.</span></span>|<span data-ttu-id="8e32a-128">任意</span><span class="sxs-lookup"><span data-stu-id="8e32a-128">Not required</span></span>|<span data-ttu-id="8e32a-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="8e32a-129">Default value: none</span></span>|
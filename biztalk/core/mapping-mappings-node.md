---
title: Mapping (Mappings ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e227dd0c22734e0d448aebc0bbf4a8960575a5e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325666"
---
# <a name="mapping-mappings-node"></a><span data-ttu-id="fa79e-102">Mapping (Mappings ノード)</span><span class="sxs-lookup"><span data-stu-id="fa79e-102">Mapping (Mappings Node)</span></span>
<span data-ttu-id="fa79e-103">バインド ファイルの Mapping ノードでは、パーティのポートとロール ポートの種類操作に参加しているパーティ間のマッピングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fa79e-103">The Mapping node of a binding file describes the mapping between a party port and role port type operation for the enlisted party.</span></span>  
  
## <a name="nodes-in-the-mapping-node"></a><span data-ttu-id="fa79e-104">Mapping ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="fa79e-104">Nodes in the Mapping node</span></span>  
 <span data-ttu-id="fa79e-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="fa79e-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="fa79e-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="fa79e-106">**Name**</span></span>|<span data-ttu-id="fa79e-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="fa79e-107">**Node Type**</span></span>|<span data-ttu-id="fa79e-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="fa79e-108">**Data Type**</span></span>|<span data-ttu-id="fa79e-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="fa79e-109">**Description**</span></span>|<span data-ttu-id="fa79e-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="fa79e-110">**Restrictions**</span></span>|<span data-ttu-id="fa79e-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="fa79e-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="fa79e-112">PortTypeName</span><span class="sxs-lookup"><span data-stu-id="fa79e-112">PortTypeName</span></span>|<span data-ttu-id="fa79e-113">属性</span><span class="sxs-lookup"><span data-stu-id="fa79e-113">Attribute</span></span>|<span data-ttu-id="fa79e-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa79e-114">xs:string</span></span>|<span data-ttu-id="fa79e-115">ポートの種類の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa79e-115">Specifies the name of the port type.</span></span>|<span data-ttu-id="fa79e-116">任意</span><span class="sxs-lookup"><span data-stu-id="fa79e-116">Not required</span></span>|<span data-ttu-id="fa79e-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="fa79e-117">Default value: empty</span></span>|  
|<span data-ttu-id="fa79e-118">OperationName</span><span class="sxs-lookup"><span data-stu-id="fa79e-118">OperationName</span></span>|<span data-ttu-id="fa79e-119">属性</span><span class="sxs-lookup"><span data-stu-id="fa79e-119">Attribute</span></span>|<span data-ttu-id="fa79e-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa79e-120">xs:string</span></span>|<span data-ttu-id="fa79e-121">このポートの種類に属する操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa79e-121">Specifies the operation belonging to this port type.</span></span>|<span data-ttu-id="fa79e-122">任意</span><span class="sxs-lookup"><span data-stu-id="fa79e-122">Not required</span></span>|<span data-ttu-id="fa79e-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="fa79e-123">Default value: empty</span></span>|  
|[<span data-ttu-id="fa79e-124">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="fa79e-124">SendPortRef</span></span>](../core/sendportref-mapping-node.md)|<span data-ttu-id="fa79e-125">レコード</span><span class="sxs-lookup"><span data-stu-id="fa79e-125">Record</span></span>|<span data-ttu-id="fa79e-126">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="fa79e-126">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="fa79e-127">マッピングに関連付けられている送信ポートの一覧のコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="fa79e-127">Container node for the list of send ports associated with a mapping.</span></span>|<span data-ttu-id="fa79e-128">任意</span><span class="sxs-lookup"><span data-stu-id="fa79e-128">Not required</span></span>|<span data-ttu-id="fa79e-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="fa79e-129">Default value: none</span></span>|
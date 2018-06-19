---
title: Enlisted Party (Enlisted Parties ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enlisted Parties node [binding file]
ms.assetid: 2ff7b563-17c5-48e9-b33e-62c821188448
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624f74d3b49b80e8000723c3f7451c52b37c8d3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239954"
---
# <a name="enlisted-party-enlisted-parties-node"></a><span data-ttu-id="03251-102">Enlisted Party (Enlisted Parties ノード)</span><span class="sxs-lookup"><span data-stu-id="03251-102">Enlisted Party (Enlisted Parties Node)</span></span>
<span data-ttu-id="03251-103">バインド ファイルの Enlisted Party ノードには、バインド ファイルと共にエクスポートされるロールに関連付けられた参加しているパーティに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="03251-103">The Enlisted Party node of a binding file contains specific information about an enlisted party associated with a role that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-enlisted-party-node"></a><span data-ttu-id="03251-104">Enlisted Party ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="03251-104">Nodes in the Enlisted Party node</span></span>  
 <span data-ttu-id="03251-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="03251-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="03251-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="03251-106">**Name**</span></span>|<span data-ttu-id="03251-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="03251-107">**Node Type**</span></span>|<span data-ttu-id="03251-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="03251-108">**Data Type**</span></span>|<span data-ttu-id="03251-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="03251-109">**Description**</span></span>|<span data-ttu-id="03251-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="03251-110">**Restrictions**</span></span>|<span data-ttu-id="03251-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="03251-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="03251-112">名前</span><span class="sxs-lookup"><span data-stu-id="03251-112">Name</span></span>|<span data-ttu-id="03251-113">属性</span><span class="sxs-lookup"><span data-stu-id="03251-113">Attribute</span></span>|<span data-ttu-id="03251-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="03251-114">xs:string</span></span>|<span data-ttu-id="03251-115">参加しているパーティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="03251-115">Specifies the name of the enlisted party</span></span>|<span data-ttu-id="03251-116">任意</span><span class="sxs-lookup"><span data-stu-id="03251-116">Not required</span></span>|<span data-ttu-id="03251-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="03251-117">Default value: empty</span></span>|  
|[<span data-ttu-id="03251-118">マッピング</span><span class="sxs-lookup"><span data-stu-id="03251-118">Mappings</span></span>](../core/mappings-enlisted-party-node.md)|<span data-ttu-id="03251-119">レコード</span><span class="sxs-lookup"><span data-stu-id="03251-119">Record</span></span>|<span data-ttu-id="03251-120">ArrayOfEnlistedPartyMapping (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="03251-120">ArrayOfEnlistedPartyMapping (ComplexType)</span></span>|<span data-ttu-id="03251-121">パーティ ポートとロール ポートの種類の操作の間のマッピングのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="03251-121">Container node for the mappings between party ports and role port type operations.</span></span>|<span data-ttu-id="03251-122">任意</span><span class="sxs-lookup"><span data-stu-id="03251-122">Not required</span></span>|<span data-ttu-id="03251-123">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="03251-123">Default value: none</span></span>|
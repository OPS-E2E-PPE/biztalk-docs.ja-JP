---
title: ModuleRef (ModuleRefCollection ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRef node [binding file]
ms.assetid: 61787779-33bd-499a-a5c1-c1e0bd306b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed580b022e9896ade824c8cf8eccc2458c7ddce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="moduleref-modulerefcollection-node"></a><span data-ttu-id="e5b43-102">ModuleRef (ModuleRefCollection ノード)</span><span class="sxs-lookup"><span data-stu-id="e5b43-102">ModuleRef (ModuleRefCollection Node)</span></span>
<span data-ttu-id="e5b43-103">バインド ファイルの ModuleRef ノードには、バインド ファイルと共にエクスポートされた .NET アセンブリに関する特定の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5b43-103">The ModuleRef node of a binding file contains specific information about a .NET assembly that was exported with the binding file.</span></span> <span data-ttu-id="e5b43-104">ModuleRef ノードには、カスタム コード、スキーマ、およびオーケストレーションを含むアセンブリの説明などを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e5b43-104">A ModuleRef node can include but is not limited to descriptions of assemblies that contain custom code, schemas, and orchestrations.</span></span>  
  
## <a name="nodes-in-the-moduleref-node"></a><span data-ttu-id="e5b43-105">ModuleRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="e5b43-105">Nodes in the ModuleRef node</span></span>  
 <span data-ttu-id="e5b43-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="e5b43-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="e5b43-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="e5b43-107">**Name**</span></span>|<span data-ttu-id="e5b43-108">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="e5b43-108">**Node Type**</span></span>|<span data-ttu-id="e5b43-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e5b43-109">**Data Type**</span></span>|<span data-ttu-id="e5b43-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="e5b43-110">**Description**</span></span>|<span data-ttu-id="e5b43-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="e5b43-111">**Restrictions**</span></span>|<span data-ttu-id="e5b43-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="e5b43-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="e5b43-113">サービス</span><span class="sxs-lookup"><span data-stu-id="e5b43-113">Services</span></span>](../core/services-moduleref-node.md)|<span data-ttu-id="e5b43-114">レコード</span><span class="sxs-lookup"><span data-stu-id="e5b43-114">Record</span></span>|<span data-ttu-id="e5b43-115">ArrayOfServiceRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="e5b43-115">ArrayOfServiceRef (ComplexType)</span></span>|<span data-ttu-id="e5b43-116">この .NET アセンブリに関連付けられているサービスのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="e5b43-116">Container node for services associated with this .NET assembly.</span></span>|<span data-ttu-id="e5b43-117">任意</span><span class="sxs-lookup"><span data-stu-id="e5b43-117">Not required</span></span>|<span data-ttu-id="e5b43-118">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="e5b43-118">Default value: none</span></span>|  
|[<span data-ttu-id="e5b43-119">TrackedSchemas (ModuleRef ノード)</span><span class="sxs-lookup"><span data-stu-id="e5b43-119">TrackedSchemas (ModuleRef Node)</span></span>](../core/trackedschemas-moduleref-node.md)|<span data-ttu-id="e5b43-120">レコード</span><span class="sxs-lookup"><span data-stu-id="e5b43-120">Record</span></span>|<span data-ttu-id="e5b43-121">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="e5b43-121">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="e5b43-122">この .NET アセンブリに関連付けられているスキーマのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="e5b43-122">Container node for schemas associated with this .NET assembly</span></span>|<span data-ttu-id="e5b43-123">任意</span><span class="sxs-lookup"><span data-stu-id="e5b43-123">Not required</span></span>|<span data-ttu-id="e5b43-124">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="e5b43-124">Default value: none</span></span>|
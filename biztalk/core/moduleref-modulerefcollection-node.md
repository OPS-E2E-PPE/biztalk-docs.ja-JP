---
title: ModuleRef (ModuleRefCollection ノード) |Microsoft Docs
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
ms.openlocfilehash: 604efe0b0d5d93c6d545b7725d2a0f85609fc32a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394416"
---
# <a name="moduleref-modulerefcollection-node"></a><span data-ttu-id="1b4ef-102">ModuleRef (ModuleRefCollection ノード)</span><span class="sxs-lookup"><span data-stu-id="1b4ef-102">ModuleRef (ModuleRefCollection Node)</span></span>
<span data-ttu-id="1b4ef-103">バインド ファイルの ModuleRef ノードには、バインド ファイルと共にエクスポートされた .NET アセンブリに関する特定の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b4ef-103">The ModuleRef node of a binding file contains specific information about a .NET assembly that was exported with the binding file.</span></span> <span data-ttu-id="1b4ef-104">ModuleRef ノードでは、含めることができますが、カスタム コード、スキーマ、およびオーケストレーションを含んでいるアセンブリの説明に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="1b4ef-104">A ModuleRef node can include but is not limited to descriptions of assemblies that contain custom code, schemas, and orchestrations.</span></span>  
  
## <a name="nodes-in-the-moduleref-node"></a><span data-ttu-id="1b4ef-105">ModuleRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="1b4ef-105">Nodes in the ModuleRef node</span></span>  
 <span data-ttu-id="1b4ef-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="1b4ef-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="1b4ef-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="1b4ef-107">**Name**</span></span>|<span data-ttu-id="1b4ef-108">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="1b4ef-108">**Node Type**</span></span>|<span data-ttu-id="1b4ef-109">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="1b4ef-109">**Data Type**</span></span>|<span data-ttu-id="1b4ef-110">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="1b4ef-110">**Description**</span></span>|<span data-ttu-id="1b4ef-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="1b4ef-111">**Restrictions**</span></span>|<span data-ttu-id="1b4ef-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="1b4ef-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="1b4ef-113">Services</span><span class="sxs-lookup"><span data-stu-id="1b4ef-113">Services</span></span>](../core/services-moduleref-node.md)|<span data-ttu-id="1b4ef-114">レコード</span><span class="sxs-lookup"><span data-stu-id="1b4ef-114">Record</span></span>|<span data-ttu-id="1b4ef-115">ArrayOfServiceRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="1b4ef-115">ArrayOfServiceRef (ComplexType)</span></span>|<span data-ttu-id="1b4ef-116">この .NET アセンブリに関連付けられたサービスのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="1b4ef-116">Container node for services associated with this .NET assembly.</span></span>|<span data-ttu-id="1b4ef-117">任意</span><span class="sxs-lookup"><span data-stu-id="1b4ef-117">Not required</span></span>|<span data-ttu-id="1b4ef-118">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="1b4ef-118">Default value: none</span></span>|  
|[<span data-ttu-id="1b4ef-119">TrackedSchemas (ModuleRef ノード)</span><span class="sxs-lookup"><span data-stu-id="1b4ef-119">TrackedSchemas (ModuleRef Node)</span></span>](../core/trackedschemas-moduleref-node.md)|<span data-ttu-id="1b4ef-120">レコード</span><span class="sxs-lookup"><span data-stu-id="1b4ef-120">Record</span></span>|<span data-ttu-id="1b4ef-121">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="1b4ef-121">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="1b4ef-122">この .NET アセンブリに関連付けられたスキーマのコンテナー ノード</span><span class="sxs-lookup"><span data-stu-id="1b4ef-122">Container node for schemas associated with this .NET assembly</span></span>|<span data-ttu-id="1b4ef-123">任意</span><span class="sxs-lookup"><span data-stu-id="1b4ef-123">Not required</span></span>|<span data-ttu-id="1b4ef-124">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="1b4ef-124">Default value: none</span></span>|
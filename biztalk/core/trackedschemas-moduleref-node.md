---
title: "TrackedSchemas (ModuleRef ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TrackedSchemas node [binding file]
ms.assetid: a2b99fbf-df6b-4a94-97b8-ac5eb819604f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 303aeb1ed17b001583a596d5b550faf63ea1200b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="trackedschemas-moduleref-node"></a><span data-ttu-id="a8597-102">TrackedSchemas (ModuleRef ノード)</span><span class="sxs-lookup"><span data-stu-id="a8597-102">TrackedSchemas (ModuleRef Node)</span></span>
<span data-ttu-id="a8597-103">バインド ファイルの TrackedSchemas ノードは、バインド ファイルと共にエクスポートされるサービスにバインドされたスキーマを記述するすべての Schema ノードの親ノードです。</span><span class="sxs-lookup"><span data-stu-id="a8597-103">The TrackedSchemas node of a binding file is the parent node for all of the Schema nodes which describe the schemas bound to the service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-trackedschemas-node"></a><span data-ttu-id="a8597-104">TrackedSchemas ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="a8597-104">Nodes in the TrackedSchemas node</span></span>  
 <span data-ttu-id="a8597-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="a8597-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="a8597-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="a8597-106">**Name**</span></span>|<span data-ttu-id="a8597-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="a8597-107">**Node Type**</span></span>|<span data-ttu-id="a8597-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a8597-108">**Data Type**</span></span>|<span data-ttu-id="a8597-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="a8597-109">**Description**</span></span>|<span data-ttu-id="a8597-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="a8597-110">**Restrictions**</span></span>|<span data-ttu-id="a8597-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="a8597-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="a8597-112">スキーマ</span><span class="sxs-lookup"><span data-stu-id="a8597-112">Schema</span></span>](../core/schema-trackedschemas-node.md)|<span data-ttu-id="a8597-113">レコード</span><span class="sxs-lookup"><span data-stu-id="a8597-113">Record</span></span>|<span data-ttu-id="a8597-114">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="a8597-114">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="a8597-115">バインド ファイルと共にエクスポートされるサービスにバインドされたスキーマのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="a8597-115">Container node for the schemas that are bound to the service that is exported with the binding file.</span></span>|<span data-ttu-id="a8597-116">任意</span><span class="sxs-lookup"><span data-stu-id="a8597-116">Not required</span></span>|<span data-ttu-id="a8597-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="a8597-117">Default value: none</span></span>|
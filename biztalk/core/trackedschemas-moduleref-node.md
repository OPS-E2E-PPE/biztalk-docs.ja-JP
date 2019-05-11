---
title: TrackedSchemas (ModuleRef ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TrackedSchemas node [binding file]
ms.assetid: a2b99fbf-df6b-4a94-97b8-ac5eb819604f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aa14543e64685e6f12a268c4e825c01d277fda9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313979"
---
# <a name="trackedschemas-moduleref-node"></a><span data-ttu-id="3a5a1-102">TrackedSchemas (ModuleRef ノード)</span><span class="sxs-lookup"><span data-stu-id="3a5a1-102">TrackedSchemas (ModuleRef Node)</span></span>
<span data-ttu-id="3a5a1-103">バインド ファイルの TrackedSchemas ノードは、すべてのバインド ファイルと共にエクスポートされるサービスにバインドされているスキーマを記述するスキーマ ノードの親ノードです。</span><span class="sxs-lookup"><span data-stu-id="3a5a1-103">The TrackedSchemas node of a binding file is the parent node for all of the Schema nodes which describe the schemas bound to the service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-trackedschemas-node"></a><span data-ttu-id="3a5a1-104">TrackedSchemas ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="3a5a1-104">Nodes in the TrackedSchemas node</span></span>  
 <span data-ttu-id="3a5a1-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="3a5a1-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="3a5a1-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="3a5a1-106">**Name**</span></span>|<span data-ttu-id="3a5a1-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="3a5a1-107">**Node Type**</span></span>|<span data-ttu-id="3a5a1-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="3a5a1-108">**Data Type**</span></span>|<span data-ttu-id="3a5a1-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="3a5a1-109">**Description**</span></span>|<span data-ttu-id="3a5a1-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="3a5a1-110">**Restrictions**</span></span>|<span data-ttu-id="3a5a1-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="3a5a1-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="3a5a1-112">[[スキーマ]](../core/schema-trackedschemas-node.md)</span><span class="sxs-lookup"><span data-stu-id="3a5a1-112">[Schema](../core/schema-trackedschemas-node.md)</span></span>|<span data-ttu-id="3a5a1-113">レコード</span><span class="sxs-lookup"><span data-stu-id="3a5a1-113">Record</span></span>|<span data-ttu-id="3a5a1-114">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="3a5a1-114">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="3a5a1-115">バインド ファイルと共にエクスポートされるサービスにバインドされているスキーマのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="3a5a1-115">Container node for the schemas that are bound to the service that is exported with the binding file.</span></span>|<span data-ttu-id="3a5a1-116">任意</span><span class="sxs-lookup"><span data-stu-id="3a5a1-116">Not required</span></span>|<span data-ttu-id="3a5a1-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="3a5a1-117">Default value: none</span></span>|
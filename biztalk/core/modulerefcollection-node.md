---
title: ModuleRefCollection ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRefCollection node [binding file]
ms.assetid: fa8593bf-6548-4615-9f98-1e0eadde9aa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a8f756d15e7b4dd88029ad169d5aac66e894aff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324502"
---
# <a name="modulerefcollection-node"></a><span data-ttu-id="69f0d-102">ModuleRefCollection ノード</span><span class="sxs-lookup"><span data-stu-id="69f0d-102">ModuleRefCollection Node</span></span>
<span data-ttu-id="69f0d-103">バインド ファイルの ModuleRefCollection セクションは、すべてのバインド ファイルと共にエクスポートされる .NET アセンブリに関する特定の情報を含む ModuleRef ノードの親ノードです。</span><span class="sxs-lookup"><span data-stu-id="69f0d-103">The ModuleRefCollection section of a binding file is the parent node for all of the ModuleRef nodes which contain specific information about .NET assemblies exported with the binding file.</span></span>  
  
## <a name="entries-in-the-modulerefcollection-section"></a><span data-ttu-id="69f0d-104">ModuleRefCollection セクションのエントリ</span><span class="sxs-lookup"><span data-stu-id="69f0d-104">Entries in the ModuleRefCollection section</span></span>  
 <span data-ttu-id="69f0d-105">次の表では、バインド ファイルのこのセクションで、ノードに対して設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="69f0d-105">The following table lists the properties that can be set for the nodes in this section of a binding file:</span></span>  
  
|<span data-ttu-id="69f0d-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="69f0d-106">**Name**</span></span>|<span data-ttu-id="69f0d-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="69f0d-107">**Node Type**</span></span>|<span data-ttu-id="69f0d-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="69f0d-108">**Data Type**</span></span>|<span data-ttu-id="69f0d-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="69f0d-109">**Description**</span></span>|<span data-ttu-id="69f0d-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="69f0d-110">**Restrictions**</span></span>|<span data-ttu-id="69f0d-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="69f0d-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="69f0d-112">ModuleRef</span><span class="sxs-lookup"><span data-stu-id="69f0d-112">ModuleRef</span></span>](../core/moduleref-modulerefcollection-node.md)|<span data-ttu-id="69f0d-113">レコード</span><span class="sxs-lookup"><span data-stu-id="69f0d-113">Record</span></span>|<span data-ttu-id="69f0d-114">ModuleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="69f0d-114">ModuleRef (ComplexType)</span></span>|<span data-ttu-id="69f0d-115">バインド ファイルと共にエクスポートされた .NET アセンブリのモジュールのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="69f0d-115">Container node for a .NET assembly module exported with the binding file.</span></span>|<span data-ttu-id="69f0d-116">任意</span><span class="sxs-lookup"><span data-stu-id="69f0d-116">Not required</span></span>|<span data-ttu-id="69f0d-117">既定値:なし</span><span class="sxs-lookup"><span data-stu-id="69f0d-117">Default value: None</span></span>|
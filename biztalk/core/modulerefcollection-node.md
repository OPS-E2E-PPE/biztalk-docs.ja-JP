---
title: ModuleRefCollection ノード |Microsoft ドキュメント
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
ms.openlocfilehash: 039cabd380195f840e9ffb99de5071026b3810c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262682"
---
# <a name="modulerefcollection-node"></a><span data-ttu-id="af4a6-102">ModuleRefCollection ノード</span><span class="sxs-lookup"><span data-stu-id="af4a6-102">ModuleRefCollection Node</span></span>
<span data-ttu-id="af4a6-103">バインド ファイルの ModuleRefCollection セクションは、バインド ファイルと共にエクスポートされる .NET アセンブリに関する特定の情報を含むすべての ModuleRef ノードの親ノードです。</span><span class="sxs-lookup"><span data-stu-id="af4a6-103">The ModuleRefCollection section of a binding file is the parent node for all of the ModuleRef nodes which contain specific information about .NET assemblies exported with the binding file.</span></span>  
  
## <a name="entries-in-the-modulerefcollection-section"></a><span data-ttu-id="af4a6-104">ModuleRefCollection セクションのエントリ</span><span class="sxs-lookup"><span data-stu-id="af4a6-104">Entries in the ModuleRefCollection section</span></span>  
 <span data-ttu-id="af4a6-105">次の表に、バインド ファイルのこのセクション内のノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="af4a6-105">The following table lists the properties that can be set for the nodes in this section of a binding file:</span></span>  
  
|<span data-ttu-id="af4a6-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="af4a6-106">**Name**</span></span>|<span data-ttu-id="af4a6-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="af4a6-107">**Node Type**</span></span>|<span data-ttu-id="af4a6-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="af4a6-108">**Data Type**</span></span>|<span data-ttu-id="af4a6-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="af4a6-109">**Description**</span></span>|<span data-ttu-id="af4a6-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="af4a6-110">**Restrictions**</span></span>|<span data-ttu-id="af4a6-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="af4a6-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="af4a6-112">ModuleRef</span><span class="sxs-lookup"><span data-stu-id="af4a6-112">ModuleRef</span></span>](../core/moduleref-modulerefcollection-node.md)|<span data-ttu-id="af4a6-113">レコード</span><span class="sxs-lookup"><span data-stu-id="af4a6-113">Record</span></span>|<span data-ttu-id="af4a6-114">ModuleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="af4a6-114">ModuleRef (ComplexType)</span></span>|<span data-ttu-id="af4a6-115">バインド ファイルと共にエクスポートされる .NET アセンブリ モジュールのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="af4a6-115">Container node for a .NET assembly module exported with the binding file.</span></span>|<span data-ttu-id="af4a6-116">任意</span><span class="sxs-lookup"><span data-stu-id="af4a6-116">Not required</span></span>|<span data-ttu-id="af4a6-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="af4a6-117">Default value: None</span></span>|
---
title: "Transforms (SendPort ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transforms node [binding file]
ms.assetid: b405397b-e394-44fa-b507-93896f800f66
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1571a38841f6567279a27c58770f4198ba3eb56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transforms-sendport-node"></a><span data-ttu-id="346a0-102">Transforms (SendPort ノード)</span><span class="sxs-lookup"><span data-stu-id="346a0-102">Transforms (SendPort Node)</span></span>
<span data-ttu-id="346a0-103">バインド ファイルの SendPort ノードの Transforms ノードには、バインド ファイルと共にエクスポートされる一方向送信ポートの送信変換のコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="346a0-103">The Transforms node of the SendPort node of a binding file contains the collection of outbound transforms of a one way send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transforms-node"></a><span data-ttu-id="346a0-104">Transforms ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="346a0-104">Nodes in the Transforms node</span></span>  
 <span data-ttu-id="346a0-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="346a0-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="346a0-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="346a0-106">**Name**</span></span>|<span data-ttu-id="346a0-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="346a0-107">**Node Type**</span></span>|<span data-ttu-id="346a0-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="346a0-108">**Data Type**</span></span>|<span data-ttu-id="346a0-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="346a0-109">**Description**</span></span>|<span data-ttu-id="346a0-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="346a0-110">**Restrictions**</span></span>|<span data-ttu-id="346a0-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="346a0-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="346a0-112">Transform (SendPort Transforms ノード)</span><span class="sxs-lookup"><span data-stu-id="346a0-112">Transform (SendPort-Transforms Node)</span></span>](../core/transform-sendport-transforms-node.md)|<span data-ttu-id="346a0-113">レコード</span><span class="sxs-lookup"><span data-stu-id="346a0-113">Record</span></span>|<span data-ttu-id="346a0-114">Transform (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="346a0-114">Transform (ComplexType)</span></span>|<span data-ttu-id="346a0-115">BizTalk Server マップまたは変換を指定します。これは送信元スキーマと送信先スキーマのマッピングを表す項目です。</span><span class="sxs-lookup"><span data-stu-id="346a0-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="346a0-116">任意</span><span class="sxs-lookup"><span data-stu-id="346a0-116">Not required</span></span>|<span data-ttu-id="346a0-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="346a0-117">Default value: none</span></span>|
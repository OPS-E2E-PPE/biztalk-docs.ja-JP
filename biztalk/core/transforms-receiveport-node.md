---
title: Transforms (ReceivePort ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transforms node [binding file]
ms.assetid: cd32f2fe-b70a-4153-86ec-bb1aa9bad0e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7d039d95a1f28afa468078ff7547e9f298633bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279242"
---
# <a name="transforms-receiveport-node"></a><span data-ttu-id="00337-102">Transforms (ReceivePort ノード)</span><span class="sxs-lookup"><span data-stu-id="00337-102">Transforms (ReceivePort Node)</span></span>
<span data-ttu-id="00337-103">バインド ファイルの ReceivePort ノードの Transforms ノードには、バインド ファイルと共にエクスポートされる一方向受信ポートの受信変換のコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="00337-103">The Transforms node of the ReceivePort node of a binding file contains the collection of inbound transforms of a one way receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transforms-node"></a><span data-ttu-id="00337-104">Transforms ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="00337-104">Nodes in the Transforms node</span></span>  
 <span data-ttu-id="00337-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="00337-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="00337-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="00337-106">**Name**</span></span>|<span data-ttu-id="00337-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="00337-107">**Node Type**</span></span>|<span data-ttu-id="00337-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="00337-108">**Data Type**</span></span>|<span data-ttu-id="00337-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="00337-109">**Description**</span></span>|<span data-ttu-id="00337-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="00337-110">**Restrictions**</span></span>|<span data-ttu-id="00337-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="00337-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="00337-112">Transform (Transforms ノード)</span><span class="sxs-lookup"><span data-stu-id="00337-112">Transform (Transforms Node)</span></span>](../core/transform-transforms-node.md)|<span data-ttu-id="00337-113">レコード</span><span class="sxs-lookup"><span data-stu-id="00337-113">Record</span></span>|<span data-ttu-id="00337-114">Transform (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="00337-114">Transform (ComplexType)</span></span>|<span data-ttu-id="00337-115">BizTalk Server マップまたは変換を指定します。これは送信元スキーマと送信先スキーマのマッピングを表す項目です。</span><span class="sxs-lookup"><span data-stu-id="00337-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="00337-116">任意</span><span class="sxs-lookup"><span data-stu-id="00337-116">Not required</span></span>|<span data-ttu-id="00337-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="00337-117">Default value: none</span></span>|
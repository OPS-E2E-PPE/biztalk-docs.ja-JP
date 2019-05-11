---
title: Transforms (ReceivePort ノード) |Microsoft Docs
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
ms.openlocfilehash: 64ecaf77dbe74cb27116be61d56d8ab3a2811e45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303018"
---
# <a name="transforms-receiveport-node"></a><span data-ttu-id="d84b9-102">Transforms (ReceivePort ノード)</span><span class="sxs-lookup"><span data-stu-id="d84b9-102">Transforms (ReceivePort Node)</span></span>
<span data-ttu-id="d84b9-103">バインド ファイルの ReceivePort ノードの Transforms ノードには、入力方向のコレクションが含まれています。 一方向の変換は、バインド ファイルと共にエクスポートされるポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="d84b9-103">The Transforms node of the ReceivePort node of a binding file contains the collection of inbound transforms of a one way receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transforms-node"></a><span data-ttu-id="d84b9-104">Transforms ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="d84b9-104">Nodes in the Transforms node</span></span>  
 <span data-ttu-id="d84b9-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="d84b9-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="d84b9-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="d84b9-106">**Name**</span></span>|<span data-ttu-id="d84b9-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="d84b9-107">**Node Type**</span></span>|<span data-ttu-id="d84b9-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="d84b9-108">**Data Type**</span></span>|<span data-ttu-id="d84b9-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="d84b9-109">**Description**</span></span>|<span data-ttu-id="d84b9-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="d84b9-110">**Restrictions**</span></span>|<span data-ttu-id="d84b9-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="d84b9-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="d84b9-112">Transform (Transforms ノード)</span><span class="sxs-lookup"><span data-stu-id="d84b9-112">Transform (Transforms Node)</span></span>](../core/transform-transforms-node.md)|<span data-ttu-id="d84b9-113">レコード</span><span class="sxs-lookup"><span data-stu-id="d84b9-113">Record</span></span>|<span data-ttu-id="d84b9-114">変換 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="d84b9-114">Transform (ComplexType)</span></span>|<span data-ttu-id="d84b9-115">BizTalk Server マップまたは変換で、送信元スキーマと送信先スキーマ間のマッピングを表す項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="d84b9-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="d84b9-116">任意</span><span class="sxs-lookup"><span data-stu-id="d84b9-116">Not required</span></span>|<span data-ttu-id="d84b9-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="d84b9-117">Default value: none</span></span>|
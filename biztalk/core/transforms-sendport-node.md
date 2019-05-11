---
title: Transforms (SendPort ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transforms node [binding file]
ms.assetid: b405397b-e394-44fa-b507-93896f800f66
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcae41bd04d094238778d16768316eb55fb2e5d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243180"
---
# <a name="transforms-sendport-node"></a><span data-ttu-id="4fd59-102">Transforms (SendPort ノード)</span><span class="sxs-lookup"><span data-stu-id="4fd59-102">Transforms (SendPort Node)</span></span>
<span data-ttu-id="4fd59-103">バインド ファイルの SendPort ノードの Transforms ノードには、バインド ファイルと共にエクスポートされる一方向送信ポートの送信変換のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4fd59-103">The Transforms node of the SendPort node of a binding file contains the collection of outbound transforms of a one way send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transforms-node"></a><span data-ttu-id="4fd59-104">Transforms ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="4fd59-104">Nodes in the Transforms node</span></span>  
 <span data-ttu-id="4fd59-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="4fd59-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="4fd59-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="4fd59-106">**Name**</span></span>|<span data-ttu-id="4fd59-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="4fd59-107">**Node Type**</span></span>|<span data-ttu-id="4fd59-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="4fd59-108">**Data Type**</span></span>|<span data-ttu-id="4fd59-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="4fd59-109">**Description**</span></span>|<span data-ttu-id="4fd59-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="4fd59-110">**Restrictions**</span></span>|<span data-ttu-id="4fd59-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="4fd59-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="4fd59-112">Transform (SendPort-Transforms ノード)</span><span class="sxs-lookup"><span data-stu-id="4fd59-112">Transform (SendPort-Transforms Node)</span></span>](../core/transform-sendport-transforms-node.md)|<span data-ttu-id="4fd59-113">レコード</span><span class="sxs-lookup"><span data-stu-id="4fd59-113">Record</span></span>|<span data-ttu-id="4fd59-114">変換 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="4fd59-114">Transform (ComplexType)</span></span>|<span data-ttu-id="4fd59-115">BizTalk Server マップまたは変換で、送信元スキーマと送信先スキーマ間のマッピングを表す項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fd59-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="4fd59-116">任意</span><span class="sxs-lookup"><span data-stu-id="4fd59-116">Not required</span></span>|<span data-ttu-id="4fd59-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="4fd59-117">Default value: none</span></span>|
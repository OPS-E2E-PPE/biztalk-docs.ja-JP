---
title: OutboundTransforms (ReceivePort ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- OutboundTransforms node [binding file]
ms.assetid: 6deea062-4eb0-47ed-869c-ed6ec9290ea7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 109995aa38731338ce53d4dea58226fa081fd17a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393422"
---
# <a name="outboundtransforms-receiveport-node"></a><span data-ttu-id="1eaec-102">OutboundTransforms (ReceivePort ノード)</span><span class="sxs-lookup"><span data-stu-id="1eaec-102">OutboundTransforms (ReceivePort Node)</span></span>
<span data-ttu-id="1eaec-103">バインド ファイルの ReceivePort ノードの OutboundTransforms ノードには、出力方向のコレクションが含まれています。 双方向の変換は、バインド ファイルと共にエクスポートされるポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="1eaec-103">The OutboundTransforms node of the ReceivePort node of a binding file contains the collection of outbound transforms of a two-way receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-outboundtransforms-node"></a><span data-ttu-id="1eaec-104">OutboundTransforms ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="1eaec-104">Nodes in the OutboundTransforms node</span></span>  
 <span data-ttu-id="1eaec-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="1eaec-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="1eaec-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="1eaec-106">**Name**</span></span>|<span data-ttu-id="1eaec-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="1eaec-107">**Node Type**</span></span>|<span data-ttu-id="1eaec-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="1eaec-108">**Data Type**</span></span>|<span data-ttu-id="1eaec-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="1eaec-109">**Description**</span></span>|<span data-ttu-id="1eaec-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="1eaec-110">**Restrictions**</span></span>|<span data-ttu-id="1eaec-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="1eaec-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="1eaec-112">Transform (OutboundTransforms ノード)</span><span class="sxs-lookup"><span data-stu-id="1eaec-112">Transform (OutboundTransforms Node)</span></span>](../core/transform-outboundtransforms-node.md)|<span data-ttu-id="1eaec-113">レコード</span><span class="sxs-lookup"><span data-stu-id="1eaec-113">Record</span></span>|<span data-ttu-id="1eaec-114">変換 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="1eaec-114">Transform (ComplexType)</span></span>|<span data-ttu-id="1eaec-115">BizTalk Server マップまたは変換で、送信元スキーマと送信先スキーマ間のマッピングを表す項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="1eaec-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="1eaec-116">任意</span><span class="sxs-lookup"><span data-stu-id="1eaec-116">Not required</span></span>|<span data-ttu-id="1eaec-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="1eaec-117">Default value: none</span></span>|
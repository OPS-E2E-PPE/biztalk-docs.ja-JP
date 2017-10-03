---
title: "OutboundTransforms (ReceivePort ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: OutboundTransforms node [binding file]
ms.assetid: 6deea062-4eb0-47ed-869c-ed6ec9290ea7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc6fa0bc804fad0d0ddea79614c392769452f1c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="outboundtransforms-receiveport-node"></a><span data-ttu-id="35637-102">OutboundTransforms (ReceivePort ノード)</span><span class="sxs-lookup"><span data-stu-id="35637-102">OutboundTransforms (ReceivePort Node)</span></span>
<span data-ttu-id="35637-103">バインド ファイルの ReceivePort ノードの OutboundTransforms ノードには、バインド ファイルと共にエクスポートされる双方向受信ポートの送信変換のコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35637-103">The OutboundTransforms node of the ReceivePort node of a binding file contains the collection of outbound transforms of a two-way receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-outboundtransforms-node"></a><span data-ttu-id="35637-104">OutboundTransforms ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="35637-104">Nodes in the OutboundTransforms node</span></span>  
 <span data-ttu-id="35637-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="35637-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="35637-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="35637-106">**Name**</span></span>|<span data-ttu-id="35637-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="35637-107">**Node Type**</span></span>|<span data-ttu-id="35637-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="35637-108">**Data Type**</span></span>|<span data-ttu-id="35637-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="35637-109">**Description**</span></span>|<span data-ttu-id="35637-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="35637-110">**Restrictions**</span></span>|<span data-ttu-id="35637-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="35637-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="35637-112">Transform (OutboundTransforms ノード)</span><span class="sxs-lookup"><span data-stu-id="35637-112">Transform (OutboundTransforms Node)</span></span>](../core/transform-outboundtransforms-node.md)|<span data-ttu-id="35637-113">レコード</span><span class="sxs-lookup"><span data-stu-id="35637-113">Record</span></span>|<span data-ttu-id="35637-114">Transform (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="35637-114">Transform (ComplexType)</span></span>|<span data-ttu-id="35637-115">BizTalk Server マップまたは変換を指定します。これは送信元スキーマと送信先スキーマのマッピングを表す項目です。</span><span class="sxs-lookup"><span data-stu-id="35637-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="35637-116">任意</span><span class="sxs-lookup"><span data-stu-id="35637-116">Not required</span></span>|<span data-ttu-id="35637-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="35637-117">Default value: none</span></span>|
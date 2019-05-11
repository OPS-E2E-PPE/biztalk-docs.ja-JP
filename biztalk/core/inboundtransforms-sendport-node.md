---
title: InboundTransforms (SendPort ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- InboundTransforms node [binding file]
ms.assetid: 5ed239b9-13d8-4099-b779-08f589a722e9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d13d48da9f4b9e3e04cb0753eb302484b6b169
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382183"
---
# <a name="inboundtransforms-sendport-node"></a><span data-ttu-id="817e5-102">InboundTransforms (SendPort ノード)</span><span class="sxs-lookup"><span data-stu-id="817e5-102">InboundTransforms (SendPort Node)</span></span>
<span data-ttu-id="817e5-103">バインド ファイルの SendPort ノードの InboundTransforms ノードには、バインド ファイルと共にエクスポートされる双方向送信ポートの受信変換のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="817e5-103">The InboundTransforms node of the SendPort node of a binding file contains the collection of inbound transforms of a two-way send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-inboundtransforms-node"></a><span data-ttu-id="817e5-104">InboundTransforms ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="817e5-104">Nodes in the InboundTransforms node</span></span>  
 <span data-ttu-id="817e5-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="817e5-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="817e5-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="817e5-106">**Name**</span></span>|<span data-ttu-id="817e5-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="817e5-107">**Node Type**</span></span>|<span data-ttu-id="817e5-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="817e5-108">**Data Type**</span></span>|<span data-ttu-id="817e5-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="817e5-109">**Description**</span></span>|<span data-ttu-id="817e5-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="817e5-110">**Restrictions**</span></span>|<span data-ttu-id="817e5-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="817e5-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="817e5-112">Transform (InboundTransforms ノード)</span><span class="sxs-lookup"><span data-stu-id="817e5-112">Transform (InboundTransforms Node)</span></span>](../core/transform-inboundtransforms-node.md)|<span data-ttu-id="817e5-113">レコード</span><span class="sxs-lookup"><span data-stu-id="817e5-113">Record</span></span>|<span data-ttu-id="817e5-114">変換 (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="817e5-114">Transform (ComplexType)</span></span>|<span data-ttu-id="817e5-115">BizTalk Server マップまたは変換で、送信元スキーマと送信先スキーマ間のマッピングを表す項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="817e5-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="817e5-116">任意</span><span class="sxs-lookup"><span data-stu-id="817e5-116">Not required</span></span>|<span data-ttu-id="817e5-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="817e5-117">Default value: none</span></span>|
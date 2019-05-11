---
title: SendPorts (DistributionList ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPorts node [binding file]
ms.assetid: 9cb645fa-cb9c-44eb-9f98-2fc507b2be67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63fda2724291b15492ecb4d9a035d33cddc0b5d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393349"
---
# <a name="sendports-distributionlist-node"></a><span data-ttu-id="d1570-102">SendPorts (DistributionList ノード)</span><span class="sxs-lookup"><span data-stu-id="d1570-102">SendPorts (DistributionList Node)</span></span>
<span data-ttu-id="d1570-103">バインド ファイルの DistributionList ノードの SendPorts ノードは、配布リストに送信ポート参照のコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="d1570-103">The SendPorts node of the DistributionList node of a binding file is the container node for the send port references in the distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1570-104">同報リストは、送信ポート グループ、BizTalk 管理者と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d1570-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendports-node"></a><span data-ttu-id="d1570-105">SendPorts ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="d1570-105">Nodes in the SendPorts node</span></span>  
 <span data-ttu-id="d1570-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="d1570-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="d1570-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="d1570-107">**Name**</span></span>|<span data-ttu-id="d1570-108">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="d1570-108">**Node Type**</span></span>|<span data-ttu-id="d1570-109">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="d1570-109">**Data Type**</span></span>|<span data-ttu-id="d1570-110">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="d1570-110">**Description**</span></span>|<span data-ttu-id="d1570-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="d1570-111">**Restrictions**</span></span>|<span data-ttu-id="d1570-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="d1570-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="d1570-113">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="d1570-113">SendPortRef</span></span>](../core/sendportref-sendports-node.md)|<span data-ttu-id="d1570-114">レコード</span><span class="sxs-lookup"><span data-stu-id="d1570-114">Record</span></span>|<span data-ttu-id="d1570-115">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="d1570-115">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="d1570-116">同報リストによって行われた送信ポートへの参照のコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="d1570-116">Container node for a reference to a send port made by the distribution list.</span></span>|<span data-ttu-id="d1570-117">任意</span><span class="sxs-lookup"><span data-stu-id="d1570-117">Not required</span></span>|<span data-ttu-id="d1570-118">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="d1570-118">Default value: none</span></span>|
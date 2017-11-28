---
title: "SendPorts (DistributionList ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendPorts node [binding file]
ms.assetid: 9cb645fa-cb9c-44eb-9f98-2fc507b2be67
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9eaf692bd61913e604731fc2e2cea373fd31f48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sendports-distributionlist-node"></a><span data-ttu-id="76f8f-102">SendPorts (DistributionList ノード)</span><span class="sxs-lookup"><span data-stu-id="76f8f-102">SendPorts (DistributionList Node)</span></span>
<span data-ttu-id="76f8f-103">バインド ファイルの DistributionList ノードの SendPorts ノードは、同報リスト内の送信ポート参照のコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="76f8f-103">The SendPorts node of the DistributionList node of a binding file is the container node for the send port references in the distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76f8f-104">同報リストは、BizTalk 管理者では送信ポート グループと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="76f8f-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendports-node"></a><span data-ttu-id="76f8f-105">SendPorts ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="76f8f-105">Nodes in the SendPorts node</span></span>  
 <span data-ttu-id="76f8f-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="76f8f-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="76f8f-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="76f8f-107">**Name**</span></span>|<span data-ttu-id="76f8f-108">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="76f8f-108">**Node Type**</span></span>|<span data-ttu-id="76f8f-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="76f8f-109">**Data Type**</span></span>|<span data-ttu-id="76f8f-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="76f8f-110">**Description**</span></span>|<span data-ttu-id="76f8f-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="76f8f-111">**Restrictions**</span></span>|<span data-ttu-id="76f8f-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="76f8f-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="76f8f-113">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="76f8f-113">SendPortRef</span></span>](../core/sendportref-sendports-node.md)|<span data-ttu-id="76f8f-114">レコード</span><span class="sxs-lookup"><span data-stu-id="76f8f-114">Record</span></span>|<span data-ttu-id="76f8f-115">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="76f8f-115">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="76f8f-116">同報リストによって参照される送信ポートのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="76f8f-116">Container node for a reference to a send port made by the distribution list.</span></span>|<span data-ttu-id="76f8f-117">任意</span><span class="sxs-lookup"><span data-stu-id="76f8f-117">Not required</span></span>|<span data-ttu-id="76f8f-118">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="76f8f-118">Default value: none</span></span>|
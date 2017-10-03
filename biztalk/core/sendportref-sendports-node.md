---
title: "SendPortRef (SendPorts ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendPortRef node [binding file]
ms.assetid: 6c799b23-a9a4-4686-a04e-0450b4eef889
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9290a535ebcaf0c23097cacbd3412f64c2808f40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sendportref-sendports-node"></a><span data-ttu-id="c6ffe-102">SendPortRef (SendPorts ノード)</span><span class="sxs-lookup"><span data-stu-id="c6ffe-102">SendPortRef (SendPorts Node)</span></span>
<span data-ttu-id="c6ffe-103">バインド ファイルの SendPorts ノードの SendPortRef ノードには、同報リストによって参照される送信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6ffe-103">The SendPortRef node of the SendPorts node of a binding file specifies the name of a send port referenced by a distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6ffe-104">同報リストは、BizTalk 管理者では送信ポート グループと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c6ffe-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendportref-node"></a><span data-ttu-id="c6ffe-105">SendPortRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="c6ffe-105">Nodes in the SendPortRef node</span></span>  
 <span data-ttu-id="c6ffe-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="c6ffe-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c6ffe-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="c6ffe-107">**Name**</span></span>|<span data-ttu-id="c6ffe-108">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="c6ffe-108">**Node Type**</span></span>|<span data-ttu-id="c6ffe-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c6ffe-109">**Data Type**</span></span>|<span data-ttu-id="c6ffe-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="c6ffe-110">**Description**</span></span>|<span data-ttu-id="c6ffe-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="c6ffe-111">**Restrictions**</span></span>|<span data-ttu-id="c6ffe-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="c6ffe-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="c6ffe-113">名前</span><span class="sxs-lookup"><span data-stu-id="c6ffe-113">Name</span></span>|<span data-ttu-id="c6ffe-114">属性</span><span class="sxs-lookup"><span data-stu-id="c6ffe-114">Attribute</span></span>|<span data-ttu-id="c6ffe-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="c6ffe-115">xs:string</span></span>|<span data-ttu-id="c6ffe-116">同報リストによって参照される送信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6ffe-116">Specifies the name of the send port referenced by the distribution list.</span></span>|<span data-ttu-id="c6ffe-117">任意</span><span class="sxs-lookup"><span data-stu-id="c6ffe-117">Not required</span></span>|<span data-ttu-id="c6ffe-118">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="c6ffe-118">Default value: empty</span></span>|
---
title: SendPortRef (SendPorts ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: 6c799b23-a9a4-4686-a04e-0450b4eef889
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63ddb7a4f33a13405be0ae555f85d2303e84bb23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393375"
---
# <a name="sendportref-sendports-node"></a><span data-ttu-id="b647d-102">SendPortRef (SendPorts ノード)</span><span class="sxs-lookup"><span data-stu-id="b647d-102">SendPortRef (SendPorts Node)</span></span>
<span data-ttu-id="b647d-103">バインド ファイルの SendPorts ノードの SendPortRef ノードには、同報リストによって参照される送信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b647d-103">The SendPortRef node of the SendPorts node of a binding file specifies the name of a send port referenced by a distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b647d-104">同報リストは、送信ポート グループ、BizTalk 管理者と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b647d-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendportref-node"></a><span data-ttu-id="b647d-105">SendPortRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="b647d-105">Nodes in the SendPortRef node</span></span>  
 <span data-ttu-id="b647d-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="b647d-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="b647d-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="b647d-107">**Name**</span></span>|<span data-ttu-id="b647d-108">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="b647d-108">**Node Type**</span></span>|<span data-ttu-id="b647d-109">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="b647d-109">**Data Type**</span></span>|<span data-ttu-id="b647d-110">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="b647d-110">**Description**</span></span>|<span data-ttu-id="b647d-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="b647d-111">**Restrictions**</span></span>|<span data-ttu-id="b647d-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="b647d-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="b647d-113">名前</span><span class="sxs-lookup"><span data-stu-id="b647d-113">Name</span></span>|<span data-ttu-id="b647d-114">属性</span><span class="sxs-lookup"><span data-stu-id="b647d-114">Attribute</span></span>|<span data-ttu-id="b647d-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="b647d-115">xs:string</span></span>|<span data-ttu-id="b647d-116">同報リストによって参照される送信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b647d-116">Specifies the name of the send port referenced by the distribution list.</span></span>|<span data-ttu-id="b647d-117">任意</span><span class="sxs-lookup"><span data-stu-id="b647d-117">Not required</span></span>|<span data-ttu-id="b647d-118">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="b647d-118">Default value: empty</span></span>|
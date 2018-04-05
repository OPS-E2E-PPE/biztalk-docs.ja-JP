---
title: SendPortRef (Mapping ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: 0fbdf44f-6dde-4d1b-b861-cb2fe6d7529d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6448147db5e45278e33b3ccf3a17f019bfa2dc56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sendportref-mapping-node"></a><span data-ttu-id="84d79-102">SendPortRef (Mapping ノード)</span><span class="sxs-lookup"><span data-stu-id="84d79-102">SendPortRef (Mapping Node)</span></span>
<span data-ttu-id="84d79-103">バインド ファイルの Mapping ノードの SendPortRef ノードには、親マッピング ノードが参照する送信ポートの名前が示されます。</span><span class="sxs-lookup"><span data-stu-id="84d79-103">The SendPortRef node of the Mapping node of a binding file lists the names of the send ports referenced by the parent mapping node.</span></span>  
  
## <a name="nodes-in-the-sendportref-node"></a><span data-ttu-id="84d79-104">SendPortRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="84d79-104">Nodes in the SendPortRef node</span></span>  
 <span data-ttu-id="84d79-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="84d79-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="84d79-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="84d79-106">**Name**</span></span>|<span data-ttu-id="84d79-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="84d79-107">**Node Type**</span></span>|<span data-ttu-id="84d79-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="84d79-108">**Data Type**</span></span>|<span data-ttu-id="84d79-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="84d79-109">**Description**</span></span>|<span data-ttu-id="84d79-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="84d79-110">**Restrictions**</span></span>|<span data-ttu-id="84d79-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="84d79-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="84d79-112">名前</span><span class="sxs-lookup"><span data-stu-id="84d79-112">Name</span></span>|<span data-ttu-id="84d79-113">属性</span><span class="sxs-lookup"><span data-stu-id="84d79-113">Attribute</span></span>|<span data-ttu-id="84d79-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="84d79-114">xs:string</span></span>|<span data-ttu-id="84d79-115">親マッピング ノードによって参照される送信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="84d79-115">Specifies the name of a send port that is referenced by the parent mapping node</span></span>|<span data-ttu-id="84d79-116">任意</span><span class="sxs-lookup"><span data-stu-id="84d79-116">Not required</span></span>|<span data-ttu-id="84d79-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="84d79-117">Default value: empty</span></span>|
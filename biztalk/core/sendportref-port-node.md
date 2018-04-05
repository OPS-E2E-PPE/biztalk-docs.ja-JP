---
title: SendPortRef (Port ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: cd9c3bf7-10a4-4567-a70c-fd74e4a3dc2c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acaca0fa147f9bec7fce93c46581c96de24ef16e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sendportref-port-node"></a><span data-ttu-id="cfa46-102">SendPortRef (Port ノード)</span><span class="sxs-lookup"><span data-stu-id="cfa46-102">SendPortRef (Port Node)</span></span>
<span data-ttu-id="cfa46-103">バインド ファイルの Port ノードの SendPortRef ノードには、サービスによって参照される送信ポートに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa46-103">The SendPortRef node of the Port node of a binding file contains information about a send port that is referenced by a service.</span></span>  
  
## <a name="nodes-in-the-sendportref-node"></a><span data-ttu-id="cfa46-104">SendPortRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="cfa46-104">Nodes in the SendPortRef node</span></span>  
 <span data-ttu-id="cfa46-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="cfa46-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="cfa46-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="cfa46-106">**Name**</span></span>|<span data-ttu-id="cfa46-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="cfa46-107">**Node Type**</span></span>|<span data-ttu-id="cfa46-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="cfa46-108">**Data Type**</span></span>|<span data-ttu-id="cfa46-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="cfa46-109">**Description**</span></span>|<span data-ttu-id="cfa46-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="cfa46-110">**Restrictions**</span></span>|<span data-ttu-id="cfa46-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="cfa46-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="cfa46-112">名前</span><span class="sxs-lookup"><span data-stu-id="cfa46-112">Name</span></span>|<span data-ttu-id="cfa46-113">属性</span><span class="sxs-lookup"><span data-stu-id="cfa46-113">Attribute</span></span>|<span data-ttu-id="cfa46-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="cfa46-114">xs:string</span></span>|<span data-ttu-id="cfa46-115">サービスによって参照される送信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfa46-115">Specifies the name of a send port that is referenced by a service.</span></span>|<span data-ttu-id="cfa46-116">任意</span><span class="sxs-lookup"><span data-stu-id="cfa46-116">Not required</span></span>|<span data-ttu-id="cfa46-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="cfa46-117">Default value: empty</span></span>|
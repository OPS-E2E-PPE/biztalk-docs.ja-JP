---
title: ReceivePortRef (Port ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceivePortRef node [binding file]
ms.assetid: dfdb4ab7-a6b7-44e3-ae45-efef27e4f875
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3612944d69014ff33428eed82565853ff624bd11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398100"
---
# <a name="receiveportref-port-node"></a><span data-ttu-id="aa8e2-102">ReceivePortRef (Port ノード)</span><span class="sxs-lookup"><span data-stu-id="aa8e2-102">ReceivePortRef (Port Node)</span></span>
<span data-ttu-id="aa8e2-103">バインド ファイルの Port ノードの ReceivePortRef ノードには、サービスによって参照される受信ポートに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa8e2-103">The ReceivePortRef node of the Port node of a binding file contains information about a receive port that is referenced by a service.</span></span>  
  
## <a name="nodes-in-the-receiveportref-node"></a><span data-ttu-id="aa8e2-104">ReceivePortRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="aa8e2-104">Nodes in the ReceivePortRef node</span></span>  
 <span data-ttu-id="aa8e2-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="aa8e2-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="aa8e2-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="aa8e2-106">**Name**</span></span>|<span data-ttu-id="aa8e2-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="aa8e2-107">**Node Type**</span></span>|<span data-ttu-id="aa8e2-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="aa8e2-108">**Data Type**</span></span>|<span data-ttu-id="aa8e2-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="aa8e2-109">**Description**</span></span>|<span data-ttu-id="aa8e2-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="aa8e2-110">**Restrictions**</span></span>|<span data-ttu-id="aa8e2-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="aa8e2-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="aa8e2-112">名前</span><span class="sxs-lookup"><span data-stu-id="aa8e2-112">Name</span></span>|<span data-ttu-id="aa8e2-113">属性</span><span class="sxs-lookup"><span data-stu-id="aa8e2-113">Attribute</span></span>|<span data-ttu-id="aa8e2-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa8e2-114">xs:string</span></span>|<span data-ttu-id="aa8e2-115">サービスによって参照される受信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa8e2-115">Specifies the name of a receive port that is referenced by a service.</span></span>|<span data-ttu-id="aa8e2-116">任意</span><span class="sxs-lookup"><span data-stu-id="aa8e2-116">Not required</span></span>|<span data-ttu-id="aa8e2-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="aa8e2-117">Default value: empty</span></span>|
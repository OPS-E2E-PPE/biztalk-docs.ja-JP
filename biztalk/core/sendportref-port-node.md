---
title: SendPortRef (Port ノード) |Microsoft Docs
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
ms.openlocfilehash: 1c7fae9c7cd92ecc7c4d11e4377c749f7f944b48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393383"
---
# <a name="sendportref-port-node"></a><span data-ttu-id="3e529-102">SendPortRef (Port ノード)</span><span class="sxs-lookup"><span data-stu-id="3e529-102">SendPortRef (Port Node)</span></span>
<span data-ttu-id="3e529-103">バインド ファイルの Port ノードの SendPortRef ノードには、サービスによって参照される送信ポートに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e529-103">The SendPortRef node of the Port node of a binding file contains information about a send port that is referenced by a service.</span></span>  
  
## <a name="nodes-in-the-sendportref-node"></a><span data-ttu-id="3e529-104">SendPortRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="3e529-104">Nodes in the SendPortRef node</span></span>  
 <span data-ttu-id="3e529-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="3e529-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="3e529-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="3e529-106">**Name**</span></span>|<span data-ttu-id="3e529-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="3e529-107">**Node Type**</span></span>|<span data-ttu-id="3e529-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="3e529-108">**Data Type**</span></span>|<span data-ttu-id="3e529-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="3e529-109">**Description**</span></span>|<span data-ttu-id="3e529-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="3e529-110">**Restrictions**</span></span>|<span data-ttu-id="3e529-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="3e529-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="3e529-112">名前</span><span class="sxs-lookup"><span data-stu-id="3e529-112">Name</span></span>|<span data-ttu-id="3e529-113">属性</span><span class="sxs-lookup"><span data-stu-id="3e529-113">Attribute</span></span>|<span data-ttu-id="3e529-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e529-114">xs:string</span></span>|<span data-ttu-id="3e529-115">サービスによって参照される送信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e529-115">Specifies the name of a send port that is referenced by a service.</span></span>|<span data-ttu-id="3e529-116">任意</span><span class="sxs-lookup"><span data-stu-id="3e529-116">Not required</span></span>|<span data-ttu-id="3e529-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="3e529-117">Default value: empty</span></span>|
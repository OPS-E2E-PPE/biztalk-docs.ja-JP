---
title: ReceivePortRef (Port ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: a47f7ff2568e6eb39fed059fb31dc31e2f0b68af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268482"
---
# <a name="receiveportref-port-node"></a><span data-ttu-id="db992-102">ReceivePortRef (Port ノード)</span><span class="sxs-lookup"><span data-stu-id="db992-102">ReceivePortRef (Port Node)</span></span>
<span data-ttu-id="db992-103">バインド ファイルの Port ノードの ReceivePortRef ノードは、サービスによって参照される受信ポートに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="db992-103">The ReceivePortRef node of the Port node of a binding file contains information about a receive port that is referenced by a service.</span></span>  
  
## <a name="nodes-in-the-receiveportref-node"></a><span data-ttu-id="db992-104">ReceivePortRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="db992-104">Nodes in the ReceivePortRef node</span></span>  
 <span data-ttu-id="db992-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="db992-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="db992-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="db992-106">**Name**</span></span>|<span data-ttu-id="db992-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="db992-107">**Node Type**</span></span>|<span data-ttu-id="db992-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="db992-108">**Data Type**</span></span>|<span data-ttu-id="db992-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="db992-109">**Description**</span></span>|<span data-ttu-id="db992-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="db992-110">**Restrictions**</span></span>|<span data-ttu-id="db992-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="db992-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="db992-112">名前</span><span class="sxs-lookup"><span data-stu-id="db992-112">Name</span></span>|<span data-ttu-id="db992-113">属性</span><span class="sxs-lookup"><span data-stu-id="db992-113">Attribute</span></span>|<span data-ttu-id="db992-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="db992-114">xs:string</span></span>|<span data-ttu-id="db992-115">サービスによって参照される受信ポートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="db992-115">Specifies the name of a receive port that is referenced by a service.</span></span>|<span data-ttu-id="db992-116">任意</span><span class="sxs-lookup"><span data-stu-id="db992-116">Not required</span></span>|<span data-ttu-id="db992-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="db992-117">Default value: empty</span></span>|
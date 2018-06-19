---
title: DistributionListRef (Port ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionListRef node [binding file]
ms.assetid: 5d0d0121-1bcc-4c26-a1a3-8937ac7c282a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 665b8c2115c5c4681f7cff057481b6ce7da320ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239754"
---
# <a name="distributionlistref-port-node"></a><span data-ttu-id="dd87a-102">DistributionListRef (Port ノード)</span><span class="sxs-lookup"><span data-stu-id="dd87a-102">DistributionListRef (Port Node)</span></span>
<span data-ttu-id="dd87a-103">バインド ファイルの Port ノードの DistributionListRef ノードには、サービスによって参照される同報リストに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd87a-103">The DistributionListRef node of the Port node of a binding file contains information about a distribution list that is referenced by a service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd87a-104">配布リストは、BizTalk Server 管理コンソールで送信ポート グループと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="dd87a-104">Distribution lists are referred to as send port groups in the BizTalk Server Administration Console.</span></span>  
  
## <a name="nodes-in-the-distributionlistref-node"></a><span data-ttu-id="dd87a-105">DistributionListRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="dd87a-105">Nodes in the DistributionListRef node</span></span>  
 <span data-ttu-id="dd87a-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="dd87a-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="dd87a-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="dd87a-107">**Name**</span></span>|<span data-ttu-id="dd87a-108">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="dd87a-108">**Node Type**</span></span>|<span data-ttu-id="dd87a-109">**データ型**</span><span class="sxs-lookup"><span data-stu-id="dd87a-109">**Data Type**</span></span>|<span data-ttu-id="dd87a-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="dd87a-110">**Description**</span></span>|<span data-ttu-id="dd87a-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="dd87a-111">**Restrictions**</span></span>|<span data-ttu-id="dd87a-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="dd87a-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="dd87a-113">名前</span><span class="sxs-lookup"><span data-stu-id="dd87a-113">Name</span></span>|<span data-ttu-id="dd87a-114">属性</span><span class="sxs-lookup"><span data-stu-id="dd87a-114">Attribute</span></span>|<span data-ttu-id="dd87a-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd87a-115">xs:string</span></span>|<span data-ttu-id="dd87a-116">サービスによって参照される同報リストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd87a-116">Specifies the name of a distribution list that is referenced by a service.</span></span>|<span data-ttu-id="dd87a-117">任意</span><span class="sxs-lookup"><span data-stu-id="dd87a-117">Not required</span></span>|<span data-ttu-id="dd87a-118">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="dd87a-118">Default value: empty</span></span>|
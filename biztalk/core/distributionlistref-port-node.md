---
title: DistributionListRef (Port ノード) |Microsoft Docs
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
ms.openlocfilehash: 77bdfe705ac85be0e97492f84e39378b8da944bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351009"
---
# <a name="distributionlistref-port-node"></a><span data-ttu-id="baf2c-102">DistributionListRef (Port ノード)</span><span class="sxs-lookup"><span data-stu-id="baf2c-102">DistributionListRef (Port Node)</span></span>
<span data-ttu-id="baf2c-103">バインド ファイルの Port ノードの DistributionListRef ノードには、サービスによって参照される同報リストに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="baf2c-103">The DistributionListRef node of the Port node of a binding file contains information about a distribution list that is referenced by a service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baf2c-104">配布リストは、BizTalk Server 管理コンソールで送信ポート グループと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="baf2c-104">Distribution lists are referred to as send port groups in the BizTalk Server Administration Console.</span></span>  
  
## <a name="nodes-in-the-distributionlistref-node"></a><span data-ttu-id="baf2c-105">DistributionListRef ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="baf2c-105">Nodes in the DistributionListRef node</span></span>  
 <span data-ttu-id="baf2c-106">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="baf2c-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="baf2c-107">**名前**</span><span class="sxs-lookup"><span data-stu-id="baf2c-107">**Name**</span></span>|<span data-ttu-id="baf2c-108">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="baf2c-108">**Node Type**</span></span>|<span data-ttu-id="baf2c-109">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="baf2c-109">**Data Type**</span></span>|<span data-ttu-id="baf2c-110">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="baf2c-110">**Description**</span></span>|<span data-ttu-id="baf2c-111">**制限**</span><span class="sxs-lookup"><span data-stu-id="baf2c-111">**Restrictions**</span></span>|<span data-ttu-id="baf2c-112">**コメント**</span><span class="sxs-lookup"><span data-stu-id="baf2c-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="baf2c-113">名前</span><span class="sxs-lookup"><span data-stu-id="baf2c-113">Name</span></span>|<span data-ttu-id="baf2c-114">属性</span><span class="sxs-lookup"><span data-stu-id="baf2c-114">Attribute</span></span>|<span data-ttu-id="baf2c-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="baf2c-115">xs:string</span></span>|<span data-ttu-id="baf2c-116">サービスによって参照される同報リストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="baf2c-116">Specifies the name of a distribution list that is referenced by a service.</span></span>|<span data-ttu-id="baf2c-117">任意</span><span class="sxs-lookup"><span data-stu-id="baf2c-117">Not required</span></span>|<span data-ttu-id="baf2c-118">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="baf2c-118">Default value: empty</span></span>|
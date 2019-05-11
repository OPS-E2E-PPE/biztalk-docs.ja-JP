---
title: Ports (Service ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ports node [binding file]
ms.assetid: 498d4310-4e9e-4e74-bc3d-5cbf1319c4ff
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8c7c160529b23a66d2c7cb444908adbaff13184
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394818"
---
# <a name="ports-service-node"></a><span data-ttu-id="dd8e7-102">Ports (Service ノード)</span><span class="sxs-lookup"><span data-stu-id="dd8e7-102">Ports (Service Node)</span></span>
<span data-ttu-id="dd8e7-103">バインド ファイルの Ports ノードは、すべてのポート ノードは、バインド ファイルと共にエクスポートされるサービスにバインドされるポートに関する特定の情報を含む親ノードです。</span><span class="sxs-lookup"><span data-stu-id="dd8e7-103">The Ports node of a binding file is the parent node for all of the Port nodes which contain specific information about ports bound to a service that is exported with the binding file.</span></span>  
  
## <a name="node-in-the-ports-node"></a><span data-ttu-id="dd8e7-104">[ポート] ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="dd8e7-104">Node in the Ports node</span></span>  
 <span data-ttu-id="dd8e7-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="dd8e7-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="dd8e7-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="dd8e7-106">**Name**</span></span>|<span data-ttu-id="dd8e7-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="dd8e7-107">**Node Type**</span></span>|<span data-ttu-id="dd8e7-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="dd8e7-108">**Data Type**</span></span>|<span data-ttu-id="dd8e7-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="dd8e7-109">**Description**</span></span>|<span data-ttu-id="dd8e7-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="dd8e7-110">**Restrictions**</span></span>|<span data-ttu-id="dd8e7-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="dd8e7-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="dd8e7-112">[[ポート]](../core/port-ports-node.md)</span><span class="sxs-lookup"><span data-stu-id="dd8e7-112">[Port](../core/port-ports-node.md)</span></span>|<span data-ttu-id="dd8e7-113">レコード</span><span class="sxs-lookup"><span data-stu-id="dd8e7-113">Record</span></span>|<span data-ttu-id="dd8e7-114">ServicePortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="dd8e7-114">ServicePortRef (ComplexType)</span></span>|<span data-ttu-id="dd8e7-115">バインド ファイルと共にエクスポートされるサービスにバインドされたポートに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd8e7-115">Specifies information about a port that is bound to a service that is exported with the binding file.</span></span>|<span data-ttu-id="dd8e7-116">任意</span><span class="sxs-lookup"><span data-stu-id="dd8e7-116">Not required</span></span>|<span data-ttu-id="dd8e7-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="dd8e7-117">Default value: none</span></span>|
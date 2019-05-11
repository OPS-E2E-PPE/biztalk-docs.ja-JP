---
title: (Service ノード) の役割 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Roles node [binding file]
ms.assetid: 847755c9-1697-41a0-b870-f9e795a1a2a6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff156bce1fa4114aac34641ce52d28cdf182ecd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240403"
---
# <a name="roles-service-node"></a><span data-ttu-id="439dd-102">Roles (Service ノード)</span><span class="sxs-lookup"><span data-stu-id="439dd-102">Roles (Service Node)</span></span>
<span data-ttu-id="439dd-103">バインド ファイルの Roles ノードは、すべては、バインド ファイルと共にエクスポートされるサービスにバインドされている各ロールに関する情報を提供するロール ノードの親ノードです。</span><span class="sxs-lookup"><span data-stu-id="439dd-103">The Roles node of a binding file is the parent node for all of the Role nodes which provide specific information about each role bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-roles-node"></a><span data-ttu-id="439dd-104">[ロール] ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="439dd-104">Nodes in the Roles node</span></span>  
 <span data-ttu-id="439dd-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="439dd-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="439dd-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="439dd-106">**Name**</span></span>|<span data-ttu-id="439dd-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="439dd-107">**Node Type**</span></span>|<span data-ttu-id="439dd-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="439dd-108">**Data Type**</span></span>|<span data-ttu-id="439dd-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="439dd-109">**Description**</span></span>|<span data-ttu-id="439dd-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="439dd-110">**Restrictions**</span></span>|<span data-ttu-id="439dd-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="439dd-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="439dd-112">ロール</span><span class="sxs-lookup"><span data-stu-id="439dd-112">Role</span></span>](../core/role-roles-node.md)|<span data-ttu-id="439dd-113">レコード</span><span class="sxs-lookup"><span data-stu-id="439dd-113">Record</span></span>|<span data-ttu-id="439dd-114">RoleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="439dd-114">RoleRef (ComplexType)</span></span>|<span data-ttu-id="439dd-115">バインド ファイルと共にエクスポートされるサービスにバインドされているロールに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="439dd-115">Specifies information about a role that is bound to a service that is exported with the binding file.</span></span>|<span data-ttu-id="439dd-116">任意</span><span class="sxs-lookup"><span data-stu-id="439dd-116">Not required</span></span>|<span data-ttu-id="439dd-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="439dd-117">Default value: none</span></span>|
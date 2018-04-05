---
title: Roles (Service ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: b47f5ae94326b0555c0c9cd84752cb9f1c409daa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="roles-service-node"></a><span data-ttu-id="6564d-102">Roles (Service ノード)</span><span class="sxs-lookup"><span data-stu-id="6564d-102">Roles (Service Node)</span></span>
<span data-ttu-id="6564d-103">バインド ファイルの Roles ノードは、そのバインド ファイルと共にエクスポートされるサービスにバインドされている各ロールに関する情報を提供するすべての Role ノードの親ノードです。</span><span class="sxs-lookup"><span data-stu-id="6564d-103">The Roles node of a binding file is the parent node for all of the Role nodes which provide specific information about each role bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-roles-node"></a><span data-ttu-id="6564d-104">Roles ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="6564d-104">Nodes in the Roles node</span></span>  
 <span data-ttu-id="6564d-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="6564d-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="6564d-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="6564d-106">**Name**</span></span>|<span data-ttu-id="6564d-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="6564d-107">**Node Type**</span></span>|<span data-ttu-id="6564d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6564d-108">**Data Type**</span></span>|<span data-ttu-id="6564d-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="6564d-109">**Description**</span></span>|<span data-ttu-id="6564d-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="6564d-110">**Restrictions**</span></span>|<span data-ttu-id="6564d-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="6564d-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="6564d-112">ロール</span><span class="sxs-lookup"><span data-stu-id="6564d-112">Role</span></span>](../core/role-roles-node.md)|<span data-ttu-id="6564d-113">レコード</span><span class="sxs-lookup"><span data-stu-id="6564d-113">Record</span></span>|<span data-ttu-id="6564d-114">RoleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="6564d-114">RoleRef (ComplexType)</span></span>|<span data-ttu-id="6564d-115">バインド ファイルと共にエクスポートされるサービスにバインドされたロールに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="6564d-115">Specifies information about a role that is bound to a service that is exported with the binding file.</span></span>|<span data-ttu-id="6564d-116">任意</span><span class="sxs-lookup"><span data-stu-id="6564d-116">Not required</span></span>|<span data-ttu-id="6564d-117">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="6564d-117">Default value: none</span></span>|
---
title: "Role (Roles ノード) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Role node [binding file]
ms.assetid: dfe2a579-7090-4d85-87e5-d627598c4ee8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d70e99568db262ef5abd5b0885cb814c722347f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="role-roles-node"></a><span data-ttu-id="6d812-102">Role (Roles ノード)</span><span class="sxs-lookup"><span data-stu-id="6d812-102">Role (Roles Node)</span></span>
<span data-ttu-id="6d812-103">バインド ファイルの Roles ノードの Role ノードは、バインド ファイルと共にエクスポートされるサービスにバインドされるロールに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d812-103">The Role node of the Roles node of a binding file specifies information about a role that is bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-role-node"></a><span data-ttu-id="6d812-104">Role ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="6d812-104">Nodes in the Role node</span></span>  
 <span data-ttu-id="6d812-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="6d812-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="6d812-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="6d812-106">**Name**</span></span>|<span data-ttu-id="6d812-107">**ノード型**</span><span class="sxs-lookup"><span data-stu-id="6d812-107">**Node Type**</span></span>|<span data-ttu-id="6d812-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="6d812-108">**Data Type**</span></span>|<span data-ttu-id="6d812-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="6d812-109">**Description**</span></span>|<span data-ttu-id="6d812-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="6d812-110">**Restrictions**</span></span>|<span data-ttu-id="6d812-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="6d812-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="6d812-112">名前</span><span class="sxs-lookup"><span data-stu-id="6d812-112">Name</span></span>|<span data-ttu-id="6d812-113">属性</span><span class="sxs-lookup"><span data-stu-id="6d812-113">Attribute</span></span>|<span data-ttu-id="6d812-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d812-114">xs:string</span></span>|<span data-ttu-id="6d812-115">ロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d812-115">Specifies the name of the role.</span></span>|<span data-ttu-id="6d812-116">任意</span><span class="sxs-lookup"><span data-stu-id="6d812-116">Not required</span></span>|<span data-ttu-id="6d812-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="6d812-117">Default value: empty</span></span>|  
|<span data-ttu-id="6d812-118">RoleLinkTypeName</span><span class="sxs-lookup"><span data-stu-id="6d812-118">RoleLinkTypeName</span></span>|<span data-ttu-id="6d812-119">属性</span><span class="sxs-lookup"><span data-stu-id="6d812-119">Attribute</span></span>|<span data-ttu-id="6d812-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d812-120">xs:string</span></span>|<span data-ttu-id="6d812-121">ロールに関連付けられているロール リンクの種類の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d812-121">Specifies the name of the role link type associated with the role</span></span>|<span data-ttu-id="6d812-122">任意</span><span class="sxs-lookup"><span data-stu-id="6d812-122">Not required</span></span>|<span data-ttu-id="6d812-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="6d812-123">Default value: empty</span></span>|  
|<span data-ttu-id="6d812-124">RoleType</span><span class="sxs-lookup"><span data-stu-id="6d812-124">RoleType</span></span>|<span data-ttu-id="6d812-125">属性</span><span class="sxs-lookup"><span data-stu-id="6d812-125">Attribute</span></span>|<span data-ttu-id="6d812-126">RoleRefType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="6d812-126">RoleRefType (SimpleType)</span></span>|<span data-ttu-id="6d812-127">ロールに関連付けられているロールの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d812-127">Specifies the role type associated with the role.</span></span>|<span data-ttu-id="6d812-128">必須</span><span class="sxs-lookup"><span data-stu-id="6d812-128">Required</span></span>|<span data-ttu-id="6d812-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="6d812-129">Default value: none</span></span><br /><br /> <span data-ttu-id="6d812-130">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d812-130">Possible values include:</span></span><br /><br /> <span data-ttu-id="6d812-131">-不明</span><span class="sxs-lookup"><span data-stu-id="6d812-131">-   Unknown</span></span><br /><span data-ttu-id="6d812-132">実装</span><span class="sxs-lookup"><span data-stu-id="6d812-132">-   Implements</span></span><br /><span data-ttu-id="6d812-133">使用します。</span><span class="sxs-lookup"><span data-stu-id="6d812-133">-   Uses</span></span>|  
|[<span data-ttu-id="6d812-134">Enlisted Parties</span><span class="sxs-lookup"><span data-stu-id="6d812-134">Enlisted Parties</span></span>](../core/enlisted-parties-role-node.md)|<span data-ttu-id="6d812-135">レコード</span><span class="sxs-lookup"><span data-stu-id="6d812-135">Record</span></span>|<span data-ttu-id="6d812-136">ArrayOfEnlistedParty (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="6d812-136">ArrayOfEnlistedParty (ComplexType)</span></span>|<span data-ttu-id="6d812-137">このロールにバインドされた参加しているパーティのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="6d812-137">Container node for the enlisted parties bound to this role.</span></span>|<span data-ttu-id="6d812-138">任意</span><span class="sxs-lookup"><span data-stu-id="6d812-138">Not required</span></span>|<span data-ttu-id="6d812-139">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="6d812-139">Default value: none</span></span>|
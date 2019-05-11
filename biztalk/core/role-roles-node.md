---
title: Role (Roles ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Role node [binding file]
ms.assetid: dfe2a579-7090-4d85-87e5-d627598c4ee8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 652702d35eb0ab1f9fd974491e5ae94e2a1cec4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254706"
---
# <a name="role-roles-node"></a><span data-ttu-id="3f84b-102">Role (Roles ノード)</span><span class="sxs-lookup"><span data-stu-id="3f84b-102">Role (Roles Node)</span></span>
<span data-ttu-id="3f84b-103">バインド ファイルの Roles ノードの Role ノードは、バインド ファイルと共にエクスポートされるサービスにバインドされているロールに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f84b-103">The Role node of the Roles node of a binding file specifies information about a role that is bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-role-node"></a><span data-ttu-id="3f84b-104">Role ノード内のノード</span><span class="sxs-lookup"><span data-stu-id="3f84b-104">Nodes in the Role node</span></span>  
 <span data-ttu-id="3f84b-105">次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="3f84b-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="3f84b-106">**名前**</span><span class="sxs-lookup"><span data-stu-id="3f84b-106">**Name**</span></span>|<span data-ttu-id="3f84b-107">**ノードの種類**</span><span class="sxs-lookup"><span data-stu-id="3f84b-107">**Node Type**</span></span>|<span data-ttu-id="3f84b-108">**[データ型]**</span><span class="sxs-lookup"><span data-stu-id="3f84b-108">**Data Type**</span></span>|<span data-ttu-id="3f84b-109">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="3f84b-109">**Description**</span></span>|<span data-ttu-id="3f84b-110">**制限**</span><span class="sxs-lookup"><span data-stu-id="3f84b-110">**Restrictions**</span></span>|<span data-ttu-id="3f84b-111">**コメント**</span><span class="sxs-lookup"><span data-stu-id="3f84b-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="3f84b-112">名前</span><span class="sxs-lookup"><span data-stu-id="3f84b-112">Name</span></span>|<span data-ttu-id="3f84b-113">属性</span><span class="sxs-lookup"><span data-stu-id="3f84b-113">Attribute</span></span>|<span data-ttu-id="3f84b-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f84b-114">xs:string</span></span>|<span data-ttu-id="3f84b-115">ロールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f84b-115">Specifies the name of the role.</span></span>|<span data-ttu-id="3f84b-116">任意</span><span class="sxs-lookup"><span data-stu-id="3f84b-116">Not required</span></span>|<span data-ttu-id="3f84b-117">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="3f84b-117">Default value: empty</span></span>|  
|<span data-ttu-id="3f84b-118">RoleLinkTypeName</span><span class="sxs-lookup"><span data-stu-id="3f84b-118">RoleLinkTypeName</span></span>|<span data-ttu-id="3f84b-119">属性</span><span class="sxs-lookup"><span data-stu-id="3f84b-119">Attribute</span></span>|<span data-ttu-id="3f84b-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f84b-120">xs:string</span></span>|<span data-ttu-id="3f84b-121">ロールに関連付けられているロール リンクの種類の名前を指定します</span><span class="sxs-lookup"><span data-stu-id="3f84b-121">Specifies the name of the role link type associated with the role</span></span>|<span data-ttu-id="3f84b-122">任意</span><span class="sxs-lookup"><span data-stu-id="3f84b-122">Not required</span></span>|<span data-ttu-id="3f84b-123">既定値: 空</span><span class="sxs-lookup"><span data-stu-id="3f84b-123">Default value: empty</span></span>|  
|<span data-ttu-id="3f84b-124">RoleType</span><span class="sxs-lookup"><span data-stu-id="3f84b-124">RoleType</span></span>|<span data-ttu-id="3f84b-125">属性</span><span class="sxs-lookup"><span data-stu-id="3f84b-125">Attribute</span></span>|<span data-ttu-id="3f84b-126">RoleRefType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="3f84b-126">RoleRefType (SimpleType)</span></span>|<span data-ttu-id="3f84b-127">ロールに関連付けられているロールの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f84b-127">Specifies the role type associated with the role.</span></span>|<span data-ttu-id="3f84b-128">必須</span><span class="sxs-lookup"><span data-stu-id="3f84b-128">Required</span></span>|<span data-ttu-id="3f84b-129">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="3f84b-129">Default value: none</span></span><br /><br /> <span data-ttu-id="3f84b-130">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f84b-130">Possible values include:</span></span><br /><br /> <span data-ttu-id="3f84b-131">-不明</span><span class="sxs-lookup"><span data-stu-id="3f84b-131">-   Unknown</span></span><br /><span data-ttu-id="3f84b-132">実装</span><span class="sxs-lookup"><span data-stu-id="3f84b-132">-   Implements</span></span><br /><span data-ttu-id="3f84b-133">-使用します。</span><span class="sxs-lookup"><span data-stu-id="3f84b-133">-   Uses</span></span>|  
|[<span data-ttu-id="3f84b-134">Enlisted Parties</span><span class="sxs-lookup"><span data-stu-id="3f84b-134">Enlisted Parties</span></span>](../core/enlisted-parties-role-node.md)|<span data-ttu-id="3f84b-135">レコード</span><span class="sxs-lookup"><span data-stu-id="3f84b-135">Record</span></span>|<span data-ttu-id="3f84b-136">ArrayOfEnlistedParty (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="3f84b-136">ArrayOfEnlistedParty (ComplexType)</span></span>|<span data-ttu-id="3f84b-137">このロールにバインドされた参加しているパーティのコンテナー ノードです。</span><span class="sxs-lookup"><span data-stu-id="3f84b-137">Container node for the enlisted parties bound to this role.</span></span>|<span data-ttu-id="3f84b-138">任意</span><span class="sxs-lookup"><span data-stu-id="3f84b-138">Not required</span></span>|<span data-ttu-id="3f84b-139">既定値: なし</span><span class="sxs-lookup"><span data-stu-id="3f84b-139">Default value: none</span></span>|
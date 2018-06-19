---
title: 環境変数が展開の状態を指定する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, variables
ms.assetid: 022b782b-008d-41a7-9880-d1c4e5e4015e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041e77eadb7c1b62e3441ee3b3c138203299f3a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246498"
---
# <a name="how-environment-variables-indicate-deployment-state"></a><span data-ttu-id="6690c-102">環境変数と展開状態の対応関係</span><span class="sxs-lookup"><span data-stu-id="6690c-102">How Environment Variables Indicate Deployment State</span></span>
<span data-ttu-id="6690c-103">処理前または処理後のスクリプトを呼び出すと、これらのスクリプトでは環境変数 BTAD_ChangeRequestAction、BTAD_InstallMode、および BTAD_HostClass を確認することにより、実行中の展開の状態 (インストール、インポート、削除、アンインストール、インポート ロールバック、インストール ロールバック) が判断されます。</span><span class="sxs-lookup"><span data-stu-id="6690c-103">Once invoked, a pre- or post-processing script can determine in which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode and BTAD_HostClass.</span></span>  
  
 <span data-ttu-id="6690c-104">次の表に、これら 3 つの環境変数の組み合わせとそれに対応する展開状態を示します。</span><span class="sxs-lookup"><span data-stu-id="6690c-104">The following table describes the combinations of the three variables that indicate the different deployment states.</span></span>  
  
|<span data-ttu-id="6690c-105">展開状態</span><span class="sxs-lookup"><span data-stu-id="6690c-105">Deployment State</span></span>|<span data-ttu-id="6690c-106">予期される値</span><span class="sxs-lookup"><span data-stu-id="6690c-106">Expected Values</span></span>|  
|----------------------|---------------------|  
||<span data-ttu-id="6690c-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="6690c-107">BTAD_ChangeRequestAction</span></span>|<span data-ttu-id="6690c-108">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="6690c-108">BTAD_InstallMode</span></span>|<span data-ttu-id="6690c-109">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="6690c-109">BTAD_HostClass</span></span>|  
|<span data-ttu-id="6690c-110">インポート (フラグの上書きなし)</span><span class="sxs-lookup"><span data-stu-id="6690c-110">Import without overwrite flag</span></span>|<span data-ttu-id="6690c-111">作成</span><span class="sxs-lookup"><span data-stu-id="6690c-111">Create</span></span>|<span data-ttu-id="6690c-112">[インポート]</span><span class="sxs-lookup"><span data-stu-id="6690c-112">Import</span></span>|<span data-ttu-id="6690c-113">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="6690c-113">ConfigurationDb</span></span>|  
|<span data-ttu-id="6690c-114">インポート (フラグの上書きあり)</span><span class="sxs-lookup"><span data-stu-id="6690c-114">Import with overwrite flag</span></span>|<span data-ttu-id="6690c-115">Update</span><span class="sxs-lookup"><span data-stu-id="6690c-115">Update</span></span>|<span data-ttu-id="6690c-116">[インポート]</span><span class="sxs-lookup"><span data-stu-id="6690c-116">Import</span></span>|<span data-ttu-id="6690c-117">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="6690c-117">ConfigurationDb</span></span>|  
|<span data-ttu-id="6690c-118">Install</span><span class="sxs-lookup"><span data-stu-id="6690c-118">Install</span></span>|<span data-ttu-id="6690c-119">Update</span><span class="sxs-lookup"><span data-stu-id="6690c-119">Update</span></span>|<span data-ttu-id="6690c-120">Install</span><span class="sxs-lookup"><span data-stu-id="6690c-120">Install</span></span>|<span data-ttu-id="6690c-121">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="6690c-121">BizTalkHostInstance</span></span>|  
|<span data-ttu-id="6690c-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="6690c-122">Uninstall</span></span>|<span data-ttu-id="6690c-123">DELETE</span><span class="sxs-lookup"><span data-stu-id="6690c-123">Delete</span></span>|<span data-ttu-id="6690c-124">Uninstall</span><span class="sxs-lookup"><span data-stu-id="6690c-124">Uninstall</span></span>|<span data-ttu-id="6690c-125">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="6690c-125">BizTalkHostInstance</span></span>|  
|<span data-ttu-id="6690c-126">インポート ロールバック</span><span class="sxs-lookup"><span data-stu-id="6690c-126">Import rollback</span></span>|<span data-ttu-id="6690c-127">DELETE</span><span class="sxs-lookup"><span data-stu-id="6690c-127">Delete</span></span>|<span data-ttu-id="6690c-128">[インポート]</span><span class="sxs-lookup"><span data-stu-id="6690c-128">Import</span></span>|<span data-ttu-id="6690c-129">ConfigurationDb</span><span class="sxs-lookup"><span data-stu-id="6690c-129">ConfigurationDb</span></span>|  
|<span data-ttu-id="6690c-130">インストール ロールバック</span><span class="sxs-lookup"><span data-stu-id="6690c-130">Install rollback</span></span>|<span data-ttu-id="6690c-131">DELETE</span><span class="sxs-lookup"><span data-stu-id="6690c-131">Delete</span></span>|<span data-ttu-id="6690c-132">Install</span><span class="sxs-lookup"><span data-stu-id="6690c-132">Install</span></span>|<span data-ttu-id="6690c-133">BizTalkHostInstance</span><span class="sxs-lookup"><span data-stu-id="6690c-133">BizTalkHostInstance</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6690c-134">参照</span><span class="sxs-lookup"><span data-stu-id="6690c-134">See Also</span></span>  
 <span data-ttu-id="6690c-135">[前処理および後処理のスクリプトを使用したアプリケーションの展開のカスタマイズ](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="6690c-135">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 <span data-ttu-id="6690c-136">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span><span class="sxs-lookup"><span data-stu-id="6690c-136">[BTAD_ChangeRequestAction](../core/btad-changerequestaction.md) </span></span>  
 <span data-ttu-id="6690c-137">[BTAD_InstallMode](../core/btad-installmode.md) </span><span class="sxs-lookup"><span data-stu-id="6690c-137">[BTAD_InstallMode](../core/btad-installmode.md) </span></span>  
 [<span data-ttu-id="6690c-138">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="6690c-138">BTAD_HostClass</span></span>](../core/btad-hostclass.md)
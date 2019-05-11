---
title: アセンブリと例外管理サンプルがインストールされているアイテム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af580992-73d4-4b16-a1cc-fa819b441fca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac0a14eeb6eaca71cf346c901b33b03f590ca563
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392287"
---
# <a name="assemblies-and-artifacts-installed-by-the-exception-management-samples"></a><span data-ttu-id="7ab13-102">アセンブリとアイテム例外管理サンプルによりインストール</span><span class="sxs-lookup"><span data-stu-id="7ab13-102">Assemblies and Artifacts Installed by the Exception Management Samples</span></span>
<span data-ttu-id="7ab13-103">次の表は、アセンブリと、ESB 例外管理サンプルのインストールされている他の成果物を示します。</span><span class="sxs-lookup"><span data-stu-id="7ab13-103">The following table lists the assemblies and other artifacts installed for the ESB Exception Management sample.</span></span>  
  
|<span data-ttu-id="7ab13-104">場所</span><span class="sxs-lookup"><span data-stu-id="7ab13-104">Location</span></span>|<span data-ttu-id="7ab13-105">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="7ab13-105">Category</span></span>|<span data-ttu-id="7ab13-106">コンポーネントの名前とバージョン</span><span class="sxs-lookup"><span data-stu-id="7ab13-106">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="7ab13-107">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-107">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-108">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="7ab13-108">Orchestrations</span></span>|<span data-ttu-id="7ab13-109">GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess</span><span class="sxs-lookup"><span data-stu-id="7ab13-109">GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess</span></span>|  
|||<span data-ttu-id="7ab13-110">GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler</span><span class="sxs-lookup"><span data-stu-id="7ab13-110">GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler</span></span>|  
|||<span data-ttu-id="7ab13-111">GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler</span><span class="sxs-lookup"><span data-stu-id="7ab13-111">GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler</span></span>|  
|<span data-ttu-id="7ab13-112">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-112">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-113">送信ポート</span><span class="sxs-lookup"><span data-stu-id="7ab13-113">Send Ports</span></span>|<span data-ttu-id="7ab13-114">EAIProcessHandler.RepairSubmit</span><span class="sxs-lookup"><span data-stu-id="7ab13-114">EAIProcessHandler.RepairSubmit</span></span>|  
|||<span data-ttu-id="7ab13-115">EAIGenericHandler.PostTmpMsg</span><span class="sxs-lookup"><span data-stu-id="7ab13-115">EAIGenericHandler.PostTmpMsg</span></span>|  
|||<span data-ttu-id="7ab13-116">EAIProcess.PostApproval</span><span class="sxs-lookup"><span data-stu-id="7ab13-116">EAIProcess.PostApproval</span></span>|  
|||<span data-ttu-id="7ab13-117">EAIProcessHandler.PostDecline</span><span class="sxs-lookup"><span data-stu-id="7ab13-117">EAIProcessHandler.PostDecline</span></span>|  
|||<span data-ttu-id="7ab13-118">すべての。Exceptions_FILE (GlobalFaultProcessor パイプラインを参照)</span><span class="sxs-lookup"><span data-stu-id="7ab13-118">ALL.Exceptions_FILE (references the GlobalFaultProcessor pipeline)</span></span>|  
|<span data-ttu-id="7ab13-119">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-120">受信ポート</span><span class="sxs-lookup"><span data-stu-id="7ab13-120">Receive Ports</span></span>|<span data-ttu-id="7ab13-121">EAIProcess.RequestPort</span><span class="sxs-lookup"><span data-stu-id="7ab13-121">EAIProcess.RequestPort</span></span>|  
|<span data-ttu-id="7ab13-122">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-123">受信場所</span><span class="sxs-lookup"><span data-stu-id="7ab13-123">Receive Locations</span></span>|<span data-ttu-id="7ab13-124">EAIProcess.RequestPort_FILE</span><span class="sxs-lookup"><span data-stu-id="7ab13-124">EAIProcess.RequestPort_FILE</span></span>|  
|||<span data-ttu-id="7ab13-125">EAIProcess.ReSubmit_HTTP</span><span class="sxs-lookup"><span data-stu-id="7ab13-125">EAIProcess.ReSubmit_HTTP</span></span>|  
|<span data-ttu-id="7ab13-126">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-126">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-127">スキーマ</span><span class="sxs-lookup"><span data-stu-id="7ab13-127">Schemas</span></span>|<span data-ttu-id="7ab13-128">GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-128">GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="7ab13-129">GlobalBank.ESB.ExceptionHandling.Schemas.Request バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-129">GlobalBank.ESB.ExceptionHandling.Schemas.Request Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="7ab13-130">GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-130">GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied Version 2.0.0.0</span></span>|  
|<span data-ttu-id="7ab13-131">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-132">パイプライン</span><span class="sxs-lookup"><span data-stu-id="7ab13-132">Pipelines</span></span>|<span data-ttu-id="7ab13-133">GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-133">GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor Version 2.0.0.0</span></span>|  
|<span data-ttu-id="7ab13-134">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-135">リソース</span><span class="sxs-lookup"><span data-stu-id="7ab13-135">Resources</span></span>|<span data-ttu-id="7ab13-136">GlobalBank.ESB.ExceptionHandling.Handlers バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-136">GlobalBank.ESB.ExceptionHandling.Handlers Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="7ab13-137">GlobalBank.ESB.ExceptionHandling.Processes バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-137">GlobalBank.ESB.ExceptionHandling.Processes Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="7ab13-138">GlobalBank.ESB.ExceptionHandling.Schemas バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-138">GlobalBank.ESB.ExceptionHandling.Schemas Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="7ab13-139">GlobalBank.ESB.ExceptionHandling.Pipelines バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-139">GlobalBank.ESB.ExceptionHandling.Pipelines Version 2.0.0.0</span></span>|  
|<span data-ttu-id="7ab13-140">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-140">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-141">ポリシー</span><span class="sxs-lookup"><span data-stu-id="7ab13-141">Policies</span></span>||  
|<span data-ttu-id="7ab13-142">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="7ab13-142">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="7ab13-143">マップ</span><span class="sxs-lookup"><span data-stu-id="7ab13-143">Maps</span></span>|<span data-ttu-id="7ab13-144">GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-144">GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied Version 2.0.0.0</span></span>|  
|<span data-ttu-id="7ab13-145">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="7ab13-145">Global assembly cache</span></span>|<span data-ttu-id="7ab13-146">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="7ab13-146">Assemblies</span></span>|<span data-ttu-id="7ab13-147">GlobalBank.ESB.ExceptionHandling.Handlers バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-147">GlobalBank.ESB.ExceptionHandling.Handlers Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="7ab13-148">GlobalBank.ESB.ExceptionHandling.Processes バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-148">GlobalBank.ESB.ExceptionHandling.Processes Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="7ab13-149">GlobalBank.ESB.ExceptionHandling.Schemas バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-149">GlobalBank.ESB.ExceptionHandling.Schemas Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="7ab13-150">GlobalBank.ESB.ExceptionHandling.Pipelines バージョン 2.0.0.0 以降</span><span class="sxs-lookup"><span data-stu-id="7ab13-150">GlobalBank.ESB.ExceptionHandling.Pipelines Version 2.0.0.0</span></span>|  
|<span data-ttu-id="7ab13-151">%Program Files %\\BizTalk Server\Pipeline コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7ab13-151">%Program Files%\\BizTalk Server\Pipeline Components</span></span>|<span data-ttu-id="7ab13-152">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7ab13-152">Pipeline components</span></span>||
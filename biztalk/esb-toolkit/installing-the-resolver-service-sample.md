---
title: "リゾルバー サービスのサンプルをインストールする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fce9bbeb-9377-41af-8ca7-740ce4d1f617
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bd438725b53362cda1b041af697283e68d77ba7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="installing-the-resolver-service-sample"></a><span data-ttu-id="0e5dd-102">リゾルバー サービスのサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0e5dd-102">Installing the Resolver Service Sample</span></span>
<span data-ttu-id="0e5dd-103">このセクションでは、リゾルバー サービスのサンプルをインストールするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0e5dd-103">This section describes the process for installing the Resolver Service sample.</span></span> <span data-ttu-id="0e5dd-104">リゾルバー サービスに依存して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="0e5dd-104">The Resolver Service depends on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core solution.</span></span> <span data-ttu-id="0e5dd-105">インストール、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コアは自動的にコピーして、適切な場所にこのサンプルに必要な中核となるアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0e5dd-105">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the core assemblies required by this sample to the correct locations.</span></span>  
  
 <span data-ttu-id="0e5dd-106">**ソリューションのプロジェクトからリゾルバー サービスのサンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="0e5dd-106">**To install the Resolver Service sample from the solution project**</span></span>  
  
1.  <span data-ttu-id="0e5dd-107">Windows エクスプローラで、\Source\Samples\ResolverService\Install\Scripts フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e5dd-107">In Windows Explorer, open the \Source\Samples\ResolverService\Install\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="0e5dd-108">Setup_bin.cmd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e5dd-108">Double-click the Setup_bin.cmd file.</span></span>  
  
3.  <span data-ttu-id="0e5dd-109">このサンプルのインストールの成功を確認するまたはアプリケーションを実行するときに問題が発生する場合、必要なアセンブリとその他のアイテムの存在をチェックする次の表に用意された一覧を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e5dd-109">To confirm successful installation of the sample, or if you are encountering issues when you run applications, you can use the list provided in the following table to check for the presence of the required assemblies and other artifacts.</span></span>  
  
|<span data-ttu-id="0e5dd-110">場所</span><span class="sxs-lookup"><span data-stu-id="0e5dd-110">Location</span></span>|<span data-ttu-id="0e5dd-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="0e5dd-111">Category</span></span>|<span data-ttu-id="0e5dd-112">コンポーネントの名前とバージョン</span><span class="sxs-lookup"><span data-stu-id="0e5dd-112">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="0e5dd-113">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-113">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-114">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="0e5dd-114">Orchestrations</span></span>|<span data-ttu-id="0e5dd-115">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-115">(none)</span></span>|  
|<span data-ttu-id="0e5dd-116">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-116">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-117">送信ポート</span><span class="sxs-lookup"><span data-stu-id="0e5dd-117">Send Ports</span></span>|<span data-ttu-id="0e5dd-118">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-118">(none)</span></span>|  
|<span data-ttu-id="0e5dd-119">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-120">受信ポート</span><span class="sxs-lookup"><span data-stu-id="0e5dd-120">Receive Ports</span></span>|<span data-ttu-id="0e5dd-121">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-121">(none)</span></span>|  
|<span data-ttu-id="0e5dd-122">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-123">受信場所</span><span class="sxs-lookup"><span data-stu-id="0e5dd-123">Receive Locations</span></span>|<span data-ttu-id="0e5dd-124">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-124">(none)</span></span>|  
|<span data-ttu-id="0e5dd-125">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-125">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-126">スキーマ</span><span class="sxs-lookup"><span data-stu-id="0e5dd-126">Schemas</span></span>|<span data-ttu-id="0e5dd-127">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-127">(none)</span></span>|  
|<span data-ttu-id="0e5dd-128">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-128">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-129">パイプライン</span><span class="sxs-lookup"><span data-stu-id="0e5dd-129">Pipelines</span></span>|<span data-ttu-id="0e5dd-130">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-130">(none)</span></span>|  
|<span data-ttu-id="0e5dd-131">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-132">リソース</span><span class="sxs-lookup"><span data-stu-id="0e5dd-132">Resources</span></span>|<span data-ttu-id="0e5dd-133">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-133">(none)</span></span>|  
|<span data-ttu-id="0e5dd-134">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-135">ポリシー</span><span class="sxs-lookup"><span data-stu-id="0e5dd-135">Policies</span></span>|<span data-ttu-id="0e5dd-136">ResolveEndpoint</span><span class="sxs-lookup"><span data-stu-id="0e5dd-136">ResolveEndpoint</span></span>|  
|||<span data-ttu-id="0e5dd-137">ResolveMap</span><span class="sxs-lookup"><span data-stu-id="0e5dd-137">ResolveMap</span></span>|  
|<span data-ttu-id="0e5dd-138">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0e5dd-138">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0e5dd-139">マップ</span><span class="sxs-lookup"><span data-stu-id="0e5dd-139">Maps</span></span>|<span data-ttu-id="0e5dd-140">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-140">(none)</span></span>|  
|<span data-ttu-id="0e5dd-141">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="0e5dd-141">Global assembly cache</span></span>|<span data-ttu-id="0e5dd-142">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="0e5dd-142">Assemblies</span></span>|<span data-ttu-id="0e5dd-143">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-143">(none)</span></span>|  
|<span data-ttu-id="0e5dd-144">%Program Files %\\BizTalk Server\Pipeline コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0e5dd-144">%Program Files%\\BizTalk Server\Pipeline Components</span></span>|<span data-ttu-id="0e5dd-145">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0e5dd-145">Pipeline components</span></span>|<span data-ttu-id="0e5dd-146">(なし)</span><span class="sxs-lookup"><span data-stu-id="0e5dd-146">(none)</span></span>|
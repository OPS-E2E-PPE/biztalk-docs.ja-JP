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
ms.openlocfilehash: b06c7383dee805612a3f599148f1d631891ace79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-resolver-service-sample"></a><span data-ttu-id="a1cad-102">リゾルバー サービスのサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1cad-102">Installing the Resolver Service Sample</span></span>
<span data-ttu-id="a1cad-103">このセクションでは、リゾルバー サービスのサンプルをインストールするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a1cad-103">This section describes the process for installing the Resolver Service sample.</span></span> <span data-ttu-id="a1cad-104">リゾルバー サービスに依存して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="a1cad-104">The Resolver Service depends on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core solution.</span></span> <span data-ttu-id="a1cad-105">インストール、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コアは自動的にコピーして、適切な場所にこのサンプルに必要な中核となるアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a1cad-105">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the core assemblies required by this sample to the correct locations.</span></span>  
  
 <span data-ttu-id="a1cad-106">**ソリューションのプロジェクトからリゾルバー サービスのサンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="a1cad-106">**To install the Resolver Service sample from the solution project**</span></span>  
  
1.  <span data-ttu-id="a1cad-107">Windows エクスプローラで、\Source\Samples\ResolverService\Install\Scripts フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1cad-107">In Windows Explorer, open the \Source\Samples\ResolverService\Install\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="a1cad-108">Setup_bin.cmd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1cad-108">Double-click the Setup_bin.cmd file.</span></span>  
  
3.  <span data-ttu-id="a1cad-109">このサンプルのインストールの成功を確認するまたはアプリケーションを実行するときに問題が発生する場合、必要なアセンブリとその他のアイテムの存在をチェックする次の表に用意された一覧を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1cad-109">To confirm successful installation of the sample, or if you are encountering issues when you run applications, you can use the list provided in the following table to check for the presence of the required assemblies and other artifacts.</span></span>  
  
|<span data-ttu-id="a1cad-110">場所</span><span class="sxs-lookup"><span data-stu-id="a1cad-110">Location</span></span>|<span data-ttu-id="a1cad-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a1cad-111">Category</span></span>|<span data-ttu-id="a1cad-112">コンポーネントの名前とバージョン</span><span class="sxs-lookup"><span data-stu-id="a1cad-112">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="a1cad-113">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-113">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-114">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="a1cad-114">Orchestrations</span></span>|<span data-ttu-id="a1cad-115">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-115">(none)</span></span>|  
|<span data-ttu-id="a1cad-116">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-116">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-117">送信ポート</span><span class="sxs-lookup"><span data-stu-id="a1cad-117">Send Ports</span></span>|<span data-ttu-id="a1cad-118">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-118">(none)</span></span>|  
|<span data-ttu-id="a1cad-119">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-120">受信ポート</span><span class="sxs-lookup"><span data-stu-id="a1cad-120">Receive Ports</span></span>|<span data-ttu-id="a1cad-121">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-121">(none)</span></span>|  
|<span data-ttu-id="a1cad-122">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-123">受信場所</span><span class="sxs-lookup"><span data-stu-id="a1cad-123">Receive Locations</span></span>|<span data-ttu-id="a1cad-124">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-124">(none)</span></span>|  
|<span data-ttu-id="a1cad-125">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-125">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-126">スキーマ</span><span class="sxs-lookup"><span data-stu-id="a1cad-126">Schemas</span></span>|<span data-ttu-id="a1cad-127">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-127">(none)</span></span>|  
|<span data-ttu-id="a1cad-128">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-128">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-129">パイプライン</span><span class="sxs-lookup"><span data-stu-id="a1cad-129">Pipelines</span></span>|<span data-ttu-id="a1cad-130">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-130">(none)</span></span>|  
|<span data-ttu-id="a1cad-131">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-132">リソース</span><span class="sxs-lookup"><span data-stu-id="a1cad-132">Resources</span></span>|<span data-ttu-id="a1cad-133">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-133">(none)</span></span>|  
|<span data-ttu-id="a1cad-134">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-135">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a1cad-135">Policies</span></span>|<span data-ttu-id="a1cad-136">ResolveEndpoint</span><span class="sxs-lookup"><span data-stu-id="a1cad-136">ResolveEndpoint</span></span>|  
|||<span data-ttu-id="a1cad-137">ResolveMap</span><span class="sxs-lookup"><span data-stu-id="a1cad-137">ResolveMap</span></span>|  
|<span data-ttu-id="a1cad-138">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a1cad-138">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a1cad-139">マップ</span><span class="sxs-lookup"><span data-stu-id="a1cad-139">Maps</span></span>|<span data-ttu-id="a1cad-140">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-140">(none)</span></span>|  
|<span data-ttu-id="a1cad-141">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="a1cad-141">Global assembly cache</span></span>|<span data-ttu-id="a1cad-142">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="a1cad-142">Assemblies</span></span>|<span data-ttu-id="a1cad-143">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-143">(none)</span></span>|  
|<span data-ttu-id="a1cad-144">%Program Files %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a1cad-144">%Program Files%\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline Components</span></span>|<span data-ttu-id="a1cad-145">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a1cad-145">Pipeline components</span></span>|<span data-ttu-id="a1cad-146">(なし)</span><span class="sxs-lookup"><span data-stu-id="a1cad-146">(none)</span></span>|
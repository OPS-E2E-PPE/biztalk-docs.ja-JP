---
title: リゾルバー サービス サンプルをインストールする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce9bbeb-9377-41af-8ca7-740ce4d1f617
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88168abccba2fc8eb266816b6820bbcdc72d0c67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249734"
---
# <a name="installing-the-resolver-service-sample"></a><span data-ttu-id="1fa5c-102">リゾルバー サービス サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-102">Installing the Resolver Service Sample</span></span>
<span data-ttu-id="1fa5c-103">このセクションでは、リゾルバー サービス サンプルをインストールするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-103">This section describes the process for installing the Resolver Service sample.</span></span> <span data-ttu-id="1fa5c-104">リゾルバー サービスに依存して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ソリューションのコアします。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-104">The Resolver Service depends on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core solution.</span></span> <span data-ttu-id="1fa5c-105">インストール、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core は自動的にコピーして、適切な場所には、このサンプルに必要なコア アセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-105">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the core assemblies required by this sample to the correct locations.</span></span>  
  
 <span data-ttu-id="1fa5c-106">**ソリューションのプロジェクトからリゾルバー サービス サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="1fa5c-106">**To install the Resolver Service sample from the solution project**</span></span>  
  
1.  <span data-ttu-id="1fa5c-107">Windows エクスプ ローラーで、\Source\Samples\ResolverService\Install\Scripts フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-107">In Windows Explorer, open the \Source\Samples\ResolverService\Install\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="1fa5c-108">Setup_bin.cmd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-108">Double-click the Setup_bin.cmd file.</span></span>  
  
3.  <span data-ttu-id="1fa5c-109">サンプルでは、正常にインストールすることを確認するか、アプリケーションを実行するときに問題が発生する場合、必要なアセンブリおよびその他の成果物の有無を確認する次の表で指定された一覧を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1fa5c-109">To confirm successful installation of the sample, or if you are encountering issues when you run applications, you can use the list provided in the following table to check for the presence of the required assemblies and other artifacts.</span></span>  
  
|<span data-ttu-id="1fa5c-110">場所</span><span class="sxs-lookup"><span data-stu-id="1fa5c-110">Location</span></span>|<span data-ttu-id="1fa5c-111">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="1fa5c-111">Category</span></span>|<span data-ttu-id="1fa5c-112">コンポーネントの名前とバージョン</span><span class="sxs-lookup"><span data-stu-id="1fa5c-112">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="1fa5c-113">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-113">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-114">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="1fa5c-114">Orchestrations</span></span>|<span data-ttu-id="1fa5c-115">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-115">(none)</span></span>|  
|<span data-ttu-id="1fa5c-116">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-116">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-117">送信ポート</span><span class="sxs-lookup"><span data-stu-id="1fa5c-117">Send Ports</span></span>|<span data-ttu-id="1fa5c-118">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-118">(none)</span></span>|  
|<span data-ttu-id="1fa5c-119">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-120">受信ポート</span><span class="sxs-lookup"><span data-stu-id="1fa5c-120">Receive Ports</span></span>|<span data-ttu-id="1fa5c-121">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-121">(none)</span></span>|  
|<span data-ttu-id="1fa5c-122">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-123">受信場所</span><span class="sxs-lookup"><span data-stu-id="1fa5c-123">Receive Locations</span></span>|<span data-ttu-id="1fa5c-124">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-124">(none)</span></span>|  
|<span data-ttu-id="1fa5c-125">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-125">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-126">スキーマ</span><span class="sxs-lookup"><span data-stu-id="1fa5c-126">Schemas</span></span>|<span data-ttu-id="1fa5c-127">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-127">(none)</span></span>|  
|<span data-ttu-id="1fa5c-128">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-128">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-129">パイプライン</span><span class="sxs-lookup"><span data-stu-id="1fa5c-129">Pipelines</span></span>|<span data-ttu-id="1fa5c-130">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-130">(none)</span></span>|  
|<span data-ttu-id="1fa5c-131">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-132">リソース</span><span class="sxs-lookup"><span data-stu-id="1fa5c-132">Resources</span></span>|<span data-ttu-id="1fa5c-133">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-133">(none)</span></span>|  
|<span data-ttu-id="1fa5c-134">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-135">ポリシー</span><span class="sxs-lookup"><span data-stu-id="1fa5c-135">Policies</span></span>|<span data-ttu-id="1fa5c-136">ResolveEndpoint</span><span class="sxs-lookup"><span data-stu-id="1fa5c-136">ResolveEndpoint</span></span>|  
|||<span data-ttu-id="1fa5c-137">ResolveMap</span><span class="sxs-lookup"><span data-stu-id="1fa5c-137">ResolveMap</span></span>|  
|<span data-ttu-id="1fa5c-138">BizTalk アプリケーション GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="1fa5c-138">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="1fa5c-139">マップ</span><span class="sxs-lookup"><span data-stu-id="1fa5c-139">Maps</span></span>|<span data-ttu-id="1fa5c-140">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-140">(none)</span></span>|  
|<span data-ttu-id="1fa5c-141">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="1fa5c-141">Global assembly cache</span></span>|<span data-ttu-id="1fa5c-142">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="1fa5c-142">Assemblies</span></span>|<span data-ttu-id="1fa5c-143">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-143">(none)</span></span>|  
|<span data-ttu-id="1fa5c-144">%Program Files %\\BizTalk Server\Pipeline コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1fa5c-144">%Program Files%\\BizTalk Server\Pipeline Components</span></span>|<span data-ttu-id="1fa5c-145">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1fa5c-145">Pipeline components</span></span>|<span data-ttu-id="1fa5c-146">(なし)</span><span class="sxs-lookup"><span data-stu-id="1fa5c-146">(none)</span></span>|
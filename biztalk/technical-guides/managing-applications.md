---
title: アプリケーションの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef1039fb-7460-444b-a45e-2783bdc7c109
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8dcfc6eaecaf13b08369a7b0036a3b3eb0c6189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396255"
---
# <a name="managing-applications"></a><span data-ttu-id="f991e-102">アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="f991e-102">Managing Applications</span></span>
<span data-ttu-id="f991e-103">BizTalk アプリケーションは、オーケストレーション、パイプライン、スキーマ、マップ、およびポートなどのアプリケーションの成果物の論理コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="f991e-103">A BizTalk application is a logical container for application artifacts, such as orchestrations, pipelines, schemas, maps, and ports.</span></span> <span data-ttu-id="f991e-104">BizTalk アプリケーションを使用すると、同じコンテナーに関連するコンポーネントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f991e-104">BizTalk applications enable you to include related components in the same container.</span></span> <span data-ttu-id="f991e-105">アプリケーション内のすべてのアイテムは、アプリケーション内で他の成果物または任意の参照先アプリケーション内のすべてのアイテムを参照できます。</span><span class="sxs-lookup"><span data-stu-id="f991e-105">Any artifact within an application may refer to any other artifacts within that application, or to any artifact in any referenced application.</span></span> <span data-ttu-id="f991e-106">BizTalk アプリケーションで可能性のある成果物の一覧については、次を参照してください[BizTalk アプリケーションとは何ですか?。](http://go.microsoft.com/fwlink/?LinkId=154994)</span><span class="sxs-lookup"><span data-stu-id="f991e-106">For a complete list of artifacts that can be in a BizTalk application, see [What is a BizTalk Application?](http://go.microsoft.com/fwlink/?LinkId=154994)</span></span> <span data-ttu-id="f991e-107">(http://go.microsoft.com/fwlink/?LinkId=154994)。</span><span class="sxs-lookup"><span data-stu-id="f991e-107">(http://go.microsoft.com/fwlink/?LinkId=154994).</span></span>  
  
 <span data-ttu-id="f991e-108">BizTalk アプリケーションは多くの日常を効率化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]タスク。</span><span class="sxs-lookup"><span data-stu-id="f991e-108">BizTalk applications streamline many everyday [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tasks.</span></span> <span data-ttu-id="f991e-109">ことができますをデプロイ、管理、開始、停止、およびトラブルシューティングを行う[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション レベル。</span><span class="sxs-lookup"><span data-stu-id="f991e-109">You can deploy, manage, start, stop, and troubleshoot [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at the application level.</span></span> <span data-ttu-id="f991e-110">これは、結果、少ない混乱でユーザー エラーのリスクです。</span><span class="sxs-lookup"><span data-stu-id="f991e-110">This results in less confusion and less risk of error for users.</span></span> <span data-ttu-id="f991e-111">BizTalk アプリケーションのコンテナーが含まれています</span><span class="sxs-lookup"><span data-stu-id="f991e-111">A BizTalk application container contains</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f991e-112">Visual Studio 環境で展開するアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="f991e-112">assemblies that are deployed to it by the Visual Studio environment.</span></span> <span data-ttu-id="f991e-113">アプリケーションが含まれる場合も、受信ポート、受信場所、ポート、プロパティの追跡設定、およびロール リンクを送信します。</span><span class="sxs-lookup"><span data-stu-id="f991e-113">The application may also contain receive ports, receive locations, send ports, property tracking settings, and role links.</span></span> <span data-ttu-id="f991e-114">手動で追加することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション、または移動するアセンブリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションからのアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="f991e-114">You can manually add [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies to the application, or move [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies from other applications.</span></span> <span data-ttu-id="f991e-115">さらに、次のように追加することができます以外[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アセンブリと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス ルール エンジン (BRE) ポリシーと BAM 定義ファイルなどの成果物。</span><span class="sxs-lookup"><span data-stu-id="f991e-115">In addition, you can add non-[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts such as Business Rule Engine (BRE) policies and BAM definition files.</span></span> <span data-ttu-id="f991e-116">暗黙的に、アプリケーションも含まれますすべてのバインドで、現在の設定によって表されます。</span><span class="sxs-lookup"><span data-stu-id="f991e-116">Implicitly, the application also contains all of the bindings that are represented by their current settings.</span></span>  
  
 <span data-ttu-id="f991e-117">前を作成することも、アプリケーションがインポートされるときにアクションを実行する処理後のスクリプトは、インストール、またはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f991e-117">You can create pre- or post-processing scripts to perform actions when an application is imported, installed, or uninstalled.</span></span> <span data-ttu-id="f991e-118">詳細については、このようなスクリプトを使用して、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](http://go.microsoft.com/fwlink/?LinkId=154995)(http://go.microsoft.com/fwlink/?LinkId=154995)します。</span><span class="sxs-lookup"><span data-stu-id="f991e-118">For more information about using such scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](http://go.microsoft.com/fwlink/?LinkId=154995) (http://go.microsoft.com/fwlink/?LinkId=154995).</span></span>  
  
 <span data-ttu-id="f991e-119">このセクションでは、展開、バージョン、およびアプリケーションまたは個別のアイテムを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f991e-119">This section describes how to deploy, version, and update applications or individual artifacts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f991e-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f991e-120">In This Section</span></span>  
  
-   [<span data-ttu-id="f991e-121">アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="f991e-121">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)  
  
-   [<span data-ttu-id="f991e-122">アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="f991e-122">Updating an Application</span></span>](../technical-guides/updating-an-application.md)
---
title: "アプリケーションの管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef1039fb-7460-444b-a45e-2783bdc7c109
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e525499671a04228763c6792961c3204a3a2d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-applications"></a><span data-ttu-id="aab0c-102">アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="aab0c-102">Managing Applications</span></span>
<span data-ttu-id="aab0c-103">BizTalk アプリケーションは、オーケストレーション、パイプライン、スキーマ、マップ、およびポートなどのアプリケーションの成果物の論理コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="aab0c-103">A BizTalk application is a logical container for application artifacts, such as orchestrations, pipelines, schemas, maps, and ports.</span></span> <span data-ttu-id="aab0c-104">BizTalk アプリケーションを使用すると、同じコンテナーに関連するコンポーネントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="aab0c-104">BizTalk applications enable you to include related components in the same container.</span></span> <span data-ttu-id="aab0c-105">アプリケーション内のすべてのアイテムには、そのアプリケーション内で他の成果物または任意の参照先アプリケーション内のすべてのアイテムを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aab0c-105">Any artifact within an application may refer to any other artifacts within that application, or to any artifact in any referenced application.</span></span> <span data-ttu-id="aab0c-106">BizTalk アプリケーションに格納できるアイテムの完全な一覧を参照してください。 [BizTalk アプリケーションは何ですか。](http://go.microsoft.com/fwlink/?LinkId=154994)</span><span class="sxs-lookup"><span data-stu-id="aab0c-106">For a complete list of artifacts that can be in a BizTalk application, see [What is a BizTalk Application?](http://go.microsoft.com/fwlink/?LinkId=154994)</span></span> <span data-ttu-id="aab0c-107">(http://go.microsoft.com/fwlink/?LinkId=154994)。</span><span class="sxs-lookup"><span data-stu-id="aab0c-107">(http://go.microsoft.com/fwlink/?LinkId=154994).</span></span>  
  
 <span data-ttu-id="aab0c-108">BizTalk アプリケーションに多くの日常的が効率化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]タスク。</span><span class="sxs-lookup"><span data-stu-id="aab0c-108">BizTalk applications streamline many everyday [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tasks.</span></span> <span data-ttu-id="aab0c-109">ことができますを展開、管理、開始、停止、およびトラブルシューティング[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション レベルでします。</span><span class="sxs-lookup"><span data-stu-id="aab0c-109">You can deploy, manage, start, stop, and troubleshoot [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] at the application level.</span></span> <span data-ttu-id="aab0c-110">これは、結果、小さい混乱とユーザーのエラーのリスクを抑えです。</span><span class="sxs-lookup"><span data-stu-id="aab0c-110">This results in less confusion and less risk of error for users.</span></span> <span data-ttu-id="aab0c-111">BizTalk アプリケーション コンテナーが含まれています</span><span class="sxs-lookup"><span data-stu-id="aab0c-111">A BizTalk application container contains</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="aab0c-112">Visual Studio 環境に展開されているアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="aab0c-112"> assemblies that are deployed to it by the Visual Studio environment.</span></span> <span data-ttu-id="aab0c-113">アプリケーションに含めることがありますも受信ポート、受信場所、ポート、プロパティの追跡設定、およびロール リンクを送信します。</span><span class="sxs-lookup"><span data-stu-id="aab0c-113">The application may also contain receive ports, receive locations, send ports, property tracking settings, and role links.</span></span> <span data-ttu-id="aab0c-114">手動で追加することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション、または移動するアセンブリを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションからのアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="aab0c-114">You can manually add [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies to the application, or move [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies from other applications.</span></span> <span data-ttu-id="aab0c-115">さらに、次のように追加することではない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アセンブリと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス ルール エンジン (BRE) ポリシーおよび BAM 定義ファイルなどの成果物です。</span><span class="sxs-lookup"><span data-stu-id="aab0c-115">In addition, you can add non-[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts such as Business Rule Engine (BRE) policies and BAM definition files.</span></span> <span data-ttu-id="aab0c-116">暗黙的に、アプリケーションも含まれますすべてのバインドで、現在の設定によって表されます。</span><span class="sxs-lookup"><span data-stu-id="aab0c-116">Implicitly, the application also contains all of the bindings that are represented by their current settings.</span></span>  
  
 <span data-ttu-id="aab0c-117">事前作成または処理後のスクリプト操作を実行するアプリケーションをインポートすると、インストール、またはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="aab0c-117">You can create pre- or post-processing scripts to perform actions when an application is imported, installed, or uninstalled.</span></span> <span data-ttu-id="aab0c-118">詳細については、このようなスクリプトを使用して、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](http://go.microsoft.com/fwlink/?LinkId=154995)(http://go.microsoft.com/fwlink/?LinkId=154995)。</span><span class="sxs-lookup"><span data-stu-id="aab0c-118">For more information about using such scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](http://go.microsoft.com/fwlink/?LinkId=154995) (http://go.microsoft.com/fwlink/?LinkId=154995).</span></span>  
  
 <span data-ttu-id="aab0c-119">このセクションでは、配置、バージョン、およびアプリケーションまたは個別のアイテムを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aab0c-119">This section describes how to deploy, version, and update applications or individual artifacts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aab0c-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aab0c-120">In This Section</span></span>  
  
-   [<span data-ttu-id="aab0c-121">アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="aab0c-121">Deploying an Application</span></span>](../technical-guides/deploying-an-application.md)  
  
-   [<span data-ttu-id="aab0c-122">アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="aab0c-122">Updating an Application</span></span>](../technical-guides/updating-an-application.md)
---
title: 展開して、BizTalk アプリケーションの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, managing
- Administration Console [BizTalk Server], applications
- bts06.deployment.application
- managing, applications
ms.assetid: d933ad2b-702b-48df-8ef6-a5702d0521e2
caps.latest.revision: 49
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355c66f7550f5e4cf2b04cfc8bb1f705cc6ade7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239202"
---
# <a name="deploying-and-managing-biztalk-applications"></a><span data-ttu-id="168ed-102">BizTalk アプリケーションの展開と管理</span><span class="sxs-lookup"><span data-stu-id="168ed-102">Deploying and Managing BizTalk Applications</span></span>
<span data-ttu-id="168ed-103">ここでは、展開、変更、更新、および展開解除の方法など、BizTalk アプリケーションの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="168ed-103">This section provides information about managing BizTalk applications, including how to deploy, modify, update, and undeploy them.</span></span> <span data-ttu-id="168ed-104">BizTalk アプリケーションは、BizTalk ビジネス ソリューションを構成する "アイテム" を表示して管理する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="168ed-104">BizTalk applications provide a way to view and manage the items, called "artifacts," that make up a BizTalk business solution.</span></span> <span data-ttu-id="168ed-105">アイテムの例としては、BizTalk アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、証明書などが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="168ed-105">Examples of artifacts are BizTalk assemblies, .NET assemblies, schemas, maps, bindings, and certificates.</span></span>  
  
 <span data-ttu-id="168ed-106">BizTalk アプリケーションを新たに作成し、そこにアイテムを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="168ed-106">You can create a BizTalk application and add artifacts to it.</span></span> <span data-ttu-id="168ed-107">アプリケーションを作成してアイテムを追加したら、BizTalk Server 管理コンソールや BTSTask コマンド ライン ツールを使用して、アプリケーションとそのアイテムの表示、パッケージ作成、展開、および管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="168ed-107">You can then view, package, deploy, and manage the application and its artifacts as a single entity from within the BizTalk Administration console or by using the BTSTask command-line tool.</span></span>  
  
 <span data-ttu-id="168ed-108">BizTalk アプリケーションの展開および保守に関する背景情報については、次を参照してください。 [Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)です。</span><span class="sxs-lookup"><span data-stu-id="168ed-108">For background information about BizTalk application deployment and maintenance, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="168ed-109">単純なアプリケーションを展開する手順については、これを理解するためのアプリケーション展開機能で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チュートリアル: 基本的な BizTalk アプリケーションの展開](../core/walkthrough-deploying-a-basic-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="168ed-109">For step-by-step instructions on deploying a simple application, which will familiarize you with the application deployment features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="168ed-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="168ed-110">In This Section</span></span>  
  
-   [<span data-ttu-id="168ed-111">BizTalk アプリケーションを配置するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="168ed-111">Best Practices for Deploying a BizTalk Application</span></span>](../core/best-practices-for-deploying-a-biztalk-application.md)  
  
-   [<span data-ttu-id="168ed-112">BizTalk アプリケーションの展開と管理のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="168ed-112">BizTalk Application Deployment and Management Checklists</span></span>](../core/biztalk-application-deployment-and-management-checklists.md)  
  
-   [<span data-ttu-id="168ed-113">チュートリアル: 基本的な BizTalk アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="168ed-113">Walkthrough: Deploying a Basic BizTalk Application</span></span>](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md) 
  
-   [<span data-ttu-id="168ed-114">BizTalk アプリケーションの展開と管理を理解します。</span><span class="sxs-lookup"><span data-stu-id="168ed-114">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)  
  
-   [<span data-ttu-id="168ed-115">BizTalk アプリケーション開始および停止する方法</span><span class="sxs-lookup"><span data-stu-id="168ed-115">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)  
  
-   [<span data-ttu-id="168ed-116">作成して、BizTalk アプリケーションの変更</span><span class="sxs-lookup"><span data-stu-id="168ed-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)  
  
-   [<span data-ttu-id="168ed-117">成果物の管理</span><span class="sxs-lookup"><span data-stu-id="168ed-117">Managing Artifacts</span></span>](../core/managing-artifacts.md)  
  
-   [<span data-ttu-id="168ed-118">バインド ファイルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="168ed-118">Customizing Binding Files</span></span>](../core/customizing-binding-files.md)  
  
-   [<span data-ttu-id="168ed-119">前処理および後処理のスクリプトを使用したアプリケーションの展開のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="168ed-119">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)  
  
-   [<span data-ttu-id="168ed-120">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="168ed-120">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)  
  
-   [<span data-ttu-id="168ed-121">BizTalk アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="168ed-121">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)  
  
-   [<span data-ttu-id="168ed-122">BizTalk アプリケーションを展開解除</span><span class="sxs-lookup"><span data-stu-id="168ed-122">Undeploying BizTalk Applications</span></span>](../core/undeploying-biztalk-applications.md)
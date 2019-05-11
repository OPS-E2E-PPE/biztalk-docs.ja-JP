---
title: BizTalk アプリケーション展開、管理 |Microsoft Docs
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
ms.openlocfilehash: 47046b468c859799d5263b52a8989e5f8cf99d2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390147"
---
# <a name="deploying-and-managing-biztalk-applications"></a><span data-ttu-id="786e5-102">BizTalk アプリケーション展開、管理</span><span class="sxs-lookup"><span data-stu-id="786e5-102">Deploying and Managing BizTalk Applications</span></span>
<span data-ttu-id="786e5-103">このセクションでは、デプロイ、変更、更新、および展開解除する方法など、BizTalk アプリケーションの管理についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="786e5-103">This section provides information about managing BizTalk applications, including how to deploy, modify, update, and undeploy them.</span></span> <span data-ttu-id="786e5-104">BizTalk アプリケーションでは、表示し、「アイテム」BizTalk ビジネス ソリューションを構成するアイテムを管理する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="786e5-104">BizTalk applications provide a way to view and manage the items, called "artifacts," that make up a BizTalk business solution.</span></span> <span data-ttu-id="786e5-105">成果物には、BizTalk アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、および証明書があります。</span><span class="sxs-lookup"><span data-stu-id="786e5-105">Examples of artifacts are BizTalk assemblies, .NET assemblies, schemas, maps, bindings, and certificates.</span></span>  
  
 <span data-ttu-id="786e5-106">BizTalk アプリケーションを作成しにアイテムを追加できます。</span><span class="sxs-lookup"><span data-stu-id="786e5-106">You can create a BizTalk application and add artifacts to it.</span></span> <span data-ttu-id="786e5-107">ことができますし、表示、パッケージ、展開、および単一のエンティティとしてから、BizTalk 管理コンソールや BTSTask コマンド ライン ツールを使用して、アプリケーションとそのアイテムを管理します。</span><span class="sxs-lookup"><span data-stu-id="786e5-107">You can then view, package, deploy, and manage the application and its artifacts as a single entity from within the BizTalk Administration console or by using the BTSTask command-line tool.</span></span>  
  
 <span data-ttu-id="786e5-108">BizTalk アプリケーションの展開と保守に関する背景情報は、次を参照してください。 [Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)します。</span><span class="sxs-lookup"><span data-stu-id="786e5-108">For background information about BizTalk application deployment and maintenance, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="786e5-109">単純なアプリケーションの展開のステップ バイ ステップの手順については、これを理解のアプリケーション展開機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チュートリアル。基本的な BizTalk アプリケーション展開](../core/walkthrough-deploying-a-basic-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="786e5-109">For step-by-step instructions on deploying a simple application, which will familiarize you with the application deployment features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Walkthrough: Deploying a Basic BizTalk Application](../core/walkthrough-deploying-a-basic-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="786e5-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="786e5-110">In This Section</span></span>  
  
-   [<span data-ttu-id="786e5-111">BizTalk アプリケーション展開のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="786e5-111">Best Practices for Deploying a BizTalk Application</span></span>](../core/best-practices-for-deploying-a-biztalk-application.md)  
  
-   [<span data-ttu-id="786e5-112">BizTalk アプリケーションの展開と管理のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="786e5-112">BizTalk Application Deployment and Management Checklists</span></span>](../core/biztalk-application-deployment-and-management-checklists.md)  
  
-   [<span data-ttu-id="786e5-113">チュートリアル: 基本的な BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="786e5-113">Walkthrough: Deploying a Basic BizTalk Application</span></span>](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md) 
  
-   [<span data-ttu-id="786e5-114">BizTalk アプリケーションの展開と管理について</span><span class="sxs-lookup"><span data-stu-id="786e5-114">Understanding BizTalk Application Deployment and Management</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)  
  
-   [<span data-ttu-id="786e5-115">BizTalk アプリケーション開始および停止する方法</span><span class="sxs-lookup"><span data-stu-id="786e5-115">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)  
  
-   [<span data-ttu-id="786e5-116">BizTalk アプリケーションの作成と変更</span><span class="sxs-lookup"><span data-stu-id="786e5-116">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)  
  
-   [<span data-ttu-id="786e5-117">アイテムの管理</span><span class="sxs-lookup"><span data-stu-id="786e5-117">Managing Artifacts</span></span>](../core/managing-artifacts.md)  
  
-   [<span data-ttu-id="786e5-118">バインド ファイルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="786e5-118">Customizing Binding Files</span></span>](../core/customizing-binding-files.md)  
  
-   [<span data-ttu-id="786e5-119">処理前および処理後のスクリプトを使用したアプリケーション展開のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="786e5-119">Using Pre- and Post-processing Scripts to Customize Application Deployment</span></span>](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)  
  
-   [<span data-ttu-id="786e5-120">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="786e5-120">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)  
  
-   [<span data-ttu-id="786e5-121">BizTalk アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="786e5-121">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)  
  
-   [<span data-ttu-id="786e5-122">BizTalk アプリケーションの展開解除</span><span class="sxs-lookup"><span data-stu-id="786e5-122">Undeploying BizTalk Applications</span></span>](../core/undeploying-biztalk-applications.md)
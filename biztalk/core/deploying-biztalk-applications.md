---
title: BizTalk アプリケーションの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.deployment.application
helpviewer_keywords:
- deploying [applications]
- managing [applications], deploying
- applications, deploying
ms.assetid: eef12d8a-6f5c-4eb2-b85b-df9281c0b88e
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f141b0b5ee89c0106e25666a4a6c253e91499aea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007651"
---
# <a name="deploying-biztalk-applications"></a><span data-ttu-id="b3693-102">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="b3693-102">Deploying BizTalk Applications</span></span>
<span data-ttu-id="b3693-103">このセクションでは、BizTalk アプリケーションの展開に関する次の情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3693-103">This section provides the following information about deploying BizTalk applications:</span></span>  
  
- <span data-ttu-id="b3693-104">アプリケーションとそのアイテムを Windows インストーラー (.msi) ファイルにエクスポートする。</span><span class="sxs-lookup"><span data-stu-id="b3693-104">Exporting an application and its artifacts to a Windows Installer (.msi) file</span></span>  
  
- <span data-ttu-id="b3693-105">.msi ファイルを別の BizTalk グループにインポートして、アプリケーションとそのアイテムを新しいグループ内に作成する。</span><span class="sxs-lookup"><span data-stu-id="b3693-105">Importing the .msi file into another BizTalk group to create the application and its artifacts in the new group</span></span>  
  
- <span data-ttu-id="b3693-106">アプリケーションを実行するコンピューターにアプリケーションをインストールする。</span><span class="sxs-lookup"><span data-stu-id="b3693-106">Installing the application on the computers that will run it</span></span>  
  
- <span data-ttu-id="b3693-107">BizTalk アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールする。</span><span class="sxs-lookup"><span data-stu-id="b3693-107">Installing BizTalk assemblies to the global assembly cache (GAC)</span></span>  
  
- <span data-ttu-id="b3693-108">アプリケーションの展開およびテストの進行状況を監視する。</span><span class="sxs-lookup"><span data-stu-id="b3693-108">Monitoring the progress of the deployment and testing the application</span></span>  
  
- <span data-ttu-id="b3693-109">アプリケーションを取引先に展開する。</span><span class="sxs-lookup"><span data-stu-id="b3693-109">Deploying an application to a business partner</span></span>  
  
- <span data-ttu-id="b3693-110">バインド ファイルを編集し、さまざまな展開環境に合わせてバインドをカスタマイズする。</span><span class="sxs-lookup"><span data-stu-id="b3693-110">Editing a binding file to customize the bindings for different deployment environments</span></span>  
  
  <span data-ttu-id="b3693-111">別のアプリケーションの展開シナリオで実行する必要があるタスクのチェックリストは、次を参照してください。 [BizTalk アプリケーションの展開と管理のチェックリスト](../core/biztalk-application-deployment-and-management-checklists.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3693-111">For checklists of tasks that you need to perform in different application deployment scenarios, see [BizTalk Application Deployment and Management Checklists](../core/biztalk-application-deployment-and-management-checklists.md).</span></span> <span data-ttu-id="b3693-112">BizTalk アプリケーションと、展開に関する背景情報は、次を参照してください。 [Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3693-112">For background information on BizTalk applications and their deployment, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="b3693-113">アプリケーションを作成して、追加または成果物を削除または別のアプリケーションへの参照を追加することで変更については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3693-113">For information about creating an application and modifying it by adding or removing artifacts or adding a reference to another application, see [Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md).</span></span> <span data-ttu-id="b3693-114">BizTalk アセンブリの展開方法の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3693-114">For information about deploying BizTalk assemblies, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3693-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b3693-115">In This Section</span></span>  
  
-   [<span data-ttu-id="b3693-116">BizTalk アプリケーション、バインド、およびポリシーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="b3693-116">Exporting BizTalk Applications, Bindings, and Policies</span></span>](../core/exporting-biztalk-applications-bindings-and-policies.md)  
  
-   [<span data-ttu-id="b3693-117">BizTalk アプリケーション、バインド、およびポリシーのインポート</span><span class="sxs-lookup"><span data-stu-id="b3693-117">Importing BizTalk Applications, Bindings, and Policies</span></span>](../core/importing-biztalk-applications-bindings-and-policies.md)  
  
-   [<span data-ttu-id="b3693-118">BizTalk アプリケーションをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="b3693-118">How to Install a BizTalk Application</span></span>](../core/how-to-install-a-biztalk-application.md)  
  
-   [<span data-ttu-id="b3693-119">BizTalk アプリケーション展開の進行状況の監視</span><span class="sxs-lookup"><span data-stu-id="b3693-119">Monitoring the Progress of Your BizTalk Application Deployment</span></span>](../core/monitoring-the-progress-of-your-biztalk-application-deployment.md)
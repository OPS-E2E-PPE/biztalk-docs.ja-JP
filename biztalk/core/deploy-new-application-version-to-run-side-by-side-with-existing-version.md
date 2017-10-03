---
title: "既存のバージョンがサイド バイ サイドで実行するアプリケーションの新しいバージョンを展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1677c6a5-2c4c-4d70-ab83-f7e0bb3aaf6e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053145729546453b959dc35c7901932c1c8690c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-a-new-version-of-an-application-to-run-side-by-side-with-an-existing-version"></a><span data-ttu-id="1eb52-102">既存のバージョンと並行して実行するアプリケーションの新しいバージョンを展開する方法</span><span class="sxs-lookup"><span data-stu-id="1eb52-102">How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version</span></span>
<span data-ttu-id="1eb52-103">新しいバージョンのサイド バイ サイドで実行するアプリケーションを展開する方法、既存のバージョン。</span><span class="sxs-lookup"><span data-stu-id="1eb52-103">How to deploy a new version of an application that will run side-by-side with an existing version.</span></span> 

## <a name="overview"></a><span data-ttu-id="1eb52-104">概要</span><span class="sxs-lookup"><span data-stu-id="1eb52-104">Overview</span></span>
<span data-ttu-id="1eb52-105">一度にすべてのパートナーを対象にするのではなく、最初は一部のビジネス パートナーだけが最新バージョンを使用できるようにするなど、アプリケーションの大幅アップグレードを段階的に実行する場合にこの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-105">You might want to do this to roll out a major application upgrade incrementally, for example making it available to a subset of business partners initially, rather than to all partners at once.</span></span> <span data-ttu-id="1eb52-106">この方法を使用すると、新しいバージョンへの完全な切り替えの準備ができるまで、新しいバージョンをまだ使用していないユーザーに、既存のアプリケーションを実行してサービスを提供し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="1eb52-106">Using this approach allows you to continue running the existing application to service the users who are not yet using the new version until you are ready to completely cut over to the new version.</span></span> <span data-ttu-id="1eb52-107">このシナリオの背景情報については、次を参照してください。[シナリオ: 次の 2 つのバージョンのアプリケーションを展開する](../core/scenario-deploying-two-versions-of-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-107">For background information on this scenario, see [Scenario: Deploying Two Versions of an Application](../core/scenario-deploying-two-versions-of-an-application.md).</span></span>  
  
 <span data-ttu-id="1eb52-108">アセンブリ バージョンを作成する場合と異なり、アプリケーション バージョンは、バージョン番号を増やす方法では作成しません。</span><span class="sxs-lookup"><span data-stu-id="1eb52-108">You do not create application versions in the same manner that you create assembly versions, by incrementing the version number.</span></span> <span data-ttu-id="1eb52-109">代わりに、元のアプリケーションとは異なる名前を持つ新しいアプリケーションを作成し、それに新しいバージョンのアプリケーション アイテムを取り込みます。</span><span class="sxs-lookup"><span data-stu-id="1eb52-109">Instead, you create a new application that has a different name than the original application, and populate it with the new versions of the application artifacts.</span></span>  
  
 <span data-ttu-id="1eb52-110">アセンブリなどの多くの種類のアイテムは、BizTalk グループ内の 1 つのアプリケーションにしか存在できません。したがって、グループ内に既に存在するアセンブリを新しいアプリケーションへ展開するには、そのバージョン番号を増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eb52-110">Because many types of artifacts, such as assemblies, can exist in only one application in a BizTalk group, you must increment the version number of any assemblies that already exist in the group before you can deploy them into the new application.</span></span> <span data-ttu-id="1eb52-111">詳細については、次を参照してください。[成果物をする必要がありますする内で一意のアプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-111">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="1eb52-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="1eb52-112">Prerequisites</span></span>  
<span data-ttu-id="1eb52-113">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="1eb52-113">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="1eb52-114">自分のアカウントも、ローカル ファイル システムおよびグローバル アセンブリ キャッシュに対する読み取り/書き込み権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-114">Your account also must have Read/Write permission on the local file system, and the global assembly cache.</span></span> <span data-ttu-id="1eb52-115">ローカル コンピューターの管理者アカウントには、このアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="1eb52-115">The Administrators account on the local computer has this permission.</span></span>  

<span data-ttu-id="1eb52-116">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-116">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span> 
  
## <a name="deploy-a-new-version-of-an-application"></a><span data-ttu-id="1eb52-117">新しいバージョンのアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-117">Deploy a new version of an application</span></span>  
  
1.  <span data-ttu-id="1eb52-118">Visual Studio で、アプリケーションの新しいバージョンに展開するアセンブを必要に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-118">In Visual Studio, make any necessary changes to the assemblies that you want to deploy into the new version of the application</span></span>  
  
2.  <span data-ttu-id="1eb52-119">次のように、各アセンブリのバージョン番号を増やします。</span><span class="sxs-lookup"><span data-stu-id="1eb52-119">Increment the version number of each assembly, as follows:</span></span>  
  
    1.  <span data-ttu-id="1eb52-120">ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-120">In Solution Explorer, right-click the BizTalk project, and then click **Properties** to launch Project Designer for the project.</span></span>  
  
    2.  <span data-ttu-id="1eb52-121">をクリックして、**アプリケーション**タブがアクティブでない場合、クリックして**アセンブリ情報**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1eb52-121">Click the **Application** tab if it is not active, and then click **Assembly Information** button.</span></span>  
  
    3.  <span data-ttu-id="1eb52-122">アセンブリ バージョン番号を大きくし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-122">Increase the assembly version number, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="1eb52-123">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-123">Save the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1eb52-124">パイプライン デザイナー オブジェクト モデルを使用して、アセンブリ バージョンを増やす際のスキーマの競合を避けます。</span><span class="sxs-lookup"><span data-stu-id="1eb52-124">Use the Pipeline Designer Object Model to avoid schema collisions when incrementing assembly versions.</span></span>  
  
3.  <span data-ttu-id="1eb52-125">ソリューションの各プロジェクトの展開プロパティで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1eb52-125">In deployment properties for each project in the solution, do the following:</span></span>  
  
    -   <span data-ttu-id="1eb52-126">アプリケーション名を新しいアプリケーションに対して使用する名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-126">Change the application name to the name you want to use for the new application.</span></span>  
  
    -   <span data-ttu-id="1eb52-127">グローバル アセンブリ キャッシュ (GAC) 内のアセンブリをインストールするためのオプションが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-127">Ensure that the option to install the assemblies in the global assembly cache (GAC) is selected.</span></span>  
  
     <span data-ttu-id="1eb52-128">手順については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-128">For instructions, see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span> <span data-ttu-id="1eb52-129">ソリューションを展開するときに、アセンブリは、新しいアプリケーションに展開され、GAC にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1eb52-129">When you deploy the solution, the assemblies will be deployed into the new application and installed in the GAC.</span></span>  
  
4.  <span data-ttu-id="1eb52-130">アセンブリを含んでいるソリューションを展開します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-130">Deploy the solution(s) containing the assemblies.</span></span> <span data-ttu-id="1eb52-131">手順については、次を参照してください。[を Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-131">For instructions, see [How to Deploy a BizTalk Assembly from Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md).</span></span>  
  
5.  <span data-ttu-id="1eb52-132">新しい受信ポート、およびパートナーがメッセージを送信する際の送信先となる新しい 1 つ以上の URL を指定する任意の必要な受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-132">Create a new receive port and any needed receive locations specifying the new URL(s) to which you want partners to send messages.</span></span> <span data-ttu-id="1eb52-133">手順については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-133">For instructions, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span> <span data-ttu-id="1eb52-134">参照してください[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-134">Also see [How to Create a Receive Location](../core/how-to-create-a-receive-location.md).</span></span>  
  
6.  <span data-ttu-id="1eb52-135">説明に従って、必要に応じて、適切な送信ポートを作成[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-135">Create the appropriate send ports as necessary, as described in [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
7.  <span data-ttu-id="1eb52-136">バインドを新しく作成された新しいアプリケーションが受信および」の説明に従って、送信ポート、[アプリケーションを構成する方法](../core/how-to-configure-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-136">Bind the new application to the newly created receive and send ports, as described in [How to Configure an Application](../core/how-to-configure-an-application.md).</span></span>  
  
8.  <span data-ttu-id="1eb52-137">」の説明に従って、テスト環境から .msi ファイルにアプリケーションをエクスポート[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-137">Export the application into an .msi file from your test environment, as described in [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1eb52-138">次の手順に従って、アプリケーションをテストし、実稼動環境へ展開することができます。</span><span class="sxs-lookup"><span data-stu-id="1eb52-138">You can use the following steps for testing the application as well as deploying it into your production environment.</span></span> <span data-ttu-id="1eb52-139">開発、テスト、ステージング、および実稼働環境でのアプリケーション展開タスクの詳細については、次を参照してください。[アプリケーション展開作業](../core/application-deployment-tasks.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-139">For more information about application deployment tasks in development, test, staging, and production, see [Application Deployment Tasks](../core/application-deployment-tasks.md).</span></span>  
  
9. <span data-ttu-id="1eb52-140">」の説明に従って、実稼働環境で BizTalk グループにアプリケーションの .msi ファイルをインポート[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-140">Import the application .msi file into the BizTalk group in your production environment, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span> <span data-ttu-id="1eb52-141">アプリケーションは、参照を必要とする場合、またはに追加できます MSI のインポート ウィザードを使用しているときに後で」の説明に従って[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-141">If the application requires references, you can add them while using the Import MSI Wizard, or later as described in [How to Add a Reference to Another Application](../core/how-to-add-a-reference-to-another-application.md).</span></span>  
  
10. <span data-ttu-id="1eb52-142">」の説明に従って、それを実行する各ホスト インスタンスで、新しいアプリケーションをインストール[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-142">Install the new application on each host instance that will run it, as described in [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span> <span data-ttu-id="1eb52-143">更新されたそれぞれのアセンブリが、アセンブリをホストする各コンピューターの GAC にインストールされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-143">Verify that each updated assembly has been installed in the GAC on each computer that hosts the assembly.</span></span> <span data-ttu-id="1eb52-144">必要に応じて、アセンブリを GAC にインストール、」の説明に従って[アセンブリを GAC にインストールする方法](../core/how-to-install-an-assembly-in-the-gac.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-144">If necessary, install the assemblies in the GAC, as described in [How to Install an Assembly in the GAC](../core/how-to-install-an-assembly-in-the-gac.md).</span></span>  
  
11. <span data-ttu-id="1eb52-145">説明に従って、アプリケーションの完全な開始を行う[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="1eb52-145">Perform a Full Start of the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
12. <span data-ttu-id="1eb52-146">パートナーに新しい URL へのメッセージの送信を開始する必要があることを通知します。</span><span class="sxs-lookup"><span data-stu-id="1eb52-146">Notify your partners that they should begin sending messages to the new URLS.</span></span> <span data-ttu-id="1eb52-147">パートナーがこれを実行すると、アプリケーションによって指定したパートナーに対するメッセージの処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="1eb52-147">Once they do this, the application begins processing messages for the specified partners.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb52-148">参照</span><span class="sxs-lookup"><span data-stu-id="1eb52-148">See Also</span></span>  
 [<span data-ttu-id="1eb52-149">BizTalk アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="1eb52-149">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)
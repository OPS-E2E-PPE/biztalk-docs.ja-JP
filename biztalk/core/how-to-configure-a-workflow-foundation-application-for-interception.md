---
title: 傍受のために Workflow Foundation のアプリケーションを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c82e83f-9dbd-4325-9f30-778eba892296
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6929161360b2b3af1bfe221e9fa3583d93b566
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967806"
---
# <a name="how-to-configure-a-workflow-foundation-application-for-interception"></a><span data-ttu-id="f29d3-102">傍受のために Workflow Foundation アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f29d3-102">How to Configure a Workflow Foundation Application for Interception</span></span>
<span data-ttu-id="f29d3-103">BAM アクティビティ データの収集を開始するには、まず、BAM インターセプター ソフトウェアをインストールし、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] インターセプターを使用するようにアプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-103">You must install the BAM interceptor software and configure your application to use the [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] interceptor service before you can begin collecting BAM activity data.</span></span> <span data-ttu-id="f29d3-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] およびその依存関係がインストールされ、BizTalk グループが少なくとも 1 つ作成されていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="f29d3-104">It is assumed that you have successfully installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and its dependencies and have created at least one BizTalk group.</span></span>  
  
## <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="f29d3-105">BAM イベント ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="f29d3-105">Installing the BAM-Eventing Software</span></span>  
 <span data-ttu-id="f29d3-106">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 用の BAM インターセプターを使用するように [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションを構成するには、まず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] セットアップ プログラムを使用して BAM イベント ソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-106">Before you can configure your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application to use the BAM interceptor for [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)], you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="f29d3-107">BAM イベント ソフトウェアをインストールして、パフォーマンス カウンターの登録の詳細については、[BAM イベント ソフトウェアをインストールする](../core/installing-the-bam-eventing-software.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f29d3-107">For more information about installing the BAM-Eventing software and registering the performance counters, see [Installing the BAM-Eventing Software](../core/installing-the-bam-eventing-software.md).</span></span>  
  
## <a name="configuring-a-windows-workflow-foundation-application-for-tracking"></a><span data-ttu-id="f29d3-108">追跡のために Windows Workflow Foundation アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f29d3-108">Configuring a Windows Workflow Foundation Application for Tracking</span></span>  
 <span data-ttu-id="f29d3-109">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションで BAM イベント情報の書き込みを開始するには、次の 4 つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-109">Four tasks must be completed before your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application can begin writing BAM event information:</span></span>  
  
- <span data-ttu-id="f29d3-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM ツールを使用して監視モデルを作成し、BAM マネージャーのコマンド ライン ツール (bm.exe) を使用して、それを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-110">An observation model must be created by using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM tools and then deployed by using the BAM Manager command-line tool (bm.exe).</span></span>  
  
- <span data-ttu-id="f29d3-111">BAM マネージャーのコマンド ライン ツール (bm.exe) を使用して、インターセプター構成ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-111">An interceptor configuration file must be created and deployed by using the BAM Manager command line-tool (bm.exe).</span></span>  
  
- <span data-ttu-id="f29d3-112">ホスト アプリケーションを実行しているユーザーは、適切な BAM アクティビティ イベント ライターのメンバーである必要があります (bam _\<アクティビティ\>_EventWriter) SQL Server の役割、インターセプタ構成情報の読み取りと書き込みアプリケーションを有効にするにはBAM のアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="f29d3-112">The user running the host application must be a member of the appropriate BAM activity event writer (bam_\<activity\>_EventWriter) SQL Server roles to enable the application to read the interceptor configuration information and write to the BAM activities.</span></span>  
  
- <span data-ttu-id="f29d3-113">BAM 追跡サービスを読み込むには、App.config ファイルまたはアプリケーション自体を変更してから、アプリケーションを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-113">The App.config file or the application itself must be modified to load the BAM tracking service and then restart the application.</span></span>  
  
  <span data-ttu-id="f29d3-114">これらのタスクを正常に完了した後にのみ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM データベースにイベントが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-114">Only after these tasks have been successfully completed will events begin appearing in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM database.</span></span>  
  
### <a name="deploying-an-observation-model"></a><span data-ttu-id="f29d3-115">監視モデルの展開</span><span class="sxs-lookup"><span data-stu-id="f29d3-115">Deploying an Observation Model</span></span>  
 <span data-ttu-id="f29d3-116">アプリケーション内でインターセプター構成ファイルを展開したり、BAM アクティビティを取得したりするには、監視モデルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-116">You must have an observation model deployed before you can deploy an interceptor configuration file or capture BAM activities in your application.</span></span>  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a><span data-ttu-id="f29d3-117">bm.exe を使用して監視モデルを展開するには</span><span class="sxs-lookup"><span data-stu-id="f29d3-117">To deploy an observation model by using bm.exe</span></span>  
  
1. <span data-ttu-id="f29d3-118">をクリックして**開始**順にクリックします**実行**Windows のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-118">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  
  
2. <span data-ttu-id="f29d3-119">型**cmd**で、**オープン**フィールドをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-119">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="f29d3-120">ディレクトリ変更のコマンドを使用して、展開する監視モデルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-120">Use the change directory command to move to the directory containing the observation model to deploy.</span></span> <span data-ttu-id="f29d3-121">たとえば、 **cd c:\businessprocess\Orders**します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-121">For example, **cd c:\businessprocess\Orders**.</span></span>  
  
4. <span data-ttu-id="f29d3-122">bm.exe を使用して、次のように監視モデルを展開します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-122">Deploy the observation model by using bm.exe:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f29d3-123">Tracking\BM.exe 展開すべて-definitionfile:\<*definitionfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="f29d3-123">Tracking\BM.exe deploy-all -definitionfile:\<*definitionfile.xml*\></span></span>  
  
    <span data-ttu-id="f29d3-124">置換するかどうかを確認\< *definitionfile.xml* \>に展開する監視ファイルの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-124">Make sure you replace \<*definitionfile.xml*\> with the name of the observation file you want to deploy.</span></span> <span data-ttu-id="f29d3-125">オプションの詳細についてを参照してください。[インターセプター管理コマンド](../core/interceptor-management-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-125">For more options see [Interceptor Management Commands](../core/interceptor-management-commands.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f29d3-126">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="f29d3-127">型**終了**、し、enter キーを押してコマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-127">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
### <a name="deploying-an-interceptor-configuration-file"></a><span data-ttu-id="f29d3-128">インターセプター構成ファイルの展開</span><span class="sxs-lookup"><span data-stu-id="f29d3-128">Deploying an Interceptor Configuration File</span></span>  
 <span data-ttu-id="f29d3-129">アプリケーションで BAM アクティビティを取得するには、インターセプター構成ファイルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-129">You must deploy an interceptor configuration file before your application can capture BAM activities.</span></span>  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a><span data-ttu-id="f29d3-130">bm.exe を使用してインターセプター構成ファイルを展開するには</span><span class="sxs-lookup"><span data-stu-id="f29d3-130">To deploy an interceptor configuration file by using bm.exe</span></span>  
  
1. <span data-ttu-id="f29d3-131">をクリックして**開始**順にクリックします**実行**Windows のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-131">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  
  
2. <span data-ttu-id="f29d3-132">型**cmd**で、**オープン**フィールドをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-132">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="f29d3-133">ディレクトリ変更のコマンドを使用して、展開するインターセプター構成ファイルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-133">Use the change directory command to move to the directory containing the interceptor configuration file to deploy.</span></span> <span data-ttu-id="f29d3-134">たとえば、 **cd c:\businessprocess\Orders**します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-134">For example, **cd c:\businessprocess\Orders**.</span></span>  
  
4. <span data-ttu-id="f29d3-135">bm.exe を使用して、次のようにインターセプター構成ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-135">Deploy the interceptor configuration file by using bm.exe:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f29d3-136">Tracking\BM.exe デプロイ インターセプター-filename:\<*icfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="f29d3-136">Tracking\BM.exe deploy-interceptor -filename:\<*icfile.xml*\></span></span>  
  
    <span data-ttu-id="f29d3-137">置換するかどうかを確認\< *icfile.xml* \>に展開するインターセプター構成ファイルの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-137">Make sure you replace \<*icfile.xml*\> with the name of the interceptor configuration file you want to deploy.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f29d3-138">使用することができます、 **-Force:true**インターセプタ構成ファイル内のものと同じ名前の既存のイベント ソースを上書きするフラグ。</span><span class="sxs-lookup"><span data-stu-id="f29d3-138">You can use the **-Force:True** flag to override existing event sources with the same name(s) as those in your interceptor configuration file.</span></span> <span data-ttu-id="f29d3-139">これを行う場合を使用して、既存の構成をバックアップすることを確認、 **get インターセプター**コマンド。</span><span class="sxs-lookup"><span data-stu-id="f29d3-139">If you do so, make sure you back up the existing configuration by using the **get-interceptor** command.</span></span> <span data-ttu-id="f29d3-140">–Force:True フラグを使用すると、上書きされるイベント ソースを参照するインターセプター構成が削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-140">Using the -Force:True flag could delete any interceptor configurations that reference the event sources being overwritten.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f29d3-141">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-141">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="f29d3-142">型**終了**、し、enter キーを押してコマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-142">Type **Exit**, and then press ENTER to close the command prompt.</span></span>  
  
   <span data-ttu-id="f29d3-143">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションを既に展開している場合は、次のポーリング間隔まで新しい構成が読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="f29d3-143">If you have already deployed your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application, the new configuration will not be loaded until the next polling interval.</span></span> <span data-ttu-id="f29d3-144">ただし、アプリケーションを構成して再起動すると、構成はすぐに取得されます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-144">However, if you configure your application and restart it, the configuration will be picked up immediately.</span></span>  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a><span data-ttu-id="f29d3-145">適切な BAM アクティビティ ロールへのユーザーの追加</span><span class="sxs-lookup"><span data-stu-id="f29d3-145">Adding the User to the Appropriate BAM Activity Role</span></span>  
 <span data-ttu-id="f29d3-146">BAM インターセプター フレームワークでは、アクティビティごとの SQL Server ロールを使用して、アクティビティ情報および構成情報へのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-146">The BAM Interceptor Framework uses per-activity SQL Server roles to control access to activities and configuration information.</span></span> <span data-ttu-id="f29d3-147">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションを実行するユーザー アカウントを、BAM プライマリ インポート データベースの適切な BAM アクティビティ ロールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-147">You must add the user account running your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application to the appropriate BAM activity role(s) in the BAM Primary Import database.</span></span>  
  
### <a name="configuring-the-application-to-load-the-bam-tracking-service"></a><span data-ttu-id="f29d3-148">BAM 追跡サービスを読み込むためのアプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="f29d3-148">Configuring the Application to Load the BAM Tracking Service</span></span>  
 <span data-ttu-id="f29d3-149">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションで BAM 追跡サービスを読み込むためのシナリオは 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-149">There are three scenarios for loading the BAM tracking service in your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application:</span></span>  
  
- <span data-ttu-id="f29d3-150">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションで、既に WorkflowRuntime を使用して [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 構成セクションを読み込んでいる場合は、BAM 追跡サービス情報を既存のセクションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-150">If your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application already uses WorkflowRuntime to load a [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] configuration section, you can added BAM tracking service information to the existing section.</span></span>  
  
- <span data-ttu-id="f29d3-151">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションで、WorkflowRuntime を使用して [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 構成セクションを読み込んでいない場合は、コードを追加して、アプリケーション構成ファイルからカスタム セクションを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-151">If your [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application does not use WorkflowRuntime to load a [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] configuration section, you will have to add code to load a custom section from your application configuration file.</span></span> <span data-ttu-id="f29d3-152">セクションを作成し、BAM 追跡サービス情報をそれに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-152">You will have to create the section and add the BAM tracking service information to it.</span></span>  
  
- <span data-ttu-id="f29d3-153">構成をハードコーディングするには、[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] API を使用し、構成ファイルを使わずに、プログラムによって追跡サービスを読み込むか、カスタム ソースから構成を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-153">If you prefer to hard-code the configuration, you can use the [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] API to programmatically load the tracking service without a configuration file, or to load the configuration from a custom source.</span></span>  
  
  <span data-ttu-id="f29d3-154">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションの構成時には、次のことを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="f29d3-154">When configuring the [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] application, note the following considerations:</span></span>  
  
- <span data-ttu-id="f29d3-155">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] インターセプターでは、WorkflowRuntime ごとに BamTrackingService が 1 つだけサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-155">The [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] interceptor supports only one BamTrackingService per one WorkflowRuntime.</span></span>  
  
- <span data-ttu-id="f29d3-156">[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] インターセプターでは、アプリケーション ドメインごとに複数の BamTrackingService がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-156">The [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] interceptor supports multiple BamTrackingService instances per application domain.</span></span>  
  
  -   <span data-ttu-id="f29d3-157">N 個の WorkflowRuntime に対して N 個の BamTrackingService がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-157">N number of BamTrackingService is supported for N number of WorkflowRuntime.</span></span>  
  
- <span data-ttu-id="f29d3-158">同じアプリケーション ドメイン内の異なる BamTrackingService インスタンスに異なる接続文字列が使用されると、インターセプターでは例外が発行されます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-158">The interceptor raises an exception if different connection strings are used for separate BamTrackingService instances in the same application domain.</span></span>  
  
- <span data-ttu-id="f29d3-159">インターセプターは、開始された最初の BamTrackingService インスタンスから IC ポーリング間隔値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-159">The interceptor obtains the IC polling interval value from the first BamTrackingService instance that starts.</span></span>  
  
- <span data-ttu-id="f29d3-160">アプリケーション ドメインで最後の BamTrackingService が停止すると、インターセプターは IC ポーリング スレッドを停止します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-160">The interceptor stops the IC polling thread when last BamTrackingService in application domain is stopped</span></span>  
  
  <span data-ttu-id="f29d3-161">WorkflowRuntime と構成情報の読み込みの詳細については、[ http://go.microsoft.com/fwlink/?LinkId=83314](http://go.microsoft.com/fwlink/?LinkId=83314)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f29d3-161">For more information on WorkflowRuntime and loading configuration information, see [http://go.microsoft.com/fwlink/?LinkId=83314](http://go.microsoft.com/fwlink/?LinkId=83314).</span></span>  
  
##### <a name="to-configure-the-appconfig-file-for-the-bam-tracking-service"></a><span data-ttu-id="f29d3-162">BAM 追跡サービスのために App.config ファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="f29d3-162">To configure the App.config file for the BAM tracking service</span></span>  
  
1.  <span data-ttu-id="f29d3-163">アプリケーションに関連付けられている App.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-163">Open the App.config file associated with your application.</span></span> <span data-ttu-id="f29d3-164">これには、Notepad.exe またはその他のテキスト エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-164">You can use Notepad.exe or another text editor for this task.</span></span>  
  
2.  <span data-ttu-id="f29d3-165">App.config ファイルに次の構成情報を挿入して、BAM 追跡サービスを追加します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-165">Add the BAM Tracking service by inserting the following configuration information into the App.config file.</span></span> <span data-ttu-id="f29d3-166">この情報は、`configuration` 要素の子となるように配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-166">It should be positioned so that it is a child of the `configuration` element.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f29d3-167">セクション要素は、WorkflowRuntime クラスを使用する際に、アプリケーション コードで使用する名前に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29d3-167">The section element should correspond to the name used by your application code when using the WorkflowRuntime class.</span></span>  
  
    ```  
    <!-- The element name must match the one expected by WorkflowRuntime in your WF application -->  
    <WorkflowServiceContainer>  
      <Services>  
        <add type="Microsoft.BizTalk.Bam.Interceptors.Workflow.BamTrackingService, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  
       ConnectionString="Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"   
          PollingIntervalSec="5"/>  
        </Services>  
    </WorkflowServiceContainer>  
    ```  
  
3.  <span data-ttu-id="f29d3-168">変更、 **ConnectionString**環境と一致する属性。</span><span class="sxs-lookup"><span data-stu-id="f29d3-168">Modify the **ConnectionString** attribute to match your environment.</span></span>  
  
4.  <span data-ttu-id="f29d3-169">アプリケーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-169">Restart your application.</span></span>  
  
##### <a name="to-modify-your-application-to-load-a-custom-configuration-section"></a><span data-ttu-id="f29d3-170">カスタム構成セクションを読み込むようにアプリケーションを変更するには</span><span class="sxs-lookup"><span data-stu-id="f29d3-170">To modify your application to load a custom configuration section</span></span>  
  
1.  <span data-ttu-id="f29d3-171">Visual Studio で Windows Workflow Foundation プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-171">Open your Windows Workflow Foundation project in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f29d3-172">適切なパラメーターを設定した BamTrackingService の新しいインスタンスを、アプリケーションの WorkflowRuntime インスタンスに追加します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-172">Add a new instance of BamTrackingService with appropriate parameters to the application's instance of WorkflowRuntime:</span></span>  
  
    ```  
    // !! Replace "WorkflowServiceContainer" with the section name  
    // you used in your App.config file.  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime("WorkflowServiceContainer");  
    ```  
  
3.  <span data-ttu-id="f29d3-173">変更されたアプリケーションを再コンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-173">Recompile and deploy the modified application.</span></span>  
  
##### <a name="to-modify-your-application-to-programmatically-load-the-bam-tracking-service"></a><span data-ttu-id="f29d3-174">アプリケーションを変更して、BAM 追跡サービスをプログラムによって読み込むには</span><span class="sxs-lookup"><span data-stu-id="f29d3-174">To modify your application to programmatically load the BAM tracking service</span></span>  
  
1.  <span data-ttu-id="f29d3-175">Visual Studio で Windows Workflow Foundation プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-175">Open your Windows Workflow Foundation project in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f29d3-176">適切なパラメーターを設定した BamTrackingService の新しいインスタンスを、アプリケーションの WorkflowRuntime インスタンスに追加します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-176">Add a new instance of BamTrackingService with appropriate parameters to the application's instance of WorkflowRuntime:</span></span>  
  
    ```  
    string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"  
    int pollingInterval = 5;  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
    workflowRuntime.AddService(new BamTrackingService(connectionString, pollingInterval));  
    ```  
  
     <span data-ttu-id="f29d3-177">パラメーターは、特定の環境に基づいて追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="f29d3-177">You can add or remove parameters based on your specific environment.</span></span>  
  
3.  <span data-ttu-id="f29d3-178">変更されたアプリケーションを再コンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="f29d3-178">Recompile and deploy the modified application.</span></span>
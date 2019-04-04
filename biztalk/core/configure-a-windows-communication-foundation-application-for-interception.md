---
title: 傍受のため、Windows Communication Foundation アプリケーションを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37f2ccde-aa79-470a-ac31-57e4168dc54a
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b18790784f58dbdab7f917a73d041f382943d2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988907"
---
# <a name="how-to-configure-a-windows-communication-foundation-application-for-interception"></a><span data-ttu-id="f7902-102">傍受のために Windows Communication Foundation アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f7902-102">How to Configure a Windows Communication Foundation Application for Interception</span></span>
<span data-ttu-id="f7902-103">BAM アクティビティ データの収集を開始するには、まず BAM インターセプター ソフトウェアをインストールし、BAM [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] インターセプターを使用するようにアプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-103">You must install the BAM interceptor software and configure your application to use the BAM [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] interceptor service before you can begin collecting BAM activity data.</span></span> <span data-ttu-id="f7902-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] およびその依存関係がインストールされ、BizTalk グループが少なくとも 1 つ作成されていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="f7902-104">It is assumed that you have successfully installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and its dependencies and have created at least one BizTalk group.</span></span>  

## <a name="installing-the-bam-eventing-software"></a><span data-ttu-id="f7902-105">BAM イベント ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="f7902-105">Installing the BAM-Eventing Software</span></span>  
 <span data-ttu-id="f7902-106">[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 用の BAM インターセプターを使用するように [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションを構成するには、まず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] セットアップ プログラムを使用して BAM イベント ソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-106">Before you can configure your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application to use the BAM interceptor for [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], you must install the BAM-Eventing software by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Setup program.</span></span> <span data-ttu-id="f7902-107">BAM イベント ソフトウェアをインストールして、パフォーマンス カウンターの登録の詳細については、[BAM イベント ソフトウェアをインストールする](../core/installing-the-bam-eventing-software.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7902-107">For more information about installing the BAM-Eventing software and registering the performance counters, see [Installing the BAM-Eventing Software](../core/installing-the-bam-eventing-software.md).</span></span>  

## <a name="configuring-a-wcf-application-for-tracking"></a><span data-ttu-id="f7902-108">追跡のための WCF アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="f7902-108">Configuring a WCF Application for Tracking</span></span>  
 <span data-ttu-id="f7902-109">[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションで BAM イベント情報の書き込みを開始するには、次の 4 つのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-109">Four tasks must be completed before your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application can begin writing BAM event information:</span></span>  

- <span data-ttu-id="f7902-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM ツールを使用して監視モデルを作成し、BAM マネージャーのコマンド ライン ツール (bm.exe) を使用してそれを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-110">An observation model must be created by using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM tools and then deployed by using the BAM Manager command line tool (bm.exe).</span></span>  

- <span data-ttu-id="f7902-111">BAM マネージャーのコマンド ライン ツール (bm.exe) を使用してインターセプター構成ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-111">An interceptor configuration file must be created and deployed by using the BAM Manager command line tool (bm.exe).</span></span>  

- <span data-ttu-id="f7902-112">ホスト アプリケーションを実行しているユーザーは、適切な BAM アクティビティ イベント ライターのメンバーである必要があります (bam _\<アクティビティ\>_EventWriter) SQL Server の役割、インターセプタ構成情報の読み取りと書き込みアプリケーションを有効にするにはBAM のアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="f7902-112">The user running the host application must be a member of the appropriate BAM activity event writer (bam_\<activity\>_EventWriter) SQL Server roles to enable the application to read the interceptor configuration information and write to the BAM activities.</span></span>  

- <span data-ttu-id="f7902-113">サーバーおよびクライアント アプリケーションの App.config ファイルを、BAM 追跡サービスを読み込むように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-113">The App.config file for the server and client application must be modified to load the BAM tracking service.</span></span> <span data-ttu-id="f7902-114">App.config ファイルの変更後にアプリケーションを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-114">After the App.config file has been modified, the application must be restarted.</span></span>  

  <span data-ttu-id="f7902-115">これらのタスクを正常に完了した後にのみ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM データベースにイベントが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7902-115">Only after these tasks have been successfully completed will events begin appearing in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM database.</span></span>  

### <a name="deploying-an-observation-model"></a><span data-ttu-id="f7902-116">監視モデルの展開</span><span class="sxs-lookup"><span data-stu-id="f7902-116">Deploying an Observation Model</span></span>  
 <span data-ttu-id="f7902-117">アプリケーション内でインターセプター構成ファイルを展開したり、BAM アクティビティを取得したりするには、監視モデルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-117">You must have an observation model deployed before you can deploy an interceptor configuration file or capture BAM activities in your application.</span></span>  

##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a><span data-ttu-id="f7902-118">bm.exe を使用して監視モデルを展開するには</span><span class="sxs-lookup"><span data-stu-id="f7902-118">To deploy an observation model by using bm.exe</span></span>  

1. <span data-ttu-id="f7902-119">をクリックして**開始**順にクリックします**実行**Windows のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7902-119">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  

2. <span data-ttu-id="f7902-120">型**cmd**で、**オープン**フィールドをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f7902-120">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  

3. <span data-ttu-id="f7902-121">ディレクトリ変更のコマンドを使用して、展開する監視モデルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7902-121">Use the change directory command to move to the directory containing the observation model to deploy.</span></span> <span data-ttu-id="f7902-122">たとえば、 **cd c:\businessprocess\Orders**します。</span><span class="sxs-lookup"><span data-stu-id="f7902-122">For example, **cd c:\businessprocess\Orders**.</span></span>  

4. <span data-ttu-id="f7902-123">bm.exe を使用して次のように監視モデルを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7902-123">Deploy the observation model using bm.exe:</span></span>  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f7902-124">Tracking\bm.exe 展開すべて-definitionfile:\<*definitionfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="f7902-124">Tracking\bm.exe deploy-all -Definitionfile:\<*definitionfile.xml*\></span></span>  

    <span data-ttu-id="f7902-125">置換するかどうかを確認\< *definitionfile.xml* \>に展開する監視モデル ファイルの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f7902-125">Make sure you replace \<*definitionfile.xml*\> with the name of the observation model file you want to deploy.</span></span> <span data-ttu-id="f7902-126">オプションの詳細についてを参照してください。[インターセプター管理コマンド](../core/interceptor-management-commands.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7902-126">For more options see [Interceptor Management Commands](../core/interceptor-management-commands.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f7902-127">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  

5. <span data-ttu-id="f7902-128">型**終了**し、enter キーを押してコマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f7902-128">Type **Exit** and then press ENTER to close the command prompt.</span></span>  

### <a name="deploying-an-interceptor-configuration-file"></a><span data-ttu-id="f7902-129">インターセプター構成ファイルの展開</span><span class="sxs-lookup"><span data-stu-id="f7902-129">Deploying an Interceptor Configuration File</span></span>  
 <span data-ttu-id="f7902-130">アプリケーションで BAM アクティビティを取得できるようにするには、インターセプター構成ファイルを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-130">You must deploy an interceptor configuration file before your application will be able to capture BAM activities.</span></span>  

##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a><span data-ttu-id="f7902-131">bm.exe を使用してインターセプター構成ファイルを展開するには</span><span class="sxs-lookup"><span data-stu-id="f7902-131">To deploy an interceptor configuration file by using bm.exe</span></span>  

1. <span data-ttu-id="f7902-132">をクリックして**開始**順にクリックします**実行**Windows のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7902-132">Click **Start** and then click **Run** to open the Windows command prompt.</span></span>  

2. <span data-ttu-id="f7902-133">型**cmd**で、**オープン**フィールドをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f7902-133">Type **cmd** in the **Open** field, and then click **OK**.</span></span>  

3. <span data-ttu-id="f7902-134">ディレクトリ変更のコマンドを使用して、展開するインターセプター構成ファイルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7902-134">Use the change directory command to move to the directory containing the interceptor configuration file to deploy.</span></span> <span data-ttu-id="f7902-135">たとえば、 **cd c:\businessprocess\Orders**します。</span><span class="sxs-lookup"><span data-stu-id="f7902-135">For example, **cd c:\businessprocess\Orders**.</span></span>  

4. <span data-ttu-id="f7902-136">bm.exe を使用して、次のようにインターセプター構成ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7902-136">Deploy the interceptor configuration file by using bm.exe:</span></span>  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="f7902-137">Tracking\bm.exe デプロイ インターセプター-filename:\<*icfile.xml*\></span><span class="sxs-lookup"><span data-stu-id="f7902-137">Tracking\bm.exe deploy-interceptor -Filename:\<*icfile.xml*\></span></span>  

    <span data-ttu-id="f7902-138">置換するかどうかを確認\< *icfile.xml* \>に展開するインターセプター構成ファイルの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f7902-138">Make sure you replace \<*icfile.xml*\> with the name of the interceptor configuration file you want to deploy.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f7902-139">使用することができます、 **-Force:true**インターセプタ構成ファイル内のものと同じ名前の既存のイベント ソースを上書きするフラグ。</span><span class="sxs-lookup"><span data-stu-id="f7902-139">You can use the **-Force:True** flag to override existing event sources with the same name(s) as those in your interceptor configuration file.</span></span> <span data-ttu-id="f7902-140">これを行う場合を使用して、既存の構成をバックアップすることを確認、 **get インターセプター**コマンド。</span><span class="sxs-lookup"><span data-stu-id="f7902-140">If you do so, make sure you back up the existing configuration by using the **get-interceptor** command.</span></span> <span data-ttu-id="f7902-141">–Force:True フラグを使用すると、上書きされるイベント ソースを参照するインターセプター構成が削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-141">Using the -Force:True flag could delete any interceptor configurations that reference the event sources being overwritten.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f7902-142">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-142">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  

5. <span data-ttu-id="f7902-143">型**終了**し、enter キーを押してコマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f7902-143">Type **Exit** and then press ENTER to close the command prompt.</span></span>  

   <span data-ttu-id="f7902-144">[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションを既に展開している場合は、次のポーリング間隔まで新しい構成が読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="f7902-144">If you have already deployed your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application, the new configuration will not be loaded until the next polling interval.</span></span> <span data-ttu-id="f7902-145">ただし、アプリケーションを構成して再起動すると、構成はすぐに取得されます。</span><span class="sxs-lookup"><span data-stu-id="f7902-145">However, if you configure your application and restart it, the configuration will be picked up immediately.</span></span>  

### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a><span data-ttu-id="f7902-146">適切な BAM アクティビティ ロールへのユーザーの追加</span><span class="sxs-lookup"><span data-stu-id="f7902-146">Adding the User to the Appropriate BAM Activity Role</span></span>  
 <span data-ttu-id="f7902-147">BAM インターセプター フレームワークでは、アクティビティごとの SQL Server ロールを使用して、アクティビティ情報および構成情報へのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="f7902-147">The BAM Interceptor Framework uses per-activity SQL Server roles to control access to activities and configuration information.</span></span> <span data-ttu-id="f7902-148">WCF アプリケーションを実行するユーザー アカウントを、BAMPrimaryImport データベースの適切な BAM アクティビティ ロールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-148">You must add the user account running your WCF application to the appropriate BAM activity role(s) in the BAMPrimaryImport database.</span></span>  

### <a name="configuring-the-windows-communication-foundation-application-to-load-the-bam-tracking-service"></a><span data-ttu-id="f7902-149">BAM 追跡サービスを読み込むための Windows Communication Foundation アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="f7902-149">Configuring the Windows Communication Foundation Application to Load the BAM Tracking Service</span></span>  
 <span data-ttu-id="f7902-150">BAM 追跡サービスを読み込むようにアプリケーションを構成するには、サーバーまたはクライアント アプリケーションの App.config ファイルにいくつかの行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f7902-150">You configure your application to load the BAM tracking service by adding a few lines to the App.config file for your server or client application.</span></span>  

 <span data-ttu-id="f7902-151">[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] のサーバーまたはクライアント アプリケーションで BAM の追跡を有効にするには、追加のエンドポイント動作と動作拡張機能を含むように App.config 構成ファイルを変更し、動作構成属性を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-151">To enable BAM tracking in your [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] server or client application, you will need to modify the App.config configuration file to include an additional endpoint behavior and behavior extension and add a behavior configuration attribute.</span></span> <span data-ttu-id="f7902-152">サービス テンプレートとクライアント テンプレートの形式はほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="f7902-152">The formats of the service and client templates are similar.</span></span>  

 <span data-ttu-id="f7902-153">[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションを構成する際は、次のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7902-153">When configuring the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] application, note the following.</span></span> <span data-ttu-id="f7902-154">同じアプリケーション (同じクライアントまたはサービス) の App.config に複数の BAM エンドポイント動作が定義されている場合、BAM では次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="f7902-154">If there is more than one BAM endpoint behaviors defined in the App.config for the same application, that is, the same client or service, BAM will take the following actions.</span></span>  

-   <span data-ttu-id="f7902-155">接続文字列が異なる場合は、例外を生成します。</span><span class="sxs-lookup"><span data-stu-id="f7902-155">If the connection strings differ, BAM will raise and exception.</span></span>  

-   <span data-ttu-id="f7902-156">ポーリング間隔のみが異なる場合は、いずれかを選択して処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="f7902-156">If only the polling interval differs, BAM will select one and move on.</span></span> <span data-ttu-id="f7902-157">どちらを選択するかをデザイン時に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f7902-157">It is not possible at design time to determine which one will be selected.</span></span>  

> [!NOTE]
>  <span data-ttu-id="f7902-158">接続文字列が同じである (同じコンピューターを参照している) 場合、BAM の処理は通常どおりに実行されます。</span><span class="sxs-lookup"><span data-stu-id="f7902-158">If the connection strings are the same, meaning that they reference the same computer, BAM processing will proceed normally.</span></span>  

 <span data-ttu-id="f7902-159">[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サーバー アプリケーション用に構成された App.config テンプレートの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f7902-159">The following sample App.config template is configured for a [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] server application.</span></span> <span data-ttu-id="f7902-160">これは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] インターセプターを使用するように構成されたカスタム動作 "bamEndpointBehavior" を使用するエンドポイントを定義しています。</span><span class="sxs-lookup"><span data-stu-id="f7902-160">It defines an endpoint that uses a custom behavior "bamEndpointBehavior" that is configured to use the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] interceptor.</span></span>  

```  
<system.serviceModel>  
  <services>  
    <service name="Service.CreditCardAuthorization">  
      <!-- The endpoint will use the "bamEndpointBehavior" -->   
      <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
    </service>  
  </services>  
  <bindings>  
    <wsDualHttpBinding>  
      <binding name="wsDualHttpBinding_ICreditCardAuthorization" transactionFlow="true" />  
    </wsDualHttpBinding>  
  </bindings>  
  <behaviors>  
    <endpointBehaviors>  
      <!-- Define a new behavior named "bamEndpointBehavior" -->  
      <behavior name="bamEndpointBehavior">  
        <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <extensions>  
    <behaviorExtensions>  
      <!-- Define a new enpoint behavior extension using WCF interceptor -->  
      <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </behaviorExtensions>  
  </extensions>  
</system.serviceModel>  
```  

 <span data-ttu-id="f7902-161">このテンプレートを実際の App.config で使用する前に、小さな変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-161">You will need to make small changes to this template before using it in your own App.config file.</span></span>  

##### <a name="to-use-this-template-in-your-wcf-service-appconfig-file"></a><span data-ttu-id="f7902-162">このテンプレートを WCF サービスの App.config ファイルで使用するには</span><span class="sxs-lookup"><span data-stu-id="f7902-162">To use this template in your WCF service App.config file</span></span>  

1. <span data-ttu-id="f7902-163">アプリケーションに関連付けられている App.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7902-163">Open the App.config file associated with your application.</span></span> <span data-ttu-id="f7902-164">これには、Notepad.exe またはその他のテキスト エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7902-164">You can use Notepad.exe or another text editor for this task.</span></span>  

2. <span data-ttu-id="f7902-165">次の XML を使用して、BamEndpointBehavior の [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 動作拡張機能を `extensions` 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="f7902-165">Add the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] BamEndpointBehavior behavior extension to the `extensions` element by using the following XML:</span></span>  

   ```  
   <behaviorExtensions>  
     <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
   </behaviorExtensions>  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="f7902-166">動作拡張機能の名前は "BamEndpointBehaviorExtension" になりますが、必要であれば環境に合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="f7902-166">The behavior extension is named "BamEndpointBehaviorExtension" and can be changed as needed to suit your environment.</span></span>  

3. <span data-ttu-id="f7902-167">次の XML を使用して、この新しい動作拡張機能を使用する新しいエンドポイント動作を `behaviors` 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="f7902-167">Add a new endpoint behavior that uses the new behavior extension to the `behaviors` element by using the following XML.</span></span> <span data-ttu-id="f7902-168">この動作拡張機能で、接続文字列とポーリング間隔 (秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7902-168">The behavior extension provides a connection string and polling interval in seconds.</span></span>  

   ```  
   <endpointBehaviors>  
     <behavior name="bamEndpointBehavior">  
       <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
     </behavior>  
   </endpointBehaviors>  
   ```  

    <span data-ttu-id="f7902-169">データ ソースは、使用している環境の BamPrimaryImport データベースをホストするコンピューターの名前に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="f7902-169">Replace the Data Source with the name of the computer hosting the BamPrimaryImport database in your environment.</span></span> <span data-ttu-id="f7902-170">ポーリング間隔は、要件に合わせて変更できます。値が大きいほど、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] インターセプターが構成の変更を検出するまでの時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="f7902-170">Change the polling interval to suit your requirements; a higher number means that the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] interceptor will take longer to detect configuration changes.</span></span> <span data-ttu-id="f7902-171">動作拡張機能の名前を変更している場合は、"BamEndpointBehaviorExtension" の代わりにその名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7902-171">If you changed the name of the behavior extension, use it to replace "BamEndpointBehaviorExtension".</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f7902-172">動作名は "BamEndpointBehavior" ですが、環境に合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="f7902-172">The behavior name is "bamEndpointBehavior" and can be changed to suit your environment.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f7902-173">`ConnectionString` を指定するときに、クリアテキストのユーザー名/パスワードの組み合わせを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f7902-173">Avoid using a cleartext username/password combination when specifying `ConnectionString`.</span></span> <span data-ttu-id="f7902-174">使用すると、データベース サーバーが危険にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-174">Doing so may compromise your database server.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f7902-175">`PollingIntervalSec` には、5 (秒) 以上の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7902-175">You must specify an `PollingIntervalSec` greater than or equal to 5 (seconds).</span></span> <span data-ttu-id="f7902-176">これより未満の値を指定した場合や `PollingIntervalSec` 要素を指定しなかった場合は、エラーが発生し、傍受が構成されません。</span><span class="sxs-lookup"><span data-stu-id="f7902-176">If you specify a lower value or omit the `PollingIntervalSec` element, an error will be raised and interception will not be configured.</span></span>  

4. <span data-ttu-id="f7902-177">追跡するエンドポイントに `behaviorConfiguration` 属性を追加し、新しい動作の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7902-177">Add the `behaviorConfiguration` attribute to the endpoint you will be tracking and provide the name of the new behavior:</span></span>  

   ```  
   <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="f7902-178">別の動作名を使用している場合は、その名前を代わりに使用してください。</span><span class="sxs-lookup"><span data-stu-id="f7902-178">If you used a different behavior name, supply it instead.</span></span>  

    <span data-ttu-id="f7902-179">この動作構成は複数のエンドポイントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="f7902-179">You can apply the behavior configuration to multiple endpoints.</span></span>  

5. <span data-ttu-id="f7902-180">変更した App.config ファイルを保存し、アプリケーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f7902-180">Save the modified App.config file and restart your application.</span></span>

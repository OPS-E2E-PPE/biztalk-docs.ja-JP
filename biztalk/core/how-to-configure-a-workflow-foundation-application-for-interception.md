---
title: "傍受のため、Workflow Foundation アプリケーションを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c82e83f-9dbd-4325-9f30-778eba892296
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70afa4ffae47abf5cdd541846831b4054414eff8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-workflow-foundation-application-for-interception"></a>傍受のために Workflow Foundation アプリケーションを構成する方法
BAM アクティビティ データの収集を開始するには、まず、BAM インターセプター ソフトウェアをインストールし、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] インターセプターを使用するようにアプリケーションを構成する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] およびその依存関係がインストールされ、BizTalk グループが少なくとも 1 つ作成されていることを前提とします。  
  
## <a name="installing-the-bam-eventing-software"></a>BAM イベント ソフトウェアのインストール  
 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 用の BAM インターセプターを使用するように [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションを構成するには、まず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] セットアップ プログラムを使用して BAM イベント ソフトウェアをインストールする必要があります。 BAM イベント ソフトウェアをインストールして、パフォーマンス カウンターの登録に関する詳細については、次を参照してください。 [BAM イベント ソフトウェアをインストールする](../core/installing-the-bam-eventing-software.md)です。  
  
## <a name="configuring-a-windows-workflow-foundation-application-for-tracking"></a>追跡のために Windows Workflow Foundation アプリケーションを構成する方法  
 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションで BAM イベント情報の書き込みを開始するには、次の 4 つのタスクを完了する必要があります。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BAM ツールを使用して監視モデルを作成し、BAM マネージャーのコマンド ライン ツール (bm.exe) を使用して、それを展開する必要があります。  
  
-   BAM マネージャーのコマンド ライン ツール (bm.exe) を使用して、インターセプター構成ファイルを作成する必要があります。  
  
-   ホスト アプリケーションを実行しているユーザーは、適切な BAM アクティビティ イベント ライターのメンバーである必要があります (bam _\<アクティビティ\>_EventWriter) SQL サーバーの役割、インターセプタ構成情報の読み取りし、書き込みをアプリケーションを有効にするにはBAM アクティビティ。  
  
-   BAM 追跡サービスを読み込むには、App.config ファイルまたはアプリケーション自体を変更してから、アプリケーションを再起動する必要があります。  
  
 これらのタスクを正常に完了した後にのみ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM データベースにイベントが表示されるようになります。  
  
### <a name="deploying-an-observation-model"></a>監視モデルの展開  
 アプリケーション内でインターセプター構成ファイルを展開したり、BAM アクティビティを取得したりするには、監視モデルを展開する必要があります。  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a>bm.exe を使用して監視モデルを展開するには  
  
1.  をクリックして**開始** をクリックし、**実行**Windows コマンド プロンプトを開きます。  
  
2.  型**cmd**で、**開く**フィールドをクリックして**[ok]**です。  
  
3.  ディレクトリ変更のコマンドを使用して、展開する監視モデルが格納されているディレクトリに移動します。 たとえば、 **cd c:\businessprocess\Orders**です。  
  
4.  bm.exe を使用して、次のように監視モデルを展開します。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\BM.exe 展開すべて-definitionfile:\<*definitionfile.xml*\>  
  
     置換するかどうかを確認\< *definitionfile.xml* \>を展開する監視ファイルの名前に置き換えます。 詳細については、次を参照してください。[インターセプター管理コマンド](../core/interceptor-management-commands.md)です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5.  型**終了**、し、enter キーを押してコマンド プロンプトを閉じます。  
  
### <a name="deploying-an-interceptor-configuration-file"></a>インターセプター構成ファイルの展開  
 アプリケーションで BAM アクティビティを取得するには、インターセプター構成ファイルを展開する必要があります。  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a>bm.exe を使用してインターセプター構成ファイルを展開するには  
  
1.  をクリックして**開始** をクリックし、**実行**Windows コマンド プロンプトを開きます。  
  
2.  型**cmd**で、**開く**フィールドをクリックして**[ok]**です。  
  
3.  ディレクトリ変更のコマンドを使用して、展開するインターセプター構成ファイルが格納されているディレクトリに移動します。 たとえば、 **cd c:\businessprocess\Orders**です。  
  
4.  bm.exe を使用して、次のようにインターセプター構成ファイルを展開します。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\BM.exe 展開インターセプター-filename:\<*icfile.xml*\>  
  
     置換するかどうかを確認\< *icfile.xml* \>を展開するインターセプター構成ファイルの名前に置き換えます。  
  
    > [!NOTE]
    >  使用することができます、 **-Force:true**インターセプタ構成ファイル内のものと同じ名前の既存のイベント ソースを上書きするフラグ。 これを行う場合を使用して、既存の構成をバックアップすることを確認、 **get インターセプター**コマンド。 –Force:True フラグを使用すると、上書きされるイベント ソースを参照するインターセプター構成が削除される可能性があります。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5.  型**終了**、し、enter キーを押してコマンド プロンプトを閉じます。  
  
 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションを既に展開している場合は、次のポーリング間隔まで新しい構成が読み込まれません。 ただし、アプリケーションを構成して再起動すると、構成はすぐに取得されます。  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a>適切な BAM アクティビティ ロールへのユーザーの追加  
 BAM インターセプター フレームワークでは、アクティビティごとの SQL Server ロールを使用して、アクティビティ情報および構成情報へのアクセスを制御します。 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションを実行するユーザー アカウントを、BAM プライマリ インポート データベースの適切な BAM アクティビティ ロールに追加する必要があります。  
  
### <a name="configuring-the-application-to-load-the-bam-tracking-service"></a>BAM 追跡サービスを読み込むためのアプリケーションの構成  
 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションで BAM 追跡サービスを読み込むためのシナリオは 3 つあります。  
  
-   [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションで、既に WorkflowRuntime を使用して [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 構成セクションを読み込んでいる場合は、BAM 追跡サービス情報を既存のセクションに追加できます。  
  
-   [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションで、WorkflowRuntime を使用して [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] 構成セクションを読み込んでいない場合は、コードを追加して、アプリケーション構成ファイルからカスタム セクションを読み込む必要があります。 セクションを作成し、BAM 追跡サービス情報をそれに追加する必要があります。  
  
-   構成をハードコーディングするには、[!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] API を使用し、構成ファイルを使わずに、プログラムによって追跡サービスを読み込むか、カスタム ソースから構成を読み込むことができます。  
  
 [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] アプリケーションの構成時には、次のことを考慮してください。  
  
-   [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] インターセプターでは、WorkflowRuntime ごとに BamTrackingService が 1 つだけサポートされます。  
  
-   [!INCLUDE[nextref_btsWinWorkflowFoundation](../includes/nextref-btswinworkflowfoundation-md.md)] インターセプターでは、アプリケーション ドメインごとに複数の BamTrackingService がサポートされます。  
  
    -   N 個の WorkflowRuntime に対して N 個の BamTrackingService がサポートされます。  
  
-   同じアプリケーション ドメイン内の異なる BamTrackingService インスタンスに異なる接続文字列が使用されると、インターセプターでは例外が発行されます。  
  
-   インターセプターは、開始された最初の BamTrackingService インスタンスから IC ポーリング間隔値を取得します。  
  
-   アプリケーション ドメインで最後の BamTrackingService が停止すると、インターセプターは IC ポーリング スレッドを停止します。  
  
 WorkflowRuntime、および構成情報の読み込みの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=83314](http://go.microsoft.com/fwlink/?LinkId=83314)です。  
  
##### <a name="to-configure-the-appconfig-file-for-the-bam-tracking-service"></a>BAM 追跡サービスのために App.config ファイルを構成するには  
  
1.  アプリケーションに関連付けられている App.config ファイルを開きます。 これには、Notepad.exe またはその他のテキスト エディターを使用できます。  
  
2.  App.config ファイルに次の構成情報を挿入して、BAM 追跡サービスを追加します。 この情報は、`configuration` 要素の子となるように配置する必要があります。  
  
    > [!NOTE]
    >  セクション要素は、WorkflowRuntime クラスを使用する際に、アプリケーション コードで使用する名前に対応する必要があります。  
  
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
  
3.  変更、 **ConnectionString**環境に合わせて属性。  
  
4.  アプリケーションを再起動します。  
  
##### <a name="to-modify-your-application-to-load-a-custom-configuration-section"></a>カスタム構成セクションを読み込むようにアプリケーションを変更するには  
  
1.  Visual Studio で Windows Workflow Foundation プロジェクトを開きます。  
  
2.  適切なパラメーターを設定した BamTrackingService の新しいインスタンスを、アプリケーションの WorkflowRuntime インスタンスに追加します。  
  
    ```  
    // !! Replace "WorkflowServiceContainer" with the section name  
    // you used in your App.config file.  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime("WorkflowServiceContainer");  
    ```  
  
3.  変更されたアプリケーションを再コンパイルして展開します。  
  
##### <a name="to-modify-your-application-to-programmatically-load-the-bam-tracking-service"></a>アプリケーションを変更して、BAM 追跡サービスをプログラムによって読み込むには  
  
1.  Visual Studio で Windows Workflow Foundation プロジェクトを開きます。  
  
2.  適切なパラメーターを設定した BamTrackingService の新しいインスタンスを、アプリケーションの WorkflowRuntime インスタンスに追加します。  
  
    ```  
    string connectionString = "Integrated Security=SSPI;Data Source=.;Initial Catalog=BAMPrimaryImport"  
    int pollingInterval = 5;  
    WorkflowRuntime workflowRuntime = new WorkflowRuntime();  
    workflowRuntime.AddService(new BamTrackingService(connectionString, pollingInterval));  
    ```  
  
     パラメーターは、特定の環境に基づいて追加または削除できます。  
  
3.  変更されたアプリケーションを再コンパイルして展開します。
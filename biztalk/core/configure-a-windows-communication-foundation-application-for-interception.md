---
title: "傍受のための Windows Communication Foundation アプリケーションを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37f2ccde-aa79-470a-ac31-57e4168dc54a
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 103eb58223ba4acd61d909640bacda76d08efe8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-windows-communication-foundation-application-for-interception"></a>傍受のために Windows Communication Foundation アプリケーションを構成する方法
BAM アクティビティ データの収集を開始するには、まず BAM インターセプター ソフトウェアをインストールし、BAM [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] インターセプターを使用するようにアプリケーションを構成する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] およびその依存関係がインストールされ、BizTalk グループが少なくとも 1 つ作成されていることを前提とします。  
  
## <a name="installing-the-bam-eventing-software"></a>BAM イベント ソフトウェアのインストール  
 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 用の BAM インターセプターを使用するように [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションを構成するには、まず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] セットアップ プログラムを使用して BAM イベント ソフトウェアをインストールする必要があります。 BAM イベント ソフトウェアをインストールして、パフォーマンス カウンターの登録に関する詳細については、次を参照してください。 [BAM イベント ソフトウェアをインストールする](../core/installing-the-bam-eventing-software.md)です。  
  
## <a name="configuring-a-wcf-application-for-tracking"></a>追跡のための WCF アプリケーションの構成  
 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションで BAM イベント情報の書き込みを開始するには、次の 4 つのタスクを完了する必要があります。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM ツールを使用して監視モデルを作成し、BAM マネージャーのコマンド ライン ツール (bm.exe) を使用してそれを展開する必要があります。  
  
-   BAM マネージャーのコマンド ライン ツール (bm.exe) を使用してインターセプター構成ファイルを作成する必要があります。  
  
-   ホスト アプリケーションを実行しているユーザーは、適切な BAM アクティビティ イベント ライターのメンバーである必要があります (bam _\<アクティビティ > _EventWriter) SQL サーバーの役割、インターセプタ構成情報の読み取りと書き込み、BAM にアプリケーションを有効にするにはアクティビティ。  
  
-   サーバーおよびクライアント アプリケーションの App.config ファイルを、BAM 追跡サービスを読み込むように変更する必要があります。 App.config ファイルの変更後にアプリケーションを再起動する必要があります。  
  
 これらのタスクを正常に完了した後にのみ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM データベースにイベントが表示されるようになります。  
  
### <a name="deploying-an-observation-model"></a>監視モデルの展開  
 アプリケーション内でインターセプター構成ファイルを展開したり、BAM アクティビティを取得したりするには、監視モデルを展開する必要があります。  
  
##### <a name="to-deploy-an-observation-model-by-using-bmexe"></a>bm.exe を使用して監視モデルを展開するには  
  
1.  をクリックして**開始** をクリックし、**実行**Windows コマンド プロンプトを開きます。  
  
2.  型**cmd**で、**開く**フィールドをクリックして**[ok]**です。  
  
3.  ディレクトリ変更のコマンドを使用して、展開する監視モデルが格納されているディレクトリに移動します。 たとえば、 **cd c:\businessprocess\Orders**です。  
  
4.  bm.exe を使用して次のように監視モデルを展開します。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm.exe 展開すべて-definitionfile:\<*definitionfile.xml*>  
  
     置換するかどうかを確認\< *definitionfile.xml*> を展開する監視モデル ファイルの名前に置き換えます。 詳細については、次を参照してください。[インターセプター管理コマンド](../core/interceptor-management-commands.md)です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5.  型**終了**し、enter キーを押してコマンド プロンプトを閉じます。  
  
### <a name="deploying-an-interceptor-configuration-file"></a>インターセプター構成ファイルの展開  
 アプリケーションで BAM アクティビティを取得できるようにするには、インターセプター構成ファイルを展開する必要があります。  
  
##### <a name="to-deploy-an-interceptor-configuration-file-by-using-bmexe"></a>bm.exe を使用してインターセプター構成ファイルを展開するには  
  
1.  をクリックして**開始** をクリックし、**実行**Windows コマンド プロンプトを開きます。  
  
2.  型**cmd**で、**開く**フィールドをクリックして**[ok]**です。  
  
3.  ディレクトリ変更のコマンドを使用して、展開するインターセプター構成ファイルが格納されているディレクトリに移動します。 たとえば、 **cd c:\businessprocess\Orders**です。  
  
4.  bm.exe を使用して、次のようにインターセプター構成ファイルを展開します。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm.exe 展開インターセプター-filename:\<*icfile.xml*>  
  
     置換するかどうかを確認\< *icfile.xml*> を展開するインターセプター構成ファイルの名前に置き換えます。  
  
    > [!NOTE]
    >  使用することができます、 **-Force:true**インターセプタ構成ファイル内のものと同じ名前の既存のイベント ソースを上書きするフラグ。 これを行う場合を使用して、既存の構成をバックアップすることを確認、 **get インターセプター**コマンド。 –Force:True フラグを使用すると、上書きされるイベント ソースを参照するインターセプター構成が削除される可能性があります。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5.  型**終了**し、enter キーを押してコマンド プロンプトを閉じます。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションを既に展開している場合は、次のポーリング間隔まで新しい構成が読み込まれません。 ただし、アプリケーションを構成して再起動すると、構成はすぐに取得されます。  
  
### <a name="adding-the-user-to-the-appropriate-bam-activity-role"></a>適切な BAM アクティビティ ロールへのユーザーの追加  
 BAM インターセプター フレームワークでは、アクティビティごとの SQL Server ロールを使用して、アクティビティ情報および構成情報へのアクセスを制御します。 WCF アプリケーションを実行するユーザー アカウントを、BAMPrimaryImport データベースの適切な BAM アクティビティ ロールに追加する必要があります。  
  
### <a name="configuring-the-windows-communication-foundation-application-to-load-the-bam-tracking-service"></a>BAM 追跡サービスを読み込むための Windows Communication Foundation アプリケーションの構成  
 BAM 追跡サービスを読み込むようにアプリケーションを構成するには、サーバーまたはクライアント アプリケーションの App.config ファイルにいくつかの行を追加します。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] のサーバーまたはクライアント アプリケーションで BAM の追跡を有効にするには、追加のエンドポイント動作と動作拡張機能を含むように App.config 構成ファイルを変更し、動作構成属性を追加する必要があります。 サービス テンプレートとクライアント テンプレートの形式はほぼ同じです。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] アプリケーションを構成する際は、次のことに注意してください。 同じアプリケーション (同じクライアントまたはサービス) の App.config に複数の BAM エンドポイント動作が定義されている場合、BAM では次の処理が行われます。  
  
-   接続文字列が異なる場合は、例外を生成します。  
  
-   ポーリング間隔のみが異なる場合は、いずれかを選択して処理を続行します。 どちらを選択するかをデザイン時に指定することはできません。  
  
> [!NOTE]
>  接続文字列が同じである (同じコンピューターを参照している) 場合、BAM の処理は通常どおりに実行されます。  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] サーバー アプリケーション用に構成された App.config テンプレートの例を次に示します。 これは、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] インターセプターを使用するように構成されたカスタム動作 "bamEndpointBehavior" を使用するエンドポイントを定義しています。  
  
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
  
 このテンプレートを実際の App.config で使用する前に、小さな変更を加える必要があります。  
  
##### <a name="to-use-this-template-in-your-wcf-service-appconfig-file"></a>このテンプレートを WCF サービスの App.config ファイルで使用するには  
  
1.  アプリケーションに関連付けられている App.config ファイルを開きます。 これには、Notepad.exe またはその他のテキスト エディターを使用できます。  
  
2.  次の XML を使用して、BamEndpointBehavior の [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 動作拡張機能を `extensions` 要素に追加します。  
  
    ```  
    <behaviorExtensions>  
      <add name="BamEndpointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </behaviorExtensions>  
    ```  
  
    > [!NOTE]
    >  動作拡張機能の名前は "BamEndpointBehaviorExtension" になりますが、必要であれば環境に合わせて変更できます。  
  
3.  次の XML を使用して、この新しい動作拡張機能を使用する新しいエンドポイント動作を `behaviors` 要素に追加します。 この動作拡張機能で、接続文字列とポーリング間隔 (秒単位) を指定します。  
  
    ```  
    <endpointBehaviors>  
      <behavior name="bamEndpointBehavior">  
        <BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" InterceptorConfigurationPollingInterval="1500" />  
      </behavior>  
    </endpointBehaviors>  
    ```  
  
     データ ソースは、使用している環境の BamPrimaryImport データベースをホストするコンピューターの名前に置き換えてください。 ポーリング間隔は、要件に合わせて変更できます。値が大きいほど、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] インターセプターが構成の変更を検出するまでの時間が長くなります。 動作拡張機能の名前を変更している場合は、"BamEndpointBehaviorExtension" の代わりにその名前を使用します。  
  
    > [!NOTE]
    >  動作名は "BamEndpointBehavior" ですが、環境に合わせて変更できます。  
  
    > [!NOTE]
    >  `ConnectionString` を指定するときに、クリアテキストのユーザー名/パスワードの組み合わせを使用しないでください。 使用すると、データベース サーバーが危険にさらされる可能性があります。  
  
    > [!NOTE]
    >  `PollingIntervalSec` には、5 (秒) 以上の値を指定する必要があります。 これより未満の値を指定した場合や `PollingIntervalSec` 要素を指定しなかった場合は、エラーが発生し、傍受が構成されません。  
  
4.  追跡するエンドポイントに `behaviorConfiguration` 属性を追加し、新しい動作の名前を指定します。  
  
    ```  
    <endpoint address="http://localhost:8081/CreditCardService" contract="Service.ICreditCardAuthorization" name="CreditCardEndPoint" binding ="wsDualHttpBinding" bindingConfiguration="wsDualHttpBinding_ICreditCardAuthorization" behaviorConfiguration="bamEndpointBehavior"/>  
    ```  
  
    > [!NOTE]
    >  別の動作名を使用している場合は、その名前を代わりに使用してください。  
  
     この動作構成は複数のエンドポイントに適用できます。  
  
5.  変更した App.config ファイルを保存し、アプリケーションを再起動します。
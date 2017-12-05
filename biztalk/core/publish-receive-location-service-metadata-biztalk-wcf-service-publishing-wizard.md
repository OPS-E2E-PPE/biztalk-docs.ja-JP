---
title: "BizTalk WCF サービス公開ウィザードを使用して、WCF 受信場所用にサービス メタデータを公開する方法は、オーケストレーション ポートにバインドされている |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, orchestration ports
- WCF services, metadata
- orchestrations, WCF services
ms.assetid: 04ccce9f-8d18-433a-8299-d06fa155db06
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dce9a66465285dc16f8de804c7a6e99fa7e62a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-bound-to-an-orchestration-port"></a>BizTalk WCF サービス公開ウィザードを使用してオーケストレーション ポートにバインドされた WCF 受信場所にサービス メタデータを公開する方法
WCF サービスを作成して、オーケストレーション ポートにバインドされた既存の WCF 受信場所にサービス メタデータを公開するには、BizTalk WCF サービス公開ウィザードを使用します。  
  
> [!NOTE]
>  BizTalk WCF サービス公開ウィザードを実行する前に、BizTalk プロジェクトを作成する必要があります。 BizTalk プロジェクトには、型修飾子がパブリックである受信ポートを 1 つ以上持つオーケストレーションが含まれている必要があります。 また、WCF アダプターにサービス メタデータを公開する前に、WCF 受信場所も作成する必要があります。これには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属している BizTalk 管理コンソール、または BTSTask コマンド ライン ツールを使用します。 WCF を作成する方法の詳細については、受信場所の各 WCF アダプタの該当するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)です。  
  
### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-bound-to-an-orchestration-port"></a>オーケストレーション ポートにバインドされた既存の WCF 受信場所にサービス メタデータを公開するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk WCF サービス公開ウィザード**です。  
  
    > [!NOTE]
    >  WCF サービスを作成して BizTalk のオーケストレーションおよびスキーマにメタデータを公開するには、BizTalk WCF サービス公開ウィザードを使用します。 一方、SOAP アダプターを使用してオーケストレーションとスキーマを Web サービスとして公開するには、BizTalk Web サービス公開ウィザードを使用します。  
  
2.  **BizTalk WCF サービス公開ウィザードへようこそ** ページで、をクリックして**次**です。  
  
3.  **WCF サービスの種類**] ページで、[、**メタデータのみのエンドポイント (MEX)**に wcf サービス メタデータを提供する WCF サービスを発行するオプションを受信場所は、次の手順で選択します。  
  
     ![WCF サービスの種類ページ](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")  
  
4.  **WCF サービスの種類** ページの 、**受信場所のメタデータを公開**ドロップダウン リストでは、wcf 受信場所で、サービス メタデータを公開し、をクリックする**次へ**.  
  
5.  **WCF サービスの作成**] ページで、[ **BizTalk オーケストレーションの WCF サービスとして発行**、クリックして**[次へ]**です。  
  
     ![WCF サービス ページを作成する](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")  
  
6.  **BizTalk アセンブリ**] ページの [、 **BizTalk アセンブリ ファイル (\*.dll)**テキスト ボックスで、BizTalk アセンブリ ファイルの名前を入力またはクリックして**参照**を参照するにはクリックして、サービス メタデータを公開するオーケストレーションを含むアセンブリ**次**です。  
  
    > [!NOTE]
    >  BizTalk アセンブリ ファイルを選択する前にすべての依存アセンブリを BizTalk アセンブリと同じフォルダーにコピーまたはグローバル アセンブリ キャッシュ (GAC) に依存アセンブリをインストールします。  
  
    > [!NOTE]
    >  BizTalk アセンブリ ファイルを GAC にインストールする場合はで選択するアセンブリに GAC にアセンブリが更新されたことを確認してください、 **BizTalk アセンブリ** ダイアログ ボックス。 GAC 内のアセンブリの完全修飾名が同じである場合、BizTalk WCF サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。  
  
    > [!NOTE]
    >  パス名が 260 文字を超えると、パス名が長すぎるというエラー メッセージが表示される場合があります。  
  
     ![BizTalk アセンブリ ページ](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")  
  
7.  **オーケストレーションとポート** ページで、プラス記号 (+) をクリックして、各アセンブリおよびオーケストレーションのツリー ノードを展開します。 メタデータを公開するオーケストレーションおよびポートのツリー ノードのチェック ボックスをオンにします。 ごとに 1 つの WCF サービスではなく選択した受信ポートの受信ポートを選択、すべての 1 つの WCF サービス (.svc ファイル) を作成する場合、**選択されているすべてのポートを 1 つの WCF サービスに結合**オプションをクリックして**[次へ]**です。  
  
    > [!NOTE]
    >  選択したすべてのポートを 1 つの WCF サービスに統合すると、選択したすべてのポートの種類が同じになり、ポート内の操作名も同じになります。  
  
     ![操作とポート ページ](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")  
  
8.  **WCF サービスのプロパティ**] ページの [、 **、WCF サービスの Targetnamespace**テキスト ボックスでは、WCF サービスのターゲットの名前空間を入力し、をクリックして**次**です。  
  
     ![WCF サービスのプロパティ ページ](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
9. **WCF サービスの場所**] ページの [、**場所**テキスト ボックスに、WCF サービスが生成される Web ディレクトリ名を入力します。 既定の場所を受け入れることができます (http://localhost/ <*BizTalk アセンブリ名*>)、WCF サービスの場所を入力、**場所**テキスト ボックス、またはをクリックして**を参照**Web ディレクトリを選択します。 次のいずれかのオプションをクリックします。  
  
    -   **既存のプロジェクトを上書きします。** : このオプションは、Web ディレクトリが存在する場合のみ選択できます。 このオプションを選択すると、同じ場所にのみ公開できます。 このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。  
  
    -   **WCF サービスへの匿名アクセスを許可します。** : このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。 既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。  
  
     このページを終了したらクリックして**次**です。  
  
     ![WCF サービスの場所 ページ](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  プロジェクトの場所には、別のサーバーを指定することもできます。 WCF サービスを別のサーバーで発行するプロジェクト名を入力として http://&lt です*servername*>/<*WCF サービスの場所*>。  
  
    > [!NOTE]
    >  プロジェクトの場所には、既定以外の Web サイトを指定することもできます。 既定以外の Web サイトに公開する場合は、URL に Web サイトのポート番号を含めます。 たとえば、http://&lt*servername*>: 8080/<*WCF サービスの場所*>。  
  
    > [!NOTE]
    >  ウィザードで Web アプリケーションの App_DataTemp フォルダーに作成される BindingInfo.xml ファイルは、パイプラインの既定値を使用します。 受信パイプラインの既定値は、 **Microsoft.BizTalk.DefaultPipelines.XMLReceive**パイプライン、および既定値、送信パイプラインは、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**パイプライン。  
  
10. **WCF サービスの概要** ページで、WCF サービスの設定を確認します。  
  
11. をクリックして**作成**WCF サービスを作成します。  
  
12. をクリックして**完了**を BizTalk WCF サービス公開ウィザードを完了します。  
  
### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a>サービス メタデータを公開する Web アプリケーションを構成するには  
  
1.  BizTalk WCF サービス公開ウィザードで作成した Web アプリケーションについて ASP.NET を有効にします。 詳細については、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。  
  
    > [!NOTE]
    >  Windows Server 2008 または Windows Vista を使用している場合は、アプリケーション プールの ID アカウントを BizTalk Server 管理者グループに追加する必要があります。 該当するアカウントを BizTalk Server 管理者グループに追加した後は、IIS サービスを再起動して設定を有効にする必要があります。  
  
2.  コマンド プロンプトを開き、BizTalk WCF サービス公開ウィザードが %SystemDrive%\InetPub で WCF サービスを作成する場所のフォルダーに移動\\、メモ帳を使用して Web.config ファイルを開きます。  
  
3.  メモ帳で、内部の次の行を追加、  **\<system.web\>** 要素。  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  この設定はオプションで、公開した WCF サービスをホストする ASP.NET アプリケーションに、オペレーティング システムのセキュリティの影響下にあるリソースへのアクセス権限を与えます。 これは、公開された WCF サービスと同じコンピューターで Windows SharePoint Services がインストールおよび実行されている場合に、WCF サービスの実行に必要な信頼レベルです。  
  
4.  Internet explorer で、**アドレス**ボックス、書式 http:// を使用して、WCF サービスの URL を入力*ホスト [: ポート]*/*apppath* /*名.svc*を公開した WCF サービスをテストします。 次の表は、これらのパラメーターについてまとめたものです。  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |*ホスト [: ポート]*|WCF サービスを配置したコンピューターの名前です。 このサーバー名の後に、コロンとポート番号を入力できます。|  
    |*アプリケーションのパス*|仮想ディレクトリ名と Web アプリケーションのパスです。|  
    |*名.svc*|WCF サービスの .svc ファイルの名前です。|  
  
5.  機密性の高いサービス メタデータが誤って漏洩を防ぐためには、次のタスクを実行することによって、実稼働環境でこの動作を無効にすることをお勧めします。  
  
    1.  メモ帳で、%SystemDrive%\InetPub で、BizTalk WCF サービス公開ウィザードが、WCF サービスを作成するフォルダーの Web.config を開き\\です。  
  
    2.  メモ帳で、次のように設定します。、、 **httpGetEnabled**属性、  **\<serviceMetadata\>** 要素を、次の行と同様に false にします。  
  
        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  
  
## <a name="see-also"></a>参照  
 [BizTalk WCF サービス公開ウィザードを使用して、コンテンツ ベース ルーティングの WCF 受信場所用にサービス メタデータを公開する方法](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md)   
 [チュートリアル: WCF-NetMsmq アダプターを使用した WCF サービスの公開](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)
---
title: "BizTalk WCF サービス公開ウィザードを使用して、コンテンツ ベース ルーティングの WCF 受信場所用にサービス メタデータを公開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, metadata
ms.assetid: e900b0a0-db17-4db9-a639-54891e02d6d7
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7be81166f4f66ed79bbb0b00b5e226c9e3c2be7b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing"></a>BizTalk WCF サービス公開ウィザードを使用してコンテンツ ベース ルーティングの WCF 受信場所にサービス メタデータを公開する方法
BizTalk WCF サービス公開ウィザードを使用して WCF サービスを作成し、コンテンツベース ルーティングの既存の WCF 受信場所にメタデータを公開します。  
  
> [!NOTE]
>  BizTalk WCF サービス公開ウィザードを実行する前に、BizTalk プロジェクトを作成する必要があります。 BizTalk プロジェクトには、WCF サービスとして公開するスキーマを含める必要があります。 また、WCF アダプターにサービス メタデータを公開する前に、WCF 受信場所も作成する必要があります。これには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属している BizTalk Server 管理コンソール、または BTSTask コマンド ライン ツールを使用します。 WCF を作成する方法の詳細については、受信場所の各 WCF アダプタの該当するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)です。  
  
### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-for-content-based-routing"></a>コンテンツベース ルーティングの既存 WCF 受信場所にサービス メタデータを公開するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** 、順にクリック**BizTalk WCF サービス公開ウィザード**です。  
  
    > [!NOTE]
    >  作成し、BizTalk オーケストレーションとスキーマを WCF サービスのメタデータを公開、BizTalk WCF サービス公開ウィザードを使用します。 一方、SOAP アダプターを使用してオーケストレーションとスキーマを Web サービスとして公開するには、BizTalk Web サービス公開ウィザードを使用します。  
  
2.  **BizTalk WCF サービス公開ウィザードへようこそ** ページで、をクリックして**次**です。  
  
3.  **WCF サービスの種類**] ページで、[、**メタデータのみのエンドポイント (MEX)**に wcf サービス メタデータを提供する WCF サービスを発行するオプションを受信場所は、次の手順で選択します。  
  
     ![WCF サービスの種類ページ](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")  
  
4.  **WCF サービスの種類** ページの 、**受信場所のメタデータを公開**ドロップダウン リストでは、wcf 受信場所で、サービス メタデータを公開し、をクリックする**次へ**.  
  
5.  **WCF サービスの作成**] ページで、[**スキーマを WCF サービスとして公開**、順にクリック**次**です。  
  
     ![WCF サービス ページを作成する](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")  
  
6.  **WCF サービス**ページで、サービス メタデータを公開する WCF サービス コントラクトを定義します。 ツリーを使用する、 **Web サービスの説明**を追加、削除、名前の変更、および公開する WCF サービスの Web サービス説明ノードの編集 ダイアログ ボックス。 **情報** ダイアログ ボックスが選択したノードに関する情報を提供し、現在のノードまたはサブノードでエラーが表示されます。  
  
    -   ツリーのルート ノード (Web サービスの説明) は、公開する WCF サービス コントラクトについての説明です。 仮想ディレクトリ名では、ルート ノードが既定の名前として使用されます。 選択して公開する WCF サービスの Web サービス説明の名前を変更することができます**web サービスの説明の名前を変更**です。  
  
         ![WCF サービス ページ](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")  
  
    -   Web メソッド ノード**Operation1**、既定のサービス ノードの**Service1**、既定で表示されている、 **Web サービスの説明**のダイアログ ボックスを使用して、要求-応答の受信場所。 一方向の WCF を選択した場合はこのサービス コントラクトの受信場所が、既定の Web メソッド ノードを右クリックし、をクリックして**web メソッドの削除**、し、次のように、一方向の Web メソッドを作成します既定のサービス ノード ポイントを右クリック。**web メソッドを追加**、クリックして**一方向**です。  
  
    -   新しい WCF サービスを追加、Web サービス説明の名前を右クリックし、をクリックして**web サービスの追加**です。 これにより、WCF 操作なしの新しい WCF サービスが作成されます。 WCF サービスの名前を変更、WCF サービス ノードを右クリックし、をクリックして**web サービスの名前を変更**、し、enter キーを押して新しい名前を受け入れます。  
  
    -   新しい WCF 操作を追加するには、WCF サービス ノードを右クリックし、 をポイント**Web メソッドの追加**、順にクリック**一方向**(要求 WCF 操作の場合) 用または**要求-応答**(用、要求-応答 WCF 操作)。  
  
    -   を設定する要求および応答スキーマの種類を右クリックし、**要求**または**応答**ノードをクリックして**スキーマの種類を選択**です。 **要求メッセージの種類** ダイアログ ボックスでドキュメント スキーマを含むアセンブリの名前を入力、 **BizTalk アセンブリ ファイル**テキスト ボックスまたはクリック**参照**を検索するにはアセンブリ。 **使用可能なスキーマ型**リスト ビューには、スキーマの各ルート要素が表示されます。 要求または応答のスキーマの種類として追加するルート ノードを選択します。  
  
        > [!NOTE]
        >  グローバル アセンブリ キャッシュ (GAC) に、BizTalk アセンブリ ファイルがインストールされている場合はで選択するアセンブリに GAC にアセンブリが更新されたことを確認してください、**要求メッセージの種類** ダイアログ ボックス。 GAC の完全修飾名が同じである場合、BizTalk WCF サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。  
  
         ![要求メッセージの種類 ページ](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")  
  
    -   名前を変更することができます、**要求**と**応答**生成されたコードに影響を与えずにノードです。 スキーマを定義した後で部分要素の名前を変更すると、WCF 操作パラメーターの名前が変更されます。 公開する WCF サービスのサービス メタデータを表示することで、変更内容を確認できます。  
  
    > [!NOTE]
    >  Web サービス説明ノードの名前を変更するとき、空白文字は使用できません。  
  
7.  をクリックして**次**ウィザードを続行します。  
  
8.  **WCF サービスのプロパティ**] ページの [、 **、WCF サービスの Targetnamespace**テキスト ボックスでは、WCF サービスのターゲットの名前空間を入力し、をクリックして**次**です。  
  
     ![WCF サービスのプロパティ ページ](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
9. **WCF サービスの場所**] ページの [、**場所**テキスト ボックスに、WCF サービスが生成される Web ディレクトリ名を入力します。 既定の場所を受け入れることができます (http://localhost/ <*Web サービス説明の名前*>)、WCF サービスの場所を入力、**場所**テキスト ボックス、またはをクリックして**を参照** Web ディレクトリを選択します。 次のいずれかのオプションをクリックします。  
  
    -   **既存のプロジェクトを上書きします。** : このオプションは、Web ディレクトリが存在する場合のみ選択できます。 このオプションを選択すると、同じ場所にのみ公開できます。 このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。  
  
    -   **WCF サービスへの匿名アクセスを許可します。** : このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。 既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。  
  
     このページを終了したらクリックして**次**です。  
  
     ![WCF サービスの場所 ページ](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  プロジェクトの場所には、別のサーバーを指定することもできます。 WCF サービスを別のサーバーで発行するプロジェクト名を入力として http://&lt です*servername*>/<*WCF サービスの場所*>。  
  
    > [!NOTE]
    >  プロジェクトの場所には、既定以外の Web サイトを指定することもできます。 既定以外の Web サイトに公開する場合は、URL に Web サイトのポート番号を含めます。 たとえば、http://&lt*servername*>: 8080/<*WCF サービスの場所*>。  
  
    > [!NOTE]
    >  このウィザードで Web アプリケーションの \App_Data\Temp フォルダーに作成される BindingInfo.xml ファイルでは、パイプラインに既定値が使用されます。 受信パイプラインの既定値は、 **Microsoft.BizTalk.DefaultPipelines.XMLReceive**パイプライン、および既定値、送信パイプラインは、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**パイプライン。  
  
10. **WCF サービスの概要** ページで、WCF サービスの設定を確認します。  
  
11. をクリックして**作成**WCF サービスを作成します。  
  
12. をクリックして**完了**を BizTalk WCF サービス公開ウィザードを完了します。  
  
### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a>サービス メタデータを公開する Web アプリケーションを構成するには  
  
1.  BizTalk WCF サービス公開ウィザードで作成した Web アプリケーションについて ASP.NET を有効にします。 詳細については、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。  
  
    > [!NOTE]
    >  その他のバージョンの Windows オペレーティング システムを使用している場合は、アプリケーション プールの ID アカウントを BizTalk Server 管理者グループに追加する必要があります。 BizTalk Server 管理者グループに、適切なアカウントを追加した後は、IIS サービスを有効にする設定を再起動する必要があります。  
  
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
  
    2.  メモ帳で、次のように設定します。、、 **httpGetEnabled**属性、  **\<serviceMetadata\>** 要素を次の行として false にします。  
  
        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  
  
## <a name="see-also"></a>参照  
 [BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)   
 [チュートリアル: WCF-NetMsmq アダプターを使用した WCF サービスの公開](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)
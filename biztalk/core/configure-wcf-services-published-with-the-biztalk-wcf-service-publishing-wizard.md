---
title: BizTalk WCF サービス公開ウィザードで公開した WCF サービスを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Publishing Wizard
- WCF services, configuring
- configuring, WCF services
- WCF Service Publishing Wizard
ms.assetid: f51b86c0-8c19-453d-a66d-3f373e9f096e
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6424d3101023b6521700a30b8cf4460e09e1ff14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988387"
---
# <a name="how-to-configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard"></a>BizTalk WCF サービス公開ウィザードで公開した WCF サービスを構成する方法
BizTalk WCF サービス公開ウィザードを使用して WCF サービスを公開した後、これらのサービスを適切に構成する必要があります。 このトピックでは、公開した WCF サービスを構成する方法について説明します。  

> [!NOTE]
>  BizTalk WCF サービス公開ウィザードを実行することで、BizTalk プロジェクトを作成し、公開することが必要になります。 BizTalk WCF サービス公開ウィザードを使用する方法の詳細については、次を参照してください[WCF サービスとして公開するオーケストレーションを BizTalk WCF サービス公開ウィザードを使用する方法](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)と[BizTalk WCF サービスを使用する方法。発行ウィザード スキーマを WCF サービスとして公開する](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)します。  

### <a name="to-configure-the-receive-locations-for-a-published-wcf-service"></a>公開した WCF サービスの受信場所を構成するには  

1. BizTalk WCF サービス公開ウィザードを実行して、BizTalk プロジェクトを公開します。  

2. 選択しなかった場合、**作成 BizTalk の受信場所**WCF サービスを作成するときに、次の図のオプション、新しい受信ポートと、公開した WCF サービス用の受信場所用の WCF アダプターを選択し、受信場所が使用するトランスポートの種類。 同じ WCF アダプタを選択する必要があります、 **WCF サービスの種類**ページが次の図に示すようにします。 受信場所の作成の詳細については、次を参照してください。[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)します。  

   > [!NOTE]
   >  BizTalk WCF サービス公開ウィザードは、Web ディレクトリの \App_Data\Temp フォルダーに、公開した WCF サービス (.svc ファイル) 用のバインド ファイル (BindingInfo.xml) を作成します。 選択した場合、**作成 BizTalk の受信場所**オプション、ウィザードでは、バインド ファイルを受信場所を作成します。 このバインド ファイルを BizTalk Server 管理コンソールでインポートし、受信場所を手動で作成することができます。 バインド ファイルをインポートする方法の詳細については、次を参照してください。[バインドのインポート](../core/importing-bindings2.md)します。  

    ![WCF サービスの種類ページ](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  

3. 必要に応じて、次のように、BizTalk Server 管理コンソールを開きます: クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk Server**順にクリックします**BizTalk Server 管理**します。  

4. コンソール ツリーで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションを展開、生成される WCF サービス必要がありますに配置すると、展開**受信場所**、WCF サービスの受信場所をダブルクリックします。  

5. **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**構成**します。  

6. 受信場所で、Wcf-basichttp アダプタまたは Wcf-wshttp アダプタをホストしている場合、**トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブをクリックし、タブで、セキュリティのプロパティを構成します。受信場所がで Wcf-customisolated アダプタをホストするかどうか、**トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブをクリックし、タブのバインド情報を構成します。  

    ![WCF のセキュリティ タブ&#45;BasicHttp アダプタ](../core/media/585ecdad-bdee-40c0-b2f1-7ace74d503e5.gif "585ecdad-bdee-40c0-b2f1-7ace74d503e5")  

   > [!NOTE]
   >  分離 WCF アダプターのトランスポート クライアントの資格情報の種類のプロパティは、この受信場所をホストするインターネット インフォメーション サービス (IIS) 仮想ディレクトリの認証スキームと一致する必要があります。 たとえば、次のプロパティに設定**Windows**も有効にする必要があります**統合 Windows 認証**これをホストする仮想ディレクトリの場所を受信します。 同様に、このプロパティが **[なし]** に設定されている場合は、この受信場所をホストする仮想ディレクトリへの匿名アクセスを許可する必要があります。 Wcf-basichttp と Wcf-wshttp アダプターのセキュリティ プロパティを構成する方法の詳細については、次を参照してください[、Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)、および[Wcf-wshttp 受信を構成する方法。場所](../core/how-to-configure-a-wcf-wshttp-receive-location.md)します。 バインド情報を構成する方法の詳細については、次を参照してください。 [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)します。  

7. 選択しなかった場合、**作成 BizTalk の受信場所**オプションで、サービス、WCF を作成するときに、**トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。**全般**] タブの [この受信場所の URI を入力、**アドレス**テキスト ボックス。 BizTalk WCF サービス公開ウィザードが前の手順で生成した仮想ディレクトリと .svc ファイル名を指定します (例 : /path/service.svc)。  

   > [!NOTE]
   >  **アドレス**プロパティのスラッシュ (「/」) で開始して、末尾に".svc"。 **アドレス**プロパティにはする必要がありますが含まれていないプロトコル スキーム、コンピューター名、またはポート番号などhttp://host:portします。 プロパティに使用できるのは、仮想ディレクトリ パスだけです。 WCF サービスのマークアップ ファイルには、.svc 拡張子を指定する必要があります。  

    ![WCF の [全般] タブ&#45;BasicHttp アダプタ](../core/media/1126fa6a-e3e9-44ad-aeb0-90c78226aeeb.gif "1126fa6a-e3e9-44ad-aeb0-90c78226aeeb")  

8. 選択した場合**トランスポート**または**TransportWithMessageCredential**で、**セキュリティ モード**ドロップダウン リストで、**セキュリティ**のタブWcf-basichttp と Wcf-wshttp アダプターを Secure Sockets Layer (SSL) で IIS を設定する必要があります。 設定した場合、**トランスポート**または**TransportWithMessageCredential** Wcf-customisolated アダプターのバインド情報でセキュリティ モードを設定することする必要がありますも IIS に SSL をします。  

9. 受信場所で、Wcf-basichttp アダプタまたは Wcf-wshttp アダプタをホストしている場合、**トランスポートのプロパティ** ダイアログ ボックスで、構成、**全般**、**バインド**、および**メッセージ**タブで必要な場合。 受信場所が Wcf-customisolated アダプタをホストしている場合は、構成、**全般**、**動作**、**他**、および**メッセージ**タブ目的です。 インポートできる、Wcf-customisolated アダプターについて、**アドレス (URI)** と**エンドポイント Id**プロパティを**全般** タブで、バインド情報、で**バインド** タブとで動作、**動作**構成ファイルからの受信場所をこのタブ。  

10. BizTalk Server 管理コンソールを使用して公開した WCF サービスの受信場所を有効にします。 受信場所を有効にする方法の詳細については、次を参照してください。[受信場所を有効にする方法](../core/how-to-enable-a-receive-location.md)します。  

    > [!NOTE]
    >  受信場所は、作成された時点では無効になっています。 BizTalk WCF サービス公開ウィザードを使用して作成した後、受信場所を有効にする必要があります。  

11. IIS 管理コンソールを使用して、公開した WCF サービスの受信場所をホストするには、IIS アプリケーション プールを構成します。 分離 WCF アダプタのアプリケーション プールを構成する方法の詳細については、次を参照してください。 [IIS 分離 WCF 受信アダプタを構成する](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)します。  

12. コマンド プロンプトを開き、%SystemDrive%\InetPub で BizTalk Server WCF サービス公開ウィザードが WCF サービスを作成するフォルダーに移動して\\、し、メモ帳を使用して Web.config ファイルを開きます。  

13. メモ帳で、次の行を追加、 **\<system.web\>** 要素。  

    ```  
    <trust level="Full" originUrl="" />  
    ```  

    > [!NOTE]
    >  この設定はオプションで、公開した WCF サービスをホストする ASP.NET アプリケーションに、オペレーティング システムのセキュリティの影響下にあるリソースへのアクセス権限を与えます。 これは、公開された WCF サービスと同じコンピューターで Windows SharePoint Services がインストールおよび実行されている場合に、WCF サービスの実行に必要な信頼レベルです。  

14. Internet explorer で、**アドレス**ボックスに、形式 http:// を使用して WCF サービスの URL を入力<em>ホスト [: ポート]</em>/*apppath* /*wcfservicename.svc*を公開した WCF サービスをテストします。 次の表は、これらのパラメーターについてまとめたものです。  


    |      パラメーター       |                                                            値                                                            |
    |----------------------|-----------------------------------------------------------------------------------------------------------------------------|
    |    *ホスト [: ポート]*     | WCF サービスを配置したコンピューターの名前です。 このサーバー名の後に、コロンとポート番号を入力できます。 |
    |      *apppath*       |                              仮想ディレクトリ名と Web アプリケーションのパスです。                               |
    | *wcfservicename.svc* |                                           WCF サービスの .svc ファイルの名前です。                                            |


15. 機密性の高いサービス メタデータが誤って公開されないように、実稼働環境ではこの動作を無効にすることをお勧めします。これには、次のタスクを実行します。  

    1.  メモ帳で、%SystemDrive%\InetPub で BizTalk Server WCF サービス公開ウィザードが WCF サービスを作成するフォルダーの Web.config を開き\\します。  

    2.  メモ帳で、次のように設定します。、、 **httpGetEnabled**属性、 **\<serviceMetadata\>** を false には、次の行要素。  

        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  

## <a name="see-also"></a>参照  
 [Wcf-basichttp アダプターを構成します。](http://msdn.microsoft.com/library/5929a338-46e0-4fc4-8837-792d7f7ae0fe)   
 [Wcf-wshttp アダプタの構成](../core/configuring-the-wcf-wshttp-adapter.md)   
 [Wcf-customisolated アダプターを構成します。](../core/configuring-the-wcf-customisolated-adapter.md)   
 [Windows Server 2003 で IIS Web サイトの認証を構成するには、方法](http://go.microsoft.com/fwlink/?LinkID=75699)
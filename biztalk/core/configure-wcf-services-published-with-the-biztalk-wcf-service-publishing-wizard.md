---
title: "BizTalk WCF サービス公開ウィザードで公開された WCF サービスを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Publishing Wizard
- WCF services, configuring
- configuring, WCF services
- WCF Service Publishing Wizard
ms.assetid: f51b86c0-8c19-453d-a66d-3f373e9f096e
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19383ca97f979d6932698d06eabd507b4a00954f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard"></a>BizTalk WCF サービス公開ウィザードで公開した WCF サービスを構成する方法
BizTalk WCF サービス公開ウィザードを使用して WCF サービスを公開した後、これらのサービスを適切に構成する必要があります。 このトピックでは、公開した WCF サービスを構成する方法について説明します。  
  
> [!NOTE]
>  BizTalk WCF サービス公開ウィザードを実行することで、BizTalk プロジェクトを作成し、公開することが必要になります。 BizTalk WCF サービス公開ウィザードを使用する方法の詳細については、次を参照してください[WCF サービスとして公開オーケストレーションに BizTalk WCF サービス公開ウィザードを使用する方法](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)と[BizTalk WCF サービスを使用する方法。スキーマを WCF サービスとして公開するウィザードを発行](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)です。  
  
### <a name="to-configure-the-receive-locations-for-a-published-wcf-service"></a>公開した WCF サービスの受信場所を構成するには  
  
1.  BizTalk WCF サービス公開ウィザードを実行して、BizTalk プロジェクトを公開します。  
  
2.  選択しなかった場合、**作成 BizTalk の受信場所**WCF サービスを作成するときに、次の図のオプション、新しいポートを受信し、公開した WCF サービスの受信場所が、用の WCF アダプターを選択受信場所が使用するトランスポートの種類。 選択すると、同じ WCF アダプタを選択する必要があります、 **WCF サービスの種類**ページの次の図に示すようにします。 受信場所の作成の詳細については、次を参照してください。[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)です。  
  
    > [!NOTE]
    >  BizTalk WCF サービス公開ウィザードは、Web ディレクトリの \App_Data\Temp フォルダーに、公開した WCF サービス (.svc ファイル) 用のバインド ファイル (BindingInfo.xml) を作成します。 選択した場合、**作成 BizTalk の受信場所**オプション、ウィザードを使用して、バインド ファイルを受信場所を作成します。 このバインド ファイルを BizTalk Server 管理コンソールでインポートし、受信場所を手動で作成することができます。 バインド ファイルのインポートの詳細については、次を参照してください。[バインドのインポート](../core/importing-bindings2.md)です。  
  
     ![WCF サービスの種類ページ](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
3.  必要に応じて、次のように、BizTalk Server 管理コンソールを開きます: をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk Server**をクリックして**BizTalk Server 管理**です。  
  
4.  コンソール ツリーで、 **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションの展開を生成した WCF サービス必要があります、配置している展開**受信場所**、WCF サービスの受信場所をダブルクリックします。  
  
5.  **受信場所のプロパティ**ダイアログ ボックスで、をクリックして**構成**です。  
  
6.  受信場所で、Wcf-basichttp アダプタまたは Wcf-wshttp アダプタをホストしている場合、**トランスポートのプロパティ** ダイアログ ボックスをクリックして、**セキュリティ**タブをクリックし、タブで、セキュリティのプロパティを構成します。受信場所がで Wcf-customisolated アダプタをホストするかどうか、**トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインディング**タブをクリックし、タブのバインド情報を構成します。  
  
     ![WCF &#45; の [セキュリティ] タブBasicHttp アダプタ](../core/media/585ecdad-bdee-40c0-b2f1-7ace74d503e5.gif "585ecdad-bdee-40c0-b2f1-7ace74d503e5")  
  
    > [!NOTE]
    >  分離 WCF アダプターのトランスポート クライアントの資格情報の種類のプロパティは、この受信場所をホストするインターネット インフォメーション サービス (IIS) 仮想ディレクトリの認証スキームと一致する必要があります。 例では、プロパティ設定されている場合の**Windows**も有効にする必要があります**統合 Windows 認証**これをホストする仮想ディレクトリの場所を受信します。 同様に、このプロパティが **[なし]** に設定されている場合は、この受信場所をホストする仮想ディレクトリへの匿名アクセスを許可する必要があります。 Wcf-basichttp と Wcf-wshttp アダプターのセキュリティ プロパティを構成する方法の詳細については、次を参照してください[、Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)、および[Wcf-wshttp 受信を構成する方法。場所](../core/how-to-configure-a-wcf-wshttp-receive-location.md)です。 バインド情報を構成する方法の詳細については、次を参照してください。 [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)です。  
  
7.  選択しなかった場合、**作成 BizTalk の受信場所**オプションで、サービス、WCF を作成するときに、**トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。**全般**] タブの [この受信場所の URI を入力、**アドレス**テキスト ボックス。 BizTalk WCF サービス公開ウィザードが前の手順で生成した仮想ディレクトリと .svc ファイル名を指定します (例 : /path/service.svc)。  
  
    > [!NOTE]
    >  **アドレス**プロパティのスラッシュ (「/」) で始まりし、終わりに".svc"です。 **アドレス**プロトコル スキーム、コンピューター名、または http://host:port などのポート番号、プロパティは設定できません。 プロパティに使用できるのは、仮想ディレクトリ パスだけです。 WCF サービスのマークアップ ファイルには、.svc 拡張子を指定する必要があります。  
  
     ![WCF &#45; の [全般] タブBasicHttp アダプタ](../core/media/1126fa6a-e3e9-44ad-aeb0-90c78226aeeb.gif "1126fa6a-e3e9-44ad-aeb0-90c78226aeeb")  
  
8.  選択した場合は**トランスポート**または**TransportWithMessageCredential**で、**セキュリティ モード**ドロップダウン リストで、**セキュリティ**タブに移動Wcf-basichttp と Wcf-wshttp アダプターでは、Secure Sockets Layer (SSL) を IIS でを設定する必要があります。 設定した場合、**トランスポート**または**TransportWithMessageCredential** Wcf-customisolated アダプターのバインド情報のセキュリティ モード、する必要がありますを設定しても IIS で SSL です。  
  
9. 受信場所で、Wcf-basichttp アダプタまたは Wcf-wshttp アダプタをホストしている場合、**トランスポートのプロパティ** ダイアログ ボックスで、構成、**全般**、**バインド**、および**メッセージ**タブで必要な場合です。 受信場所が Wcf-customisolated アダプタをホストしている場合は、構成、**全般**、**動作**、**他の**、および**メッセージ**タブ用途にします。 インポートすることができます、Wcf-customisolated アダプターの場合、**アドレス (URI)**と**エンドポイント Id**プロパティを**全般** タブで、バインド情報、で**バインド** タブ、および上の動作、**動作**構成ファイルからの受信場所をこのタブです。  
  
10. BizTalk Server 管理コンソールを使用して公開した WCF サービスの受信場所を有効にします。 受信場所を有効にする方法の詳細については、次を参照してください。[受信場所を有効にする方法](../core/how-to-enable-a-receive-location.md)です。  
  
    > [!NOTE]
    >  受信場所は、作成された時点では無効になっています。 BizTalk WCF サービス公開ウィザードを使用して作成した後、受信場所を有効にする必要があります。  
  
11. IIS 管理コンソールを使用して、公開した WCF サービスの受信場所をホストするには、IIS アプリケーション プールを構成します。 分離 WCF アダプタのアプリケーション プールを構成する方法の詳細については、次を参照してください。[分離 WCF 受信アダプタの IIS を構成する](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)です。  
  
12. コマンド プロンプトを開き、BizTalk WCF サービス公開ウィザードが %SystemDrive%\InetPub で WCF サービスを作成する場所のフォルダーに移動\\、メモ帳を使用して Web.config ファイルを開きます。  
  
13. メモ帳で、内部の次の行を追加、  **\<system.web\>** 要素。  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  この設定はオプションで、公開した WCF サービスをホストする ASP.NET アプリケーションに、オペレーティング システムのセキュリティの影響下にあるリソースへのアクセス権限を与えます。 これは、公開された WCF サービスと同じコンピューターで Windows SharePoint Services がインストールおよび実行されている場合に、WCF サービスの実行に必要な信頼レベルです。  
  
14. Internet explorer で、**アドレス**ボックス、書式 http:// を使用して、WCF サービスの URL を入力*ホスト [: ポート]*/*apppath* /*名.svc*を公開した WCF サービスをテストします。 次の表は、これらのパラメーターについてまとめたものです。  
  
    |パラメーター|値|  
    |---------------|-----------|  
    |*ホスト [: ポート]*|WCF サービスを配置したコンピューターの名前です。 このサーバー名の後に、コロンとポート番号を入力できます。|  
    |*アプリケーションのパス*|仮想ディレクトリ名と Web アプリケーションのパスです。|  
    |*名.svc*|WCF サービスの .svc ファイルの名前です。|  
  
15. 機密性の高いサービス メタデータが誤って公開されないように、実稼働環境ではこの動作を無効にすることをお勧めします。これには、次のタスクを実行します。  
  
    1.  メモ帳で、%SystemDrive%\InetPub で、BizTalk WCF サービス公開ウィザードが、WCF サービスを作成するフォルダーの Web.config を開き\\です。  
  
    2.  メモ帳で、次のように設定します。、、 **httpGetEnabled**属性、  **\<serviceMetadata\>** 要素を次の行として false にします。  
  
        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  
  
## <a name="see-also"></a>参照  
 [Wcf-basichttp アダプタを構成します。](http://msdn.microsoft.com/library/5929a338-46e0-4fc4-8837-792d7f7ae0fe)   
 [Wcf-wshttp アダプタを構成します。](../core/configuring-the-wcf-wshttp-adapter.md)   
 [Wcf-customisolated アダプタを構成します。](../core/configuring-the-wcf-customisolated-adapter.md)   
 [Windows Server 2003 の IIS Web サイト認証を構成するには、方法](http://go.microsoft.com/fwlink/?LinkID=75699)
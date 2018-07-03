---
title: マルチ サーバー展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], multi-server deployment
- planning, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, deploying
- Windows SharePoint Services adapters, multi-server deployment
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
ms.assetid: 0c6e2aa0-e873-461b-8101-9b0988019597
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e857aece2911aa9f1b3551f339524d2262cc0bf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979763"
---
# <a name="multiserver-deployment"></a>マルチサーバー展開
このトピックでは、Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプターを、マルチサーバー環境に設定および展開する場合の考慮事項について説明します。  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-multiserver-deployment"></a>マルチサーバー展開への Windows SharePoint Services アダプターのインストール  
 Windows SharePoint Service アダプター Web サービス コンポーネントを選択すると、送受信されるドキュメントを Windows SharePoint Services アダプターが Windows SharePoint Services 経由で処理するために必要なソフトウェアがインストールされます。 この Web サービスは、Windows SharePoint Services がインストールされているサーバーにインストールする必要があります。  
  
 アダプター Web サービスでは、複数の SharePoint サイトを、同一の IIS サイトにあるか、異なる IIS サイトにあるかにかかわらず、処理できます。  
  
 Windows SharePoint Services アダプターには、次の 3 つのコンポーネントがあります。  
  
- ランタイム コンポーネント  
  
- デザイン時コンポーネント  
  
- アダプター Web サービス  
  
  アダプター ランタイムは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム機能によって自動的にインストールおよび構成されます。 アダプターのデザイン時コンポーネントは、その他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 機能によってインストールおよび構成されます。 デザイン時コンポーネントを操作するには、管理ツール、開発ツール、SDK に含まれているツールか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム機能を使用して、Windows SharePoint Services ポートを作成します。 ランタイム コンポーネントおよびデザイン時コンポーネントの構成オプションは、カスタマイズできません。 Windows SharePoint Services アダプター Web サービス オプションのみをカスタマイズすることができます。  
  
  SharePoint Enabled Hosts グループのメンバーだけでは、アダプター Web サービスを呼び出すアクセス許可があります。 Windows SharePoint Services アダプターのランタイムで必要な Windows SharePoint Services のアクセス許可の詳細については、セキュリティ」セクションを参照してください。 [、Windows SharePoint Services アダプターとは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)します。  
  
> [!NOTE]
>  BAS をインストールするとき、Windows SharePoint Services アダプター Web サービス コンポーネントが自動的に選択されます。  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプターをインストールするには  
  
1. インストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)します。  
  
2. **コンポーネントのインストール**画面で、**使用可能なコンポーネント****追加ソフトウェア**を選択します**Windows SharePoint Services アダプターWeb サービス**します。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムをホストするコンピューター、および Windows SharePoint Services を実行するコンピューターでセットアップと構成を実行する必要があります。  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-multiserver-deployment"></a>マルチサーバー展開の Windows SharePoint Services アダプター Web サービスの構成  
 Windows SharePoint Services アダプターは、BizTalk Server 構成を使用して構成します。 これらのツールの詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)します。  
  
### <a name="using-a-custom-configuration"></a>ユーザー構成の使用  
 BizTalk Server 構成では、ローカル コンピューターにインストールした機能の構成状態に関する高レベルの分析が提供されます。 このツールを使用すると、機能の構成と構成解除、セキュリティ設定の構成、および他のコンピューターの構成のインポートとエクスポートを行えます。  
  
 使用して、 **Windows SharePoint Services**ページはこのコンピューターに Windows SharePoint Services アダプターを構成します。 次の表は、構成のオプションを示しています。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**このコンピューターで Windows SharePoint Services アダプターを有効にします。**|選択**このコンピューターで Windows SharePoint Services アダプターを有効にする**このコンピューターでアダプターを有効にします。|  
|**Windows グループ**|**Windows グループ**一覧は、BizTalk SharePoint アダプター有効になっているホスト Windows グループの編集可能なビューを提供します。|  
|**Windows SharePoint Services アダプター Web サイト**|Windows SharePoint Services アダプター Web サービスをホストする Web サイトを選択します。|  
  
 ユーザー構成を使用して Windows SharePoint Services アダプターを構成する際は、次のことが行われます。  
  
-   別の Windows グループを指定しない限り、既定で SharePoint Enabled Hosts Windows グループが作成されます。  
  
-   別の Web サイトを指定しない限り、Windows SharePoint Services アダプターのホストには既定の Web サイトが使用されます。  
  
-   BTSSharePointAdapterWSAppPool アプリケーション プールが、Windows SharePoint Services アプリケーション プールを実行するために使用するアカウントで実行されるように作成および構成されます。  
  
-   BTSharePointAdapterWS 仮想アプリケーションが、BTSSharePointAdapterWSAppPool アプリケーション プールで実行されるように作成および構成されます。  
  
> [!NOTE]
>  この仮想ディレクトリが既に存在する場合は、構成を行ってもメタベースのプロパティが更新されません。 仮想ディレクトリを削除して、構成を再実行する必要があります。  
  
- BTSharePointAdapterWS 仮想アプリケーションに Web サービスが含められます。  
  
  BizTalk Server の構成の詳細については、次を参照してください。[のインポートとエクスポートの BizTalk Server 構成](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)します。  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-custom-configuration"></a>ユーザー設定を使用して Windows SharePoint Services アダプターを構成するには  
  
1. **BizTalk Server 構成**を選択、 **SharePoint アダプター**ノード。  
  
2. 選択**このコンピューターで Windows SharePoint Services アダプターを有効にする**します。  
  
3. **Windows グループ**、Windows SharePoint Services アダプターを使用する Windows グループを選択します。 既定では、SharePoint Enabled Hosts です。  
  
4. **Windows SharePoint Services アダプター Web サイト**ドロップダウン ボックスで、Web サイトのアダプター コンポーネントのインストール先を選択します。 特に選択しない場合、既定の Web サイトが選択されます。  
  
   > [!NOTE]
   >  他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントがインストールされていないリモート SharePoint Server コンピューターに Windows SharePoint Services アダプター Web サイトをインストールする構成は、完全にサポートされている構成です。  
  
5. **[構成の適用]** をクリックします。  
  
## <a name="considerations-for-a-multiserver-deployment"></a>マルチサーバー展開に関する考慮事項  
 ![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")  
  
### <a name="general-considerations"></a>全般的な考慮事項  
 マルチサーバー環境で Windows SharePoint Services アダプターを設定および展開する際は、次のことを考慮してください。  
  
- 各サーバー上で、BizTalk Service アカウントを SharePoint Enabled Hosts Windows グループに追加します。  
  
- SharePoint のサーバーの管理ツールを使用して、SharePoint Enabled Hosts グループを SharePoint の関係者ロールに追加します。  
  
- [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] では、SharePoint アダプター Web サービスを実行する ID に次のアクセス許可が必要です。  
  
   **読み取り**に対するアクセス許可、 **Program files \microsoft BizTalk Server\<バージョン\>\Business Activity Services\BTSharePointV3AdapterWS**フォルダー。 Windows の 64 ビット バージョンを使用している場合と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アクセス許可を設定する必要があります、 **Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\Business Activity Services\BTSharePointV3AdapterWS**  
  
   **読み取り**次のレジストリ キーに対する権限: **hkey_local_machine \software\microsoft\shared Server\Extensions\12.0\Secure\ConfigDB**します。  
  
   SharePoint データベースを含む SQL Server に対するログオン アクセス許可。  
  
   メンバー、**パブリック**と**WSS_Content_Application_Pools** SharePoint 構成データベース内のロール。  
  
   メンバー、**パブリック**と**db 所有者**SharePoint コンテンツ データベース内のロール。  
  
- Web サービスをインストールする Web サイトは、SharePoint Services Web サイトとして拡張しておく必要があります。  
  
- Windows SharePoint Services アダプターは、サイレント インストールでインストールおよび構成できます。 詳細については、次を参照してください。[付録 a: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)します。  
  
### <a name="considerations-for-network-load-balancing-nlb"></a>ネットワーク負荷分散 (NLB) に関する考慮事項  
 Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプターを使用すると、同一グループ内に構成されている複数の BizTalk サーバーと共に Windows SharePoint Services サーバーを NLB クラスターにすることができます。 この場合、SharePoint のマニュアルで推奨されているように、Windows SharePoint Services を NLB クラスターにインストールする必要があります。  
  
 NLB を設定したマルチサーバー環境で Windows SharePoint Services アダプターを設定および展開する際は、次のことを考慮してください。  
  
-   既存の BizTalk 管理データベースを指すようにオプションを選択することによって、Windows SharePoint Services を構成します。 1 台目のコンピューターで作成した BizTalk 管理データベースを指すように設定します。 これは、Windows SharePoint Services に対して、Web サーバー環境を使用することを示す操作です。 既存のコンテンツ データベースを指すことによって、Web サイトを拡張します。  
  
-   Web サーバー環境内の各 Windows SharePoint Services コンピューターで、同一の Web サイト (ポート 80 の既定の Web サイトなど) を拡張する必要があります。  
  
-   BTSharePointAdapterWS を各 NLB ホストと同様にインストールおよび構成する必要があります。 構成する必要がある NLB 設定を次に示します。  
  
    -   プロトコル: TCP  
  
    -   ポート: 80 (Windows SharePoint Services アダプター Web サービスがインストールおよび構成された IIS Web サイトの HTTP ポート)  
  
    -   フィルターのモード: 複数ホスト  
  
    -   関係: なし  
  
> [!NOTE]
>  この設定はサイトが HTTPS 用に構成されていない場合にのみ使用できます。 HTTPS を構成しているサイトに BTSharePointAdapterWS Web サービスをインストールする場合、単一クライアントの関係を使用する必要があります。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプター](../core/windows-sharepoint-services-adapter.md)   
 [シングルサーバー展開](../core/single-server-deployment.md)
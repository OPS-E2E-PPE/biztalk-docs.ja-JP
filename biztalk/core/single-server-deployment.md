---
title: "シングル サーバー配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, deploying
- configuring [Windows SharePoint Services adapters], customizing
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
- Windows SharePoint Services adapters, configuring
- configuring [Windows SharePoint Services adapters], single-server deployment
- Windows SharePoint Services adapters, single-server deployment
ms.assetid: 94ba8241-9a30-46ca-b962-721e2d00f420
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6796bbbad4722e959962ea88e9854bce82476be4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="single-server-deployment"></a>シングルサーバー展開
このトピックでは、Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプターを、シングルサーバー環境に設定および展開する場合の考慮事項について説明します。  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-single-server-deployment"></a>シングルサーバー展開への Windows SharePoint Services アダプターのインストール  
 Windows SharePoint Service アダプター Web サービス コンポーネントを選択すると、送受信されるドキュメントを Windows SharePoint Services アダプターが Windows SharePoint Services 経由で処理するために必要なソフトウェアが、インストールされます。 この Web サービスは、Windows SharePoint Services がインストールされているサーバーにインストールする必要があります。 アダプター Web サービスでは、ビジネス アクティビティ サービス (BAS) をホストする Web サイトを含めた複数の SharePoint サイトを、同一の IIS サイトにあるか、異なる IIS サイトにあるかにかかわらず、処理できます。  
  
 Windows SharePoint Services アダプターには、3 つのコンポーネントがあります。  
  
-   ランタイム コンポーネント  
  
-   デザイン時コンポーネント  
  
-   アダプター Web サービス  
  
 アダプター ランタイムは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム機能によって自動的にインストールおよび構成されます。 アダプターのデザイン時コンポーネントがインストールされ、他の構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]機能します。 デザイン時コンポーネントを操作するには、管理ツール、開発ツール、SDK に含まれているツールか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム機能を使用して、Windows SharePoint Services ポートを作成します。 ランタイム コンポーネントおよびデザイン時コンポーネントの構成オプションは、カスタマイズできません。 Windows SharePoint Services アダプター Web サービス オプションのみカスタマイズできます。  
  
 アダプター Web サービスを呼び出すアクセス許可は、SharePoint Enabled Hosts グループのメンバーのみに与えられます。 Windows SharePoint Services アダプター ランタイムで必要な Windows SharePoint Services のアクセス許可の詳細については、セキュリティ」セクションを参照してください。 [Windows SharePoint Services アダプターは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)です。  
  
> [!NOTE]
>  BAS をインストールするとき、Windows SharePoint Services アダプター Web サービス コンポーネントが自動的に選択されます。  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプターをインストールするには  
  
1.  BizTalk Server をインストールします。 詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)です。  
  
2.  **コンポーネントのインストール**画面で、**使用可能なコンポーネント****追加のソフトウェア** **Windows SharePoint Services アダプターWeb サービス**です。  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-single-server-deployment"></a>シングルサーバー展開の Windows SharePoint Services アダプター Web サービスの構成  
 Windows SharePoint Services アダプターは、基本構成またはユーザー構成のいずれかを使用して構成できます。 これらのツールの詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)です。  
  
### <a name="using-a-basic-configuration"></a>基本構成の使用  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、サーバーの構成に既定の設定を使用できます。 サーバーの基本構成は、構成ウィザードで入力するデータベース サーバー名、ユーザー名、およびパスワードを使用して構成されます。 基本構成を使用して Windows SharePoint Services アダプター Web サービスを構成する際は、次のことが行われます。  
  
-   SharePoint Enabled Hosts Windows グループが作成されます。  
  
-   Windows SharePoint Service アダプターをホストする Web サイトには、既定の Web サイトが使用されます。  
  
-   BTSSharePointAdapterWSAppPool アプリケーション プールが作成され、Windows SharePoint Services アプリケーション プールの実行にも使用されるアカウントで実行するように構成します。  
  
-   BTSharePointAdapterWS 仮想アプリケーションが、BTSSharePointAdapterWSAppPool アプリケーション プールで実行されるように作成および構成されます。  
  
> [!NOTE]
>  この仮想ディレクトリが既に存在する場合は、構成を行ってもメタベースのプロパティが更新されません。 仮想ディレクトリを削除し、構成を再実行する必要があります。  
  
-   BTSharePointAdapterWS 仮想アプリケーションに Web サービスが含められます。  
  
 基本構成の詳細については、次を参照してください。[基本的な構成](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5)です。  
  
### <a name="using-a-custom-configuration"></a>ユーザー構成の使用  
 BizTalk Server 構成では、ローカル コンピューターにインストールした機能の構成状態に関する高レベルの分析が提供されます。 このツールを使用すると、機能の構成と構成解除、セキュリティ設定の構成、および他のコンピューターの構成のインポートとエクスポートを行えます。  
  
 使用して、 **Windows SharePoint Services アダプター Web サービス**ページはこのコンピューターに Windows SharePoint Services アダプターを構成します。 次の表は、構成のオプションを示しています。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**このコンピューターで Windows SharePoint Services アダプターを有効にします。**|選択**このコンピューターで Windows SharePoint Services アダプターを有効にする**をこのコンピューターでアダプターを有効にします。|  
|**Windows グループ**|**Windows グループ**一覧は、BizTalk SharePoint Adapter Enabled Hosts Windows グループの編集可能なビューを提供します。|  
|**Windows SharePoint Services アダプター Web サイト**|Windows SharePoint Service アダプター Web サービスをホストする Web サイトを選択します。|  
  
 カスタム構成を使用して、Windows SharePoint Services アダプターを構成するときに、次の処理が発生します。  
  
-   別の Windows グループを指定しない限り、既定で SharePoint Enabled Hosts Windows グループが作成されます。  
  
-   別の Web サイトを指定しない限り、Windows SharePoint Services アダプターのホストには既定の Web サイトが使用されます。  
  
-   BTSSharePointAdapterWSAppPool アプリケーション プールが、Windows SharePoint Services アプリケーション プールを実行するために使用するアカウントで実行されるように作成および構成されます。  
  
-   BTSharePointAdapterWS 仮想アプリケーションが、BTSSharePointAdapterWSAppPool アプリケーション プールで実行されるように作成および構成されます。  
  
> [!NOTE]
>  この仮想ディレクトリが既に存在する場合は、構成を行ってもメタベースのプロパティが更新されません。 仮想ディレクトリを削除し、構成を再実行する必要があります。  
  
-   BTSharePointAdapterWS 仮想アプリケーションに Web サービスが含められます。  
  
 カスタム構成マネージャの詳細については、次を参照してください。[のインポートとエクスポートの BizTalk Server 構成](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)です。  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-a-custom-configuration"></a>ユーザー構成を使用して Windows SharePoint Services アダプターを構成するには  
  
1.  **BizTalk Server 構成**、select、 **SharePoint アダプター**ノード。  
  
2.  選択**このコンピューターで Windows SharePoint Services アダプターを有効にする**です。  
  
3.  **Windows グループ**は、Windows SharePoint Services アダプターを使用する Windows グループを選択します。 既定では、SharePoint Enabled Hosts です。  
  
4.  **Windows SharePoint Services アダプター Web サイト**ドロップダウン ボックスで、Web サイトのアダプター コンポーネントをインストールします。 特に選択しない場合、既定の Web サイトが選択されます。  
  
5.  **[構成の適用]** をクリックします。  
  
## <a name="considerations-for-a-single-server-deployment"></a>シングルサーバー展開に関する考慮事項  
 シングルサーバー環境で Windows SharePoint Services アダプターを設定および展開する際は、次のことを考慮してください。  
  
-   サーバー上で、BizTalk Service アカウントを SharePoint Enabled Hosts Windows グループに追加します。  
  
-   SharePoint のサーバーの管理ツールを使用して、SharePoint Enabled Hosts グループを SharePoint の関係者ロールに追加します。  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] では、SharePoint アダプター Web サービスを実行する ID に次のアクセス許可が必要です。  
  
     **読み取り**に対するアクセス許可、 **Program files \microsoft BizTalk Server\<バージョン\>\Business Activity Services\BTSharePointV3AdapterWS**フォルダーです。 アクセス許可に設定する必要がある場合は、64 ビット バージョンの Windows および BizTalk Server を使用して、 **%program Files (x86) \Microsoft BizTalk Server\<バージョン\>\Business Activity Services\BTSharePointV3AdapterWS**  
  
     **読み取り**次のレジストリ キーに対する権限: **hkey_local_machine \software\microsoft\shared Server\Extensions\12.0\Secure\ConfigDB**です。  
  
     SharePoint データベースを含む SQL Server に対するログオン アクセス許可。  
  
     メンバー、**パブリック**と**WSS_Content_Application_Pools** SharePoint 構成データベース内のロール。  
  
     メンバー、**パブリック**と**db 所有者**SharePoint コンテンツ データベース内のロール。  
  
-   Web サービスをインストールする Web サイトは、SharePoint Services Web サイトとして拡張しておく必要があります。  
  
-   インストールして、サイレント インストールを使用して Windows SharePoint Services アダプターを構成することができます。 詳細については、次を参照してください。[付録 a: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)です。  
  
## <a name="see-also"></a>参照  
 [Windows SharePoint Services アダプター](../core/windows-sharepoint-services-adapter.md)   
 [マルチサーバー展開](../core/multiserver-deployment.md)
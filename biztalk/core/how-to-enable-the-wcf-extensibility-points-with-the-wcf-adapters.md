---
title: WCF アダプターで WCF 機能拡張ポイントを有効にする |Microsoft Docs
description: アセンブリをインストール、machine.config を構成する、BizTalk 管理者に拡張機能の追加、作成する BizTalk Server で WCF アダプターの WCF 機能拡張ポイントを有効にする受信場所
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c2af105-5272-4a6a-95d2-066312ab788e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5fe619b78bae05d373293293366cafc117c3ea8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980427"
---
# <a name="how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters"></a>WCF アダプターを使用して WCF 機能拡張ポイントを有効にする方法
次の 3 つの WCF 機能拡張ポイントを有効にする、動作拡張機能、バインド要素拡張機能、およびバインド拡張機能-Wcf-custom および Wcf-customisolated アダプタを使用します。 これを行うには、まず WCF 機能拡張ポイントを実装するアセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールし、コンピューターの machine.config ファイルを変更した後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して WCF-Custom アダプターまたは WCF-CustomIsolated アダプターを構成します。  
  
参照してください[WCF の拡張](https://docs.microsoft.com/dotnet/framework/wcf/extending/extending-wcf)WCF 機能拡張ポイントの詳細について。
  
 
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 [展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)詳細情報を提供します。  
  
## <a name="install-assemblies-implementing-a-wcf-extensibility-point-in-the-gac"></a>GAC に WCF の機能拡張ポイントを実装するアセンブリをインストールします。  
  
1. WCF 機能拡張ポイントを実装するアセンブリを、ローカル コンピューター上のフォルダーにコピーします。  
  
2. WCF 機能拡張ポイントが使用するアセンブリがある場合、そのアセンブリをローカル コンピューター上のフォルダーにコピーします。  
  
3. 開始、 **Visual Studio コマンド プロンプト**します。  
  
4. 次のコマンドを入力します。  
  
    **gacutil.exe/if"\<**  *アセンブリ .dll ファイルへのパス*  **\>"**  
  
5. これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。  
  
6. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトで、手順 1. と 2. でコピーしたすべてのアセンブリについて手順 4. と 5. を繰り返します。  
  
7. 複数ある場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターと管理コンピューターは、すべてのコンピューター上の 1 ~ 6 のこの手順の手順を繰り返します。  
  
   > [!NOTE]
   >  WCF アダプターの WCF 機能拡張ポイントを有効にするには、アダプターを実行している BizTalk ホスト インスタンスが、WCF 機能拡張ポイントが実装されているアセンブリを実行時に読み込む必要があります。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-extension"></a>WCF バインド拡張機能の machine.config ファイルを構成します。  
  
1. コマンド プロンプトでは、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダー、および順に開いて、 **machine.config**メモ帳を使用してファイル。  
  
2. メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel\>\\< 拡張\>** 要素内でそれらの要素を追加する、  **\<構成\>** 、machine.config の要素ファイルを開き、追加、 **\<bindingExtensions\>** 内の WCF バインド拡張機能要素 **\<system.serverModel\>\\< 拡張\>** 要素。 たとえば、netHttpBinding、カスタム バインド拡張機能を有効にするに次のコードを追加、 **\<構成\>** machine.config ファイルの要素。  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingExtensions>  
         <add name="netHttpBinding" type="Microsoft.Samples.Channels.NetHttpBindingCollectionElement, NetHttpBinding, Version=3.0.0.0, Culture=neutral, PublicKeyToken=5b637b51c4aaa2a8" />  
       </bindingExtensions>        
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   >  - コマンドを使用して登録するアセンブリに関する情報を見つけることができます**gacutil/lr** *< アセンブリ名 >* します。  
   >  - 参照してください[bindingExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingextensions)この要素にします。
  
3. メモ帳で、machine.config ファイルを保存します。  
  
4. 複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。  
  
   > [!NOTE]
   >  BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。  
  
## <a name="configure-a-wcf-binding-extension-by-using-the-biztalk-administration-console"></a>BizTalk 管理コンソールを使用して WCF バインド拡張機能を構成します。  
  
1. 開いている**BizTalk Server 管理**します。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。  
  
2. WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。  
  
3. WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。  
  
4. WCF 機能拡張ポイントを使用する受信場所を構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**受信場所**、右側のウィンドウでダブルクリック*\<受信場所\>* します。  
  
   -   **受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**クリックしてを使用する WCF アダプタに応じて**構成**します。  
  
5. WCF 機能拡張ポイントを使用する送信ポートを構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**送信ポート**、右側のウィンドウでダブルクリック*\<送信ポート\>* します。  
  
   -   **送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
6. トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブで、バインド拡張機能を選択し、他のトランスポートの設定を構成します。  
  
7. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、クリックしてすべての開いているダイアログ ボックスを閉じます、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-element-extension"></a>WCF バインド要素拡張機能の machine.config ファイルを構成します。  
  
1. コマンド プロンプトでは、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダー、および順に開いて、 **machine.config**メモ帳を使用してファイル。  
  
2. メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel\>\\< 拡張\>** 要素内でそれらの要素を追加する、  **\<構成\>** 、machine.config の要素ファイルを開き、追加、 **\<bindingElementExtensions\>** WCF バインド要素の要素内に拡張機能、  **\<system.serverModel\>\\< 拡張\>** 要素。 たとえば、カスタム バインド要素拡張、droppingInterceptor を有効にするに次のコードを追加、 **\<構成\>** machine.config ファイルの要素。  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingElementExtensions>  
         <add name="droppingInterceptor" type="Microsoft.ServiceModel.Samples.DroppingServerElement, MessageInterceptor, Version=0.0.0.0, Culture=neutral, PublicKeyToken=098514eef14aa34a"/>  
       </bindingElementExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   > - コマンドを使用して登録するアセンブリに関する情報を見つけることができます**gacutil/lr** *< アセンブリ名 >* します。  
   > - 参照してください[bindingElementExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingelementextensions)この要素にします。
  
3. メモ帳で、machine.config ファイルを保存します。  
  
4. 複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。  
  
   > [!NOTE]
   >  BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。  
  
## <a name="configure-a-wcf-binding-element-extension-by-using-the-biztalk-administration-console"></a>BizTalk 管理コンソールを使用して WCF バインド要素拡張機能を構成します。  
  
1. 開いている**BizTalk Server 管理**します。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。  
  
2. WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。  
  
3. WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。  
  
4. WCF 機能拡張ポイントを使用する受信場所を構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**受信場所**、右側のウィンドウでダブルクリック*\<受信場所\>* します。  
  
   -   **受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**クリックしてを使用する WCF アダプタに応じて**構成**します。  
  
5. WCF 機能拡張ポイントを使用する送信ポートを構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**送信ポート**、右側のウィンドウでダブルクリック*\<送信ポート\>* します。  
  
   -   **送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
6. トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブで、**バインドの種類**ドロップダウン リストで、 **customBinding**します。  
  
7. トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブのクライアント領域を右クリックし、**バインド**ボックスの一覧をクリックして**拡張機能を追加**。  
  
8. **バインディング要素拡張機能の選択**ダイアログ ボックスは、バインド要素拡張機能を選択しをクリックして**OK**します。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブで追加されたバインド要素の順序を調整、**バインド**一覧で追加したバインド要素拡張機能の種類に応じて、次のように前の手順:  
  
    -   **バインド**ボックスの一覧で、バインド要素拡張機能を右クリックし、順にクリックします**拡張機能を上へ移動**または**拡張機能を下へ移動**します。 最下位のバインド要素拡張機能、**バインド**チャネル スタックの一番下のコンポーネントに対応するリスト。 最上位のバインド要素で、**バインド**通信スタックの一番上のコンポーネントに対応するリスト。  
  
        > [!NOTE]
        >  参照してください[カスタム バインド](https://docs.microsoft.com/dotnet/framework/wcf/extending/custom-bindings)詳細については、カスタム バインドのバインド要素の特定の順序。
  
10. トランスポートのプロパティ ダイアログ ボックスでは、他のトランスポートの設定を構成します。  
  
11. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、クリックしてすべての開いているダイアログ ボックスを閉じます、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-behavior-extension"></a>WCF 動作拡張機能の machine.config ファイルを構成します。  
  
1. コマンド プロンプトでは、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダー、および順に開いて、 **machine.config**メモ帳を使用してファイル。  
  
2. メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel\>\\< 拡張\>** 要素内でそれらの要素を追加する、  **\<構成\>** 、machine.config の要素ファイルを開き、追加、 **\<behaviorExtensions\>** WCF 動作拡張機能の要素内で、  **\<system.serverModel\>\\< 拡張\>** 要素。 たとえば、schemaValidator、カスタム動作拡張機能を有効にするに次のコードを追加、 **\<構成\>** machine.config ファイルの要素。  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <behaviorExtensions>  
         <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ad307e213604f592"/>  
       </behaviorExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   > [!NOTE]
   >  - コマンドを使用して登録するアセンブリに関する情報を見つけることができます**gacutil/lr** *< アセンブリ名 >* します。  
   >  - 参照してください[behaviorExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/behaviorextensions)この要素にします。
  
3. メモ帳で、machine.config ファイルを保存します。  
  
4. 複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。  
  
   > [!NOTE]
   >  BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。  
  
## <a name="configure-a-wcf-behavior-extension-by-using-the-biztalk-administration-console"></a>BizTalk 管理コンソールを使用して WCF 動作拡張機能を構成します。  
  
1. 開いている**BizTalk Server 管理**します。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。  
  
2. WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。  
  
3. WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。  
  
4. BizTalk 管理コンソールで、WCF 機能拡張ポイントを使用して、展開を受信場所を構成する場合**BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**受信場所**、右側のウィンドウでダブルクリック*\<受信場所\>* します。  
  
   -   **受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**クリックしてを使用する WCF アダプタに応じて**構成**します。  
  
5. BizTalk 管理コンソールで、WCF 機能拡張ポイントを使用して、展開する送信ポートを構成する場合**BizTalk グループ**、展開 *\<BizTalk アプリケーション\>*、展開**送信ポート**、右側のウィンドウでダブルクリック*\<送信ポート\>* します。  
  
   -   **送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。  
  
6. トランスポートのプロパティ ダイアログ ボックスで、**動作** タブで、右クリック**ServiceBehavior**または**EndpointBehavior**動作拡張機能の種類に応じて、**動作拡張機能の選択** ダイアログ ボックスでは動作拡張機能を選択し、クリックして**OK**。  
  
7. トランスポートのプロパティ ダイアログ ボックスでは、他のトランスポートの設定を構成します。  
  
8. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、クリックしてすべての開いているダイアログ ボックスを閉じます、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。  
  
## <a name="configure-a-wcf-custom-receive-location-with-an-ssl-certificate"></a>WCF カスタム SSL 証明書を使用して受信場所  
  
-   HTTP カーネル モード ドライバー (HTTP.sys) を使用する場合は、Wcf-custom 受信場所、 **httpsTransport** Secure Sockets Layer (SSL) 通信で、受信場所のバインド要素: 証明書が必要ですソケット (IP アドレスとポートの組み合わせ) ごとに登録します。 SSL 証明書をコンピューター上のポートにバインドするには、HttpCfg.exe ツールを使用します。 詳細については、[How To: SSL 証明書を使用して、ポート構成](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate)を参照してください。
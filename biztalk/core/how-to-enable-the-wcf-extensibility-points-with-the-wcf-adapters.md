---
title: "WCF アダプターで WCF 機能拡張ポイントを有効にする |Microsoft ドキュメント"
description: "アセンブリをインストールし、machine.config の構成、拡張 BizTalk 管理者を追加作成する受信場所で BizTalk Server で WCF アダプターの WCF 機能拡張ポイントを有効にするには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c2af105-5272-4a6a-95d2-066312ab788e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be2980f3235552f263efbd4fce92c0042216b88c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters"></a>WCF アダプターを使用して WCF 機能拡張ポイントを有効にする方法
次の 3 つの WCF 機能拡張ポイントを有効にする — 動作拡張機能、バインド要素の拡張機能、およびバインド拡張機能: Wcf-custom および Wcf-customisolated アダプタを使用しています。 これを行うには、まず WCF 機能拡張ポイントを実装するアセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールし、コンピューターの machine.config ファイルを変更した後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して WCF-Custom アダプターまたは WCF-CustomIsolated アダプターを構成します。  
  
参照してください[WCF の拡張](https://docs.microsoft.com/dotnet/framework/wcf/extending/extending-wcf)の詳細については、WCF 機能拡張ポイントです。
  
 
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 [展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)詳細な情報を提供します。  
  
## <a name="install-assemblies-implementing-a-wcf-extensibility-point-in-the-gac"></a>GAC に WCF 機能拡張ポイントを実装するアセンブリをインストールします。  
  
1.  WCF 機能拡張ポイントを実装するアセンブリを、ローカル コンピューター上のフォルダーにコピーします。  
  
2.  WCF 機能拡張ポイントが使用するアセンブリがある場合、そのアセンブリをローカル コンピューター上のフォルダーにコピーします。  
  
3.  開始、 **Visual Studio コマンド プロンプト**です。  
  
4.  次のコマンドを入力します。  
  
     **gacutil.exe/if"\<**  *アセンブリ .dll ファイルのパスを* **>"**  
  
5.  これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。  
  
6.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトで、手順 1. と 2. でコピーしたすべてのアセンブリについて手順 4. と 5. を繰り返します。  
  
7.  複数ある場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターと管理コンピューターは、すべてのコンピューターに 1 ~ 6 のこの手順を手順を繰り返します。  
  
    > [!NOTE]
    >  WCF アダプターの WCF 機能拡張ポイントを有効にするには、アダプターを実行している BizTalk ホスト インスタンスが、WCF 機能拡張ポイントが実装されているアセンブリを実行時に読み込む必要があります。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-extension"></a>WCF バインド拡張機能の machine.config ファイルを構成します。  
  
1.  コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。  
  
2.  メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel >\\< 拡張\>**要素内にその要素の追加、  **\<構成 >** 、machine.config の要素ファイル、および追加し、  **\<bindingExtensions >**要素内の WCF バインド拡張機能、  **\<system.serverModel >\\< 拡張\>**要素。 たとえば、netHttpBinding、カスタム バインド拡張機能を有効にする次のコードを追加、 **\<構成 >** machine.config ファイルの要素。  
  
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
    >  - コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。  
    >  - 参照してください[bindingExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingextensions)この要素上です。
  
3.  メモ帳で、machine.config ファイルを保存します。  
  
4.  複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。  
  
    > [!NOTE]
    >  BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。  
  
## <a name="configure-a-wcf-binding-extension-by-using-the-biztalk-administration-console"></a>BizTalk 管理コンソールを使用して WCF バインド拡張機能を構成します。  
  
1.  開いている**BizTalk Server 管理**です。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。  
  
2.  WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。  
  
3.  WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。  
  
4.  WCF 機能拡張ポイントを使用する受信場所を構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所 >*です。  
  
    -   **受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。  
  
5.  WCF 機能拡張ポイントを使用する送信ポートを構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート >*です。  
  
    -   **送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
6.  トランスポートのプロパティ ダイアログ ボックスで、**バインディング** タブで、バインド拡張機能を選択し、他のトランスポートの設定を構成します。  
  
7.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-binding-element-extension"></a>WCF バインド要素拡張機能の machine.config ファイルを構成します。  
  
1.  コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。  
  
2.  メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel >\\< 拡張\>**要素内にその要素の追加、  **\<構成 >** 、machine.config の要素ファイル、および追加し、  **\<bindingElementExtensions >**要素内に WCF バインド要素拡張機能、  **\<system.serverModel >\\< 拡張\>**要素。 たとえば、droppingInterceptor、カスタム バインディング要素拡張を有効にする次のコードを追加、 **\<構成 >** machine.config ファイルの要素。  
  
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
    > - コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。  
    > - 参照してください[bindingElementExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/bindingelementextensions)この要素上です。
  
3.  メモ帳で、machine.config ファイルを保存します。  
  
4.  複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。  
  
    > [!NOTE]
    >  BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。  
  
## <a name="configure-a-wcf-binding-element-extension-by-using-the-biztalk-administration-console"></a>BizTalk 管理コンソールを使用して WCF バインド要素拡張機能を構成します。  
  
1.  開いている**BizTalk Server 管理**です。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。  
  
2.  WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。  
  
3.  WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。  
  
4.  WCF 機能拡張ポイントを使用する受信場所を構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所 >*です。  
  
    -   **受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。  
  
5.  WCF 機能拡張ポイントを使用する送信ポートを構成する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート >*です。  
  
    -   **送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
6.  トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブの 、**バインディングの種類**ドロップダウン リストで、 **customBinding**です。  
  
7.  トランスポートのプロパティ ダイアログ ボックスで、**バインド** タブでのクライアント領域を右クリックし、**バインド**一覧をクリックして**拡張機能を追加**です。  
  
8.  **バインディング要素拡張機能の選択**ダイアログ ボックスをバインディング要素拡張を選択し、をクリックして**OK**です。  
  
9. トランスポートのプロパティ ダイアログ ボックスで、**バインディング** タブで追加されたバインド要素の順序を調整、**バインディング**で追加したバインド要素拡張の種類に応じて一覧、次のように前の手順:  
  
    -   **バインディング**ボックスの一覧をバインド要素拡張を右クリックし、をクリックして**拡張機能を上へ移動**または**拡張機能を下へ移動**です。 最下位のバインド要素拡張機能、**バインディング**一覧は、チャネル スタックの一番下のコンポーネントに対応しています。 内の最上位のバインド要素、**バインディング**一覧は、通信スタックの一番上のコンポーネントに対応しています。  
  
        > [!NOTE]
        >  参照してください[カスタム バインド](https://docs.microsoft.com/dotnet/framework/wcf/extending/custom-bindings)詳細については、カスタム バインドのバインド要素の特定の順序に関するします。
  
10. トランスポートのプロパティ ダイアログ ボックスで、他のトランスポートの設定を構成します。  
  
11. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。  
  
## <a name="configure-the-machineconfig-file-for-a-wcf-behavior-extension"></a>WCF 動作拡張機能の machine.config ファイルを構成します。  
  
1.  コマンド プロンプトで、%frameworkdir%\v4 に移動します。X.XXXXX\CONFIG フォルダーを開き、 **machine.config**メモ帳を使用して、ファイルです。  
  
2.  メモ帳で、machine.config ファイルがない場合、  **\<system.serverModel >\\< 拡張\>**要素内にその要素の追加、  **\<構成 >** 、machine.config の要素ファイル、および追加し、  **\<behaviorExtensions >**要素内に WCF 動作拡張機能、  **\<system.serverModel >\\< 拡張\>**要素。 たとえば、schemaValidator、カスタム動作拡張機能を有効にする次のコードを追加、 **\<構成 >** machine.config ファイルの要素。  
  
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
    >  - コマンドを使用して登録するアセンブリの情報を得られる**gacutil/lr** *< assembly_name >*です。  
    >  - 参照してください[behaviorExtensions](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/wcf/behaviorextensions)この要素上です。
  
3.  メモ帳で、machine.config ファイルを保存します。  
  
4.  複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンピューターと管理コンピューターがある場合は、すべてのコンピューターで手順 1. ～ 3. を繰り返します。  
  
    > [!NOTE]
    >  BizTalk ホスト インスタンスおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの WCF 拡張機能ポイントを処理するには、WCF インフラストラクチャのすべてのコンピューターでこれらの手順を繰り返す必要があります。  
  
## <a name="configure-a-wcf-behavior-extension-by-using-the-biztalk-administration-console"></a>BizTalk 管理コンソールを使用して WCF 動作拡張機能を構成します。  
  
1.  開いている**BizTalk Server 管理**です。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを既に開いている場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを再起動します。  
  
2.  WCF-Custom アダプターを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、[プラットフォームの設定]、[ホスト インスタンス] の順に展開し、アダプターを実行している BizTalk ホスト インスタンスを再起動します。  
  
3.  WCF-CustomIsolated アダプターを使用する場合は、IIS 管理コンソールで、WCF 受信場所に関連付けられたアプリケーション プールを再起動します。  
  
4.  BizTalk 管理コンソールで、WCF 機能拡張ポイントを使用して、展開の受信場所を構成する場合**BizTalk グループ**、展開 *\<BizTalk アプリケーション >*、展開**受信場所**、右側のペインをダブルクリックして*\<受信場所 >*です。  
  
    -   **受信場所のプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**または**Wcf-customisolated**を使用して、をクリックする、WCF アダプタによって**構成**です。  
  
5.  BizTalk 管理コンソールで、WCF 機能拡張ポイントを使用して、展開する送信ポートを構成する場合**BizTalk グループ**、展開 *\<BizTalk アプリケーション >*の展開**送信ポート**、右側のペインをダブルクリックして*\<送信ポート >*です。  
  
    -   **送信ポートのプロパティ** ダイアログ ボックスで、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。  
  
6.  トランスポートのプロパティ ダイアログ ボックスで、**動作** タブを右クリックして**ServiceBehavior**または**endpointbehavior**動作拡張機能の種類に応じて、**動作拡張機能の選択**ダイアログ ボックスでは、動作拡張機能を選択し、をクリックして**OK**です。  
  
7.  トランスポートのプロパティ ダイアログ ボックスで、他のトランスポートの設定を構成します。  
  
8.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックしてすべての開いているダイアログ ボックスを閉じる、 **OK**ボタン、およびエラー メッセージとエラーがあるイベント ログが表示されないことを確認します。  
  
## <a name="configure-a-wcf-custom-receive-location-with-an-ssl-certificate"></a>WCF カスタムを構成する SSL 証明書を使用して受信場所  
  
-   Wcf-custom 受信場所がなどを使用して HTTP カーネル モード ドライバー (HTTP.sys) が発生する場合、 **httpsTransport**通信用に Secure Sockets Layer (SSL)、受信場所のバインド要素は、証明書が必要各ソケット (IP アドレスとポートの組み合わせ) に登録されます。 SSL 証明書をコンピューター上のポートにバインドするには、HttpCfg.exe ツールを使用します。 詳細については、次を参照してください。[操作方法: SSL 証明書を使用するポートを構成](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate)です。
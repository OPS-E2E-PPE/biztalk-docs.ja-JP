---
title: "更新または BizTalk アダプター パック 2016 のアンインストール |Microsoft ドキュメント"
description: "セットアップ ウィザードまたは msiexec を使用して、変更または BizTalk Server に含まれている BAP 2016 のアンインストールなど、バインドを削除して、カスタムの Rfc を削除"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3d6c001-1005-4d7b-a143-eaa37b48f898
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c30fa3b107113991a8b4893fa2626a53d67159
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="update-or-uninstall-the-biztalk-adapter-pack-2016"></a>更新または BizTalk アダプター パック 2016 のアンインストール
変更またはアンインストールする方法、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。

<a name="BKMK_Modify_Adap"></a>
## <a name="change-or-update-the-installation"></a>変更または更新のインストール  
変更するセットアップ ウィザードを実行する前に、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、インストールを確認してください、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]がインストールされています。 
  
 対話モード (セットアップ ウィザード) で、またはサイレント モード (コマンド ライン) で、インストールを変更することができます。
  
### <a name="use-the-setup-wizard"></a>セットアップ ウィザードを使用します。  
  
1.  BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。  
  
2.  **プログラムと機能****プログラムのアンインストール**です。  
  
3.  右クリック**Microsoft BizTalk Adapter Pack**、し、**変更**です。  
  
4.  [ようこそ] 画面で、次のように選択します。**次**です。  
  
5.  **変更、修復、または削除インストール**:  
  
    -   インストールするコンポーネントを選択する**変更**し、手順 6. に進みます。  
  
    -   最新のインストールのエラーを修復するには、次のように選択します。**修復**手順 7. に進みます。  
  
    -   削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、コンピューターから選択**削除**し、手順 10 に進みます。  
  
6.  場合は、インストールを変更することを選択します。  
  
    -   展開して、 **Microsoft BizTalk Adapter Pack**ノード ベース アダプター、.NET Framework データ プロバイダー、またはその両方をインストールするかを選択します。  
  
    -   展開して、**ベース アダプター**ノードすべてのアダプターまたは特定のアダプターをインストールするかを選択します。  
  
    -   展開して、 **ADO プロバイダー**ノードすべてのプロバイダーまたは特定のプロバイダーをインストールするかを選択します。  
  
    -   **[次へ]** を選択します。  
  
    -   選択**変更**、し、**完了**です。  
  
7.  インストールを修復して、選択した場合、 **Microsoft BizTalk Adapter Pack の修復の準備完了**ダイアログ ボックスで、**修復**です。 ウィザードでは、インストールの修復を開始します。  
  
8.  必要に応じて、ユーザーの設定を変更、CEIP のオプトインに関連し、 **OK**です。 
  
9. **[完了]** を選択します。  
  
10. アダプターを削除した場合、 **Microsoft BizTalk Adapter Pack を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**です。  
  
### <a name="use-msiexec-in-silent-mode"></a>サイレント モードで msiexec を使用します。  
  
1.  コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラーです。  
  
2.  次のようなコマンドを実行します。  
  
    > [!NOTE]
    >  変更する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次のコマンドでの x64 ベースのプラットフォームにサイレント モードでインストールを交換して`AdaptersSetup.msi`で`AdaptersSetup64.msi`です。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
    ```  
  
     このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]をインストールし、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]です。  
  
     別の値を使用して、`REMOVE`と`ADDLOCAL`プロパティを追加または特定のコンポーネントを削除することができます。 内のテーブルを参照してください**サイレント モードでインストール**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)これらのプロパティを使用できる値についてはします。  
  
     Msiexec コマンドの一部として、/f オプションを使用して、サイレントの修復を実行することもできます。 例:  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn /f  
    ```  
  
     さまざまなさまざまな組み合わせを使用するには、/f オプションを使用します。 Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。 移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。  
  
    > [!IMPORTANT]
    >  変更中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでインストールで CEIP を有効または無効にするための設定を変更することはできません。 True または false に、CEIP_OPTIN を明示的に設定した場合でも、インストールは残りの中に選択した環境を設定します。  

## <a name="uninstall-or-remove-the-biztalk-adapter-pack"></a>アンインストールするか、BizTalk Adapter Pack を削除します。  
  
> [!IMPORTANT]
>  TRFC 機能を使用する SQL Server データベースでテーブルを作成した場合、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、アンインストールする前に手動で削除する必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールのコピー、`SapAdapter-DbScript-Uninstall.sql`ファイルを通常*\<インストール ドライブ >: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*です。 作成したテーブルを削除するには、このファイルを実行します。  
  
次の手順を削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]コンピューターからです。 あるかどうかを確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]セットアップ ウィザードを実行する前にインストールします。  
  
 削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード) またはサイレント モード (コマンド ライン)。
  
### <a name="uninstall-using-the-setup-wizard"></a>セットアップ ウィザードを使用してアンインストールします。  
  
1.  **プログラムと機能****プログラムのアンインストール**です。  
  
2.  右クリック**Microsoft BizTalk Adapter Pack**、し、**アンインストール**です。  
  
### <a name="uninstall-in-silent-mode"></a>サイレント モードでアンインストールします。  
  
1.  コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラーです。  
  
2.  次のコマンドを実行します。  
  
    > [!NOTE]
    >  削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードで、次のコマンドの x64 ベースのプラットフォーム上で置き換える`AdaptersSetup.msi`で`AdaptersSetup64.msi`です。  
  
    ```  
    msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
    ```  
  
     このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]から、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。  
  
     異なる値を提供することによって、`REMOVE`プロパティから特定のコンポーネントを削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。 内のテーブルを参照してください**サイレント モードでインストール**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)このプロパティの使用できる値についてはします。  
  
     完全に削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、次のコマンドを実行します。  
  
    ```  
    msiexec /x AdaptersSetup.msi /qn  
    ```  
  
     Msiexec コマンドの種類の詳細については`msiexec`キーを押して、コマンド ライン`ENTER`です。 移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。
  
## <a name="remove-the-bindings"></a>バインドを削除します。  
 次の手順を完了*のみ*machine.config ファイルから、アダプターのバインドまたは .NET Framework Data Provider の登録を削除するセットアップ ウィザードが失敗した場合。  
  
1.  コンピューター上の machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な*\<システム ドライブ >: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG*です。  
  
2.  テキスト エディターを使用してファイルを開きます。  
  
3.  アダプターのバインドの登録を削除します。  
  
    1.  検索、`system.serviceModel`要素、および要素の下には、次の削除。  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  検索、 `bindingElementExtensions` system.serviceModel\extensions 下にある要素。  
  
    3.  次のセクションでは、削除、`bindingElementExtensions`バインドに応じて、使用可能なアダプターのノードです。 セットアップ ウィザードをすべて削除に失敗する場合は、すべてのバインディングを削除する必要があります。  
  
         [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  検索、 `bindingExtensions` system.serviceModel\extensions 下にある要素。  
  
    5.  次のセクションでは、削除、`bindingExtensions`バインドに応じて、使用可能なアダプターのノードです。 セットアップ ウィザードをすべて削除に失敗する場合は、すべてのバインディングを削除する必要があります。  
  
         [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、削除します。  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]、削除します。  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]、削除します。  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]、削除します。  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]、削除します。  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  .NET Framework データ プロバイダーの登録を削除します。  
  
    -   検索、 `DbProviderFactories` system.data ノードの下の要素。  
  
    -   まだ登録されている .NET Framework データ プロバイダーを探します。 次のセクションでは、削除、`DbProviderFactories`によっては、既存の .NET Framework データ プロバイダーのノード。 存在する場合は、すべてのプロバイダーを削除する必要があります。  
  
         [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、削除します。  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]、削除します。  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  machine.config ファイルを保存して閉じます。  
  
## <a name="remove-the-custom-rfcs"></a>カスタム Rfc を削除します。  
SAP システムにインストールされているカスタム Rfc を削除するには、この手順を完了します。 参照してください[インストールまたは削除するカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。  
  

---
title: 更新または、BizTalk Adapter Pack 2016 のアンインストール |Microsoft Docs
description: セットアップ ウィザードまたは msiexec を使用して、変更または BizTalk Server に含まれている BAP 2016 のアンインストールなど、バインドを削除し、カスタム Rfc の削除
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3d6c001-1005-4d7b-a143-eaa37b48f898
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eef0252a2907287c3197d40558d605f5c9f5660e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981867"
---
# <a name="update-or-uninstall-the-biztalk-adapter-pack-2016"></a>更新または、BizTalk Adapter Pack 2016 のアンインストール
変更またはアンインストールする方法、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。

<a name="BKMK_Modify_Adap"></a>
## <a name="change-or-update-the-installation"></a>変更または更新のインストール  
変更には、セットアップ ウィザードを実行する前に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、確認、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]がインストールされています。 
  
 対話モード (セットアップ ウィザード) で、またはサイレント モード (コマンドライン) でのインストールを変更することができます。
  
### <a name="use-the-setup-wizard"></a>セットアップ ウィザードを使用します。  
  
1. BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。  
  
2. **プログラムと機能**、**プログラムのアンインストール**します。  
  
3. 右クリックして**Microsoft BizTalk Adapter Pack**、し、**変更**します。  
  
4. [ようこそ] 画面で、次のように選択します。**次**します。  
  
5. **変更、修復、または削除インストール**:  
  
   - インストールするコンポーネントを選択する**変更**し、手順 6. に進みます。  
  
   - 最新のインストールのエラーを修復するには、選択**修復**手順 7. に進みます。  
  
   - 削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、コンピューターから次のように選択します。**削除**し、手順 10 に進みます。  
  
6. インストールを変更する場合。  
  
   -   展開、 **Microsoft BizTalk Adapter Pack**ノード ベース アダプター、.NET Framework データ プロバイダー、またはその両方をインストールするかを選択します。  
  
   -   展開、**ベース アダプター**ノードをすべてのアダプターまたは特定のアダプターのインストールを選択します。  
  
   -   展開、 **ADO プロバイダー**ノードすべてのプロバイダーまたは特定のプロバイダーをインストールするかを選択します。  
  
   -   **[次へ]** を選択します。  
  
   -   選択**変更**、し、**完了**します。  
  
7. インストールを修復することを選んだ場合、 **Microsoft BizTalk Adapter Pack の修復の準備完了**ダイアログ ボックスで、**修復**します。 ウィザードでは、インストールの修復を開始します。  
  
8. 必要な場合、基本設定を変更、CEIP のオプトインに関連し、 **OK**。 
  
9. **[完了]** を選択します。  
  
10. アダプターを削除した場合、 **Microsoft BizTalk Adapter Pack を削除する準備ができて**ダイアログ ボックスで、**削除**、し、**完了**。  
  
### <a name="use-msiexec-in-silent-mode"></a>サイレント モードで msiexec を使用します。  
  
1. コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラー。  
  
2. 次のようなコマンドを実行します。  
  
   > [!NOTE]
   >  変更する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 、次のコマンドでの x64 ベースのプラットフォームでサイレント モードでインストールを交換して`AdaptersSetup.msi`で`AdaptersSetup64.msi`。  
  
   ```  
   msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature ADDLOCAL=SapBaseAdapterFeature  
   ```  
  
    このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]をインストールし、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]します。  
  
    別の値を使用して、`REMOVE`と`ADDLOCAL`プロパティを追加または特定のコンポーネントを削除することができます。 内のテーブルを参照してください**サイレント モードでインストール**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)これらのプロパティを使用できる値についてはします。  
  
    Msiexec コマンドの一部として、/f オプションを使用して、サイレントの修復を実行することもできます。 以下に例を示します。  
  
   ```  
   msiexec /i AdaptersSetup.msi /qn /f  
   ```  
  
    /F オプションを使用して、さまざまなさまざまな組み合わせを使用できます。 Msiexec コマンドの種類の詳細については`msiexec`コマンドライン、およびキーを押して`ENTER`します。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)します。  
  
   > [!IMPORTANT]
   >  変更中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでインストール、または ceip のオプトインの設定を変更することはできません。 True または false に、CEIP_OPTIN を明示的に設定した場合でも、インストールは残りの中に選択した環境を設定します。  

## <a name="uninstall-or-remove-the-biztalk-adapter-pack"></a>アンインストールするか、BizTalk Adapter Pack の削除  
  
> [!IMPORTANT]
>  TRFC 機能を使用する SQL Server データベースでテーブルを作成した場合、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、アンインストールする前に削除する必要があります手動で、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールのコピーを`SapAdapter-DbScript-Uninstall.sql`ファイルを通常*\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* します。 作成したテーブルを削除するには、このファイルを実行します。  
  
削除するには、次の手順を完了、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]コンピューターから。 必ず、[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]セットアップ ウィザードを実行する前にインストールされています。  
  
 削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モード (セットアップ ウィザード)、またはサイレント モード (コマンドライン)。
  
### <a name="uninstall-using-the-setup-wizard"></a>セットアップ ウィザードを使用したアンインストールします。  
  
1.  **プログラムと機能**、**プログラムのアンインストール**します。  
  
2.  右クリックして**Microsoft BizTalk Adapter Pack**、し、**アンインストール**します。  
  
### <a name="uninstall-in-silent-mode"></a>サイレント モードでアンインストールします。  
  
1. コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストーラー。  
  
2. 次のコマンドを実行します。  
  
   > [!NOTE]
   >  削除する、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードで、次のコマンドでの x64 ベースのプラットフォームで置き換える`AdaptersSetup.msi`で`AdaptersSetup64.msi`。  
  
   ```  
   msiexec /i AdaptersSetup.msi /qn REMOVE=DbFeature  
   ```  
  
    このコマンドを削除、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]から、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。  
  
    さまざまな値を提供することで、`REMOVE`プロパティから特定のコンポーネントを削除することができます、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールします。 内のテーブルを参照してください**サイレント モードでインストール**で[インストール BAP](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)このプロパティの使用できる値についてはします。  
  
    完全に削除する、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、次のコマンドを実行します。  
  
   ```  
   msiexec /x AdaptersSetup.msi /qn  
   ```  
  
    Msiexec コマンドの種類の詳細については`msiexec`コマンドライン、およびキーを押して`ENTER`します。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)します。
  
## <a name="remove-the-bindings"></a>バインドを削除します。  
 次の手順を完了*のみ*アダプター バインドまたは .NET Framework データ プロバイダーの登録、machine.config ファイルから削除するセットアップ ウィザードが失敗した場合。  
  
1. コンピューターの machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config はで使用可能な*\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG*します。  
  
2. テキスト エディターを使用してファイルを開きます。  
  
3. アダプターのバインドの登録を削除します。  
  
   1. 検索、`system.serviceModel`要素、および次の要素の下から削除します。  
  
      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="OracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
  
      ```  
  
   2. 検索、 `bindingElementExtensions` system.serviceModel\extensions の下の要素。  
  
   3. 次のセクションでは、削除、`bindingElementExtensions`ノードで、使用可能なアダプターのバインドによって異なります。 セットアップ ウィザードは、削除が失敗した場合、すべてのバインドを削除する必要があります。  
  
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
  
   4. 検索、 `bindingExtensions` system.serviceModel\extensions の下の要素。  
  
   5. 次のセクションでは、削除、`bindingExtensions`ノードで、使用可能なアダプターのバインドによって異なります。 セットアップ ウィザードは、削除が失敗した場合、すべてのバインドを削除する必要があります。  
  
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
  
4. .NET Framework Data Provider の登録を削除します。  
  
   - 検索、 `DbProviderFactories` system.data ノードの下の要素。  
  
   - まだ登録されている .NET Framework データ プロバイダーを探します。 次のセクションでは、削除、`DbProviderFactories`によっては、既存の .NET Framework データ プロバイダーのノード。 存在する場合は、すべてのプロバイダーを削除する必要があります。  
  
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
  
5. machine.config ファイルを保存して閉じます。  
  
## <a name="remove-the-custom-rfcs"></a>カスタム Rfc を削除します。  
SAP システムがインストールされているカスタム Rfc を削除するには、この手順を完了します。 参照してください[インストールまたは削除のカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。  
  

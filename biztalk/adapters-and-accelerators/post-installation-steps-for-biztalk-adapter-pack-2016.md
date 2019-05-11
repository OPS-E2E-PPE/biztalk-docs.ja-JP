---
title: BizTalk Adapter Pack 2016 のインストール手順を投稿 |Microsoft Docs
description: BAP など 2016 をインストールした後に完了する手順は、BizTalk 管理コンソール、Oracle、更新プログラムおよびアダプターのバインドを登録するアダプターを追加します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8946bfe-92bb-470d-bec4-9bc3a07ce0d2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54c02d5fa7573516bb998e1e47c3c4a929feba77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363995"
---
# <a name="post-installation-steps-for-biztalk-adapter-pack-2016"></a>BizTalk Adapter Pack 2016 のインストール後の手順
インストールした後、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、いくつかのインストール後の手順します。 このトピックでは、次の手順を使用します。   

## <a name="add-the-adapter-to-biztalk-administration"></a>アダプターを BizTalk 管理コンソールに追加します。

1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

2. 展開、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**します。  

3. 右クリック**アダプター**を選択します**新規**、選び**アダプター**します。  

    ![アダプターを追加する](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  

4. **アダプター プロパティ**などのボックスの一覧からアダプターを選択**WCF-SAP**など、名前を入力します**WCF-SAP**します。  

    ![SAP アダプターを BizTalk に追加](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")  

5. **[OK]** を選択します。  

## <a name="use-a-newer-oracledataaccessdll-version"></a>新しい Oracle.DataAccess.dll バージョンを使用して、  

Wcf-oracledb アダプターを使用または生成されたアダプターを使用する Visual Studio を使用するポートを構成するときに、アダプターが Oracle.DataAccess.dll バージョン 2.111.7.0 必要があることをメッセージが表示されます。 このメッセージを解決するには、サポートされている Oracle.DataAccess.dll バージョンをインストールします (を参照してください[サポート対象バージョンの一覧](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))、し、更新、`bindingRedirect`次の手順を使用して OracleDB 構成ファイル内の要素。  

1.  BizTalk Server では、次のフォルダーに移動します。  

     *drive*:\Program Files\Microsoft BizTalk Adapter Pack(x64)\bin  

     *ドライブ*: \Program Files (x86) \Microsoft BizTalk Adapter Pack\bin  

2.  Microsoft.Adapters.OracleDB.config ファイルを開きます。  

3.  次のセクションの検索とし、コピー/貼り付け、次の。  

    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  

    ```  

    > [!NOTE]
    >  この例では設定*newVersion* 2.112.1.00 にします。 この値は、インストールしたバージョンに設定します。  

> [!IMPORTANT]
> - このグループに複数の BizTalk Server がある場合は、グループ内のすべての BizTalk サーバー上でこの変更を加えます。  
> - *NewVersion* Oracle.DataAccess.dll ファイルをコンピューターにインストールされているのバージョンに基づいて更新する値が必要です。  Oracle.DataAccess.dll は、Oracle からインストールする Oracle クライアントと共に含まれます。  Oracle クライアント バージョンをインストールする必要がありますのみ[BizTalk Adapter Pack でサポートされている](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)します。  

## <a name="create-sql-server-database-objects-sap-adapter-only"></a>SQL Server データベース オブジェクト (SAP アダプターのみ) を作成します。  
 SAP システムで Trfc を呼び出すには、実行、 *SapAdapter-DbScript-Install.sql* SQL スクリプト。 このスクリプトがインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、SQL Server のデータベース オブジェクトを作成します。 スクリプトは通常にインストールされて*\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* します。 Trfc を呼び出すため、アダプターを使用しているときにそのデータベース名を入力する場合に限り、任意の SQL Server データベースに対してこのスクリプトを実行できます。

## <a name="register-the-adapter-bindings"></a>アダプターのバインドを登録します。
中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストール、セットアップ ウィザードがアダプター バインドまたは、.NET Framework Data Provider for mySAP Business Suite を登録に失敗する可能性があります。 アダプターのインストール、セットアップが続行されます。 これは、Windows Communication Foundation (WCF) のインストールによって発生する可能性があります、[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]インストール、または壊れている machine.config ファイル。  

> [!IMPORTANT]
> 次の手順を完了*のみ*machine.config ファイルで、アダプターのバインド、または .NET Framework データ プロバイダーを登録するセットアップ ウィザードが失敗した場合。  

1. コンピューターの machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config はで使用可能な*\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG*します。  

2. テキスト エディターを使用してファイルを開きます。  

3. アダプターのバインドを登録します。  

   1. 検索、`system.serviceModel`要素、およびその下にある次の追加。  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. 検索、 `bindingElementExtensions` system.serviceModel\extensions の下の要素。  

   3. 不足しているアダプターのバインドを探します。 次のセクションを追加、`bindingElementExtensions`ノード、不足しているアダプターのバインドによって異なります。 セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのバインドを登録する必要があります。  

       [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。  

      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。  

      ```  
      <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. 検索、 `bindingExtensions` system.serviceModel\extensions の下の要素。  

   5. 不足しているアダプターのバインドを探します。 次のセクションを追加、`bindingExtensions`ノード、不足しているアダプターのバインドによって異なります。 セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのバインドを登録する必要があります。  

       [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。  

      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。  

      ```  
      <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  公開キーの値を取得するには、次を参照してください。**公開キーとバージョン特定**(」を参照)。  

4. .NET Framework データ プロバイダーを登録します。  

   1. 検索、 `DbProviderFactories` system.data ノードの下の要素。  

   2. 不足している .NET Framework データ プロバイダーを探します。 次のセクションを追加、`DbProviderFactories`不足しているプロバイダーによって、ノード。 セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのプロバイダーを登録する必要があります。  

       [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]を追加します。  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
          description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]を追加します。  

      ```  
      <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
          description=".NET Framework Data Provider for Siebel eBusiness Applications"  
          type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. machine.config ファイルを保存して閉じます。  

## <a name="determine-the-public-key-and-version"></a>公開キーとバージョンを決定します。  
 公開キーと、アダプターまたは .NET Framework Data Provider のバージョンを確認するのには、次の手順を完了します。  

1. 通常、Windows ディレクトリに移動*C:\WINDOWS\assembly*します。  

2. DLL を公開キーを必要し、し、選択を右クリックして**プロパティ**します。 次の表では、各アダプターおよびプロバイダーの Dll の名前を示します。  


   |                         アダプターおよび .NET Framework データ プロバイダー                         |       DLL の名前        |
   |--------------------------------------------------------------------------------------|------------------------------|
   |           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |    Microsoft.Adapters.SAP    |
   |        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |  Microsoft.Adapters.Siebel   |
   |        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        | Microsoft.Adapters.OracleDB  |
   | [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] | Microsoft.Adapters.OracleEBS |
   |            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |  Microsoft.Adapters.Sql.dll  |
   |        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |   Microsoft.Data.SAPClient   |
   |     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | Microsoft.Data.SiebelClient  |


3. **全般** タブで、**公開キー トークンの**値は、DLL の公開キー。 **バージョン**値は、DLL のバージョン番号。  

4. 公開キーをコピーし、**キャンセル**します。  

## <a name="install-the-custom-rfcs"></a>カスタム Rfc をインストールします。  
必要なだけ*場合*を使用する、 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。 参照してください[インストールのカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)で、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]ドキュメント。 

> [!IMPORTANT]
>  提供されるカスタム Rfc の以前のバージョンを使用しているかどうか、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、このリリースで提供する Rfc にアップグレードする必要があります。 そうでは、以前の Rfc を削除し、このリリースに含まれている Rfc をインストールします。  

## <a name="install-the-enterprise-applications"></a>エンタープライズ アプリケーションをインストールします。  
手順と、さまざまなエンタープライズ LOB システムをインストールするためのガイダンスでは、エンタープライズ システムによって提供されるインストール ガイドの使用をお勧めします。 存在する場合は、特定の構成の変更は、アダプターのドキュメントを参照してください。   

## <a name="installation-and-post-installation-checklist"></a>インストールとインストール後のチェックリスト  

- すべてをインストールすることを確認、[ソフトウェアの前提条件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)正しいインストール オプションを使用します。

- インストールされているコンピューターにインストールされているエンタープライズ LOB アプリケーションのサポートされているバージョンがあるかどうかを確認、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 参照してください[サポートされている基幹業務 (LOB) システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)します。  

- エンタープライズに接続する LOB システムのアダプターのみをインストールすることをインストールしたことを確認して、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**カスタム**インストール オプションです。 使用していないことを確認、**完了**インストール オプションです。 参照してください[BizTalk Adapter Pack をインストールする](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)します。  

- TRFC の呼び出しを使用して、SAP システムを作成するかどうか、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、SQL Server データベースで必要なテーブルを作成するかどうかを確認します。 参照してください**SQL Server データベースの作成オブジェクト**(」を参照)。

- 実行中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードでは、バインドを登録できませんでしたというエラー メッセージが表示可能性があります。 場合は、手動で登録します。 参照してください**アダプターのバインドを登録**(」を参照)。  

- インストールした場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、SAP システムにカスタム Rfc をインストールするかどうかを確認します。 参照してください[カスタム Rfc をインストール](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。

## <a name="more-good-info"></a>詳細な情報
[変更または削除する BizTalk Adapter Pack](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)  
[BizTalk Adapter Pack に関する FAQ](../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
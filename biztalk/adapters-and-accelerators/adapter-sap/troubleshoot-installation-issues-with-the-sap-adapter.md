---
title: "SAP アダプターでのインストールに関する問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: fdfdaf44-c32d-43a5-998d-02032c0b9211
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc33d5d15ef876e18a5a17fa33944dd7d1b36461
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshoot-installation-issues-with-the-sap-adapter"></a>SAP アダプターでのインストールに関する問題をトラブルシューティングします。
Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。 このセクションでは、インストール エラーを解決するのには、トラブルシューティングの手法について説明します。  
  
## <a name="logging-messages-for-setup-actions"></a>セットアップ操作のログ メッセージ  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 さらに、セットアップでは、アダプターのバインドの登録などの特定のカスタム アクションも実行します。 セットアップを実行する標準的なだけでなくカスタムの操作のメッセージをログに記録できます。  
  
-   [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] MSI を使用してアダプターの特定ファイルをインストールします。 したがって、セットアップのログ記録は、標準の MSI ログです。  
  
-   セットアップ プログラムを実行するカスタム動作のログは %temp%\adaptersetup.log 使用です。 ログ ファイルにトレースが失敗した場合、トレースもイベント ログにできます。  
  
##  <a name="BKMK_SAPSetupBinding"></a>アダプターのバインドまたはデータ プロバイダーの登録に失敗します。  
 **問題**  
  
 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドを登録に失敗するか、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]アダプターのインストールが続行されますが、します。  
  
 **原因**  
  
 問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。 アダプターのバインドは、machine.config ファイルに書き込まれます。  
  
 **解決策**  
  
 手動で登録する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドまたは[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
### <a name="register-the-adapter-bindings-or-the-data-provider"></a>アダプターのバインドまたはデータ プロバイダーを登録します。  
  
1.  コンピューター上の machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。  
  
     このパスに\<バージョン\>.NET Framework のバージョンです。  
  
2.  テキスト エディターを使用してファイルを開きます。  
  
3.  登録する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド。  
  
    1.  要素"system.serviceModel"を検索し、その下にある、次を追加します。  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        </client>  
        ```  
  
    2.  "BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    3.  不足している検索[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドします。 "BindingElementExtensions"ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を追加します。  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  "BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    5.  不足している検索[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドします。 "BindingExtensions"ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を追加します。  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
        > [!NOTE]
        >  公開キーを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。  
  
4.  登録する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:  
  
    1.  "DbProviderFactories"、"system.data"ノードの下の要素を検索します。  
  
    2.  不足している検索[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。 "DbProviderFactories"ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を追加します。  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient" description=".NET Framework Data Provider for mySAP Business Suite" type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  machine.config ファイルを保存して閉じます。  
  
###  <a name="BKMK_PubKey"></a>公開キーとバージョンを決定します。  
 公開キーを確認するには、次の手順を実行[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]または[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
1.  Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  
  
2.  対象の公開キーを指定してを選択し、DLL を右クリックして**プロパティ**です。 次の表の Dll の名前を一覧表示[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
    |アダプター/データ プロバイダー|DLL の名前|  
    |----------------------------|---------------------|  
    |[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]|Microsoft.Adapters.SAP|  
    |[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]|Microsoft.Data.SAPClient|  
  
3.  **全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。 同様に、値のに対して、**バージョン**ラベルは、DLL のバージョン番号を指定します。  
  
4.  公開キーをコピーし、をクリックして**キャンセル**です。  
  
##  <a name="BKMK_SAPConsumeBinding"></a>有効なアダプターにはインストールされているエラーがありません。

 **問題**  
  
 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。  
  
```  
No valid adapters are installed on this machine  
```  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。 64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。 そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。 ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、そのため起動、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグイン、machine.config ファイルの 32 ビット バージョンのバインドをチェックし、エラーが失敗しました。  
  
 **解決策**  
  
-   32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。  
  
    > [!IMPORTANT]
    >  64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。  
  
-   クライアント Dll の 32 ビットおよび 64 ビット バージョンの両方を追加、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (librfc32u.dll) など、PATH 変数にします。 Dll の 32 ビット バージョンは、C:\Windows\SysWow64 フォルダーに追加する必要があります。 Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。  
  
    > [!IMPORTANT]
    >  (32 ビットまたは 64 ビット) のアダプターが、64 ビット オペレーティング システムをあるコンピューター上で実行されているアプリケーションを作成するアダプターを使用している場合は、アダプターと同じ種類 (32 ビットまたは 64 ビット) にアプリケーションをマークする必要があります。 また、(32 ビットまたは 64 ビット) の RFC SDK のバージョンはアダプター (32 ビットまたは 64 ビット) のバージョンと同じにする必要があります。  
    >   
    >  たとえば、32 ビット アダプターが 64 ビット オペレーティング システム搭載のコンピューターで実行されている場合、32 ビットとして、アダプターのクライアント アプリケーションを設定してください。  
  
     SAP クライアント Dll の詳細については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。  
  
##  <a name="BKMK_SAPInvalidBinding"></a>SAP アダプターのポートを構成中に無効なバインド エラー  
 **問題**  
  
 アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sapBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 **原因**  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。 64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。 そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。 ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、32 ビット プロセスとして実行されるされため、アダプターのポートを構成するときに、machine.config ファイルの 32 ビット バージョンのバインドを確認エラーは失敗します。  
  
 **解決策**  
  
-   32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。  
  
    > [!IMPORTANT]
    >  64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。  
  
-   クライアント Dll の 32 ビットおよび 64 ビット バージョンの両方を追加、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (librfc32u.dll) など、PATH 変数にします。 Dll の 32 ビット バージョンは、C:\Windows\SysWow64 フォルダーに追加する必要があります。 Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。  
  
    > [!IMPORTANT]
    >  (32 ビットまたは 64 ビット) のアダプターが、64 ビット オペレーティング システムをあるコンピューター上で実行されているアプリケーションを作成するアダプターを使用している場合は、アダプターと同じ種類 (32 ビットまたは 64 ビット) にアプリケーションをマークする必要があります。 また、(32 ビットまたは 64 ビット) の RFC SDK のバージョンはアダプター (32 ビットまたは 64 ビット) のバージョンと同じにする必要があります。  
    >   
    >  たとえば、32 ビット アダプターが 64 ビット オペレーティング システム搭載のコンピューターで実行されている場合、32 ビットとして、アダプターのクライアント アプリケーションを設定してください。  
  
     SAP クライアント Dll の詳細については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。
  
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)
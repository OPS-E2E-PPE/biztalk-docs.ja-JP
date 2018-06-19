---
title: Oracle データベース アダプターのインストールに関するトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation issues, troubleshooting
- troubleshooting, installation issues
ms.assetid: 2054b725-d657-4039-b83b-119571935f62
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dc2603a2e86d29797919fb51c3985c384ff9580
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962320"
---
# <a name="troubleshoot-installation-issues-with-the-oracle-database-adapter"></a>Oracle データベース アダプターのインストールに関するをトラブルシューティングします。
Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。 このセクションでは、インストール エラーを解決するのにはトラブルシューティングの手法の使用について説明しもいくつかの既知の問題を示します。  
  
## <a name="logging-messages-for-setup-actions"></a>セットアップ操作のログ メッセージ  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 さらに、セットアップでは、アダプターのバインドの登録などの特定のカスタム アクションも実行します。 セットアップを実行する標準的なだけでなくカスタムの操作のメッセージをログに記録できます。  
  
-   [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] MSI を使用してアダプターに固有のファイルをインストールします。 したがって、セットアップのログ記録は、標準の MSI ログです。 
  
-   セットアップ プログラムを実行するカスタム アクションのすべてのログは %temp%\adaptersetup.log です。 ログ ファイルにトレースが失敗した場合、トレースもイベント ログにできます。  
  
##  <a name="BKMK_OraDBBinding"></a>アダプターのバインドの登録に失敗します。  
 **問題**  
  
 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドの登録に失敗するが、アダプターのインストールが続行されます。  
  
 **原因**  
  
 問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。 アダプターのバインドは、machine.config ファイルに書き込まれます。  
  
 **解決策**  
  
手動で登録、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド。 
  
1.  コンピューター上の machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。  
  
     このパスに\<バージョン\>.NET Framework のバージョンです。  
  
2.  テキスト エディターを使用してファイルを開きます。  
  
3.  登録する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド。  
  
    1.  要素"system.serviceModel"を検索し、その下にある、次を追加します。  
  
        ```  
        <client>  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        </client>  
        ```  
  
    2.  "BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    3.  不足している検索[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドします。 "BindingElementExtensions"ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を追加します。  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  "BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    5.  不足している検索[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドします。 "BindingExtensions"ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を追加します。  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  公開キーとバージョンを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。  
  
4.  machine.config ファイルを保存して閉じます。  
  
####  <a name="BKMK_PubKey"></a>公開キーとバージョンを決定します。  
 公開キーを確認するには、次の手順を実行[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
1.  Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  
  
2.  公開キーと、バージョンを対象し、なるを選択し、DLL を右クリックして**プロパティ**です。 次の表に、dll の名前[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
    |[アダプター]|DLL の名前|  
    |-------------|---------------------|  
    |[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]|Microsoft.Adapters.OracleDB|  
  
3.  **全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。 同様に、値のに対して、**バージョン**ラベルは、DLL のバージョン番号を指定します。  
  
4.  公開キーをコピーし、をクリックして**キャンセル**です。  
  
##  <a name="BKMK_ConsumeBinding"></a>64 ビット インストールで アダプター サービスのアドインまたはアダプター サービス参照の追加プラグインを使用しているときにエラー  
 **問題**  
  
 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。  
  
```  
No valid adapters are installed on this machine  
```  
  
 **原因**  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。 64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。 そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。 ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、そのため起動、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグイン、machine.config ファイルの 32 ビット バージョンのバインドをチェックし、エラーが失敗しました。  
  
 **解決策**  
  
-   32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。  
  
    > [!IMPORTANT]
    >  64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。  
  
-   Oracle クライアント 11.1.0.6 パッチ セット 11.1.0.7 に Oracle Data Access Components の 32 ビットおよび 64 ビット両方のバージョンをインストールします。  
  
    > [!NOTE]
    >  アプリケーションは ODP.NET の最新のバージョンで動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。 詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイトです。  
  
##  <a name="BKMK_InvalidBinding"></a>BizTalk Server 管理コンソールで、64 ビット インストールでの Oracle データベース アダプターのポートの構成中に無効なバインド エラー  
 **問題**  
  
 アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleDBBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 **原因**  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。 64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。 そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。 ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、32 ビット プロセスとして実行されるされため、アダプターのポートを構成するときに、machine.config ファイルの 32 ビット バージョンのバインドを確認エラーは失敗します。  
  
 **解決策**  
  
-   32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。  
  
    > [!IMPORTANT]
    >  64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。  
  
-   Oracle クライアント 11.1.0.6 パッチ セット 11.1.0.7 に Oracle Data Access Components の 32 ビットおよび 64 ビット両方のバージョンをインストールします。  
  
    > [!NOTE]
    >  アプリケーションは ODP.NET の最新のバージョンで動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。 詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイトです。 
  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)
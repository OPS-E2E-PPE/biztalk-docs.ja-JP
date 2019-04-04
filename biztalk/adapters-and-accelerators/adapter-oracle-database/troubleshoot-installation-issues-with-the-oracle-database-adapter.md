---
title: Oracle データベース アダプターのインストールに関する問題のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 1fff4cc7948bd05043de9d9028b2c2a39bf940b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975963"
---
# <a name="troubleshoot-installation-issues-with-the-oracle-database-adapter"></a>Oracle データベース アダプターのインストールに関する問題をトラブルシューティングします。
Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。 このセクションでは、インストールのエラーを解決するトラブルシューティング手法の使用について説明しもいくつかの既知の問題一覧表示されます。  

## <a name="logging-messages-for-setup-actions"></a>セットアップ操作ではログ メッセージ  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 さらに、セットアップには、アダプターのバインドを登録するなどの特定のカスタム アクションも実行します。 セットアップを実行する標準とカスタムの操作のメッセージを記録できます。  

- [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ MSI を使用してアダプターに固有のファイルをインストールします。 したがって、セットアップのログ記録は、標準の MSI ログです。 

- セットアップ プログラムを実行するカスタム アクションのすべてのログは %temp%\adaptersetup.log でご利用いただけます。 ログ ファイルにトレースが失敗した場合、トレースはイベント ログで使用できるもします。  

##  <a name="BKMK_OraDBBinding"></a> セットアップが失敗するアダプターのバインドを登録するには  
 **問題**  

 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドを登録に失敗するが、アダプターのインストールが続行されます。  

 **原因**  

 問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている machine.config ファイル。 アダプターのバインドは、machine.config ファイルに書き込まれます。  

 **解決方法**  

手動で登録、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド。 

1. コンピューターの machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。  

    このパスで\<バージョン\>は .NET Framework のバージョンです。  

2. テキスト エディターを使用してファイルを開きます。  

3. 登録する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド。  

   1. 要素の"system.serviceModel"を検索し、その下にある、次を追加します。  

      ```  
      <client>  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
      </client>  
      ```  

   2. "BindingElementExtensions"system.serviceModel\extensions 下の要素を検索します。  

   3. 不足している検索[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドします。 "BindingElementExtensions"ノードの下の次のセクションを追加します。  

       [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を追加します。  

      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. "BindingExtensions"system.serviceModel\extensions 下の要素を検索します。  

   5. 不足している検索[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドします。 "BindingExtensions"ノードの下の次のセクションを追加します。  

       [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を追加します。  

      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  公開キーとバージョンを確認する方法については、[公開キーとバージョンを決定する](#BKMK_PubKey)を参照してください。  

4. machine.config ファイルを保存して閉じます。  

####  <a name="BKMK_PubKey"></a> 公開キーとバージョンを決定します。  
 公開キーを確認するには、次の手順を実行[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  

1. Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  

2. 対象の公開キーと、バージョンを選び、DLL を右クリックして**プロパティ**します。 次の表に、DLL の名前[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  


   |                                  [アダプター]                                  |       DLL の名前       |
   |---------------------------------------------------------------------------|-----------------------------|
   | [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] | Microsoft.Adapters.OracleDB |


3. **全般**タブの値を比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。 同様に、値、**バージョン**ラベルは、DLL のバージョン番号を指定します。  

4. クリックして、公開キーをコピー**キャンセル**します。  

##  <a name="BKMK_ConsumeBinding"></a> Consume Adapter Service アドインまたはアダプター サービス参照の追加プラグインを使用して、64 ビットのインストール中にエラー  
 **問題**  

 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。  

```  
No valid adapters are installed on this machine  
```  

 **原因**  

 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が machine.config ファイルの System.ServiceModel で登録されている、WCF カスタム バインドします。 64 ビット プラットフォームには、2 つの machine.config ファイル、64 ビット アプリケーションで使用されるその他および 32 ビット アプリケーションによって使用されるものです。 そのため、64 ビット版をインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。 ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、起動したときにそのため、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグインのバインディングは、machine.config ファイルの 32 ビット バージョンをチェックし、失敗エラーが発生します。  

 **解決方法**  

- 32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。  

  > [!IMPORTANT]
  >  64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 32 ビットおよび 64 ビットのサイド バイ サイドでインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされていません。  

- 更新プログラム セット 11.1.0.7 で Oracle クライアント 11.1.0.6 の Oracle のデータ アクセス コンポーネントの 32 ビットおよび 64 ビット両方のバージョンをインストールします。  

  > [!NOTE]
  >  ODP.NET の最新バージョンで、アプリケーションの動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。 詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイト。  

##  <a name="BKMK_InvalidBinding"></a> BizTalk Server 管理コンソールで、64 ビット インストールで Oracle データベース アダプターのポートを構成するときに無効なバインド エラー  
 **問題**  

 アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleDBBinding".  
Verify the binding extension is registered in machine.config."  
```  

 **原因**  

 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が machine.config ファイルの System.ServiceModel で登録されている、WCF カスタム バインドします。 64 ビット プラットフォームには、2 つの machine.config ファイル、64 ビット アプリケーションで使用されるその他および 32 ビット アプリケーションによって使用されるものです。 そのため、64 ビット版をインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。 ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、32 ビット プロセスとして実行され、そのため、アダプターのポートを構成するときにチェック、machine.config ファイルの 32 ビット バージョンにバインドし失敗エラーが発生します。  

 **解決方法**  

- 32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。  

  > [!IMPORTANT]
  >  64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 32 ビットおよび 64 ビットのサイド バイ サイドでインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされていません。  

- 更新プログラム セット 11.1.0.7 で Oracle クライアント 11.1.0.6 の Oracle のデータ アクセス コンポーネントの 32 ビットおよび 64 ビット両方のバージョンをインストールします。  

  > [!NOTE]
  >  ODP.NET の最新バージョンで、アプリケーションの動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。 詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイト。 

## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)
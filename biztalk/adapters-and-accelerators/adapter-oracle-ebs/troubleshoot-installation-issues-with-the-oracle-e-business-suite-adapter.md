---
title: Oracle E-business Suite アダプターを使用したインストールの問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09b3af20-ab87-44e8-8ded-c19432552be7
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fb1d5f0e1f17870c9824b30e5da55a2740cb81b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968131"
---
# <a name="troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターを使用したインストールの問題のトラブルシューティングします。
Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。 このセクションでは、インストール エラーを解決するトラブルシューティングの手法を使用して説明します。  

## <a name="logging-messages-for-setup-actions"></a>セットアップ操作ではログ メッセージ  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 さらに、セットアップには、アダプターのバインドを登録するなどの特定のカスタム アクションも実行します。 セットアップを実行する標準とカスタムの操作のメッセージを記録できます。  

- [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ MSI を使用してアダプターに固有のファイルをインストールします。 したがって、セットアップのログ記録は、標準の MSI ログです。 [Windows インストーラーのログ記録](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx)について詳しく説明します。 

- セットアップ プログラムを実行するカスタム アクションのすべてのログは %temp%\adaptersetup.log でご利用いただけます。 ログ ファイルにトレースが失敗した場合、トレースはイベント ログで使用できるもします。  

## <a name="known-issues"></a>既知の問題  
 インストールするときに発生する可能性が最も一般的なエラーを次に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]と共に、考えられる原因と解決します。  



###  <a name="BKMK_OraAppBinding"></a> セットアップが失敗するアダプターのバインドを登録するには  
 **問題**  

 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドを登録に失敗するが、アダプターのインストールが続行されます。  

 **原因**  

 問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている machine.config ファイル。 アダプターのバインドは、machine.config ファイルに書き込まれます。  

 **解決方法**  

 手動で登録する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。  

##### <a name="to-register-the-adapter-binding"></a>アダプターのバインドを登録するには  

1. コンピューターの machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。  

    このパスで\<*バージョン*\>は .NET Framework のバージョンです。  

2. テキスト エディターを使用してファイルを開きます。  

3. 登録する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインド。  

   1. 要素の"system.serviceModel"を検索し、その下にある、次を追加します。  

      ```  
      <client>  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleebs" />  
      </client>  
      ```  

   2. "BindingElementExtensions"system.serviceModel\extensions 下の要素を検索します。  

   3. 不足している検索[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。 "BindingElementExtensions"ノードの下の次のセクションを追加します。  

       [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を追加します。  

      ```  
      <add name="oracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. "BindingExtensions"system.serviceModel\extensions 下の要素を検索します。  

   5. 不足している検索[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。 "BindingExtensions"ノードの下の次のセクションを追加します。  

       [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を追加します。  

      ```  
      <add name="oracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  公開キーとバージョンを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)します。  

4. machine.config ファイルを保存して閉じます。  

####  <a name="BKMK_PubKey"></a> 公開キーとバージョンを決定します。  
 公開キーを確認するには、次の手順を実行[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  

###### <a name="to-determine-the-public-key"></a>公開キーを確認するには  

1. Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  

2. 対象の公開キーと、バージョンを選び、DLL を右クリックして**プロパティ**します。 次の表に、DLL の名前[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  


   |                                         [アダプター]                                         |       DLL の名前        |
   |-----------------------------------------------------------------------------------------|------------------------------|
   | [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] | Microsoft.Adapters.OracleEBS |


3. **全般**タブの値を比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。 同様に、値、**バージョン**ラベルは、DLL のバージョン番号を指定します。  

4. クリックして、公開キーをコピー**キャンセル**します。  

###  <a name="BKMK_ConsumeOraApp"></a> Consume Adapter Service アドインまたはアダプター サービス参照の追加プラグインを使用して、64 ビットのインストール中にエラー  
 **問題**  

 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。  

```  
No valid adapters are installed on this machine  
```  

 **原因**  

 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]が machine.config ファイルの System.ServiceModel で登録されている、WCF カスタム バインドします。 64 ビット プラットフォームには、2 つの machine.config ファイル、64 ビット アプリケーションで使用されるその他および 32 ビット アプリケーションによって使用されるものです。 そのため、64 ビット版をインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。 ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、起動したときにそのため、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグインのバインディングは、machine.config ファイルの 32 ビット バージョンをチェックし、失敗エラーが発生します。  

 **解決方法**  

- 32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。  

  > [!IMPORTANT]
  >  64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 32 ビットおよび 64 ビットのサイド バイ サイドでインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされていません。  

- 更新プログラム セット 11.1.0.7 で Oracle クライアント 11.1.0.6 の Oracle のデータ アクセス コンポーネントの 32 ビットおよび 64 ビット両方のバージョンをインストールします。  

  > [!NOTE]
  >  ODP.NET の最新バージョンで、アプリケーションの動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。 詳細についてを参照してください"Oracle データ プロバイダーの .NET FAQ" [ http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)します。  

###  <a name="BKMK_OraAppInvalidBinding"></a> 64 ビット インストールで BizTalk Server 管理コンソールでの Oracle E-business Suite アダプターのポートを構成するときに無効なバインド エラー  
 **問題**  

 アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleEBSBinding".  
Verify the binding extension is registered in machine.config."  
```  

 **原因**  

 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]が machine.config ファイルの System.ServiceModel で登録されている、WCF カスタム バインドします。 64 ビット プラットフォームには、2 つの machine.config ファイル、64 ビット アプリケーションで使用されるその他および 32 ビット アプリケーションによって使用されるものです。 そのため、64 ビット版をインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。 ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、32 ビット プロセスとして実行され、そのため、アダプターのポートを構成するときにチェック、machine.config ファイルの 32 ビット バージョンにバインドし失敗エラーが発生します。  

 **解決方法**  

- 32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。  

  > [!IMPORTANT]
  >  64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。 32 ビットおよび 64 ビットのサイド バイ サイドでインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされていません。  

- 更新プログラム セット 11.1.0.7 で Oracle クライアント 11.1.0.6 の Oracle のデータ アクセス コンポーネントの 32 ビットおよび 64 ビット両方のバージョンをインストールします。  

  > [!NOTE]
  >  ODP.NET の最新バージョンで、アプリケーションの動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。 詳細についてを参照してください"Oracle データ プロバイダーの .NET FAQ" [ http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)します。  

## <a name="see-also"></a>参照  
[Oracle EBS アダプターのトラブルシューティング](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
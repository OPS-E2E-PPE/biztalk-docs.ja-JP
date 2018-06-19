---
title: Siebel アダプターのインストールに関する問題のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: f9f066d9-37b6-4a18-9f60-d0931ea91a18
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff49285df7e43103f2ad7441cbc82b96bb59eaa4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964872"
---
# <a name="troubleshoot-installation-issues-with-the-siebel-adapter"></a>Siebel アダプターのインストールに関する問題をトラブルシューティングします。
Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールは、コンピューター上の製品バイナリをコピーし、各アダプターのバインドを登録します。 このセクションでは、インストール エラーを解決するのには、トラブルシューティングの手法について説明します。  
  
## <a name="setup-logging"></a>セットアップのログ  
 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 さらに、セットアップでは、アダプターのバインドの登録などの特定のカスタム アクションも実行します。 セットアップで行われた標準とカスタム操作の両方のメッセージをログに記録できます。  
  
-   [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] MSI を使用してアダプターの特定ファイルをインストールします。 そのため、セットアップのログ記録は、標準の MSI ログになります。  
  
-   セットアップ プログラムによって実行されるカスタム動作のログは %temp%\adaptersetup.log 使用です。 ログ ファイルにトレースが失敗した場合、トレースもイベント ログにできます。  
  
## <a name="known-issues"></a>既知の問題  
  
### <a name="setup-fails-to-register-adapter-bindings"></a>アダプターのバインドの登録に失敗します。  
 **問題**  
  
 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、登録に失敗する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドまたは[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]アダプターのインストールが続行されますが、します。  
  
 **原因**  
  
 WCF のインストールに問題があります[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config です。 アダプターのバインドは、machine.config ファイルに書き込まれます。  
  
 **解決策**  
  
手動で登録、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドと[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]次の手順を使用します。 
  
1.  コンピューター上の machine.config ファイルに移動します。 たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。  
  
     このパスに\<バージョン\>.NET Framework のバージョンです。  
  
2.  テキスト エディターを使用してファイルを開きます。  
  
3.  登録する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインド。  
  
    1.  要素"system.serviceModel"を検索し、その下にある、次を追加します。  
  
        ```  
        <client>  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        </client>  
        ```  
  
    2.  "BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    3.  不足している検索[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドします。 "BindingElementExtensions"ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を追加します。  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  "BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。  
  
    5.  不足している検索[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドします。 "BindingExtensions"ノードの下に、次のセクションを追加します。  
  
         [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を追加します。  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
        > [!NOTE]
        >  公開キーを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。  
  
4.  登録する、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:  
  
    1.  DbProviderFactories system.data ノードの下の要素を検索します。  
  
    2.  不足している検索[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。 DbProviderFactories ノードの下の次のセクションを追加します。  
  
         [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を追加します。  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  machine.config ファイルを保存して閉じます。  
  
####  <a name="BKMK_PubKey"></a>公開キーとバージョンを決定します。  
 公開キーを確認するには、次の手順を実行[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]または[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。  
  
###### <a name="to-determine-the-public-key"></a>公開キーを確認するには  
  
1.  Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。  
  
2.  対象となる公開キーを押し、DLL を右クリックして**プロパティ**です。 次の表は、各アダプターおよびプロバイダーの Dll の名前を一覧表示します。  
  
    |アダプター/ADO プロバイダー|DLL の名前|  
    |---------------------------|---------------------|  
    |[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]|Microsoft.Adapters.Siebel|  
    |[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]|Microsoft.Data.SiebelClient|  
  
3.  **全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。 同様に、値のに対して、**バージョン**ラベルは、DLL のバージョン番号を指定します。  
  
4.  公開キーをコピーし、をクリックして**キャンセル**です。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
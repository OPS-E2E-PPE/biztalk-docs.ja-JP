---
title: インストールに関するエラー メッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, error message
- error messages, installation
ms.assetid: 593b033f-03da-43ae-a948-f87aa5e4bccd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec99a2e9f20b09c4daddad0336037c7f539782a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971920"
---
# <a name="installation-error-message"></a>インストールに関するエラー メッセージ
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service をインストールした後に、送信場所または受信場所を定義すると、次のエラーが発生する可能性があります。  
  
 メッセージング エンジンが受信 URL に追加できませんでした"\<送信/受信場所の URL\>"アダプター"TIBCO EMS"にします。 理由:"ファイルまたはアセンブリ名 TIBCO。EMS、またはその依存関係の 1 つが見つかりませんでした。"  
  
## <a name="possible-causes"></a>考えられる原因  
 通常、このエラーの原因は以下のいずれかです。  
  
### <a name="assembly-not-in-gac"></a>アセンブリが GAC に存在しない  
 BizTalk Adapter for TIBCO EMS は .NET Framework アプリケーションであり、.NET Framework アセンブリ TIBCO.EMS を使用します。 このアセンブリは、.NET Framework が実行時に特定できるように、.NET Framework グローバル アセンブリ キャッシュ (GAC) に存在している必要があります。  
  
#### <a name="solution"></a>解決方法  
 アセンブリが GAC に存在するかどうかを判断するには、コマンド プロンプトを開き、次のコマンドを入力します。  
  
 `GACUTIL /L TIBCO.EMS`  
  
 結果に項目が表示されない場合は、アセンブリを GAC に追加する必要があります。 そのためには、コマンド プロンプトを開き、ディレクトリを TIBCO EMS のインストール クライアントの \cs ディレクトリ (既定のインストール場所は C:\TIBCO\EMS\Clients\CS) に変更し、次のコマンドを実行します。  
  
 `GACUTIL /i TIBCO.EMS.DLL`  
  
### <a name="different-version-of-assembly-in-gac"></a>GAC のアセンブリのバージョンが異なる  
 TIBCO.EMS.dll アセンブリは GAC に存在していますが、バージョンが BizTalk Adapter for TIBCO EMS のビルドに使用されたバージョンとは異なります。 コンピュータにインストールされた TIBCO.EMS.dll が Version 4.2 以上の場合は、アダプタのビルドに使用されたバージョンと互換性があります (TIBCO で情報を確認できます)。  
  
#### <a name="solution"></a>解決方法  
 .NET Framework にはこの問題を回避する方法が用意されています。 呼び出された*バインディングのリダイレクト*、構成ファイルを使用します。  
  
 エラー メッセージが表示されないようにするには、次の操作を行います。  
  
1.  任意のテキスト エディタを使用して、ファイル BTSNTSVC.exe.config を開きます。  
  
     ファイルは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ディレクトリ (既定のインストール場所は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]) にあります。  
  
2.  子として、次のエントリを BTSNTSVC.exe.config ファイルに追加、 \<assemblyBinding\>要素。  
  
```  
<dependentAssembly>  
    <assemblyIdentity name='TIBCO.EMS'  
        publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
    <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
        newVersion='1.0.0.0' />  
</dependentAssembly>  
```  
  
 BTSNTSVC.exe.config ファイルが変更されていない場合、 \<assemblyBinding\>要素は次のようになりますできません。  
  
```  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
    <probing privatePath="BizTalk Assemblies;Developer  
        Tools;Tracking;Tracking\interop" />  
    <dependentAssembly>  
        <assemblyIdentity name='TIBCO.EMS'  
            publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
        <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
            newVersion='1.0.0.0' />  
    </dependentAssembly>  
</assemblyBinding>  
```  
  
1.  コマンド プロンプトでコマンドを入力:`GACUTIL /L TIBCO.EMS`です。  
  
2.  出力から TIBCO.EMS アセンブリ バージョン番号をコピーします。  
  
    > [!CAUTION]
    >  2 つのバージョン番号が表示されます。1 つは gacutil ユーティリティのバージョン番号です。 2 番目のバージョンの番号は、直後に表示する**バージョン =** です。  
  
3.  直後に、引用符の間、BTSNTSVC.exe.config ファイルにバージョン番号を貼り付け**newVersion =** (前の XML 例内の文字を太字)。  
  
4.  変更した BTSNTSVC.exe.config ファイルを保存します。  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストを再起動します。  
  
## <a name="see-also"></a>参照  
 [TIBCO Enterprise Message Service のトラブルシューティング](../core/troubleshooting-tibco-enterprise-message-service.md)
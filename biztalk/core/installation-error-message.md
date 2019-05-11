---
title: インストールに関するエラー メッセージ |Microsoft Docs
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
ms.openlocfilehash: f2513ed65a332839cf1cbeef1b64e99c169b66ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382173"
---
# <a name="installation-error-message"></a>インストールに関するエラー メッセージ
送信を定義する、TIBCO Enterprise Message Service の Microsoft BizTalk Adapter をインストールまたは受信した後、場所は、次のエラーを可能性があります。  
  
 メッセージング エンジンは、受信 URL を追加できませんでした"\<送信/受信場所 URL\>"アダプター"TIBCO EMS"にします。 理由: "ファイルまたはアセンブリ名 TIBCO。EMS、またはその依存関係の 1 つが見つかりません。"  
  
## <a name="possible-causes"></a>考えられる原因  
 このエラーは、次の原因の 1 つは、通常は。  
  
### <a name="assembly-not-in-gac"></a>アセンブリを GAC に存在しません。  
 BizTalk Adapter for TIBCO EMS は、.NET Framework アプリケーションであり、TIBCO、.NET Framework アセンブリを使用します。EMS します。 このアセンブリは、実行時に .NET Framework 用 .NET Framework グローバル アセンブリ キャッシュ (GAC) に存在する必要があります。  
  
#### <a name="solution"></a>ソリューション  
 アセンブリが GAC に存在するかどうかを判断するには、コマンド プロンプトを開きし、次のコマンドを入力します。  
  
 `GACUTIL /L TIBCO.EMS`  
  
 結果項目が表示されない場合は、GAC にアセンブリを追加する必要があります。 これを行うには、コマンド プロンプトを開き、TIBCO EMS のインストール クライアントの \cs ディレクトリ (既定のインストール場所は C:\TIBCO\EMS\Clients\CS) に移動して、次のコマンドを実行します。  
  
 `GACUTIL /i TIBCO.EMS.DLL`  
  
### <a name="different-version-of-assembly-in-gac"></a>アセンブリが GAC 内の別のバージョン  
 TIBCO します。EMS.dll アセンブリが GAC には、TIBCO EMS 用 BizTalk アダプターを構築するために使用する 1 つから別のバージョン。 場合、TIBCO します。コンピューターにインストールされている EMS.dll はから製品バージョン 4.2 以降 (TIBCO で情報を確認できます)、アダプタのビルドに使用するバージョンと互換性が必要です。  
  
#### <a name="solution"></a>ソリューション  
 .NET Framework では、この問題を回避する方法を提供します。 呼び出された*バインド リダイレクト*、構成ファイルを使用します。  
  
 エラー メッセージを削除するこれらの手順に従います。  
  
1. 任意のテキスト エディターでは、ファイル BTSNTSVC.exe.config を開きます。  
  
    ファイルがである、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディレクトリ (既定のインストール場所は: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)])。  
  
2. 子として、BTSNTSVC.exe.config ファイルに次のエントリを追加、 \<assemblyBinding\>要素。  
  
```  
<dependentAssembly>  
    <assemblyIdentity name='TIBCO.EMS'  
        publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
    <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
        newVersion='1.0.0.0' />  
</dependentAssembly>  
```  
  
 BTSNTSVC.exe.config ファイルが変更されていない場合、 \<assemblyBinding\>要素にいない次のようになります。  
  
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
  
1. コマンド プロンプトでコマンドを入力:`GACUTIL /L TIBCO.EMS`します。  
  
2. TIBCO をコピーします。EMS の出力からのアセンブリ バージョン番号。  
  
   > [!CAUTION]
   >  2 つのバージョン番号が表示されます。 1 つは gacutil ユーティリティのバージョン番号。 2 番目のバージョンの番号は、直後に表示する**バージョン =** します。  
  
3. 直後に、引用符の間、BTSNTSVC.exe.config ファイルにバージョン番号を貼り付ける**newVersion =** (前の例の XML 文字を太字)。  
  
4. 変更した BTSNTSVC.exe.config ファイルを保存します。  
  
5. 再起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト。  
  
## <a name="see-also"></a>参照  
 [TIBCO Enterprise Message Service のトラブルシューティング](../core/troubleshooting-tibco-enterprise-message-service.md)
---
title: "ルール エンジンの構成およびチューニング パラメーター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, registry keys
- registry keys
- Business Rules Engine, registry keys
- troubleshooting, business rules
- validating, business rules
- business rules, validating
ms.assetid: cb0bcffe-bbc6-4495-84d2-2a822c3413b3
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d2acc5b70f7a2be120db5159f893922135a429
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rule-engine-configuration-and-tuning-parameters"></a>ルール エンジンの構成およびチューニング パラメーター
次の表に、構成の検証およびトラブルシューティングに利用できるレジストリ キーの一覧を示します。 これらのレジストリ キーが格納されている**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BusinessRules\3.0**です。  
  
 製品を許可するものではこれらのキーに記載された最初の 3 つのキー、を除き — とユーザーではなく — をルール エンジンをカスタマイズします。 これらはすべてインストール時に作成されますが、値を設定するためのインターフェイスは提供されません。  
  
 次の表の列は、次のように定義されています。  
  
-   **名前**です。 レジストリ キーの名前。  
  
-   **説明**です。 レジストリ キーの場所と用途に関する簡単な説明。  
  
-   **構成の既定値**です。 レジストリ キーが存在しない場合に返される値。  
  
-   **インストールの既定値**です。 ルール エンジンのインストール時に BizTalk Server によって設定される値。  
  
|名前|Description|構成の既定値|インストールの既定値|  
|----------|-----------------|--------------------|---------------------|  
|InstallPath|構成時に使用される BRE ファイルの場所。|(null)|C:\Program Files\Common Files\Microsoft BizTalk (64 ビット オペレーティング システムでは C:\Program Files (x86)\Common Files\Microsoft BizTalk)|  
|DatabaseServer|使用されるデータベース サーバー。|(空の文字列)|BRE の構成時に指定されたデータベース サーバーの名前。|  
|DatabaseName|使用されるデータベース ユーザーの名前。|(空の文字列)|BRE の構成時に指定されたデータベースの名前。 通常は BizTalkRuleEngineDb。|  
|PubSubAdapterAssembly|パブリッシュ/サブスクライブ アダプターのアセンブリ名。|Microsoft.RuleEngine|Microsoft.RuleEngine|  
|PubSubAdapterClass|パブリッシュ/サブスクライブ アダプターのクラス名。|Microsoft.RuleEngine.PubSubAdapter|Microsoft.RuleEngine.PubSubAdapter|  
|DeploymentDriverAssembly|展開ドライバーのアセンブリ名。|Microsoft.RuleEngine|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|展開ドライバーのクラス名。|Microsoft.RuleEngine.RuleSetDeploymentDriver|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
|TrackingInterceptorAssembly|追跡情報インターセプターのアセンブリ名。|(空の文字列)|Microsoft.BizTalk.RuleEngineExtensions|  
|TrackingInterceptorClass|追跡情報インターセプターのクラス名。|(空の文字列)|Microsoft.BizTalk.RuleEngineExtensions.RuleSetTrackingInterceptor|  
|TranslationTimeout|ルール セットの変換に使用できる最大時間 (ミリ秒)。 **注:**これは ruleset ごとに、RuleSetConfiguration を使用してオーバーライドすることができます)。|60000 (1 分)|60000|  
|UpdateServiceName|更新サービスの名前。.NET リモート処理で、サービスを探す場合に使用されます。|RemoteUpdateService|RemoteUpdateService|  
|UpdateServiceHost|更新サービスをホストするコンピューター。.NET リモート処理で、サービスを探す場合に使用されます。 **注:**サービスが現在受信メッセージを同じコンピューターにのみに制限します。|localhost|localhost|  
|UpdateServicePort|更新サービスが使用する TCP ポート番号。.NET リモート処理で、サービスを探す場合に使用されます。|3132|3132|  
|CacheEntries|更新サービスによってキャッシュされるルール セットの最大数。|32|32|  
|CacheTimeout|更新サービス キャッシュのエントリが期限切れになるまでの時間 (秒)。|3600 (1 時間)|3600|  
|PollingInterval|更新サービスが更新のために SqlRuleStore をチェックする時間 (秒)。|60 (1 分)|60|  
|SqlTimeout|SQL ルール ストアにアクセスする SQL コマンドのタイムアウト値。 このキーの値は、次のように解釈されます。<br /><br /> < 0 - .NET の既定値 (30 秒) の使用<br /><br /> = 0 - 無限のタイムアウト<br /><br /> > 0 - クエリがタイムアウトするまでの最大時間|-1|-1|  
  
 説明したように StaticSupport をという名前のレジストリ キーを追加することもできます。[クラスの静的メンバーの呼び出し](../core/invoking-static-members-of-a-class.md)です。  
  
 レジストリの設定は、ルール エンジン インスタンスをホストする全アプリケーションに対してグローバルに適用されます。 これらのレジストリの設定は、アプリケーション レベルで、アプリケーション構成ファイルを使用して上書きすることができます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションでは、ホスト アプリケーションは BTSNTSvc.exe であり、構成ファイルは BTSNTSvc.exe.config です。これらは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール ディレクトリ内にあります。  次に示すように、アプリケーション構成ファイルで上書きする構成パラメーターに対して値を指定する必要があります。  
  
```  
<configuration>  
    <configSections>  
        <section name="Microsoft.RuleEngine" type="System.Configuration.SingleTagSectionHandler" />  
    </configSections>  
    <Microsoft.RuleEngine  
        UpdateServiceHost="localhost"  
        UpdateServicePort="3132"  
        UpdateServiceName="RemoteUpdateService"  
        CacheEntries="32"  
        CacheTimeout="3600"  
        PollingInterval="60"  
        TranslationTimeout="3600"  
        CachePruneInterval="60"  
        DatabaseServer="(localhost)"  
        DatabaseName="BizTalkRuleEngineDb"  
        SqlTimeout="-1"  
        StaticSupport="1"  
    />  
</configuration>  
```
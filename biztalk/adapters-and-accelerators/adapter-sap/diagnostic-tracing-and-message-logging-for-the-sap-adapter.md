---
title: 診断トレースと SAP アダプターのメッセージがログ記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and adapter
- tracing, within the adapter
- tracing, between the adapter and the LOB application
- troubleshooting, tracing and logging
ms.assetid: 5c60af54-896d-4873-acbf-32fbcd051ee2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 430886c524ab3f7c9dc6ca0af6f221f081a596e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373490"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-sap-adapter"></a>診断トレースと SAP アダプターのメッセージ ログ
診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。 アダプター クライアントは、3 つのレベルの診断トレースをアクティブ化できます。  
  
- アダプターのクライアントとアダプターの間  
  
- アダプター内  
  
- アダプターと基幹業務 (LOB) アプリケーションの間  
  
  このセクションでは、これらのレベルでトレースをアクティブ化についての情報を提供します。  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>アダプターのクライアントと、アダプターのトレース  
 アダプター クライアントには、アダプターのクライアントとアダプター間のトレースの問題に WCF トレースが有効にすることができます。 WCF トレースを使用して、WCF サービス モデルを使用して、アダプターのクライアントからは、シリアル化の問題の診断に役立つ入力 XML をトレースします。 WCF トレースは、WCF チャネル モデルまたはアダプター クライアントにアダプターからの出力メッセージには使用されません。 抜粋をそれぞれの構成ファイルに追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。 また、デザイン時と実行時の両方のトレースを有効にできます。  
  
- **デザイン時トレース**します。 デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。  
  
- **実行時にトレース**します。 実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
  - WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。  
  
  WCF トレースを有効にするには、内で次の抜粋を追加、`<configuration>`タグ。  
  
```  
<system.diagnostics>  
    <sources>  
      <source name ="System.ServiceModel" switchValue="Verbose">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name ="System.ServiceModel.MessageLogging"   
              switchValue="Verbose, ActivityTracing">          
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name ="System.Runtime.Serialization" switchValue="Verbose">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
   </sources>  
   <sharedListeners>  
      <add name="xml" type="System.Diagnostics.XmlWriterTraceListener"                
           traceOutputOptions="LogicalOperationStack"   
           initializeData="C:\log\WCFTrace.svclog" />  
   </sharedListeners>  
   <trace autoflush="true" />  
  </system.diagnostics>  
  <system.serviceModel>  
    <diagnostics>  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="false"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="false"/>  
    </diagnostics>      
  </system.serviceModel>  
```  
  
 これにより、WCF トレースが C:\log\WCFTrace.svclog を保存します。 WCF トレースの詳細については、次を参照してください。[トレース](https://msdn.microsoft.com/library/ms730342.aspx)します。 
  
> [!IMPORTANT]
>  トレースを有効にすると、機密性の高いビジネス データを公開することの潜在的なセキュリティ脅威を軽減することを確認します。 推奨事項を参照してください[ベスト プラクティス、SAP アダプターをセキュリティで保護する](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)します。  
  
## <a name="tracing-within-the-adapter"></a>アダプターのトレース  
 アダプターは、さまざまなカテゴリの有用な情報をエラー、警告、および情報メッセージなど、トレース ファイルにログインします。 このような情報は、アダプターの処理フローを理解し、アダプターに関する問題の診断に役立ちます。 アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターの BizTalk アプリケーションと WCF の抜粋をそれぞれの構成ファイルに追加することでモデルのアプリケーションをサービスのトレースします。 また、デザイン時と実行時の両方のトレースを有効にできます。  
  
- **デザイン時トレース**します。 デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。  
  
- **実行時にトレース**します。 実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
  - WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。  
  
  有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内の抜粋を次の追加、`<configuration>`タグ。  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.SAP" switchValue="Information">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="xml" type="System.Diagnostics.XmlWriterTraceListener"   
   traceOutputOptions="LogicalOperationStack"   
          initializeData="C:\log\AdapterTrace.svclog" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 これにより、WCF トレースが C:\log\AdapterTrace.svclog を保存します。  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a>アダプターと LOB アプリケーション間でのトレース  
 診断するには、疑いがある問題に関連する、LOB アプリケーション アダプターと LOB アプリケーション間の通信のトレースを有効にする必要があります。 アダプターは、この情報にアクセスする (クライアント/サーバー側) のトレース LOB によっても異なります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]によりアダプターでクライアント接続 URI の"RfcSdkTrace"パラメーターを指定することで、SAP システム内でトレースをオンにします。 SAP システム内のトレース情報の流れを RFC SDK を有効にするには、このパラメーターを指定する必要があります。 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
 さらに、RFC SDK トレースのレベルに設定した RFC_TRACE 環境変数を作成することもできます。 RFC_TRACE は、SAP によって定義された環境変数は、RFC SDK によって使用されます。 場合この変数が定義されていない、または 0 に設定されている場合は、最小限に抑えられますが、RFC SDK トレース レベルです。 変数が 1 または 2 に設定されている場合、トレース レベルの詳細については以上。  
  
> [!NOTE]
>  RFC_TRACE 環境変数が設定されているかに関係なく RFC SDK トレースが有効になっている*のみ*"RfcSdkTrace"パラメーターに設定されている場合、接続 URI の場合は true。 この環境変数の値は、RFC SDK トレースのレベルのみを制御します。 RfcSdkTrace が設定されている場合は true、メッセージをアダプターと SAP システムの間のトレースは、コンピューターに"system32"フォルダーにコピーされます。 別の場所に、RFC SDK トレースを保存するには、RFC_TRACE_DIR の環境変数を設定することができます。 これらの環境変数の詳細については、SAP のマニュアルを参照してください。  
  
## <a name="viewing-the-traces"></a>トレースを表示します。  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 ツールの詳細については、次を参照してください。[相関トレースの表示と問題のサービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)します。
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk Server 管理コンソールを使用するポートと受信ポートの送信ポートなどのアイテムのさまざまな追跡オプションを構成することができます。 追跡構成設定を使用すると、受信と送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 BizTalk アプリケーションの追跡を構成する方法の詳細については、次を参照してください。、[管理成果物](../../core/managing-artifacts.md)します。
  
 履歴および追跡したデータを表示するのに状態と動作状況の追跡 (HAT) を使用することもできます。 詳細については、次を参照してください。[履歴の表示と追跡データ](../../core/viewing-historical-and-tracked-data.md)します。
 
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)
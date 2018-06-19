---
title: 診断トレースとメッセージ ログを SAP アダプターの |Microsoft ドキュメント
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
ms.openlocfilehash: beb5565141521c08e295a9d5cee88406c16df7de
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007176"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-sap-adapter"></a>診断トレースと SAP アダプターのメッセージ ログ
診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。 アダプターのクライアントは、3 つのレベルでの診断のトレースをアクティブ化できます。  
  
-   アダプターのクライアントとアダプター間で  
  
-   アダプター内  
  
-   アダプターと基幹業務 (LOB) アプリケーションの間  
  
 このセクションでは、これらのレベルでトレースをアクティブ化に関する情報を提供します。  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>アダプターのクライアントとアダプター間でのトレース  
 アダプターのクライアントは、アダプターのクライアントとアダプター間のトレースの問題への WCF トレースを有効にできます。 WCF トレースは、WCF サービス モデルを使用して、アダプターのクライアントから取得し、シリアル化の問題の診断に役立つは入力 XML の追跡に使用します。 WCF トレースは、WCF チャネル モデルまたはアダプターのクライアントに、アダプターからの出力メッセージには使用されません。 それぞれの構成ファイルの抜粋を追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。 また、デザイン時と実行時の両方でトレースを有効にできます。  
  
-   **デザイン時にトレース**です。 デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>* \Common7\IDE です。  
  
-   **実行時にトレース**です。 実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
    -   WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。  
  
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
  
 これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。 WCF トレースの詳細については、次を参照してください。[トレース](https://msdn.microsoft.com/library/ms730342.aspx)です。 
  
> [!IMPORTANT]
>  トレースを有効にすると、機密のビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。 推奨事項を参照してください[ベスト プラクティス、SAP アダプターをセキュリティで保護する](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)です。  
  
## <a name="tracing-within-the-adapter"></a>アダプターのトレース  
 アダプターは、エラー、警告、および情報メッセージなど、トレース ファイルに有用な情報のさまざまなカテゴリをログオンします。 このような情報は、アダプター内のプロセス フローを理解し、アダプターに関する問題の診断に役立ちます。 アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターが BizTalk アプリケーションと WCF サービスの抜粋をそれぞれの構成ファイルに追加することによってモデル アプリケーション用にトレースされます。 また、デザイン時と実行時の両方でトレースを有効にできます。  
  
-   **デザイン時にトレース**です。 デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>* \Common7\IDE です。  
  
-   **実行時にトレース**です。 実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
    -   WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。  
  
 有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内で次の抜粋を追加、`<configuration>`タグ。  
  
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
  
 これは、C:\log\AdapterTrace.svclog に WCF トレースを保存します。  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a>アダプターと LOB アプリケーション間でのトレース  
 診断と思われる問題アダプターと、LOB アプリケーション間の通信のトレースを有効にする必要があります、LOB アプリケーションに関連付けられます。 アダプターは、この情報にアクセスする (クライアントとサーバー側) をトレース LOB によっても異なります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントが接続 URI の"RfcSdkTrace"パラメーターを指定することで、SAP システム内のトレースを有効にできるようにします。 RFC SDK SAP システム内のトレース情報のフローを有効にするには、このパラメーターを指定する必要があります。 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
 さらに、RFC SDK トレースのレベルに設定した RFC_TRACE 環境変数を作成することもできます。 RFC_TRACE が SAP で定義されている環境変数であるし、RFC SDK を使用しています。 この変数は定義されていないか、0 に設定されている、RFC SDK トレース レベルが最低限のものです。 変数が 1 または 2 に設定されている場合は、トレース レベルの詳細になります。  
  
> [!NOTE]
>  RFC_TRACE 環境変数が設定されているかに関係なく、RFC SDK トレースが有効になっている*のみ*"RfcSdkTrace"パラメーターに設定されている場合、接続 URI の場合は true です。 この環境変数の値は、RFC SDK トレースのレベルのみを制御します。 RfcSdkTrace が設定されている場合は true、メッセージをアダプターと、SAP システムの間でのトレースがコンピューターに"system32"フォルダーにコピーされます。 他の場所に、RFC SDK トレースを保存するには、RFC_TRACE_DIR 環境変数を設定することができます。 これらの環境変数の詳細については、SAP のマニュアルを参照してください。  
  
## <a name="viewing-the-traces"></a>トレースの表示  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 ツールの詳細については、次を参照してください。[相関トレースの表示とトラブル サービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)です。
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk Server 管理コンソールでは、受信ポートと送信ポートなどの項目に対してさまざまな追跡オプションを構成できます。 追跡構成設定を使用すると、着信および発信のイベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 BizTalk アプリケーションの追跡の構成の詳細については、次を参照してください。、[成果物の管理](../../core/managing-artifacts.md)です。
  
 また、履歴および追跡したデータを表示するのに状態と動作状況の追跡 (HAT) を使用することができます。 詳細については、次を参照してください。[履歴の表示と追跡データ](../../core/viewing-historical-and-tracked-data.md)です。
 
## <a name="see-also"></a>参照  
[SAP アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)
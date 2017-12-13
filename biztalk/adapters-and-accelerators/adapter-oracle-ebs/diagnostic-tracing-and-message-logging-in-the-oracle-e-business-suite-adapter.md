---
title: "診断トレースと Oracle E-business Suite アダプターでメッセージのログ記録 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0d6be2a-cbd0-4c9c-be6f-9631063346e2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de2444cecbd661e9af4457f5f19c7e929d1c9c5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter"></a>診断トレースと Oracle E-business Suite アダプターでメッセージのログ記録
診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。 このトピックではサポートされてトレースの次の 3 種類に関する情報を提供する[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
-   クライアント識別子を使用して oracle サーバー側のトレース
  
-   アダプターのクライアントとアダプター間での WCF トレース
  
-   アダプター内で WCF トレース
 
## <a name="oracle-server-side-tracing-using-a-client-identifier"></a>Oracle サーバー側トレースを使用して、クライアント識別子  
 Oracle では、Oracle データベースでのクライアント アプリケーションによって実行される操作のサーバー側トレースを実行することができます。 クライアント アプリケーションからの要求は、別のデータベース セッションにルーティングすることができます、いるため、要求の発生元を追跡するが困難になります。 ただし、Oracle では、クライアント識別子を使用してエンド ツー エンドのアプリケーションのトレースが容易になります。 
 
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 `OracleConnectionClientId` Oracle への接続にアダプターによって使用される接続のデザイン時にクライアント識別子を指定できるようにするプロパティをバインドします。 アダプター クライアント識別子では、Oracle、上のアダプターのクライアントによって実行される操作のトレースを選択的に役立つし、フィルター処理して、クライアント識別子に基づく Oracle サーバーのトレースを表示することもできます。 Oracle ではクライアント識別子のトレースを有効にする方法については、次を参照してください。 [http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746)です。  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a>アダプターのクライアントとアダプター間での WCF トレース  
 アダプターのクライアントは、アダプターのクライアントとアダプター間のトレースの問題への WCF トレースを有効にできます。 WCF トレースは、WCF サービス モデルを使用して、アダプターのクライアントから取得し、シリアル化の問題の診断に役立つは入力 XML の追跡に使用します。 WCF トレースは、WCF チャネル モデルまたはアダプターのクライアントに、アダプターからの出力メッセージには使用されません。 それぞれの構成ファイルの抜粋を追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。 また、デザイン時と実行時の両方でトレースを有効にできます。  
  
-   **デザイン時にトレース**です。 デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>*\Common7\IDE です。  
  
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
  
 これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。 [WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)詳しく説明します。  
  
> [!IMPORTANT]
>  トレースを有効にする場合に発生することが重要なビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。 推奨事項については、次を参照してください。、[メッセージとインスタンス データ追跡のベスト プラクティス](../../core/best-practices-for-message-and-instance-data-tracking.md)です。  
  
## <a name="wcf-tracing-within-the-adapter"></a>アダプター内で WCF トレース  
 アダプターは、エラー、警告、および情報メッセージなど、トレース ファイルに有用な情報のさまざまなカテゴリをログオンします。 このような情報は、アダプター内のプロセス フローを理解し、アダプターに関する問題の診断に役立ちます。 アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターが BizTalk アプリケーションと WCF サービスの抜粋をそれぞれの構成ファイルに追加することによってモデル アプリケーション用にトレースされます。 また、デザイン時と実行時の両方でトレースを有効にできます。  
  
-   **デザイン時にトレース**です。 デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>*\Common7\IDE です。  
  
-   **実行時にトレース**です。 実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。[!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)]、このファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)]です。 BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
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
      <source name="Microsoft.Adapters.OracleEBS" switchValue="Information">  
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
  
## <a name="viewing-the-traces"></a>トレースの表示  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 [サービス トレース ビューアーを使用して相関トレースの表示とトラブルシューティング](https://msdn.microsoft.com/library/aa751795.aspx)このツールの詳細を提供します。  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk Server 管理コンソールでは、受信ポートと送信ポートなどの項目に対してさまざまな追跡オプションを構成できます。 追跡構成設定を使用すると、着信および発信のイベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 BizTalk アプリケーションの追跡の構成の詳細については、次を参照してください。[管理し、成果物を追跡](../../core/managing-artifacts.md)です。  
  
 グループ ハブを使用することもできます。[メッセージとインスタンス データの履歴を表示](../../core/viewing-tracked-message-and-instance-data.md)、などのベスト プラクティスは、追跡クエリ、および詳細を保存します。
  
## <a name="see-also"></a>参照  
[アダプターのトラブルシューティング](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
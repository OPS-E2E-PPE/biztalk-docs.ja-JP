---
title: "診断トレースと SQL アダプターでメッセージのログ記録 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6599b4d-5650-4592-96af-ee43fb36357d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff799af25c6ba74301eeab19eb793c2e84fd90e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="diagnostic-tracing-and-message-logging-in-the-sql-adapter"></a>診断トレースと SQL アダプターでメッセージのログ記録
診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。 アダプターのクライアントは、2 つのレベルの診断トレースをアクティブ化できます。  
  
-   アダプターのクライアントとアダプター間で  
  
-   アダプター内  
  
 このセクションでは、これらのレベルでトレースをアクティブ化に関する情報を提供します。  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>アダプターのクライアントとアダプター間でのトレース  
 アダプターのクライアントは、アダプターのクライアントとアダプター間のトレースの問題への WCF トレースを有効にできます。 WCF トレースは、WCF サービス モデルを使用して、アダプターのクライアントから取得し、シリアル化の問題の診断に役立つは入力 XML の追跡に使用します。 WCF トレースは、WCF チャネル モデルまたはアダプターのクライアントに、アダプターからの出力メッセージには使用されません。 それぞれの構成ファイルの抜粋を追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。 また、デザイン時に両方のトレースを有効にし、実行時できます。  
  
-   **デザイン時にトレース**です。 デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ >*: \Program Files\Microsoft Visual Studio  *\<バージョン >*\Common7\IDE です。  
  
-   **実行時にトレース**です。 実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション、BizTalk 構成ファイル、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。[!INCLUDE[prague](../../includes/prague-md.md)]、このファイルは通常 \<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[prague](../../includes/prague-md.md)]です。  
  
    -   WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。  
  
 WCF トレースを有効にするには、内で次の抜粋を追加、`<configuration>`タグ。  
  
```  
\<system.diagnostics>  
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
  \</system.diagnostics>  
  \<system.serviceModel>  
    <diagnostics>  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="false"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="false"/>  
    </diagnostics>      
  \</system.serviceModel>  
```  
  
 これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。 WCF トレースの詳細については、次を参照してください。[トレース](https://msdn.microsoft.com/library/ms730342.aspx)です。  
  
> [!IMPORTANT]
>  トレースを有効にすると、機密のビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。 推奨事項を参照してください[ベスト プラクティスは、SQL アダプタをセキュリティで保護する](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)です。
  
## <a name="tracing-within-the-adapter"></a>アダプターのトレース  
 アダプターは、エラー、警告、および情報メッセージなど、トレース ファイルに有用な情報のさまざまなカテゴリをログオンします。 このような情報は、アダプター内のプロセス フローを理解し、アダプターに関する問題の診断に役立ちます。 アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターが BizTalk アプリケーションと WCF サービスの抜粋をそれぞれの構成ファイルに追加することによってモデル アプリケーション用にトレースされます。 また、デザイン時に両方のトレースを有効にし、実行時できます。  
  
-   **デザイン時にトレース**です。 デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ >*: \Program Files\Microsoft Visual Studio  *\<バージョン >*\Common7\IDE です。  
  
-   **実行時にトレース**です。 実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション、BizTalk 構成ファイル、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]、このファイルは通常 \<インストール ドライブ >: \Program Files\Microsoft[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]です。  
  
    -   WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。  
  
 有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内で次の抜粋を追加、`<configuration>`タグ。  
  
```  
\<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.Sql" switchValue="Information">  
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
  \</system.diagnostics>  
```  
  
 これは、C:\log\AdapterTrace.svclog に WCF トレースを保存します。  
  
## <a name="viewing-the-traces"></a>トレースの表示  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 ツールの詳細については、次を参照してください。[相関トレースの表示とトラブル サービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)です。
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk Server 管理コンソールでは、受信ポートと送信ポートなどの項目に対してさまざまな追跡オプションを構成できます。 追跡構成設定を使用すると、着信および発信のイベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 BizTalk アプリケーションの追跡の構成の詳細については、次を参照してください。、[成果物の管理](../../core/managing-artifacts.md)です。
  
 また、履歴および追跡したデータを表示するのに状態と動作状況の追跡 (HAT) を使用することができます。 詳細については、次を参照してください。[履歴の表示と追跡データ](../../core/viewing-historical-and-tracked-data.md)です。
  
## <a name="see-also"></a>参照  
 [SQL アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
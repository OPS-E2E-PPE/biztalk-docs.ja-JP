---
title: "診断トレースとメッセージ ログを Siebel アダプターの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and the adapter
- logging, troubleshooting
- troubleshooting, tracing and message logging
- tracing, between the adapter and the LOB application
- message logging, troubleshooting
- tracing, troubleshooting
ms.assetid: fd2de692-45b7-45bc-b79c-381f3b1cf592
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6b27dd6d169c9ea7e5012be3e03329e6888522
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a>診断トレースと Siebel アダプターのメッセージ ログ
アダプターのクライアントを効果的に診断アダプターを使用するときに発生する問題の診断トレーシングを有効にできます。 アダプターのクライアントは、次の 3 つの異なるレベルでトレースをアクティブ化できます。  
  
-   アダプターのクライアントとアダプター間で  
  
-   アダプター内  
  
-   アダプターと基幹業務 (LOB) アプリケーションの間  
  
 このセクションでは、これらのレベルでトレースをアクティブ化に関する情報を提供します。  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>アダプターのクライアントとアダプター間でのトレース  
 アダプターのクライアントは、アダプターのクライアントとアダプター間のトレースの問題への WCF トレースを有効にできます。 WCF トレースは、アダプターを WCF サービス モデルを使用してクライアントからの入力 Xml の追跡に使用し、シリアル化の問題を診断する際に便利です。 WCF トレースは、WCF チャネル モデルまたはアダプターのクライアントに、アダプターからの出力メッセージには使用されません。 それぞれの構成ファイルの抜粋を追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。 また、デザイン時と実行時の両方でトレースを有効にできます。  
  
-   **デザイン時にトレース**です。 デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>*\Common7\IDE です。  
  
-   **実行時にトレース**です。 実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
    -   WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。  
  
 WCF トレースを有効にするには、内で次の抜粋を追加する必要があります、`<configuration>`タグ。
  
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
  
 これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。 [WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)詳細な情報を提供します。
  
> [!IMPORTANT]
>  トレースを有効にすると、機密のビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。 参照してください[ベスト プラクティス Siebel アダプターをセキュリティで保護するには](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md) 
  
## <a name="tracing-within-the-adapter"></a>アダプターのトレース  
 BizTalk Adapter Pack のアダプターは、エラー、警告、および情報など、トレース ファイルに有用な情報のさまざまなカテゴリをログインします。 このような情報は、アダプター内のプロセス フローを理解し、アダプターに関する問題の診断に役立ちます。 アクティブ化できます[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターが BizTalk アプリケーションと WCF サービスの抜粋をそれぞれの構成ファイルに追加することによってモデル アプリケーション用にトレースされます。 また、デザイン時と実行時の両方でトレースを有効にできます。  
  
-   **デザイン時にトレース**です。 デザイン時機能を使用することは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 これらすべてのツールを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 そのため、デザイン時の操作のトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: \Program Files\Microsoft Visual Studio *\<バージョン\>*\Common7\IDE です。  
  
-   **実行時にトレース**です。 実行時のトレースを使用しているアプリケーションによっては抜粋を追加する必要があります。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションに BizTalk 構成ファイルで、通常 BTSNTSvc.exe.config の抜粋を追加する必要があります。BizTalk Server のこのファイルは通常 \<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
    -   WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルの抜粋を追加する必要があります。  
  
 有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内で次の抜粋を追加する必要があります、`<configuration>`タグ。  
  
```  
<system.diagnostics>  
    <sources>  
      <source name="Microsoft.ServiceModel.Channels" switchValue="Error">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="Microsoft.Adapters.Siebel" switchValue="Information">  
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
  
 これでは、WCF トレースを C:\log\AdapterTrace.svclog に保存します。  
  
## <a name="tracing-between-the-adapter-and-the-lob-application"></a>アダプターと LOB アプリケーション間でのトレース  
 アダプターと LOB アプリケーション内で疑いがある問題を診断する LOB アプリケーション間の通信のトレースを有効にする必要があります。 アダプターは、この情報にアクセスする (クライアントとサーバー側) をトレース LOB によっても異なります。 オンにする LOB トレースの詳細については、このドキュメントから除外されます。  
  
 さらに、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインディング プロパティを提供 (**ログデータ**) に設定した場合どの**True**トレース レベルに設定されている場合と**Verbose**、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターと Siebel システム間で情報のフローをログに記録します。 この情報は、同じトレース ファイルでアダプターのトレースと共に記録されます。  
  
 このバインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。  
  
## <a name="viewing-the-traces"></a>トレースの表示  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 ツールの詳細については、次を参照してください。[相関トレースの表示とトラブルシューティング サービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)です。  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk 管理コンソールを使用すると、受信ポート、送信ポートなどのさまざまな追跡オプションを構成できます。 追跡構成設定を有効にすると、受信/送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 BizTalk アプリケーションの追跡の構成の詳細については、次を参照してください。[成果物の管理](../../core/managing-artifacts.md)です。
  
グループ ハブを使用することもできます。[追跡メッセージを表示し、インスタンス データ](../../core/viewing-tracked-message-and-instance-data.md)追跡チェックリストについては、およびベスト プラクティスを含め、します。
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
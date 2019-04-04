---
title: 診断トレースとメッセージの Siebel アダプターのログ記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing, between the adapter client and the adapter
- logging, troubleshooting
- troubleshooting, tracing and message logging
- tracing, between the adapter and the LOB application
- message logging, troubleshooting
- tracing, troubleshooting
ms.assetid: fd2de692-45b7-45bc-b79c-381f3b1cf592
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ab369a74058f374ee229eb25d0697dc96f539ed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994579"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-siebel-adapter"></a>診断トレースとメッセージ ログの Siebel アダプターの
アダプター クライアントには、実質的に、アダプターの使用時に発生する問題を診断する診断トレースが有効にすることができます。 アダプター クライアントは、次の 3 つの異なるレベルでトレースをアクティブ化できます。  
  
- アダプターのクライアントとアダプターの間  
  
- アダプター内  
  
- アダプターと基幹業務 (LOB) アプリケーションの間  
  
  このセクションでは、これらのレベルでトレースをアクティブ化についての情報を提供します。  
  
## <a name="tracing-between-the-adapter-client-and-the-adapter"></a>アダプターのクライアントと、アダプターのトレース  
 アダプター クライアントには、アダプターのクライアントとアダプター間のトレースの問題に WCF トレースが有効にすることができます。 WCF のトレースはアダプターを WCF サービス モデルを使用してクライアントからの入力 Xml をトレースするために使用し、シリアル化の問題の診断に役立つ。 WCF トレースは、WCF チャネル モデルまたはアダプター クライアントにアダプターからの出力メッセージには使用されません。 抜粋をそれぞれの構成ファイルに追加することで、BizTalk アプリケーションと WCF サービス モデルのアプリケーションの WCF トレースをアクティブにできます。 また、デザイン時と実行時の両方のトレースを有効にできます。  
  
- **デザイン時トレース**します。 デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。  
  
- **実行時にトレース**します。 実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
  - WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。  
  
  WCF トレースを有効にするには、内の次の抜粋を追加する必要があります、`<configuration>`タグ。
  
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
  
 これにより、WCF トレースが C:\log\WCFTrace.svclog を保存します。 [WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)詳細情報を提供します。
  
> [!IMPORTANT]
>  トレースを有効にすると、機密性の高いビジネス データを公開することの潜在的なセキュリティ脅威を軽減することを確認します。 参照してください[ベスト プラクティス、Siebel アダプターをセキュリティで保護するには](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md) 
  
## <a name="tracing-within-the-adapter"></a>アダプターのトレース  
 BizTalk Adapter Pack アダプターでは、さまざまなカテゴリの有用な情報をエラー、警告、および情報など、トレース ファイルにログインします。 このような情報は、アダプターの処理フローを理解し、アダプターに関する問題の診断に役立ちます。 アクティブ化できます[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターの BizTalk アプリケーションと WCF の抜粋をそれぞれの構成ファイルに追加することでモデルのアプリケーションをサービスのトレースします。 また、デザイン時と実行時の両方のトレースを有効にできます。  
  
- **デザイン時トレース**します。 デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。  
  
- **実行時にトレース**します。 実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
  - WCF サービス モデル .NET アプリケーションのプロジェクトの app.config ファイルに抜粋を追加する必要があります。  
  
  有効にする[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターのトレース、内の次の抜粋を追加する必要があります、`<configuration>`タグ。  
  
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
 アダプターと LOB アプリケーション内で疑いがある問題を診断する LOB アプリケーション間の通信のトレースを有効にする必要があります。 アダプターは、この情報へのアクセスを取得する (クライアント/サーバー側) のトレース LOB によっても異なります。 LOB のトレースの有効化の詳細については、このドキュメントから除外されます。  
  
 さらに、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドのプロパティを提供します (**ログデータ**) に設定する場合**True**トレース レベル設定されている場合と**Verbose**、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターと Siebel システム間の情報フローのログを記録します。 この情報は、同じトレース ファイルにアダプターのトレースと共に記録されます。  
  
 このバインドのプロパティの詳細については、[for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)を参照してください。  
  
## <a name="viewing-the-traces"></a>トレースを表示します。  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 ツールの詳細については、[相関トレースの表示とトラブルシューティングのサービス トレース ビューアーを使用して](https://msdn.microsoft.com/library/aa751795.aspx)を参照してください。  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk 管理コンソールでは受信ポートは、送信ポートなどのさまざまな追跡オプションを構成することができます。 追跡の構成設定を使用すると、受信/送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 BizTalk アプリケーションの追跡を構成する方法の詳細については、[管理成果物](../../core/managing-artifacts.md)を参照してください。
  
グループ ハブを使用することもできます。[追跡メッセージを表示し、インスタンス データ](../../core/viewing-tracked-message-and-instance-data.md)追跡チェックリスト、およびベスト プラクティスなど。
  
## <a name="see-also"></a>参照  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
---
title: 診断トレースと Oracle データベース アダプターのメッセージのログ記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing
- message logging
- tracing, within the adapter
- tracing, between the adapter client and the adapter
ms.assetid: 971d34e4-5609-42c6-85b9-d9b1989fc47d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e9de4c43e6f1721297b522ae76f5876731aa997
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013403"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter"></a>診断トレースとメッセージ ログの Oracle Database アダプター
診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。 このトピックでは、次の 2 種類のトレースではサポートに関する情報を提供[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
-   アダプターのクライアントとアダプター間での WCF トレース  
  
-   アダプターの WCF トレース  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a>アダプターのクライアントとアダプター間での WCF トレース  
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
  
 これにより、WCF トレースが C:\log\WCFTrace.svclog を保存します。 [WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)適切な情報を提供します。
  
> [!IMPORTANT]
>  トレースを有効にすると、機密性の高いビジネス データを公開することの潜在的なセキュリティ脅威を軽減することを確認します。 推奨事項は、次を参照してください[ベスト プラクティス、Oracle Database アダプターをセキュリティで保護するには。](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)
  
## <a name="wcf-tracing-within-the-adapter"></a>アダプターの WCF トレース  
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
      <source name=" Microsoft.Adapters.OracleDB" switchValue="Information">  
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
  
## <a name="viewing-the-traces"></a>トレースを表示します。  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 参照してください[相関トレースの表示は、サービス トレース ビューアーを使用して、トラブルシューティング](https://msdn.microsoft.com/library/aa751795.aspx)します。
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk Server 管理コンソールを使用するポートと受信ポートの送信ポートなどのアイテムのさまざまな追跡オプションを構成することができます。 追跡構成設定を使用すると、受信と送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 [アイテムの管理](../../core/managing-artifacts.md)詳細情報が含まれています。 

  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)
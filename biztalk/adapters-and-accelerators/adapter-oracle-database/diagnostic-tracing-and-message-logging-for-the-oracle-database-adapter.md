---
title: 診断トレースとメッセージ ログ、Oracle データベース アダプターの |Microsoft ドキュメント
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
ms.openlocfilehash: 1d3b7dc5c4feb78abb71360de4497aa20c9e9638
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006195"
---
# <a name="diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter"></a>診断トレースと Oracle データベース アダプターのメッセージ ログ
診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。 このトピックは次の 2 種類のでサポートされているトレースに関する情報を提供[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]:  
  
-   アダプターのクライアントとアダプター間での WCF トレース  
  
-   アダプター内で WCF トレース  
  
## <a name="wcf-tracing-between-the-adapter-client-and-the-adapter"></a>アダプターのクライアントとアダプター間での WCF トレース  
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
  
 これは、C:\log\WCFTrace.svclog に WCF トレースを保存します。 [WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)適切な詳細を提供します。
  
> [!IMPORTANT]
>  トレースを有効にすると、機密のビジネス データを公開するための潜在的なセキュリティ上の脅威を軽減することを確認してください。 推奨事項については、次を参照してください[ベスト プラクティス、Oracle データベース アダプターをセキュリティで保護するには。](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)
  
## <a name="wcf-tracing-within-the-adapter"></a>アダプター内で WCF トレース  
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
  
 これは、C:\log\AdapterTrace.svclog に WCF トレースを保存します。  
  
## <a name="viewing-the-traces"></a>トレースの表示  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 参照してください[相関トレースの表示は、サービス トレース ビューアーを使用して、トラブルシューティング](https://msdn.microsoft.com/library/aa751795.aspx)です。
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk Server 管理コンソールでは、受信ポートと送信ポートなどの項目に対してさまざまな追跡オプションを構成できます。 追跡構成設定を使用すると、着信および発信のイベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 [成果物の管理](../../core/managing-artifacts.md)詳細な情報が含まれています。 

  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)
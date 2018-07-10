---
title: 診断トレースと Oracle E-business Suite アダプターでメッセージのログ記録 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0d6be2a-cbd0-4c9c-be6f-9631063346e2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00bf78bcc7c6589889691de7ec6c20621f1883ee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985955"
---
# <a name="diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter"></a>診断トレースと Oracle E-business Suite アダプターでメッセージのログ記録
診断トレースは、効果的にアダプターを使用するときに発生する可能性がある問題を診断するのに役立ちます。 このトピックでは、次の 3 種類のトレースではサポートに関する情報を提供[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:  
  
-   クライアント識別子を使用して oracle サーバー側のトレース
  
-   アダプターのクライアントとアダプター間での WCF トレース
  
-   アダプターの WCF トレース
 
## <a name="oracle-server-side-tracing-using-a-client-identifier"></a>クライアント識別子を使用して oracle サーバー側トレース  
 Oracle では、Oracle データベースでのクライアント アプリケーションによって実行される操作のサーバー側トレースを実行できます。 クライアント アプリケーションからの要求は、別のデータベース セッションにルーティング可能であるため、要求の送信元のトレースが困難になります。 ただし、Oracle では、クライアント識別子を使用してエンド ツー エンド アプリケーションのトレースが容易になります。 
 
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開、 `OracleConnectionClientId` Oracle に接続するアダプターによって使用される接続のデザイン時にクライアント識別子を指定できるプロパティをバインドします。 アダプターのクライアント識別子では、Oracle でアダプター クライアントによって実行される操作のトレースを選択的に役立つをフィルター処理して、クライアント識別子に基づく Oracle サーバーのトレースを表示することもできます。 Oracle ではクライアント識別子のトレースを有効にする方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/p/?LinkId=135746](http://go.microsoft.com/fwlink/p/?LinkId=135746)します。  
  
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
  
 これにより、WCF トレースが C:\log\WCFTrace.svclog を保存します。 [WCF トレース](https://msdn.microsoft.com/library/ms730342.aspx)詳細に説明します。  
  
> [!IMPORTANT]
>  トレースを有効にする場合に生じるおそれのある機密性の高いビジネス データを公開することの潜在的なセキュリティ脅威を軽減することを確認します。 推奨事項は、次を参照してください。、[メッセージとインスタンス データ追跡のベスト プラクティス](../../core/best-practices-for-message-and-instance-data-tracking.md)します。  
  
## <a name="wcf-tracing-within-the-adapter"></a>アダプターの WCF トレース  
 アダプターは、さまざまなカテゴリの有用な情報をエラー、警告、および情報メッセージなど、トレース ファイルにログインします。 このような情報は、アダプターの処理フローを理解し、アダプターに関する問題の診断に役立ちます。 アクティブ化することができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]とアダプターの BizTalk アプリケーションと WCF の抜粋をそれぞれの構成ファイルに追加することでモデルのアプリケーションをサービスのトレースします。 また、デザイン時と実行時の両方のトレースを有効にできます。  
  
- **デザイン時トレース**します。 デザイン時動作は、使用することがあります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 これらすべてのツールから使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 そのため、デザイン時エクスペリエンスのトレースを有効にする必要がありますに追加する抜粋にある devenv.exe.config ファイル*\<インストール ドライブ\>*: Visual Studio \Program Files\Microsoft *\<バージョン\>* \Common7\IDE です。  
  
- **実行時にトレース**します。 実行時のトレースを使用するアプリケーションに応じて抜粋を追加する必要があります。  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションでは、BizTalk 構成ファイルで、通常は BTSNTSvc.exe.config に抜粋を追加する必要があります。[!INCLUDE[btsbiztalkserver2006r2](../../includes/btsbiztalkserver2006r2-md.md)]、このファイルは通常 [\<インストール ドライブ\>: \Program Files\Microsoft[!INCLUDE[btsBizTalkServer2006](../../includes/btsbiztalkserver2006-md.md)]します。 BizTalk server では、このファイルは通常で使用可能な\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。  
  
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
  
 これにより、WCF トレースが C:\log\AdapterTrace.svclog を保存します。  
  
## <a name="viewing-the-traces"></a>トレースを表示します。  
 Windows Communication Foundation (WCF) サービス トレース ビューアー ツールを使用するには、トレースを表示します。 [サービス トレース ビューアーを使用して相関トレースの表示とトラブルシューティングの](https://msdn.microsoft.com/library/aa751795.aspx)このツールの詳細が示されます。  
  
## <a name="configuring-tracking-for-biztalk-applications"></a>BizTalk アプリケーションの追跡の構成  
 BizTalk Server 管理コンソールを使用するポートと受信ポートの送信ポートなどのアイテムのさまざまな追跡オプションを構成することができます。 追跡構成設定を使用すると、受信と送信イベント データ、メッセージのプロパティ、メッセージ本文、およびオーケストレーションを追跡します。 BizTalk アプリケーションの追跡を構成する方法の詳細については、次を参照してください。[の管理と追跡、アーティファクト](../../core/managing-artifacts.md)します。  
  
 グループ ハブを使用することもできます。[追跡対象のメッセージとインスタンス データを表示する](../../core/viewing-tracked-message-and-instance-data.md)、追跡クエリでは、その他の保存のベスト プラクティスなど。
  
## <a name="see-also"></a>参照  
[アダプターのトラブルシューティング](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)
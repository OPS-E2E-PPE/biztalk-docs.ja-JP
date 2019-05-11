---
title: ファイルのインベントリ サービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, file inventory
ms.assetid: 32c25372-31e1-4059-b4ed-f12e62f315d5
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 172d3d1495b14655f66a9ce11e616a3cb456dcab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345491"
---
# <a name="file-inventory-for-the-service-oriented-solution"></a>ファイルのインベントリ サービス指向ソリューション
このセクションでは、サブディレクトリ、およびサービス指向ソリューションのソース ファイルを示します。 サービス指向ソリューションのソース ファイルの既定のインストール ディレクトリは[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \scenarios\so です。 次の表では、このパスを交換する前に説明\<インストール ディレクトリ\>します。  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln  
  
|ファイル|説明|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.sln|Visual Studio ソリューション ファイルです。|  
|ReplacePKToken.vbs|ソリューションのビルド時に、ソリューション ファイルに公開キー トークンを修正する VBScript です。|  
|ReplacePKToken.wsf|ReplacePKToken VBScript 用の Windows スクリプト ファイル。|  
|SetupBTSSoln.bat|公開キーを作成し、公開キーへの参照の更新ソリューションをコンパイルします。 ソリューションのデプロイについては、次を参照してください。[サービス指向ソリューションを展開する](../core/deploying-the-service-oriented-solution.md)します。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\BAM  
  
|ファイル|説明|  
|----------|-----------------|  
|ServiceLevelTracking.xls|BAM データの Excel スプレッドシートです。|  
|ServiceLevelTracking.xml|BAM のデータ項目の種類を定義するスキーマです。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\Bindings  
  
|ファイル|説明|  
|----------|-----------------|  
|AdapterSOAOrchBindings.xml|ソリューションのアダプター バージョンのファイルをバインドします。|  
|InlineSOAOrchBindings.xml|ソリューションのインライン バージョンのファイルをバインドします。|  
|StubSOAOrchBindings.xml|バインド ファイル、ソリューションのスタブ バージョン用です。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\ConfigHelper  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|ConfigHelper.csproj|C#プロジェクト ファイルです。|  
|ConfigParameters.cs|C#SSO 構成ヘルパ メソッドのコード ファイルです。|  
|ConfigPropertyBag.cs|C#SSO 構成ヘルパ メソッドで使用されるプロパティ バッグのコード ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\ErrorHelper  
  
|ファイル|説明|  
|----------|-----------------|  
|CustomerServiceErrors.cs|C#カスタマー サービス エラーのコード ファイルです。|  
|ErrorHelper.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\InPipeline  
  
|ファイル|説明|  
|----------|-----------------|  
|InPipeline.btp|SSO チケットをメッセージに追加するパイプラインが表示されます。|  
|InPipeline.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\InPipelineComp  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|InPipelineComp.csproj|C#プロジェクト ファイルです。|  
|SSOTicketIssuer.cs|C#SSO チケットを発行するパイプライン コンポーネントのコード ファイルです。|  
|SSOTicketIssuer.resx|リソース ファイル。|  
|SSOTicketIssuerIcon.bmp|パイプライン コンポーネントのアイコン ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\Maps  
  
|ファイル|説明|  
|----------|-----------------|  
|Aggregate_To_CustomerServiceResponse.btm|バックエンド システムからの 3 つの応答の集計を 1 つの応答メッセージに変換するマップです。|  
|Aggregate_To_ErrorResponse.btm|エラーが発生したときに、1 つのエラー応答に 3 つの応答の集計を変換するマップです。|  
|CustomerServiceRequest_To_CreditLimiRequest.btm|カスタマー サービス要求をクレジット限度額を要求するメッセージに変換するマップです。|  
|CustomerServiceRequest_To_CreditLimitResponse.btm|カスタマー サービス要求をクレジットの上限で応答メッセージに変換するマップです。|  
|CustomerServiceRequest_To_CustomerServiceResponseDenied.btm|要求拒否メッセージをカスタマー サービス要求を変換するマップします。|  
|CustomerServiceRequest_To_LastPaymentRequest.btm|最後の支払い情報を要求するメッセージをカスタマー サービス要求を変換するマップします。|  
|CustomerServiceRequest_To_LastPaymentResponseTimeout.btm|最新支払い応答メッセージをカスタマー サービス要求を変換するマップします。|  
|CustomerServiceRequest_To_PendingTransactionResponse.btm|カスタマー サービス要求を pending transaction 応答メッセージに変換するマップです。|  
|CustomerServiceRequest_To_PendingTransactionsRequest.btm|カスタマー サービス要求を保留中のトランザクション情報を要求するメッセージに変換するマップです。|  
|Maps.btproj|BizTalk プロジェクト ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\Orchestrations\Adapter  
  
|ファイル|説明|  
|----------|-----------------|  
|CustomerService.odx|アダプター バージョンの**CustomerService**オーケストレーションします。|  
|CustomerServiceNativeRequestResponse.odx|フロント エンドとして機能するオーケストレーションのアダプタ バージョン、 **CustomerService**オーケストレーションします。|  
|CustomerServiceReceiveSend.odx|フロント エンドとして機能するオーケストレーションのアダプタ バージョン、 **CustomerService**オーケストレーションします。|  
|Orchestrations.Adapter.btproj|BizTalk プロジェクト ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\Orchestrations\Adapter\Web References\PendTransWS  
  
|ファイル|説明|  
|----------|-----------------|  
|PendTransWS.disco|生成されたファイルです。|  
|PendTransWS.wsdl|生成されたファイルです。|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイル|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|Reference1.xsd|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\btssoln\orchestrations\adapter\web  
  
|ファイル|説明|  
|----------|-----------------|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|StubSAPWS.disco|生成されたファイルです。|  
|StubSAPWS.wsdl|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\Orchestrations\Inline  
  
|ファイル|説明|  
|----------|-----------------|  
|CustomerService.odx|インライン バージョンの**CustomerService**オーケストレーションします。|  
|CustomerServiceNativeRequestResponse.odx|フロント エンドとして機能するオーケストレーションのインライン バージョン、 **CustomerService**オーケストレーションします。|  
|CustomerServiceReceiveSend.odx|フロント エンドとして機能するオーケストレーションのインライン バージョン、 **CustomerService**オーケストレーションします。|  
|Orchestrations.Inline.btproj|BizTalk プロジェクト ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\Orchestrations\Stub  
  
|ファイル|説明|  
|----------|-----------------|  
|CustomerService.odx|スタブ バージョンの**CustomerService**オーケストレーションします。|  
|CustomerServiceNativeRequestResponse.odx|フロント エンドとして機能するオーケストレーションのスタブ バージョン、 **CustomerService**オーケストレーションします。|  
|Orchestrations.Stub.btproj|BizTalk プロジェクト ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\Orchestrations\Stub\Web References\StubPendTransWS  
  
|ファイル|説明|  
|----------|-----------------|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|Reference1.xsd|生成されたファイルです。|  
|StubPendTransWS.disco|生成されたファイルです。|  
|StubPendTransWS.wsdl|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\Orchestrations\Stub\Web References\StubPmntTrckWS  
  
|ファイル|説明|  
|----------|-----------------|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|Reference1.xsd|生成されたファイルです。|  
|StubPmntTrckWS.disco|生成されたファイルです。|  
|StubPmntTrckWS.wsdl|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\btssoln\orchestrations\stub\web  
  
|ファイル|説明|  
|----------|-----------------|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|StubSAPWS.disco|生成されたファイルです。|  
|StubSAPWS.wsdl|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\OrchProxy\Adapter  
  
|ファイル|説明|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成されたファイルです。|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|OrchProxy.Adapter.csproj.webinfo|生成されたファイルです。|  
|TraceExtension.cs|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
|WsdlExtension.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\OrchProxy\Adapter\app_code  
  
|ファイル|説明|  
|----------|-----------------|  
|assemblyinfo.cs|生成されたファイルです。|  
|customerserviceport.asmx.cs|生成されたファイルです。|  
|datatypes.cs|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\OrchProxy\Inline  
  
|ファイル|説明|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成されたファイルです。|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|OrchProxy.Inline.csproj.webinfo|生成されたファイルです。|  
|TraceExtension.cs|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
|WsdlExtension.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\OrchProxy\Inline\app_code  
  
|ファイル|説明|  
|----------|-----------------|  
|assemblyinfo.cs|生成されたファイルです。|  
|customerserviceport.asmx.cs|生成されたファイルです。|  
|datatypes.cs|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\OrchProxy\Stub  
  
|ファイル|説明|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成されたファイルです。|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|OrchProxy.Stub.csproj.webinfo|生成されたファイルです。|  
|TraceExtension.cs|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
|WsdlExtension.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\OrchProxy\Stub\app_code  
  
|ファイル|説明|  
|----------|-----------------|  
|assemblyinfo.cs|生成されたファイルです。|  
|customerserviceport.asmx.cs|生成されたファイルです。|  
|datatypes.cs|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\PaymentTracker  
  
|ファイル|説明|  
|----------|-----------------|  
|App.ico|Payment tracker シミュレーターのアイコン ファイルです。|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|MessageProcessor.cs|C#payment tracker メッセージを処理し、適切な応答を返すクラスのコードです。|  
|PaymentTracker.cs|C#payment tracker システムをシミュレートするクラスのコードです。|  
|PaymentTracker.csproj|C#プロジェクト ファイルです。|  
|PaymentTrackerSimulator.cs|C#payment tracker シミュレーター用のサーバーのコードです。|  
|runit.cmd|Payment tracker シミュレーターを開始するコマンド ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\PaymentTrackerCall  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Exceptions.cs|C#payment tracking システムの例外を定義するコードです。|  
|PaymentTrackerCall.csproj|C#プロジェクト ファイルです。|  
|PaymentTrackerCaller.cs|C#payment tracking システム インラインをオーケストレーションからを呼び出すコードです。|  
  
 Files in \<Install Directory\>\BTSSoln\PendTransCall  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Exceptions.cs|C#例外、pending transactions システムを定義するコードです。|  
|PendingTransactionsCaller.cs|C#オーケストレーションから pending transaction システム インラインを呼び出すコードです。|  
|PendingTransactionsWebService.disco|生成されたファイルです。|  
|PendingTransactionsWebService.wsdl|生成されたファイルです。|  
|PendTransCall.csproj|C#プロジェクト ファイルです。|  
|WebServiceReference.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\PmTrkPipeline  
  
|ファイル|説明|  
|----------|-----------------|  
|PaymentTrackerReceivePipeline.btp|Payment tracking システムのパイプラインが表示されます。|  
|PaymentTrackerSendPipeline.btp|Payment tracking システムのパイプラインを送信します。|  
|PmTrkPipeline.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\PmTrkPipelineComp  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|MQSeriesHeaderSetter.cs|C#メッセージの受信および送信 payment tracking システムからのいくつかの MQSeries メッセージ ヘッダーの設定を処理するパイプライン コンポーネントのコードは.|  
|MQSeriesHeaderSetter.resx|リソース ファイル。|  
|PmTrkPipelineComp.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\SchemaClasses  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|BAPI_BANKACCT_GET_DETAIL.cs|対応するスキーマ (.xsd) ファイルから生成されます。|  
|CustomerServiceRequest.cs|対応するスキーマ (.xsd) ファイルから生成されます。|  
|CustomerServiceResponse.cs|対応するスキーマ (.xsd) ファイルから生成されます。|  
|LastPaymentRequest.cs|対応するスキーマ (.xsd) ファイルから生成されます。|  
|LastPaymentResponse.cs|対応するスキーマ (.xsd) ファイルから生成されます。|  
|PendingTransactionsRequest.cs|対応するスキーマ (.xsd) ファイルから生成されます。|  
|PendingTransactionsResponse.cs|対応するスキーマ (.xsd) ファイルから生成されます。|  
|SchemaClasses.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\BTSSoln\Schemas  
  
|ファイル|説明|  
|----------|-----------------|  
|BAPI_BANKACCT_GET_DETAIL.xsd|SAP の要求と応答メッセージのスキーマです。|  
|CustomerServiceRequest.xsd|カスタマー サービス要求メッセージのスキーマです。|  
|CustomerServiceResponse.xsd|カスタマー サービス応答メッセージのスキーマです。|  
|genClasses.cmd|コマンド ファイルを生成するC#クラス スキーマからのファイル。|  
|LastPaymentRequest.xsd|最新支払い要求メッセージのスキーマです。|  
|LastPaymentResponse.xsd|最新支払い応答メッセージのスキーマです。|  
|PendingTransactionsRequest.xsd|保留中のトランザクション要求メッセージのスキーマです。|  
|PendingTransactionsResponse.xsd|Pending transaction 応答メッセージのスキーマです。|  
|Schemas.btproj|BizTalk プロジェクト ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\Scripts  
  
|ファイル|説明|  
|----------|-----------------|  
|ConfigStoreApp.xml|SSO 構成値を定義する XML ファイルです。|  
|CreateInitialConfigInSSO.cmd|初期 SSO 構成値を作成するコマンド ファイルです。|  
|DeployAllBinding.cmd|すべてのアセンブリを展開するコマンド ファイルです。|  
|DeployStubBinding.cmd|アセンブリのスタブ バージョンを展開するコマンド ファイルです。|  
|PendTransAffApp.xml|保留中のトランザクションの値を定義する XML ファイルには、アプリケーションが関連します。|  
|PendTransUserMap.xml|保留中のトランザクションの関連アプリケーションのユーザーの資格情報のマッピングを定義する XML ファイル。|  
|PmntTrckAffApp.xml|保留中のトランザクションの値を定義する XML ファイルには、アプリケーションが関連します。|  
|PmntTrckUserMap.xml|Payment tracking 関連アプリケーションのユーザーの資格情報のマッピングを定義する XML ファイル。|  
|RemoveReceivePort.vbs|受信ポートを削除する汎用 VBScript です。|  
|RemoveSendPort.vbs|送信ポートを削除する汎用 VBScript です。|  
|SetConfigValuesInSSO.cmd|Sso 構成値を設定するコマンド ファイルです。|  
|StartAll.vbs|参加させ、すべてのオーケストレーションを開始するコマンド ファイルです。|  
|StartStub.vbs|参加させ、オーケストレーションのスタブ バージョンを開始するコマンド ファイルです。|  
|UndeployAll.cmd|すべてのアセンブリの展開を解除するコマンド ファイルです。|  
|UndeployStub.cmd|アセンブリのスタブ バージョンを展開解除するコマンド ファイルです。|  
|UnEnlistAll.vbs|すべてのオーケストレーションの参加を解除するコマンド ファイルです。|  
|UnEnlistStub.vbs|オーケストレーションのスタブ バージョンの参加を解除するコマンド ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\ServiceLevelTracking  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|ServiceLevelTracking.cs|C#サービス レベル BAM 追跡のためのヘルパー関数です。|  
|ServiceLevelTracking.csproj|C#プロジェクト ファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\SimpleClient  
  
|ファイル|説明|  
|----------|-----------------|  
|AdapterCustomerServicePort.disco|生成されたファイルです。|  
|AdapterCustomerServicePort.wsdl|生成されたファイルです。|  
|App.ico|単純なクライアント アプリケーションのアイコン ファイルです。|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|InlineCustomerServicePort.disco|生成されたファイルです。|  
|InlineCustomerServicePort.wsdl|生成されたファイルです。|  
|SimpleClient.cs|要求を行うための単純な Windows フォーム アプリケーション。|  
|SimpleClient.csproj|C#プロジェクト ファイルです。|  
|SimpleClient.resx|リソース ファイル。|  
|WebServiceReferences.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\PaymentTrack  
  
|ファイル|説明|  
|----------|-----------------|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|StubPmntTrck.csproj.webinfo|生成されたファイルです。|  
|StubPmntTrckWS.asmx|生成されたファイルです。|  
|StubPmntTrckWS.asmx.resx|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\PaymentTrack\app_code  
  
|ファイル|説明|  
|----------|-----------------|  
|assemblyinfo.cs|アセンブリ情報ファイルです。|  
|global.asax.cs|生成されたファイルです。|  
|StubPmntTrckWS.asmx.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\PendingTrans  
  
|ファイル|説明|  
|----------|-----------------|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|StubPendTransWS.asmx|生成されたファイルです。|  
|StubPendTransWS.asmx.resx|生成されたファイルです。|  
|StubPendTransWS.csproj.webinfo|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\PendingTrans\app_code  
  
|ファイル|説明|  
|----------|-----------------|  
|assemblyinfo.cs|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
|StubPendTransWS.asmx.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\SAP  
  
|ファイル|説明|  
|----------|-----------------|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|StubSAP.csproj.webinfo|生成されたファイルです。|  
|StubSAPWS.asmx|生成されたファイルです。|  
|StubSAPWS.asmx.resx|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\SAP\app_code  
  
|ファイル|説明|  
|----------|-----------------|  
|assemblyinfo.cs|アセンブリ情報ファイルです。|  
|global.asax.cs|生成されたファイルです。|  
|stubsapws.asmx.cs|生成されたファイルです。|  
  
 Files in \<Install Directory\>\BTSSoln\StubWebServices\StubSAPCall  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Exceptions.cs|C#スタブ SAP 呼び出しのタイムアウト例外を定義するコードです。|  
|StubSAPCall.csproj|C#プロジェクト ファイルです。|  
|StubSAPCallHelper.cs|C#スタブ SAP web サービスを呼び出すヘルパ アセンブリのコードです。|  
|StubSAPWSProxy.cs|C#スタブ SAP web サービスを呼び出すヘルパ アセンブリのコードです。|  
  
 Files in \<Install Directory\>\BTSSoln\Utilities  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|CustomerServiceHelper.cs|C#ヘルパー メソッドとクラスのコードです。|  
|ReceivePipelineHelper.cs|C#オーケストレーションからパイプラインを呼び出すためのヘルパ アセンブリのコードです。|  
|Utilities.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\MFAccess  
  
|ファイル|説明|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.MainframeAccess.sln|Visual Studio ソリューション ファイルです。|  
|SetupMFAccess.bat|ソリューションのメインフレーム アクセス コンポーネントをビルドするバッチ ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\MFAccess\HISTIComponent  
  
|ファイル|説明|  
|----------|-----------------|  
|bizcbl.txt|メインフレームで実行する COBOL プログラムです。|  
|HISTIComponent.tiproj|トランザクション インテグレータのプロジェクト ファイルです。|  
|MainFrameProgramVTCS2Description.txt|トランザクション インテグレータのエクスポート ファイルです。|  
|SOHISTIUsingCOM.TLB|タイプ ライブラリ。|  
  
 内のファイル\<インストール ディレクトリ\>\MFAccess\HISTISimpleTester  
  
|ファイル|説明|  
|----------|-----------------|  
|App.ico|アイコン ファイル|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Form1.cs|メインフレームへの接続をテストする Windows フォーム プログラムです。|  
|Form1.resx|リソース ファイル|  
|HISTISimpleTester.csproj|C#プロジェクト ファイルです。|  
|Interop.SOHISTIUsingCOM.dll.reg|DLL 登録ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\MFAccess\PendingTransactions  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Global.asax|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|PendingTransactions.csproj|C#プロジェクト ファイルです。|  
|PendingTransactions.csproj.webinfo|生成されたファイルです。|  
|PendTransWS.asmx|生成されたファイルです。|  
|PendTransWS.asmx.cs|生成されたファイルです。|  
|PendTransWS.asmx.resx|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\MFAccess\SchemaClasses  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|BAPI_BANKACCT_GET_DETAIL.cs|C#対応するスキーマ (.xsd) ファイルから生成されるクラス。|  
|CustomerServiceRequest.cs|C#対応するスキーマ (.xsd) ファイルから生成されるクラス。|  
|CustomerServiceResponse.cs|C#対応するスキーマ (.xsd) ファイルから生成されるクラス。|  
|LastPaymentRequest.cs|C#対応するスキーマ (.xsd) ファイルから生成されるクラス。|  
|LastPaymentResponse.cs|C#対応するスキーマ (.xsd) ファイルから生成されるクラス。|  
|PendingTransactionsRequest.cs|C#対応するスキーマ (.xsd) ファイルから生成されるクラス。|  
|PendingTransactionsResponse.cs|C#対応するスキーマ (.xsd) ファイルから生成されるクラス。|  
|SchemaClasses.csproj|C#プロジェクト ファイルです。|  
  
## <a name="see-also"></a>参照  
 [サービスのコンポーネント指向のソリューション](../core/components-of-the-service-oriented-solution.md)   
 [サービス指向ソリューション リファレンス](../core/service-oriented-solution-reference.md)
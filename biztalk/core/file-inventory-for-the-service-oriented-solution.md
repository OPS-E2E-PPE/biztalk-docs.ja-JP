---
title: "ファイル インベントリ サービス指向ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service solution tutorial, file inventory
ms.assetid: 32c25372-31e1-4059-b4ed-f12e62f315d5
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac62241b8c3bf3244bb9e055a5b744acd5080048
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="file-inventory-for-the-service-oriented-solution"></a>ファイル インベントリ サービス指向ソリューション
このセクションでは、サービス指向ソリューションのサブディレクトリおよびソース ファイルについて説明します。 サービス指向ソリューションのソース ファイルの既定のインストール ディレクトリは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\SO です。 次の表では、このパスを交換する前に説明\<インストール ディレクトリ >。  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln  
  
|ファイル|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.sln|Visual Studio ソリューション ファイル。|  
|ReplacePKToken.vbs|ソリューションのビルド時に、ソリューション ファイル内の公開キー トークンを修正する VBScript です。|  
|ReplacePKToken.wsf|ReplacePKToken VBScript 用の Windows スクリプト ファイルです。|  
|SetupBTSSoln.bat|公開キーを作成し、公開キーへの参照を更新し、ソリューションをコンパイルします。 ソリューションを展開する方法の詳細については、次を参照してください。[サービス指向ソリューションの配置](../core/deploying-the-service-oriented-solution.md)です。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\BAM  
  
|ファイル|Description|  
|----------|-----------------|  
|ServiceLevelTracking.xls|BAM データの Excel スプレッドシートです。|  
|ServiceLevelTracking.xml|BAM データ項目の型を定義するスキーマです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\Bindings  
  
|ファイル|Description|  
|----------|-----------------|  
|AdapterSOAOrchBindings.xml|ソリューションのアダプタ バージョンのバインド ファイルです。|  
|InlineSOAOrchBindings.xml|ソリューションのインライン バージョンのバインド ファイルです。|  
|StubSOAOrchBindings.xml|ソリューションのスタブ バージョンのバインド ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\ConfigHelper  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|ConfigHelper.csproj|C# のプロジェクト ファイルです。|  
|ConfigParameters.cs|SSO 構成ヘルパ メソッドの C# コード ファイルです。|  
|ConfigPropertyBag.cs|SSO 構成ヘルパ メソッドで使用されるプロパティ バッグの C# コード ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\ErrorHelper  
  
|ファイル|Description|  
|----------|-----------------|  
|CustomerServiceErrors.cs|カスタマー サービス エラーの C# コード ファイルです。|  
|ErrorHelper.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\InPipeline  
  
|ファイル|Description|  
|----------|-----------------|  
|InPipeline.btp|SSO チケットをメッセージに追加する受信パイプラインです。|  
|InPipeline.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\InPipelineComp  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|InPipelineComp.csproj|C# のプロジェクト ファイルです。|  
|SSOTicketIssuer.cs|SSO チケットを発行するパイプライン コンポーネントの C# コード ファイルです。|  
|SSOTicketIssuer.resx|リソース ファイルです。|  
|SSOTicketIssuerIcon.bmp|パイプライン コンポーネントのアイコン ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\Maps  
  
|ファイル|Description|  
|----------|-----------------|  
|Aggregate_To_CustomerServiceResponse.btm|バックエンド システムからの 3 つの応答の集計を 1 つの応答メッセージに変換するマップです。|  
|Aggregate_To_ErrorResponse.btm|エラーが発生した場合に、3 つの応答の集計を 1 つのエラー応答に変換するマップです。|  
|CustomerServiceRequest_To_CreditLimiRequest.btm|カスタマー サービス要求を、クレジット限度額を要求するメッセージに変換するマップです。|  
|CustomerServiceRequest_To_CreditLimitResponse.btm|カスタマー サービス要求を、クレジット限度額を使用して応答するメッセージに変換するマップです。|  
|CustomerServiceRequest_To_CustomerServiceResponseDenied.btm|カスタマー サービス要求を、要求拒否メッセージに変換するマップです。|  
|CustomerServiceRequest_To_LastPaymentRequest.btm|カスタマー サービス要求を、最新支払い情報を要求するメッセージに変換するマップです。|  
|CustomerServiceRequest_To_LastPaymentResponseTimeout.btm|カスタマー サービス要求を最新支払い応答メッセージに変換するマップです。|  
|CustomerServiceRequest_To_PendingTransactionResponse.btm|カスタマー サービス要求を Pending Transaction 応答メッセージに変換するマップです。|  
|CustomerServiceRequest_To_PendingTransactionsRequest.btm|カスタマー サービス要求を、Pending Transaction 情報を要求するメッセージに変換するマップです。|  
|Maps.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\Orchestrations\Adapter  
  
|ファイル|Description|  
|----------|-----------------|  
|CustomerService.odx|アダプター バージョンの**CustomerService**オーケストレーションです。|  
|CustomerServiceNativeRequestResponse.odx|フロント エンドとして機能するオーケストレーションのアダプタ バージョン、 **CustomerService**オーケストレーションです。|  
|CustomerServiceReceiveSend.odx|フロント エンドとして機能するオーケストレーションのアダプタ バージョン、 **CustomerService**オーケストレーションです。|  
|Orchestrations.Adapter.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \btssoln\orchestrations\adapter\web  
  
|ファイル|Description|  
|----------|-----------------|  
|PendTransWS.disco|生成されたファイルです。|  
|PendTransWS.wsdl|生成されたファイルです。|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|Reference1.xsd|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \btssoln\orchestrations\adapter\web  
  
|ファイル|Description|  
|----------|-----------------|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|StubSAPWS.disco|生成されたファイルです。|  
|StubSAPWS.wsdl|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\Orchestrations\Inline  
  
|ファイル|Description|  
|----------|-----------------|  
|CustomerService.odx|インライン バージョンの**CustomerService**オーケストレーションです。|  
|CustomerServiceNativeRequestResponse.odx|フロント エンドとして機能するオーケストレーションのインライン バージョン、 **CustomerService**オーケストレーションです。|  
|CustomerServiceReceiveSend.odx|フロント エンドとして機能するオーケストレーションのインライン バージョン、 **CustomerService**オーケストレーションです。|  
|Orchestrations.Inline.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\Orchestrations\Stub  
  
|ファイル|Description|  
|----------|-----------------|  
|CustomerService.odx|スタブ バージョン、 **CustomerService**オーケストレーションです。|  
|CustomerServiceNativeRequestResponse.odx|フロント エンドとして機能するオーケストレーションのスタブ バージョン、 **CustomerService**オーケストレーションです。|  
|Orchestrations.Stub.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \btssoln\orchestrations\stub\web  
  
|ファイル|Description|  
|----------|-----------------|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|Reference1.xsd|生成されたファイルです。|  
|StubPendTransWS.disco|生成されたファイルです。|  
|StubPendTransWS.wsdl|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \btssoln\orchestrations\stub\web  
  
|ファイル|Description|  
|----------|-----------------|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|Reference1.xsd|生成されたファイルです。|  
|StubPmntTrckWS.disco|生成されたファイルです。|  
|StubPmntTrckWS.wsdl|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \btssoln\orchestrations\stub\web  
  
|ファイル|Description|  
|----------|-----------------|  
|Reference.map|生成されたファイルです。|  
|Reference.map.cs|生成されたファイルです。|  
|Reference.odx|生成されたファイルです。|  
|Reference.xsd|生成されたファイルです。|  
|StubSAPWS.disco|生成されたファイルです。|  
|StubSAPWS.wsdl|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\OrchProxy\Adapter  
  
|ファイル|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成されたファイルです。|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|OrchProxy.Adapter.csproj.webinfo|生成されたファイルです。|  
|TraceExtension.cs|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
|WsdlExtension.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\OrchProxy\Adapter\app_code  
  
|ファイル|Description|  
|----------|-----------------|  
|assemblyinfo.cs|生成されたファイルです。|  
|customerserviceport.asmx.cs|生成されたファイルです。|  
|datatypes.cs|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\OrchProxy\Inline  
  
|ファイル|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成されたファイルです。|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|OrchProxy.Inline.csproj.webinfo|生成されたファイルです。|  
|TraceExtension.cs|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
|WsdlExtension.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\OrchProxy\Inline\app_code  
  
|ファイル|Description|  
|----------|-----------------|  
|assemblyinfo.cs|生成されたファイルです。|  
|customerserviceport.asmx.cs|生成されたファイルです。|  
|datatypes.cs|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\OrchProxy\Stub  
  
|ファイル|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|生成されたファイルです。|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|OrchProxy.Stub.csproj.webinfo|生成されたファイルです。|  
|TraceExtension.cs|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
|WsdlExtension.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\OrchProxy\Stub\app_code  
  
|ファイル|Description|  
|----------|-----------------|  
|assemblyinfo.cs|生成されたファイルです。|  
|customerserviceport.asmx.cs|生成されたファイルです。|  
|datatypes.cs|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\PaymentTracker  
  
|ファイル|Description|  
|----------|-----------------|  
|App.ico|Payment Tracker シミュレーターのアイコン ファイルです。|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|MessageProcessor.cs|Payment Tracker メッセージを処理して適切な応答を返すクラスの C# コードです。|  
|PaymentTracker.cs|Payment Tracker システムをシミュレートするクラスの C# コードです。|  
|PaymentTracker.csproj|C# のプロジェクト ファイルです。|  
|PaymentTrackerSimulator.cs|Payment Tracker シミュレーターのサーバーの C# コードです。|  
|runit.cmd|Payment Tracker シミュレーターを起動するコマンド ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\PaymentTrackerCall  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Exceptions.cs|Payment Tracking システムの例外を定義する C# コードです。|  
|PaymentTrackerCall.csproj|C# のプロジェクト ファイルです。|  
|PaymentTrackerCaller.cs|オーケストレーションから Payment Tracking システム インラインを呼び出す C# コードです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\PendTransCall  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Exceptions.cs|Pending Transaction システムの例外を定義する C# コードです。|  
|PendingTransactionsCaller.cs|オーケストレーションから Pending Transactions システム インラインを呼び出す C# コードです。|  
|PendingTransactionsWebService.disco|生成されたファイルです。|  
|PendingTransactionsWebService.wsdl|生成されたファイルです。|  
|PendTransCall.csproj|C# のプロジェクト ファイルです。|  
|WebServiceReference.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\PmTrkPipeline  
  
|ファイル|Description|  
|----------|-----------------|  
|PaymentTrackerReceivePipeline.btp|Payment Tracking システムの受信パイプラインです。|  
|PaymentTrackerSendPipeline.btp|Payment Tracking システムの送信パイプラインです。|  
|PmTrkPipeline.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\PmTrkPipelineComp  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|MQSeriesHeaderSetter.cs|Payment Tracking システムの受信および送信メッセージ用の MQSeries メッセージ ヘッダー設定を処理するパイプライン コンポーネントの C# コードです。|  
|MQSeriesHeaderSetter.resx|リソース ファイルです。|  
|PmTrkPipelineComp.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\SchemaClasses  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|BAPI_BANKACCT_GET_DETAIL.cs|対応するスキーマ (.xsd) ファイルから生成されました。|  
|CustomerServiceRequest.cs|対応するスキーマ (.xsd) ファイルから生成されました。|  
|CustomerServiceResponse.cs|対応するスキーマ (.xsd) ファイルから生成されました。|  
|LastPaymentRequest.cs|対応するスキーマ (.xsd) ファイルから生成されました。|  
|LastPaymentResponse.cs|対応するスキーマ (.xsd) ファイルから生成されました。|  
|PendingTransactionsRequest.cs|対応するスキーマ (.xsd) ファイルから生成されました。|  
|PendingTransactionsResponse.cs|対応するスキーマ (.xsd) ファイルから生成されました。|  
|SchemaClasses.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\Schemas  
  
|ファイル|Description|  
|----------|-----------------|  
|BAPI_BANKACCT_GET_DETAIL.xsd|SAP の要求メッセージと応答メッセージのスキーマです。|  
|CustomerServiceRequest.xsd|カスタマー サービス要求メッセージのスキーマです。|  
|CustomerServiceResponse.xsd|カスタマー サービス応答メッセージのスキーマです。|  
|genClasses.cmd|スキーマから C# クラス ファイルを生成するコマンド ファイルです。|  
|LastPaymentRequest.xsd|最新支払い要求メッセージのスキーマです。|  
|LastPaymentResponse.xsd|最新支払い応答メッセージのスキーマです。|  
|PendingTransactionsRequest.xsd|Pending Transaction 要求メッセージのスキーマです。|  
|PendingTransactionsResponse.xsd|Pending Transaction 応答メッセージのスキーマです。|  
|Schemas.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\Scripts  
  
|ファイル|Description|  
|----------|-----------------|  
|ConfigStoreApp.xml|SSO 構成値を定義する XML ファイルです。|  
|CreateInitialConfigInSSO.cmd|初期 SSO 構成値を作成するコマンド ファイルです。|  
|DeployAllBinding.cmd|アセンブリをすべて展開するコマンド ファイルです。|  
|DeployStubBinding.cmd|アセンブリのスタブ バージョンを展開するコマンド ファイルです。|  
|PendTransAffApp.xml|Pending Transactions 関連アプリケーションの値を定義する XML ファイルです。|  
|PendTransUserMap.xml|Pending Transactions 関連アプリケーションの資格情報のマッピングを定義する XML ファイルです。|  
|PmntTrckAffApp.xml|Pending Transactions 関連アプリケーションの値を定義する XML ファイルです。|  
|PmntTrckUserMap.xml|Payment Tracking 関連アプリケーションの資格情報のマッピングを定義する XML ファイルです。|  
|RemoveReceivePort.vbs|受信ポートを削除する汎用 VBScript です。|  
|RemoveSendPort.vbs|送信ポートを削除する汎用 VBScript です。|  
|SetConfigValuesInSSO.cmd|SSO 内の構成値を設定するコマンド ファイルです。|  
|StartAll.vbs|すべてのオーケストレーションを参加させ、開始するコマンド ファイルです。|  
|StartStub.vbs|オーケストレーションのスタブ バージョンを参加させ、開始するコマンド ファイルです。|  
|UndeployAll.cmd|アセンブリをすべて展開解除するコマンド ファイルです。|  
|UndeployStub.cmd|アセンブリのスタブ バージョンを展開解除するコマンド ファイルです。|  
|UnEnlistAll.vbs|すべてのオーケストレーションを参加解除するコマンド ファイルです。|  
|UnEnlistStub.vbs|オーケストレーションのスタブ バージョンを展開解除するコマンド ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\ServiceLevelTracking  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|ServiceLevelTracking.cs|サービス レベル BAM 追跡の C# ヘルパ関数です。|  
|ServiceLevelTracking.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\SimpleClient  
  
|ファイル|Description|  
|----------|-----------------|  
|AdapterCustomerServicePort.disco|生成されたファイルです。|  
|AdapterCustomerServicePort.wsdl|生成されたファイルです。|  
|App.ico|単純なクライアント アプリケーションのアイコン ファイルです。|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|InlineCustomerServicePort.disco|生成されたファイルです。|  
|InlineCustomerServicePort.wsdl|生成されたファイルです。|  
|SimpleClient.cs|要求を行うための簡単な Windows フォーム アプリケーションです。|  
|SimpleClient.csproj|C# のプロジェクト ファイルです。|  
|SimpleClient.resx|リソース ファイルです。|  
|WebServiceReferences.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\StubWebServices\PaymentTrack  
  
|ファイル|Description|  
|----------|-----------------|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|StubPmntTrck.csproj.webinfo|生成されたファイルです。|  
|StubPmntTrckWS.asmx|生成されたファイルです。|  
|StubPmntTrckWS.asmx.resx|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\StubWebServices\PaymentTrack\app_code  
  
|ファイル|Description|  
|----------|-----------------|  
|assemblyinfo.cs|アセンブリ情報ファイルです。|  
|global.asax.cs|生成されたファイルです。|  
|StubPmntTrckWS.asmx.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\StubWebServices\PendingTrans  
  
|ファイル|Description|  
|----------|-----------------|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|StubPendTransWS.asmx|生成されたファイルです。|  
|StubPendTransWS.asmx.resx|生成されたファイルです。|  
|StubPendTransWS.csproj.webinfo|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\StubWebServices\PendingTrans\app_code  
  
|ファイル|Description|  
|----------|-----------------|  
|assemblyinfo.cs|生成されたファイルです。|  
|global.asax.cs|生成されたファイルです。|  
|StubPendTransWS.asmx.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\StubWebServices\SAP  
  
|ファイル|Description|  
|----------|-----------------|  
|Global.asax|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|StubSAP.csproj.webinfo|生成されたファイルです。|  
|StubSAPWS.asmx|生成されたファイルです。|  
|StubSAPWS.asmx.resx|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\StubWebServices\SAP\app_code  
  
|ファイル|Description|  
|----------|-----------------|  
|assemblyinfo.cs|アセンブリ情報ファイルです。|  
|global.asax.cs|生成されたファイルです。|  
|stubsapws.asmx.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\StubWebServices\StubSAPCall  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Exceptions.cs|スタブ SAP 呼び出しのタイムアウト例外を定義する C# コードです。|  
|StubSAPCall.csproj|C# のプロジェクト ファイルです。|  
|StubSAPCallHelper.cs|スタブ SAP Web サービスを呼び出すヘルパ アセンブリの C# コードです。|  
|StubSAPWSProxy.cs|スタブ SAP Web サービスを呼び出すヘルパ アセンブリの C# コードです。|  
  
 内のファイル\<インストール ディレクトリ > \BTSSoln\Utilities  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|CustomerServiceHelper.cs|ヘルパ メソッドおよびクラスの C# コード ファイルです。|  
|ReceivePipelineHelper.cs|オーケストレーションからパイプラインを呼び出すためのヘルパ アセンブリの C# コードです。|  
|Utilities.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \MFAccess  
  
|ファイル|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.MainframeAccess.sln|Visual Studio ソリューション ファイル。|  
|SetupMFAccess.bat|ソリューションのメインフレーム アクセス コンポーネントをビルドするバッチ ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \MFAccess\HISTIComponent  
  
|ファイル|Description|  
|----------|-----------------|  
|bizcbl.txt|メインフレームで実行する COBOL プログラムです。|  
|HISTIComponent.tiproj|トランザクション インテグレータのプロジェクト ファイルです。|  
|MainFrameProgramVTCS2Description.txt|トランザクション インテグレータのエクスポート ファイルです。|  
|SOHISTIUsingCOM.TLB|タイプ ライブラリです。|  
  
 内のファイル\<インストール ディレクトリ > \MFAccess\HISTISimpleTester  
  
|ファイル|Description|  
|----------|-----------------|  
|App.ico|アイコン ファイルです。|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Form1.cs|メインフレームへの接続をテストする Windows フォーム プログラムです。|  
|Form1.resx|リソース ファイル|  
|HISTISimpleTester.csproj|C# のプロジェクト ファイルです。|  
|Interop.SOHISTIUsingCOM.dll.reg|DLL 登録ファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \MFAccess\PendingTransactions  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|Global.asax|生成されたファイルです。|  
|Global.asax.cs|生成されたファイルです。|  
|Global.asax.resx|生成されたファイルです。|  
|PendingTransactions.csproj|C# のプロジェクト ファイルです。|  
|PendingTransactions.csproj.webinfo|生成されたファイルです。|  
|PendTransWS.asmx|生成されたファイルです。|  
|PendTransWS.asmx.cs|生成されたファイルです。|  
|PendTransWS.asmx.resx|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ > \MFAccess\SchemaClasses  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|BAPI_BANKACCT_GET_DETAIL.cs|対応するスキーマ (.xsd) ファイルから生成された C# クラスです。|  
|CustomerServiceRequest.cs|対応するスキーマ (.xsd) ファイルから生成された C# クラスです。|  
|CustomerServiceResponse.cs|対応するスキーマ (.xsd) ファイルから生成された C# クラスです。|  
|LastPaymentRequest.cs|対応するスキーマ (.xsd) ファイルから生成された C# クラスです。|  
|LastPaymentResponse.cs|対応するスキーマ (.xsd) ファイルから生成された C# クラスです。|  
|PendingTransactionsRequest.cs|対応するスキーマ (.xsd) ファイルから生成された C# クラスです。|  
|PendingTransactionsResponse.cs|対応するスキーマ (.xsd) ファイルから生成された C# クラスです。|  
|SchemaClasses.csproj|C# のプロジェクト ファイルです。|  
  
## <a name="see-also"></a>参照  
 [コンポーネントのサービス指向ソリューション](../core/components-of-the-service-oriented-solution.md)   
 [サービス指向ソリューション リファレンス](../core/service-oriented-solution-reference.md)
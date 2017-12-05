---
title: "ビジネス プロセス管理ソリューションのインベントリをファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: process management solution tutorial, file inventory
ms.assetid: 3efb7495-9543-4fe0-8f4b-26c19b3b6db9
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cc187a96e7252fad7edacba10b7a3dcc39c1b33
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="file-inventory-for-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのファイル一覧
このセクションでは、ビジネス プロセス管理ソリューションのサブディレクトリおよびソース ファイルについて説明します。 ビジネス プロセス管理ソリューションのソース ファイルの既定のインストール ディレクトリは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\BPM です。 次の表では、このパスを交換する前に説明\<インストール ディレクトリ\>です。  
  
 内のファイル\<インストール ディレクトリ\>  
  
|ファイル|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.SouthridgeVideo.sln|Visual Studio ソリューション ファイル。|  
|readme.html|ソリューションの Readme ファイルです。|  
|ReplacePKToken.vbs|ソリューションのビルド時に、ソリューション ファイル内の公開キー トークンを修正する VBScript です。|  
|ReplacePKToken.wsf|ReplacePKToken VBScript 用の Windows スクリプト ファイルです。|  
|SetupBPM.bat|公開キーを作成し、公開キーへの参照を更新し、ソリューションをコンパイルします。 ソリューションを展開する方法の詳細については、次を参照してください。[ビジネス プロセス管理ソリューションを展開する](../core/deploying-the-business-process-management-solution.md)です。|  
  
 内のファイル\<インストール ディレクトリ\>\BAM  
  
|ファイル|Description|  
|----------|-----------------|  
|BAMServiceOrder.xls|BAM データの Excel スプレッドシートです。|  
|BAMServiceOrder.xml|BAM データ項目の型を定義するスキーマです。|  
  
 内のファイル\<インストール ディレクトリ\>\Bindings  
  
|ファイル|Description|  
|----------|-----------------|  
|CableOrderAppBindings-test.xml|テスト版のバインド ファイル、 **CableOrderApp**アプリケーションです。|  
|CableOrderAppBindings.xml|用のバインド ファイル、 **CableOrderAPP**アプリケーションです。|  
|MessagingAppBindings-test.xml|テスト版のバインド ファイル、 **MessagingApp**アプリケーションです。|  
|MessagingAppBindings.xml|用のバインド ファイル、 **MessagingApp**アプリケーションです。|  
|OrderBrokerAppBindings-test.xml|テスト版のバインド ファイル、 **OrderBrokerApp**アプリケーションです。|  
|OrderBrokerAppBindings.xml|用のバインド ファイル、 **OrderBrokerApp**アプリケーションです。|  
  
 内のファイル\<インストール ディレクトリ\>\CableProvisioningSystemClient  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|注文システムをシミュレートするコンポーネントのクライアント側のアセンブリ ファイルです。|  
|CableProvisioningSystemClient.csproj|C# のプロジェクト ファイルです。|  
|CPSClient.cs|クライアントのソースです。 含まれています、 **OrderHandlerWrapper**クラスのコード。|  
|OrderException.cs|定義するクラスの c# ファイル、 **OrderException**です。|  
  
 内のファイル\<インストール ディレクトリ\>\CableProvisioningSystemServer  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|注文システムをシミュレートするコンポーネントのサーバー側のアセンブリ ファイルです。|  
|CableProvisioningSystemServer.csproj|C# のプロジェクト ファイルです。|  
|CableProvisioningSystemServer.csproj.user|Visual Studio プロジェクトのユーザー オプション ファイルです。|  
|CPSServer.cs|サーバーのソースです。|  
  
 内のファイル\<インストール ディレクトリ\>\CSRWebApp  
  
|ファイル|Description|  
|----------|-----------------|  
|CSRMainForm.aspx|カスタマー サービスの入力 ASP フォームです。|  
|CSRMainForm.aspx.cs|フォームの C# コードです。|  
|Web.Config|フォームの構成ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\CSRWebApp\App_WebReferences\SouthridgeVideo_OrderBroker  
  
|ファイル|Description|  
|----------|-----------------|  
|orderbrokerorch_orderport.disco|Disco ファイルです、 **OrderBroker** web サービスとして表示されます。|  
|orderbrokerorch_orderport.discomap|生成されたファイルです。|  
|orderbrokerorch_orderport.wsdl|WSDL ファイルを**OrderBroker** web サービスとして表示されます。|  
  
 内のファイル\<インストール ディレクトリ\>\FacilitiesSimulator  
  
|ファイル|Description|  
|----------|-----------------|  
|FacilitiesSimulator.csproj|Facilities Simulator の C# プロジェクト ファイルです。|  
|FacilitiesSimulator.csproj.user|Visual Studio プロジェクトのユーザー オプション ファイルです。|  
|FacilitiesSimulatorForm.cs|Facilities Simulator の C# コードです。|  
|FacilitiesSimulatorForm.resx|リソース ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\HistoryDB  
  
|ファイル|Description|  
|----------|-----------------|  
|CreateDatabase.cmd|履歴データベースを作成する SQL ファイルを実行するファイルです。|  
|SouthridgeVideoHistory.sql|履歴データベースを作成する SQL コマンドです。|  
  
 内のファイル\<インストール ディレクトリ\>\IOperationsSystem  
  
|ファイル|Description|  
|----------|-----------------|  
|IOperationsSystem.cs|操作システムのインターフェイス定義です。|  
|IOperationsSystem.csproj|C# のプロジェクト ファイルです。|  
|IOperationsSystem.csproj.user|Visual Studio プロジェクトのユーザー オプション ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\IOrderHandler  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|IOrderHandler.cs|インターフェイスの定義、 **OrderHandler**です。|  
|IOrderHandler.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Maps  
  
|ファイル|Description|  
|----------|-----------------|  
|Maps.btproj|BizTalk プロジェクト ファイルです。|  
|Order_To_SQLUpdateStatus.btm|状態を更新するために注文をメッセージに変換するマップです。|  
  
 内のファイル\<インストール ディレクトリ\>\MessagingSchemas  
  
|ファイル|Description|  
|----------|-----------------|  
|ErrorEnvelope.xsd|エラー メッセージのエンベロープを定義するスキーマです。|  
|MessagingSchemas.btproj|BizTalk プロジェクト ファイルです。|  
|OrderEnvelope.xsd|注文のエンベロープを定義するスキーマです。|  
|OrderStatusEnvelope.xsd|注文の状態メッセージのエンベロープを定義するスキーマです。|  
|SQLUpdateStatus.xsd|SQL の状態更新メッセージのエンベロープを定義するスキーマです。|  
  
 内のファイル\<インストール ディレクトリ\>\OperationsClient  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|OperationsClient.csproj|操作クライアントの C# プロジェクトです。|  
|OpsClient.cs|操作クライアントの C# コードです。|  
|OpsExceptions.cs|操作の例外を定義する C# コードです。|  
  
 内のファイル\<インストール ディレクトリ\>\OperationsHandler  
  
|ファイル|Description|  
|----------|-----------------|  
|OperationsHandler.csproj|操作ハンドラの C# プロジェクト ファイルです。|  
|OpsHandler.cs|C# コード、 **OpsHandler**です。 によって使用される、 **OpsClient**操作システムの要求を行うことです。|  
  
 内のファイル\<インストール ディレクトリ\>\OperationsServer  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|OperationsServer.csproj|操作サーバーの C# プロジェクト ファイルです。|  
|OpsServer.cs|インスタンスを提供する操作サーバーの c# コード、 **OpsHandler**オブジェクト。|  
  
 内のファイル\<インストール ディレクトリ\>\OpsAdapter  
  
|ファイル|Description|  
|----------|-----------------|  
|OpsAdapter.sln|Ops アダプタの Visual Studio ソリューションです。|  
|Register_Ops_Adapter.vbs|Ops アダプタを登録する VBScript です。|  
|SetupOpsAdapter.bat|Ops アダプタを設定するバッチ ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OpsAdapter\IOpsAIC  
  
|ファイル|Description|  
|----------|-----------------|  
|IOpsAIC.cs|インターフェイスを定義するための c# コード ファイル、**初期化**と**Execute** Ops アダプタによって呼び出されるメソッド。|  
|IOpsAIC.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OpsAdapter\OpsAdapterMgmt  
  
|ファイル|Description|  
|----------|-----------------|  
|AdapterManagement.cs|Ops アダプタの C# ソース ファイルです。|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|OpsAdapterMgmt.csproj|Ops アダプタの C# ソース ファイルです。|  
|TransmitHandler.xsd|Ops アダプタの C# ソース ファイルです。|  
|TransmitLocation.xsd|Ops アダプタの C# ソース ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OpsAdapter\OpsTxAdapter  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|OpsAdapterExceptions.cs|Ops アダプタの C# ソース ファイルです。|  
|OpsAdapterProperties.cs|Ops アダプタの C# ソース ファイルです。|  
|OpsTransmitAdapterBatch.cs|Ops アダプタの C# ソース ファイルです。|  
|OpsTransmitter.cs|Ops アダプタの C# ソース ファイルです。|  
|OpsTxAdapter.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\CableOrderActions  
  
|ファイル|Description|  
|----------|-----------------|  
|Activate.odx|**Activate**オーケストレーションが注文処理ステージで使用します。|  
|Analyze.odx|**分析**オーケストレーションが注文処理ステージで使用します。|  
|CableOrderActions.btproj|BizTalk プロジェクト ファイルです。|  
|Cancel.odx|**キャンセル**オーケストレーションが注文処理ステージで使用します。|  
|Change.odx|**変更**オーケストレーションが注文処理ステージで使用します。|  
|Complete.odx|**完了**オーケストレーションが注文処理ステージで使用します。|  
|Validate.odx|**検証**オーケストレーションが注文処理ステージで使用します。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\CableOrderStage1  
  
|ファイル|Description|  
|----------|-----------------|  
|CableOrder1.odx|最初の注文処理ステージのオーケストレーションです。|  
|CableOrderStage1.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\CableOrderStage2  
  
|ファイル|Description|  
|----------|-----------------|  
|CableOrder2.odx|2 番目の注文処理ステージのオーケストレーションです。|  
|CableOrderStage2.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\OrderBroker  
  
|ファイル|Description|  
|----------|-----------------|  
|OrderBroker.btproj|BizTalk プロジェクト ファイルです。|  
|OrderBroker.odx|**OrderBroker**オーケストレーションです。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\OrderManager  
  
|ファイル|Description|  
|----------|-----------------|  
|CheckInterrupt.odx|**CheckInterrupt**オーケストレーションです。|  
|ErrorHandler.odx|**ErrorHandler**オーケストレーションです。|  
|ExceptionHandler.odx|**ExceptionHandler**オーケストレーションです。|  
|Interrupter.odx|**Interrupter**オーケストレーションです。|  
|OrderManager.btproj|BizTalk プロジェクト ファイルです。|  
|OrderManager.odx|**OrderManager**オーケストレーションです。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderBrokerMaps  
  
|ファイル|Description|  
|----------|-----------------|  
|CSR_OrderRequest_To_Order.btm|カスタマー サービスの注文要求を注文メッセージに変換するマップです。|  
|CSR_OrderRequest_To_Servicing_OrderRequest.btm|カスタマー サービスの注文要求をサービスへのメッセージに変換するマップです。|  
|CSR_OrderRequest_To_SQLHistoryInsert.btm|カスタマー サービスの注文要求を履歴更新メッセージに変換するマップです。|  
|OrderBrokerMaps.btproj|BizTalk プロジェクト ファイルです。|  
|Order_To_CSR_OrderRequest.btm|注文メッセージをカスタマー サービスの注文要求に変換するマップです。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderBrokerSchemas  
  
|ファイル|Description|  
|----------|-----------------|  
|CSR_OrderRequest.xsd|カスタマー サービス要求のスキーマです。|  
|OrderBrokerSchemas.btproj|BizTalk プロジェクト ファイルです。|  
|Servicing_OrderRequest.xsd|サービス システムに送信されるメッセージを定義するスキーマです。|  
|SQLHistoryInsert.xsd|SQL 履歴メッセージのスキーマです。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderBroker_Proxy  
  
|ファイル|Description|  
|----------|-----------------|  
|Global.asax|生成されたファイルです。|  
|Index.htm|生成されたファイルです。|  
|OrderBrokerOrch_OrderPort.asmx|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderBroker_Proxy\App_Code  
  
|ファイル|Description|  
|----------|-----------------|  
|DataTypes.cs|生成されたファイルです。|  
|OrderBrokerOrch_OrderPort.asmx.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderHandler  
  
|ファイル|Description|  
|----------|-----------------|  
|OrderHandler.cs|C# コード、 **OrderHandler**オブジェクト。|  
|OrderHandler.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Rules  
  
|ファイル|Description|  
|----------|-----------------|  
|DecodeAndValidateOrderRules.xml|ビジネス ルール エンジンのルール ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\SampleMessages  
  
|ファイル|Description|  
|----------|-----------------|  
|CSR_OrderRequest.xml|サンプルのカスタマー サービスの注文要求です。|  
|OrderEnvelope.xml|サンプルの注文エンベロープです。|  
  
 内のファイル\<インストール ディレクトリ\>\SchemaClasses  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|InternalMessages.cs|ソリューションのコンポーネント間で通信するために使用するメッセージを定義するクラスの C# コードです。|  
|SchemaClasses.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Schemas  
  
|ファイル|Description|  
|----------|-----------------|  
|Order.xsd|注文メッセージ用のスキーマです。|  
|OrderPropertySchema.xsd|注文メッセージ用の昇格させたプロパティ スキーマです。|  
|Schemas.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Scripts  
  
|ファイル|Description|  
|----------|-----------------|  
|CleanDirs.cmd|ソリューションのテスト版専用のファイルが使用するディレクトリを削除するコマンド ファイルです。|  
|CreateAppReferences.vbs|アプリケーション参照を作成する VBScript です。|  
|CreateQueues.vbs|MSMQ キューを作成する VBScript です。|  
|CreateSouthridgeVideoApplication.cmd|SSO 構成ストアの構成値を作成するコマンド ファイルです。|  
|CreateTestDirectories.cmd|ソリューションのテスト版のディレクトリを作成するコマンド ファイルです。|  
|DeployBPM.cmd|ソリューションを展開するコマンド ファイルです。|  
|regac.bat|グローバル アセンブリ キャッシュ (GAC) のアセンブリを登録するバッチ ファイルです。|  
|SouthridgeVideoSSOConfiguration.xml|初期 SSO 構成値を含むファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\ServiceLevelTracking  
  
|ファイル|Description|  
|----------|-----------------|  
|Activity_CustomerOrderRequest.cs|カスタマーの注文要求の BAM アクティビティを定義する C# コードです。|  
|Activity_OrderManager.cs|注文マネージャの BAM アクティビティを定義する C# コードです。|  
|Activity_ServiceOrderRequest.cs|サービスの注文要求の BAM アクティビティを定義する C# コードです。|  
|ServiceLevelTracking.cs|アクティビティの抽象基本クラスを定義する C# コードです。|  
|ServiceLevelTracking.csproj|C# のプロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Utilities  
  
|ファイル|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|CableOrderException.cs|ケーブル注文の例外クラスを定義する C# コードです。|  
|Helper.cs|さまざまなヘルパ クラスおよびヘルパ メソッドの C# コードです。|  
|Recaller.cs|C# コード、 **Recaller**オブジェクト。|  
|SSOConfigHelper.cs|SSO 構成ヘルパー オブジェクトと SSO 構成ヘルパー メソッドの C# コードです。|  
|Utilities.csproj|C# のプロジェクト ファイルです。|  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューション リファレンス](../core/business-process-management-solution-reference.md)   
 [ビジネス プロセス管理ソリューションのコンポーネント](../core/components-of-the-business-process-management-solution.md)
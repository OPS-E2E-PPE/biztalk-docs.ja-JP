---
title: ビジネス プロセス管理ソリューションのファイルのインベントリ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, file inventory
ms.assetid: 3efb7495-9543-4fe0-8f4b-26c19b3b6db9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2f01ad1c8d0f9cafae6ade68de653f609827353
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388031"
---
# <a name="file-inventory-for-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのファイル一覧
このセクションでは、サブディレクトリ、およびビジネス プロセス管理ソリューションのソース ファイルを示します。 ビジネス プロセス管理ソリューションのソース ファイルの既定のインストール ディレクトリは[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \scenarios\bpm です。 次の表では、このパスを交換する前に説明\<インストール ディレクトリ\>します。  
  
 内のファイル\<インストール ディレクトリ\>  
  
|ファイル|説明|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.SouthridgeVideo.sln|Visual Studio ソリューション ファイルです。|  
|readme.html|ソリューションの Readme ファイルです。|  
|ReplacePKToken.vbs|ソリューションのビルド時に、ソリューション ファイルに公開キー トークンを修正する VBScript です。|  
|ReplacePKToken.wsf|ReplacePKToken VBScript 用の Windows スクリプト ファイル。|  
|SetupBPM.bat|公開キーを作成し、公開キーへの参照の更新ソリューションをコンパイルします。 ソリューションのデプロイについては、次を参照してください。[ビジネス プロセス管理ソリューションの展開](../core/deploying-the-business-process-management-solution.md)します。|  
  
 内のファイル\<インストール ディレクトリ\>\BAM  
  
|ファイル|説明|  
|----------|-----------------|  
|BAMServiceOrder.xls|BAM データの Excel スプレッドシートです。|  
|BAMServiceOrder.xml|BAM のデータ項目の種類を定義するスキーマです。|  
  
 内のファイル\<インストール ディレクトリ\>\Bindings  
  
|ファイル|説明|  
|----------|-----------------|  
|CableOrderAppBindings-test.xml|テスト版のバインド ファイル、 **CableOrderApp**アプリケーション。|  
|CableOrderAppBindings.xml|バインド ファイル、 **CableOrderAPP**アプリケーション。|  
|MessagingAppBindings-test.xml|テスト版のバインド ファイル、 **MessagingApp**アプリケーション。|  
|MessagingAppBindings.xml|バインド ファイル、 **MessagingApp**アプリケーション。|  
|OrderBrokerAppBindings-test.xml|テスト版のバインド ファイル、 **OrderBrokerApp**アプリケーション。|  
|OrderBrokerAppBindings.xml|バインド ファイル、 **OrderBrokerApp**アプリケーション。|  
  
 内のファイル\<インストール ディレクトリ\>\CableProvisioningSystemClient  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|注文システムをシミュレートするコンポーネントのクライアント側のアセンブリ ファイルです。|  
|CableProvisioningSystemClient.csproj|C#プロジェクト ファイルです。|  
|CPSClient.cs|クライアントのソースです。 含まれています、 **OrderHandlerWrapper**クラス コード。|  
|OrderException.cs|C#クラスを定義するためのファイル、 **OrderException**します。|  
  
 内のファイル\<インストール ディレクトリ\>\CableProvisioningSystemServer  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|注文システムをシミュレートするコンポーネントのサーバー側のアセンブリ ファイルです。|  
|CableProvisioningSystemServer.csproj|C#プロジェクト ファイルです。|  
|CableProvisioningSystemServer.csproj.user|Visual Studio プロジェクト ユーザー オプション ファイル|  
|CPSServer.cs|サーバーのソース。|  
  
 内のファイル\<インストール ディレクトリ\>\CSRWebApp  
  
|ファイル|説明|  
|----------|-----------------|  
|CSRMainForm.aspx|顧客サービスの入力 ASP フォームです。|  
|CSRMainForm.aspx.cs|C#フォームの背後にあるコードです。|  
|Web.Config|フォームの構成ファイル。|  
  
 Files in \<Install Directory\>\CSRWebApp\App_WebReferences\SouthridgeVideo_OrderBroker  
  
|ファイル|説明|  
|----------|-----------------|  
|orderbrokerorch_orderport.disco|Disco ファイル、 **OrderBroker** web サービスとして表示されます。|  
|orderbrokerorch_orderport.discomap|生成されたファイルです。|  
|orderbrokerorch_orderport.wsdl|WSDL ファイルを**OrderBroker** web サービスとして表示されます。|  
  
 内のファイル\<インストール ディレクトリ\>\FacilitiesSimulator  
  
|ファイル|説明|  
|----------|-----------------|  
|FacilitiesSimulator.csproj|C#facilities simulator のプロジェクト ファイルです。|  
|FacilitiesSimulator.csproj.user|Visual Studio プロジェクト ユーザー オプション ファイル|  
|FacilitiesSimulatorForm.cs|C#facilities simulator のコードです。|  
|FacilitiesSimulatorForm.resx|リソース ファイル。|  
  
 内のファイル\<インストール ディレクトリ\>\HistoryDB  
  
|ファイル|説明|  
|----------|-----------------|  
|CreateDatabase.cmd|履歴データベースを作成する SQL ファイルをドライブにファイルです。|  
|SouthridgeVideoHistory.sql|履歴データベースを作成する SQL コマンド。|  
  
 内のファイル\<インストール ディレクトリ\>\IOperationsSystem  
  
|ファイル|説明|  
|----------|-----------------|  
|IOperationsSystem.cs|操作システムの定義をインターフェイスします。|  
|IOperationsSystem.csproj|C#プロジェクト ファイルです。|  
|IOperationsSystem.csproj.user|Visual Studio プロジェクト ユーザー オプション ファイル|  
  
 内のファイル\<インストール ディレクトリ\>\IOrderHandler  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|IOrderHandler.cs|インターフェイスの定義、 **OrderHandler**します。|  
|IOrderHandler.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Maps  
  
|ファイル|説明|  
|----------|-----------------|  
|Maps.btproj|BizTalk プロジェクト ファイルです。|  
|Order_To_SQLUpdateStatus.btm|状態を更新するメッセージを注文に変換するマップです。|  
  
 内のファイル\<インストール ディレクトリ\>\MessagingSchemas  
  
|ファイル|説明|  
|----------|-----------------|  
|ErrorEnvelope.xsd|エラー メッセージのエンベロープを定義するスキーマです。|  
|MessagingSchemas.btproj|BizTalk プロジェクト ファイルです。|  
|OrderEnvelope.xsd|注文のエンベロープを定義するスキーマです。|  
|OrderStatusEnvelope.xsd|注文のステータス メッセージのエンベロープを定義するスキーマです。|  
|SQLUpdateStatus.xsd|SQL の状態更新メッセージのエンベロープを定義するスキーマです。|  
  
 内のファイル\<インストール ディレクトリ\>\OperationsClient  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|OperationsClient.csproj|C#操作クライアントのプロジェクトです。|  
|OpsClient.cs|C#操作クライアントのコードです。|  
|OpsExceptions.cs|C#操作の例外を定義するコードです。|  
  
 内のファイル\<インストール ディレクトリ\>\OperationsHandler  
  
|ファイル|説明|  
|----------|-----------------|  
|OperationsHandler.csproj|C#操作ハンドラーのプロジェクト ファイルです。|  
|OpsHandler.cs|C#コードを**OpsHandler**します。 使用される、 **OpsClient**操作システムの要求を行います。|  
  
 内のファイル\<インストール ディレクトリ\>\OperationsServer  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|OperationsServer.csproj|C#操作サーバーのプロジェクト ファイルです。|  
|OpsServer.cs|C#インスタンスを提供する操作サーバーのコード、 **OpsHandler**オブジェクト。|  
  
 内のファイル\<インストール ディレクトリ\>\OpsAdapter  
  
|ファイル|説明|  
|----------|-----------------|  
|OpsAdapter.sln|Ops アダプタの visual Studio ソリューションです。|  
|Register_Ops_Adapter.vbs|Ops アダプタを登録する VBScript です。|  
|SetupOpsAdapter.bat|Ops アダプタを設定するバッチ ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OpsAdapter\IOpsAIC  
  
|ファイル|説明|  
|----------|-----------------|  
|IOpsAIC.cs|C#インターフェイスを定義するためのコード ファイル、**初期化**と**Execute** Ops アダプタによって呼び出されるメソッド。|  
|IOpsAIC.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OpsAdapter\OpsAdapterMgmt  
  
|ファイル|説明|  
|----------|-----------------|  
|AdapterManagement.cs|C#Ops アダプタのソース ファイルです。|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|OpsAdapterMgmt.csproj|C#Ops アダプタのソース ファイルです。|  
|TransmitHandler.xsd|C#Ops アダプタのソース ファイルです。|  
|TransmitLocation.xsd|C#Ops アダプタのソース ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OpsAdapter\OpsTxAdapter  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|OpsAdapterExceptions.cs|C#Ops アダプタのソース ファイルです。|  
|OpsAdapterProperties.cs|C#Ops アダプタのソース ファイルです。|  
|OpsTransmitAdapterBatch.cs|C#Ops アダプタのソース ファイルです。|  
|OpsTransmitter.cs|C#Ops アダプタのソース ファイルです。|  
|OpsTxAdapter.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\CableOrderActions  
  
|ファイル|説明|  
|----------|-----------------|  
|Activate.odx|**Activate**オーケストレーションが注文処理ステージで使用します。|  
|Analyze.odx|**分析**オーケストレーションが注文処理ステージで使用します。|  
|CableOrderActions.btproj|BizTalk プロジェクト ファイルです。|  
|Cancel.odx|**キャンセル**オーケストレーションが注文処理ステージで使用します。|  
|Change.odx|**変更**オーケストレーションが注文処理ステージで使用します。|  
|Complete.odx|**完了**オーケストレーションが注文処理ステージで使用します。|  
|Validate.odx|**検証**オーケストレーションが注文処理ステージで使用します。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\CableOrderStage1  
  
|ファイル|説明|  
|----------|-----------------|  
|CableOrder1.odx|最初の注文処理ステージのオーケストレーションです。|  
|CableOrderStage1.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\CableOrderStage2  
  
|ファイル|説明|  
|----------|-----------------|  
|CableOrder2.odx|2 番目の注文処理ステージのオーケストレーションです。|  
|CableOrderStage2.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\OrderBroker  
  
|ファイル|説明|  
|----------|-----------------|  
|OrderBroker.btproj|BizTalk プロジェクト ファイルです。|  
|」の OrderBroker.odx|**OrderBroker**オーケストレーションします。|  
  
 内のファイル\<インストール ディレクトリ\>\Orchestrations\OrderManager  
  
|ファイル|説明|  
|----------|-----------------|  
|CheckInterrupt.odx|**CheckInterrupt**オーケストレーションします。|  
|ErrorHandler.odx|**ErrorHandler**オーケストレーションします。|  
|ExceptionHandler.odx|**ExceptionHandler**オーケストレーションします。|  
|Interrupter.odx|**Interrupter**オーケストレーションします。|  
|OrderManager.btproj|BizTalk プロジェクト ファイルです。|  
|OrderManager.odx|**OrderManager**オーケストレーションします。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderBrokerMaps  
  
|ファイル|説明|  
|----------|-----------------|  
|CSR_OrderRequest_To_Order.btm|注文メッセージをカスタマー サービスの注文要求を変換するマップします。|  
|CSR_OrderRequest_To_Servicing_OrderRequest.btm|カスタマー サービスの注文要求をサービスにメッセージを変換するマップします。|  
|CSR_OrderRequest_To_SQLHistoryInsert.btm|カスタマー サービスの注文要求を履歴更新メッセージに変換するマップです。|  
|OrderBrokerMaps.btproj|BizTalk プロジェクト ファイルです。|  
|Order_To_CSR_OrderRequest.btm|カスタマー サービスの注文要求を注文メッセージを変換するマップします。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderBrokerSchemas  
  
|ファイル|説明|  
|----------|-----------------|  
|CSR_OrderRequest.xsd|カスタマー サービス要求のスキーマです。|  
|OrderBrokerSchemas.btproj|BizTalk プロジェクト ファイルです。|  
|Servicing_OrderRequest.xsd|サービスのシステムに送信されるメッセージを定義するスキーマです。|  
|SQLHistoryInsert.xsd|SQL 履歴メッセージのスキーマです。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderBroker_Proxy  
  
|ファイル|説明|  
|----------|-----------------|  
|Global.asax|生成されたファイルです。|  
|index.htm|生成されたファイルです。|  
|OrderBrokerOrch_OrderPort.asmx|生成されたファイルです。|  
|Web.config|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderBroker_Proxy\App_Code  
  
|ファイル|説明|  
|----------|-----------------|  
|DataTypes.cs|生成されたファイルです。|  
|OrderBrokerOrch_OrderPort.asmx.cs|生成されたファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\OrderHandler  
  
|ファイル|説明|  
|----------|-----------------|  
|OrderHandler.cs|C#コードを**OrderHandler**オブジェクト。|  
|OrderHandler.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Rules  
  
|ファイル|説明|  
|----------|-----------------|  
|DecodeAndValidateOrderRules.xml|ビジネス ルール エンジンの規則ファイル。|  
  
 内のファイル\<インストール ディレクトリ\>\SampleMessages  
  
|ファイル|説明|  
|----------|-----------------|  
|CSR_OrderRequest.xml|サンプル顧客サービスの注文要求。|  
|OrderEnvelope.xml|サンプルの注文エンベロープです。|  
  
 内のファイル\<インストール ディレクトリ\>\SchemaClasses  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|InternalMessages.cs|C#ソリューションのコンポーネント間の通信に使用されるメッセージを定義するクラスのコードです。|  
|SchemaClasses.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Schemas  
  
|ファイル|説明|  
|----------|-----------------|  
|Order.xsd|注文メッセージのスキーマです。|  
|OrderPropertySchema.xsd|注文メッセージのプロパティのスキーマを昇格します。|  
|Schemas.btproj|BizTalk プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Scripts  
  
|ファイル|説明|  
|----------|-----------------|  
|CleanDirs.cmd|専用ソリューションのテスト バージョンのファイルで使用するディレクトリを削除するコマンド ファイルです。|  
|CreateAppReferences.vbs|アプリケーション参照を作成する VBScript です。|  
|CreateQueues.vbs|MSMQ キューを作成する VBScript です。|  
|CreateSouthridgeVideoApplication.cmd|SSO 構成ストアの構成値を作成するコマンド ファイルです。|  
|CreateTestDirectories.cmd|ソリューションのテスト版のディレクトリを作成するコマンド ファイルです。|  
|DeployBPM.cmd|ソリューションを配置するコマンド ファイルです。|  
|regac.bat|グローバル アセンブリ キャッシュ (GAC) にアセンブリを登録するバッチ ファイルです。|  
|SouthridgeVideoSSOConfiguration.xml|初期 SSO 構成値を含むファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\ServiceLevelTracking  
  
|ファイル|説明|  
|----------|-----------------|  
|Activity_CustomerOrderRequest.cs|C#顧客の注文要求の BAM アクティビティを定義するコードです。|  
|Activity_OrderManager.cs|C#注文マネージャの BAM アクティビティを定義するコードです。|  
|Activity_ServiceOrderRequest.cs|C#サービスの注文要求の BAM アクティビティを定義するコードです。|  
|ServiceLevelTracking.cs|C#アクティビティの抽象基本クラスを定義するコードです。|  
|ServiceLevelTracking.csproj|C#プロジェクト ファイルです。|  
  
 内のファイル\<インストール ディレクトリ\>\Utilities  
  
|ファイル|説明|  
|----------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報ファイルです。|  
|CableOrderException.cs|C#ケーブル注文の例外クラスを定義するコードです。|  
|Helper.cs|C#さまざまなヘルパー クラスとメソッドのコードです。|  
|Recaller.cs|C#コードを**Recaller**オブジェクト。|  
|SSOConfigHelper.cs|C#SSO 構成ヘルパー オブジェクトやメソッドのコードです。|  
|Utilities.csproj|C#プロジェクト ファイルです。|  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューション リファレンス](../core/business-process-management-solution-reference.md)   
 [ビジネス プロセス管理ソリューションのコンポーネント](../core/components-of-the-business-process-management-solution.md)
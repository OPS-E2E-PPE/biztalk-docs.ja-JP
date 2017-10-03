---
title: "WCF LOB アダプター SDK に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2cda4248-2efa-4e3d-a5ce-9a57728c51e1
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 090c53b91ad30f522bc5522fbeb457d7de868456
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-wcf-lob-adapter-sdk"></a>WCF LOB アダプター SDK に関する既知の問題
このトピックに関連付けられている既知の問題について説明、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 これらの問題の解決策を提供します。  
  
## <a name="unable-to-change-sdk-features-using-add-or-remove-programs"></a>追加または削除するプログラムを使用して SDK の機能を変更できません。
 **問題**: を使用して**プログラム追加と削除**コントロール パネル の機能を変更する障害が発生した、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Windows Vista を実行するコンピューターでします。  
  
 **解像度**: を使用せずに**プログラム追加と削除**インストールを変更するには、Setup.exe プログラムを再実行します。  
  
## <a name="base-runtime"></a>基本ランタイム  
  
### <a name="applications-using-transactions-in-asynchronous-proxy-must-explicitly-call-proxyopen"></a>非同期のプロキシでトランザクションを使用するアプリケーションが Proxy.Open を明示的に呼び出す必要があります。  
 **問題**: 非同期プロキシでアダプターでトランザクションを使用するアプリケーションはプロキシを明示的に呼び出す必要があります。トランザクションをフロー用に開く。  
  
 **解像度**: これを行うプロキシがによって生成された後、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ように、クライアント プログラム。  
  
```  
EchoAdapterClient echoAdapterProxy = new EchoAdapterClient("mEchoConfiguration");  
echoAdapterProxy.Open();  
...  
```  
  
### <a name="iduplexchannel-shape-not-supported"></a>IDuplexChannel 図形がサポートされていません  
 **問題**:、IDuplexChannel チャネル形状は、このリリースでサポートされていません。  
  
 **解像度**: WCF チャネル モデルを使用して、双方向チャネルをサポートする WCF カスタム バインドを作成します。  
  
### <a name="request-schema-generated-with-or-without-in-or-out-parameters"></a>パラメーターまたは Out パラメーターの有無が生成されるスキーマを要求します。  
 **問題**: で、 **ExportInputXmlSchema**クラスのメソッド**OperationMetadata**、要求スキーマは、常に生成場合でも、任意で、または out パラメーターことはできません。  
  
### <a name="providing-multiple-operation-namespaces"></a>複数の操作の名前空間を提供します。  
 **問題**: アダプター開発者が 1 つの操作のグループの複数の操作の名前空間を提供している場合、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]無効な WSDL が生成されます。 生成された入力と出力メッセージ パーツが各操作には、適切なスキーマ参照にリンクできません。  
  
 **解像度**: 各 OperationMetadata.OperationGroup が単一 OperationMetadata.OperationNamespace にマップされていることを確認します。  
  
### <a name="overloaded-operations-not-supported"></a>オーバー ロードされた操作がサポートされていません  
 **問題**: このリリースで SDK の動的なコントラクト ジェネレーター (WSDL ビルダー) コンポーネントをサポートしていないオーバー ロードされた操作は、同じ操作という名前が異なる署名します。  
  
### <a name="fault-contract-not-supported"></a>エラー コントラクトがサポートされていません  
 **問題**: このリリースでは、SDK の動的なコントラクト ジェネレーター (WSDL ビルダー) コンポーネントをサポートしませんエラー コントラクトのメタデータ。  
  
### <a name="failure-when-receiving-messages"></a>メッセージの受信時のエラー  
 **問題**: 受信するとき、失敗する場合は、特定のメッセージを処理するとき、アダプターの可能性がある、**受信タイムアウト**小さな値に設定されているプロパティをバインドします。 返されたエラーがアダプターに固有のものです。  
  
 **回避策**: 設定、**受信タイムアウト**プロパティのバインドに大きな値の場合は、インスタンスの 23時 59分: 59 に、これは、最大値。  
  
### <a name="adapter-stalls-during-message-processing"></a>メッセージの処理中にアダプターの停止  
 **問題**: アダプターへの要求の数が多い、作業項目の処理が失速見える可能性があります。  
  
 新しい接続を開くときに、アダプターは .NET スレッド プールで処理される作業項目をキューします。 接続を開いた後さらに作業項目がキューに入れを各メッセージを処理します。 Threadpool が不足している新しい接続を開く要求はメッセージを処理する要求をブロックして、デッドロックが発生します。  
  
 **解像度**: 最終的に、要求がタイムアウトし、推奨される解像度の値を処理するか、スレッド プール内のスレッドの数を増やすメッセージの数を減らすかが、処理は続行されます。  
  
 スレッドの数を増やすの値を変更[ProcessModelSection.MaxWorkerThreads プロパティ](https://msdn.microsoft.com/library/system.web.configuration.processmodelsection.maxworkerthreads.aspx)です。  
  
## <a name="design-time-proxy-and-schema-generation-tools"></a>デザイン時のプロキシとスキーマの生成ツール  
  
### <a name="limitations-with-select-contract-type"></a>契約の種類の制限事項  
 **問題**:「Select コントラクト型」フィルターが適用される、カテゴリ ツリーと使用可能な操作の一覧です。 場合は、アダプターのコンシューマーが受信および送信の両方の操作を含むカテゴリ ノードを選択し、すべての WSDL と「選択コントラクト型」のフィルター処理に関係なく、生成されたプロキシの一部となります。  
  
 **解像度**: カテゴリ全体を選択する代わりに個々 の操作を選択します。  
  
### <a name="error-with-add-adapter-service-reference-visual-studio-plug-in"></a>アダプター サービス参照を Visual Studio プラグインの追加エラーが発生しました  
 **問題**: Visual Studio を使用して、プロキシは既に生成されている場合に、BizTalk プロジェクト、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、同じアダプターから別のプロキシを生成すると、このエラーが生成されます:"名前空間 '\<グローバル名前空間 >'既にときに '{コントラクト名}' の定義を含むプロジェクトをコンパイルします"。  
  
 このリリースでは、プロキシの編集は許可されません。  
  
 **解像度**: BizTalk プロジェクトで余分なプロキシ ファイルを削除します。 生成されたプロキシに含まれるその他の操作する場合は、プロキシ ファイルを削除し、使用、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を検索または、メタデータを参照して、プロキシを再生成します。  
  
### <a name="error-with-consume-adapter-service-biztalk-project-add-in"></a>エラーが発生しましたがアダプターを使用する BizTalk プロジェクト アドインでは、サービス  
 **問題**: 前の問題と同様に、BizTalk プロジェクトで Visual Studio で、共通の型から生成されたスキーマに存在する場合、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、BizTalk プロジェクトがコンパイルに失敗します。  
  
 **解像度**: BizTalk プロジェクトで余分な XML スキーマ ファイルを削除、検索または必要なメタデータを参照する アダプター サービス参照を使用して、新しい XML スキーマ ファイルを再生成します。  
  
### <a name="error-with-rootnode-typename-in-biztalk-projects"></a>RootNode TypeName BizTalk プロジェクト内のエラー  
 **問題**: で、BizTalk プロジェクトから、スキーマが生成される場合、Visual Studio で、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティで、次のエラーが発生コンパイル時:"ノード\<ノード参照 >-このルート ノードの有効な .NET 型名を指定します。  このルート ノードの現在の .NET 型名が正しくありません (予約済みの BizTalk キーワードまたは、無効な c# 識別子)。  
  
 **解像度**: エラーで参照されているルート ノードを選択し、プロパティで、削除、無効な文字または予約済みの単語を**RootNode TypeName**プロパティです。  
  
### <a name="metadata-generation-tool-limitations"></a>メタデータの生成ツールの制限  
 **問題**: アダプター開発者向けに XML スキーマ構造を提供している場合、OperationMetadata や TypeMetadata の派生クラスと構造が無視されるか、DataContractSerializer、メタデータによって禁止されていますが、XML スキーマに含まれています生成ツールにフォールバック シリアル化に XmlSerializer を使用します。  
  
 **解像度**: スキーマでは、禁止されている構成要素を削除するかを使用して、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] DataContractSerializer に準拠している XML スキーマ定義を生成するメタデータ オブジェクト モデルです。  
  
### <a name="binding-name-property-does-not-take-effect"></a>名前プロパティのバインドは反映されません。  
 **問題**: でバインディング名プロパティを変更する、**バインド プロパティの [全般**のタブ、**アダプター サービス参照の追加**] ダイアログ ボックスが有効になりません。  
  
 **解像度**: を使用して、AdapterBinding 派生クラスを次のように名前を変更します。  
  
```  
[Browsable(false)]  
public new virtual string Name  
{  
     set  
     {  
          base.Name = value;  
     }  
     get  
     {  
          return base.Name;  
     }  
}  
```  
  
### <a name="timeout-when-retrieving-metadata"></a>メタデータの取得時のタイムアウト  
 **問題**: などのツールを使用してメタデータを取得するとき、タイムアウト時間に発生する場合は、アダプターには、多くの操作が含まれており、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、WCF アダプター サービス開発ウィザード、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]でさまざまな操作を取得しようとする場合ある時。  
  
 **解像度**: を減らして、操作を選択します。  
  
### <a name="avoid-generating-schemas-which-reference-an-external-import"></a>外部のインポートの参照を生成するスキーマを回避します。  
 **問題**: 外部インポートする 1 つまたは複数の参照を含むスキーマの生成を回避する必要があります。 これは、外部リンクは後にできません。  
  
## <a name="setup"></a>セットアップ  
  
### <a name="setup-halts-while-checking-disk-space"></a>セットアップが停止したディスク領域を確認中には  
 **問題**: インストールするときに[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、使用可能なディスク領域のセットアップを確認し、セットアップは続行できないことを示すダイアログ ボックスが表示される可能性があります。  
  
 **解像度**: のサイレント インストールを実行することによって、この問題を回避することがこの問題が発生したときに[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]コマンド プロンプトでします。 例:  
  
```  
Msiexec.exe /package AdapterFramework.msi /qr  
```  
  
### <a name="biztalk-server-developer-tools-required"></a>必要な BizTalk Server 開発者ツール  
 **問題**: ターゲット システムに Visual Studio と Microsoft BizTalk Server 開発者ツールがないが、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]セットアップは失敗します。 これは、BizTalk Server 開発ツールをインストールするために、コンピューター上に存在することが必要なため、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
 **解像度**: 対象のコンピュータに BizTalk Server をインストールする前に開発者ツールのインストールがあることを確認する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。  
  
### <a name="corrupt-biztalk-server-installation-causes-sdk-to-fail"></a>BizTalk Server のエラーが発生する SDK インストール原因が壊れています  
 **問題**: BizTalk Server のインストールに失敗、次のエラーで失敗する SDK のインストールが発生する可能性があります:"DirectoryNotFound exception"。  
  
 **解像度**: BizTalk Server をアンインストールしています。  
  
 
## <a name="see-also"></a>参照  
 [BizTalk Server の概要](../../core/getting-started-with-biztalk-server.md)
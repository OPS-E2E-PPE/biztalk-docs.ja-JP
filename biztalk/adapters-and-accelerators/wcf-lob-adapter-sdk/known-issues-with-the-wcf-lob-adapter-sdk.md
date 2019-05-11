---
title: WCF LOB Adapter SDK に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cda4248-2efa-4e3d-a5ce-9a57728c51e1
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4142612b58c4978da1e97c69e112b91f19509fe9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363597"
---
# <a name="known-issues-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK に関する既知の問題
このトピックでは、関連付けられている既知の問題を説明します、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 これらの問題の解決策も提供します。  
  
## <a name="unable-to-change-sdk-features-using-add-or-remove-programs"></a>追加または削除するプログラムを使用して SDK の機能を変更できません。
 **問題**:使用して**プログラム追加と削除**コントロール パネルの の機能を変更するが失敗した、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]コンピューターで、Windows Vista を実行します。  
  
 **解像度**:使用する代わりに**プログラム追加と削除**インストールを変更するには、Setup.exe プログラムを再実行します。  
  
## <a name="base-runtime"></a>基本ランタイム  
  
### <a name="applications-using-transactions-in-asynchronous-proxy-must-explicitly-call-proxyopen"></a>トランザクションを使用して、非同期プロキシでアプリケーションが Proxy.Open を明示的に呼び出す必要があります。  
 **問題**:非同期のプロキシでアダプターを使用したトランザクションを使用するアプリケーションでは、プロキシを明示的に呼び出す必要があります。トランザクションをフロー用に開く。  
  
 **解像度**:これによって、プロキシが生成されたら、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]クライアント プログラムに示すようにします。  
  
```  
EchoAdapterClient echoAdapterProxy = new EchoAdapterClient("mEchoConfiguration");  
echoAdapterProxy.Open();  
...  
```  
  
### <a name="iduplexchannel-shape-not-supported"></a>IDuplexChannel 図形がサポートされていません  
 **問題**:このリリースでは、IDuplexChannel チャネル形状がサポートされていません。  
  
 **解像度**:双方向チャネルをサポートする WCF カスタム バインドを作成するのにには、WCF チャネル モデルを使用します。  
  
### <a name="request-schema-generated-with-or-without-in-or-out-parameters"></a>要求のスキーマや Out パラメーターの有無を生成  
 **問題**:**ExportInputXmlSchema**クラスのメソッド**OperationMetadata**、要求スキーマは常に生成場合でも、任意で、または out パラメーターを含めてもなりません。  
  
### <a name="providing-multiple-operation-namespaces"></a>複数の操作の名前空間を提供します。  
 **問題**:アダプター開発者は、1 つの操作のグループの複数の操作の名前空間を提供する場合、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]無効な WSDL を生成します。 生成された入力と出力メッセージの部分の各操作は、適切なスキーマのリファレンスをリンクできません。  
  
 **解像度**:各 OperationMetadata.OperationGroup が 1 つ OperationMetadata.OperationNamespace にマップされていることを確認します。  
  
### <a name="overloaded-operations-not-supported"></a>オーバー ロードされた操作がサポートされていません  
 **問題**:このリリースでは、SDK の動的なコントラクト ジェネレーター (WSDL ビルダー) コンポーネントはオーバー ロードされた操作、名前が同じで別の署名は、操作をサポートしません。  
  
### <a name="fault-contract-not-supported"></a>エラー コントラクトがサポートされていません  
 **問題**:このリリースで、SDK の動的なコントラクト ジェネレーター (WSDL ビルダー) コンポーネントは、フォールト コントラクトのメタデータをサポートしません。  
  
### <a name="failure-when-receiving-messages"></a>エラー メッセージを受信するときに  
 **問題**:アダプターの場合は、特定のメッセージを処理するときの失敗の可能性がある、受信するときに、**受信タイムアウト**小さい値に設定されているプロパティをバインドします。 返されたエラーは、アダプターに固有のものです。  
  
 **回避策**:設定、**受信タイムアウト**プロパティのバインドに大きな値の場合は、たとえば 23時 59分: 59 に、これは、最大値。  
  
### <a name="adapter-stalls-during-message-processing"></a>メッセージの処理中にアダプターの停止  
 **問題**:アダプターへの要求の数が多い場合は、遅延する作業項目の処理があります。  
  
 新しい接続を開くときに、アダプターは、.NET threadpool によって処理される作業項目をキューします。 接続を開くと、さらに作業項目は、各メッセージの処理にキューイングされます。 Threadpool が不足している、新しい接続を開く要求がメッセージを処理する要求をブロックされて、デッドロックが発生します。  
  
 **解像度**:最終的に、要求がタイムアウトになり、推奨される解決策は処理を threadpool のスレッドの数を増やすメッセージの数を減らすか、ただし、処理が続行されます。  
  
 値を変更すると、スレッドの数を増やすには、 [ProcessModelSection.MaxWorkerThreads プロパティ](https://msdn.microsoft.com/library/system.web.configuration.processmodelsection.maxworkerthreads.aspx)します。  
  
## <a name="design-time-proxy-and-schema-generation-tools"></a>デザイン時のプロキシとスキーマの生成ツール  
  
### <a name="limitations-with-select-contract-type"></a>契約の種類の制限事項  
 **問題**:「契約の種類」のフィルター処理は、カテゴリ ツリーと、使用可能な操作の一覧に適用されます。 アダプターのコンシューマーが受信と送信の両方の操作を含むカテゴリ ノードを選択した場合は、WSDL および「選択のコントラクト型」のフィルター処理に関係なく、生成されたプロキシの一部それらすべてになります。  
  
 **解像度**:全体のカテゴリを選択する代わりに個々 の操作を選択します。  
  
### <a name="error-with-add-adapter-service-reference-visual-studio-plug-in"></a>アダプター サービス参照を Visual Studio プラグインを追加するとエラー  
 **問題**:BizTalk プロジェクトで Visual Studio を使用して、プロキシは既に生成されている場合、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、同じアダプターから別のプロキシを生成すると、このエラーが生成されます。"名前空間 '\<グローバル名前空間\>' と既に '{コントラクト名}' の定義が含まれています、プロジェクトをコンパイルします"。  
  
 このリリースでは、プロキシの編集は許可されません。  
  
 **解像度**:BizTalk プロジェクト内の余分なプロキシ ファイルを削除します。 追加の操作は、生成されたプロキシに含まれる場合に、プロキシ ファイルを削除し、使用、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を検索または、メタデータを参照し、プロキシを再生成します。  
  
### <a name="error-with-consume-adapter-service-biztalk-project-add-in"></a>エラーがアダプターを使用するサービスの BizTalk プロジェクト アドイン  
 **問題**:前の問題のように、BizTalk プロジェクトで Visual Studio で、共通の型から生成されたスキーマに存在する場合、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、BizTalk プロジェクトのコンパイルに失敗します。  
  
 **解像度**:BizTalk プロジェクトで余分な XML スキーマ ファイルを削除し、検索または必要なメタデータを参照する Consume Adapter Service 参照を使用し、新しい XML スキーマ ファイルを再生成します。  
  
### <a name="error-with-rootnode-typename-in-biztalk-projects"></a>BizTalk プロジェクト内の RootNode TypeName とエラー  
 **問題**:BizTalk プロジェクトで Visual Studio から、スキーマが生成される場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]無効な文字または予約語が含まれて、 **RootNode TypeName**プロパティ、コンパイル時に次のエラーが発生します。"ノード\<ノード参照\>-このルート ノードの有効な .NET 型名を指定します。  このルート ノードの現在の .NET 型名が無効です (予約済みの BizTalk キーワードまたは無効なはC#識別子)。  
  
 **解像度**:エラーで参照されているルート ノードを選択し、プロパティで、削除、無効な文字または予約語から、 **RootNode TypeName**プロパティ。  
  
### <a name="metadata-generation-tool-limitations"></a>メタデータの生成ツールの制限事項  
 **問題**:アダプター開発者が XML スキーマ構造を提供する場合、OperationMetadata や TypeMetadata の派生クラスでメタデータの生成ツールにフォールバックを使用して、XML スキーマには無視または DataContractSerializer が禁止されている構成要素が含まれていますシリアル化に XmlSerializer です。  
  
 **解像度**:スキーマで禁止されている構成要素を削除するか、使用、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] DataContractSerializer に準拠する XML スキーマ定義を生成するメタデータ オブジェクト モデルです。  
  
### <a name="binding-name-property-does-not-take-effect"></a>Name プロパティのバインドは無効になります  
 **問題**:バインド名のプロパティを変更する、**バインド プロパティの [全般**のタブ、**アダプター サービス参照の追加**] ダイアログ ボックスが有効になりません。  
  
 **解像度**:使用して、AdapterBinding 派生したクラス名を次のように変更します。  
  
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
  
### <a name="timeout-when-retrieving-metadata"></a>メタデータを取得するときにタイムアウト  
 **問題**:アダプターに多くの操作が含まれている場合などのツールを使用してメタデータを取得するときにタイムアウトが発生する可能性があります、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、WCF アダプター サービス開発ウィザード、または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]一度に多くの操作を取得しようとした場合。  
  
 **解像度**:選択した操作の数を減らします。  
  
### <a name="avoid-generating-schemas-which-reference-an-external-import"></a>外部のインポートを参照するスキーマの生成を回避します。  
 **問題**:外部のインポートを 1 つまたは複数の参照を含むスキーマの生成を避ける必要があります。 これは、外部のリンクは後にありません。  
  
## <a name="setup"></a>セットアップ  
  
### <a name="setup-halts-while-checking-disk-space"></a>セットアップが停止中に、ディスク領域を確認します。  
 **問題**:インストールするときに[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]セットアップが使用可能なディスク領域を確認して、セットアップは続行できませんを示すダイアログ ボックスが表示される可能性があります。  
  
 **解像度**:サイレント インストールを実行することによって、この問題を回避することがこの問題が発生したときに[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]コマンド プロンプトでします。 例 :  
  
```  
Msiexec.exe /package AdapterFramework.msi /qr  
```  
  
### <a name="biztalk-server-developer-tools-required"></a>必要な BizTalk Server 開発者ツール  
 **問題**:ターゲット システムの開発者ツールがない場合は Visual Studio と Microsoft BizTalk Server があるときに、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]セットアップは失敗します。 これは、BizTalk Server の開発者ツールをインストールするには、コンピューター上に存在する必要があるため、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
 **解像度**:対象のコンピュータが BizTalk Server をインストールする前に、開発者ツールのインストールされているかどうかを必ず、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。  
  
### <a name="corrupt-biztalk-server-installation-causes-sdk-to-fail"></a>BizTalk Server のインストール エラーの原因が失敗する SDK が壊れています  
 **問題**:BizTalk Server のインストールに失敗、次のエラーで失敗する SDK のインストールがあります。"DirectoryNotFound exception。"  
  
 **解像度**:アンインストールし、BizTalk Server を再インストールします。  
  
 
## <a name="see-also"></a>参照  
 [BizTalk Server の概要](../../core/getting-started-with-biztalk-server.md)
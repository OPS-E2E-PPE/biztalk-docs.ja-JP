---
title: "カスタム パーティの解決 (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, parties
- pipeline components [custom], examples
- pipeline components [custom], parties
- examples, pipeline components [custom]
- parties, pipeline components [custom]
- parties, custom
ms.assetid: 1f88450f-5fe9-486d-bfb8-fd11181c78b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b88d8126a1d63760888edbcd7691ad4bd76426
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="custom-party-resolution-biztalk-server-sample"></a>カスタム パーティの解決 (BizTalk Server サンプル)
カスタム パーティの解決サンプルでは、カスタム パイプライン コンポーネントを作成し、カスタム パーティを解決する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 カスタム パーティの解決サンプルでは、次の一連の手順を使用してタスクを実行します。  
  
1.  XML ドキュメントがフォルダから取得されます。  
  
2.  パイプラインによりパーティが解決されます。  
  
3.  XML メッセージがフォルダに書き込まれます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<サンプル パス >*\Pipelines\CustomPartyResolution\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs|C# ソース ファイルのアセンブリ情報です。|  
|Cleanup.bat|クリーンアップ バッチ ファイルです。|  
|CustomPartyResolution.sln|ソリューション ファイルです。|  
|CustomPartyResolutionBinding.xml|バインド ファイルです。|  
|CustomPartyResolutionPipeline.btp|パイプライン ファイルです。|  
|CustomPartyResolutionPipeline.btproj|パイプライン プロジェクト ファイルです。|  
|CustomPartyResolutionPipelineComponent.cs|パイプライン コンポーネント C# ソース コードです。|  
|CustomPartyResolutionPipelineComponent.csproj|パイプライン コンポーネント Visual Studio プロジェクト ファイルです。|  
|InboundDocumentSchema.xsd|受信ドキュメント スキーマです。|  
|PartyResolutionStream.cs|パーティの解決ストリーム C# ソース コードです。|  
|RoutingPropertySchema.xsd|ルーティング プロパティ スキーマ ファイルです。|  
|SampleInboundDocumentSchema.xml|受信ドキュメント スキーマ ファイルです。|  
|SampleInboundDocumentSchema_Party1.xml|サンプル データ インスタンスです。|  
|SampleInboundDocumentSchema_Party2.xml|サンプル データ インスタンスです。|  
|Setup.bat|サンプル パイプライン コンポーネント バッチ ファイルをビルドおよび設定します。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-custom-party-resolution-sample"></a>カスタム パーティの解決サンプルをビルドおよび初期化するには  
  
1.  コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。  
  
     *\<サンプル パス >*\Pipelines\CustomPartyResolution\  
  
2.  ファイル Setup.bat を実行します。処理内容は次のとおりです。  
  
    -   サンプルで使用される入力ディレクトリと出力ディレクトリを作成します。  
  
    -   新しいキー ファイルを生成します。  
  
    -   カスタム パーティの解決パイプライン コンポーネントをビルドおよび展開します。  
  
    -   ビルドしたパイプライン コンポーネントへのコピー、 *\<インストール パス >*\Pipeline Components ディレクトリ。  
  
    -   送信ポートおよび受信ポートを作成します。  
  
> [!NOTE]
>  このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-custom-party-resolution-sample"></a>カスタム パーティの解決サンプルを実行するには  
  
1.  ファイル SampleInboundDocumentSchema_Party1.xml または SampleInboundDocumentSchema_Party2.xml を \In フォルダにコピーします。  
  
2.  その結果が \Out フォルダにファイル名で表示されます*guid*.xml です。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダ)](../core/pipelines-biztalk-server-samples-folder.md)
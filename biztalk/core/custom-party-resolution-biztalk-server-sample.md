---
title: カスタム パーティの解決 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- pipeline components [custom], examples
- pipeline components [custom], parties
- examples, pipeline components [custom]
- parties, pipeline components [custom]
- parties, custom
ms.assetid: 1f88450f-5fe9-486d-bfb8-fd11181c78b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 066d551cc2d802778673492de5de352fbcd48fa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353351"
---
# <a name="custom-party-resolution-biztalk-server-sample"></a>カスタム パーティの解決 (BizTalk Server サンプル)
カスタム パーティの解決サンプルでは、カスタム パーティを解決するカスタム パイプライン コンポーネントを記述する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 カスタム パーティの解決サンプルでは、次の一連の手順を使用してタスクを実現します。  
  
1.  XML ドキュメントは、フォルダーから取得されます。  
  
2.  パイプラインは、パーティを解決します。  
  
3.  XML メッセージは、フォルダーに書き込まれます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<サンプル パス >* \Pipelines\CustomPartyResolution\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報C#ソース ファイル。|  
|Cleanup.bat|クリーンアップ バッチ ファイルです。|  
|CustomPartyResolution.sln|ソリューション ファイルです。|  
|CustomPartyResolutionBinding.xml|バインド ファイルです。|  
|CustomPartyResolutionPipeline.btp|パイプライン ファイルです。|  
|CustomPartyResolutionPipeline.btproj|パイプライン プロジェクト ファイルです。|  
|CustomPartyResolutionPipelineComponent.cs|パイプライン コンポーネントC#ソース コード。|  
|CustomPartyResolutionPipelineComponent.csproj|パイプライン コンポーネント Visual Studio プロジェクト ファイルです。|  
|InboundDocumentSchema.xsd|受信ドキュメント スキーマです。|  
|PartyResolutionStream.cs|パーティの解決ストリームC#ソース コード。|  
|RoutingPropertySchema.xsd|ルーティング プロパティ スキーマ ファイルです。|  
|SampleInboundDocumentSchema.xml|受信ドキュメント スキーマ ファイルです。|  
|SampleInboundDocumentSchema_Party1.xml|サンプル データのインスタンスです。|  
|SampleInboundDocumentSchema_Party2.xml|サンプル データのインスタンスです。|  
|Setup.bat|ビルドおよび設定のサンプル パイプライン コンポーネント バッチ ファイルです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-custom-party-resolution-sample"></a>ビルドして、カスタム パーティの解決サンプルの初期化  
  
1.  コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。  
  
     *\<サンプル パス >* \Pipelines\CustomPartyResolution\  
  
2.  次の操作を実行する、Setup.bat ファイルを実行します。  
  
    -   このサンプルで使用される入力と出力ディレクトリを作成します。  
  
    -   新しいキー ファイルを生成します。  
  
    -   ビルドし、カスタム パーティの解決パイプライン コンポーネントを展開します。  
  
    -   ビルドしたパイプライン コンポーネントのコピー、 *\<インストール パス >* \Pipeline Components ディレクトリ。  
  
    -   ポートと受信ポート、送信を作成します。  
  
> [!NOTE]
>  エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-custom-party-resolution-sample"></a>カスタム パーティの解決サンプルを実行するには  
  
1.  ファイル SampleInboundDocumentSchema_Party1.xml または SampleInboundDocumentSchema_Party2.xml を \In フォルダにコピーします。  
  
2.  結果が \Out フォルダにファイル名に表示されます*guid*.xml です。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)
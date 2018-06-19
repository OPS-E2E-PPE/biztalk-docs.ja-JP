---
title: XSLT 変換コンポーネント (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- XSLT, examples
- examples, XSLT
ms.assetid: 9152e897-4db9-4924-b37e-fd9e908dbef1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1879cb4d748e974454f929bde2018c24b5d276f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974928"
---
# <a name="xslt-transform-component-biztalk-server-sample"></a>XSLT 変換コンポーネント (BizTalk Server サンプル)
XSLT 変換コンポーネント サンプルは、カスタム パイプライン コンポーネントを作成し、XSLT を使用して XML メッセージを変換する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、次の手順で変換を行います。  
  
1.  XML ドキュメントがフォルダから取得されます。  
  
2.  パイプラインは Transform.xsl を使用して、XML ドキュメントを電子メール メッセージの HTML 本文に変換します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Pipelines\XslTransformComponent\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs|C# アセンブリ ファイル。|  
|Cleanup.bat|サンプルのクリーンアップ ファイル。|  
|Confirmation.xsd|サンプルのスキーマ ファイル。|  
|DocInstance.xml|変換するサンプルの .xml ファイル。|  
|SendHtmlMessage.btproj|BizTalk プロジェクト。|  
|Setup.bat|構成バッチ ファイル。|  
|Xml2HtmlSendPipeline.btp|BizTalk Server パイプライン ファイル。|  
|XslTransform.csproj|C# プロジェクト。|  
|XslTransformComponent.sln|サンプルのソリューション ファイル。|  
|XslTransformComponentBinding.XML|XML バインド ファイル。|  
|XslTransformer.cs|C# ソース コード。|  
|Transform.xsl|DocInstance.xml の変換に使用する XSLT ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順を使用して、XSLT 変換コンポーネント サンプルをビルドおよび初期化します。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウでディレクトリ変更 (**cd)** 次のフォルダーに。  
  
     *\<パスのサンプル\>* \Pipelines\XslTransformComponent  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   サンプルで使用される入力 (\In) フォルダと出力 (\Out) フォルダを作成します。  
  
    -   新しいキー ファイルを生成します。  
  
    -   XSLT 変換コンポーネント パイプラインをビルドおよび展開します。  
  
    -   ビルドしたパイプライン コンポーネントへのコピー、\<インストール パス\>\Pipeline Components フォルダーです。  
  
    -   送信ポートおよび受信ポートを作成します。  
  
    > [!NOTE]
    >  このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。  
  
    > [!NOTE]
    >  Setup.bat が行った変更を元に戻すには、BizTalk Server 管理 MMC コンソールでホスト インスタンスをまず停止し、再起動する必要があります。 次に、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順を使用して、XSLT 変換コンポーネント サンプルを実行します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  DocInstance.xml を \In フォルダにコピーします。  
  
2.  \Out フォルダ内の結果を確認します (出力ファイル名は guid.htm)。  
  
## <a name="configuring-this-sample-using-smtp"></a>SMTP を使用したこのサンプルの構成  
 次の手順を使用して、SMTP サーバーで使用する XSLT 変換コンポーネント サンプルを構成します。  
  
#### <a name="to-configure-this-sample-using-smtp"></a>SMTP を使用してこのサンプルを構成するには  
  
1.  SMTP のトランスポートの種類を使用するように XSLT 変換コンポーネントの送信ポートを再構成します。  
  
2.  SMTP 構成に合わせてアドレス (URI) パラメータを変更し、SMTP 設定を構成します。  
  
## <a name="running-this-sample-with-output-to-an-smtp-port"></a>SMTP ポートに出力するためのこのサンプルの実行  
 次の手順を使用して、XSLT 変換コンポーネント サンプルを実行し、SMTP ポートに出力します。  
  
#### <a name="to-run-this-sample-with-output-to-an-smtp-port"></a>SMTP ポートに出力するためのこのサンプルを実行するには  
  
1.  DocInstance.xml を \In フォルダにコピーします。  
  
2.  SMTP に構成されている送信先受信者のメール クライアントの結果を確認します。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)
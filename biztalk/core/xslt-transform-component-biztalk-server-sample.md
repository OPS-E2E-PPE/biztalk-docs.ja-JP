---
title: XSLT 変換コンポーネント (BizTalk Server サンプル) |Microsoft Docs
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
ms.openlocfilehash: 7695bfd51eced669ab4bc71cd2823ec694d4284d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279108"
---
# <a name="xslt-transform-component-biztalk-server-sample"></a>XSLT 変換コンポーネント (BizTalk Server サンプル)
XSLT 変換コンポーネント サンプルでは、XSLT を使用して XML メッセージを変換するカスタム パイプライン コンポーネントを記述する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 サンプルでは、次の手順で変換を実現します。  
  
1.  XML ドキュメントは、フォルダーから取得されます。  
  
2.  パイプラインは Transform.xsl を使用して電子メール メッセージの HTML 本文に XML ドキュメントを変換します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<Samples Path\>* \Pipelines\XslTransformComponent\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|AssemblyInfo.cs|C#アセンブリ ファイルです。|  
|Cleanup.bat|サンプルのクリーンアップ ファイル。|  
|Confirmation.xsd|サンプル スキーマ ファイルです。|  
|DocInstance.xml|サンプルの .xml ファイルを変換します。|  
|SendHtmlMessage.btproj|BizTalk プロジェクトです。|  
|Setup.bat|構成バッチ ファイルです。|  
|Xml2HtmlSendPipeline.btp|BizTalk Server パイプライン ファイルです。|  
|XslTransform.csproj|C#プロジェクトです。|  
|XslTransformComponent.sln|サンプル ソリューション ファイルです。|  
|XslTransformComponentBinding.XML|XML バインド ファイルです。|  
|XslTransformer.cs|C#ソース コードです。|  
|Transform.xsl|DocInstance.xml の変換に使用される XSLT ファイル。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順を使用して、ビルドして、XSLT 変換コンポーネント サンプルを初期化します。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウでディレクトリ変更 (**cd)** 次のフォルダーに。  
  
     *\<Samples Path\>* \Pipelines\XslTransformComponent  
  
2.  ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
    -   入力 (\In) と、サンプルで使用される出力 (\Out) フォルダーを作成します。  
  
    -   新しいキー ファイルを生成します。  
  
    -   ビルドし、XSLT 変換コンポーネント パイプラインをデプロイします。  
  
    -   ビルドしたパイプライン コンポーネントのコピー、\<インストール パス\>\Pipeline Components フォルダー。  
  
    -   ポートと受信ポート、送信を作成します。  
  
    > [!NOTE]
    >  エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。  
  
    > [!NOTE]
    >  Setup.bat による変更を元に戻したりするにはまず停止し、BizTalk Server 管理 MMC コンソールから、ホスト インスタンスを再起動します。 次に、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 XSLT 変換コンポーネント サンプルを実行するのにには、次の手順を使用します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  DocInstance.xml を \In フォルダにコピーします。  
  
2.  (出力ファイル名は guid.htm) \Out フォルダで結果を確認します。  
  
## <a name="configuring-this-sample-using-smtp"></a>SMTP を使用してこのサンプルの構成  
 SMTP サーバーを使用するのに XSLT 変換コンポーネント サンプルを構成するのにには、次の手順を使用します。  
  
#### <a name="to-configure-this-sample-using-smtp"></a>SMTP を使用してこのサンプルを構成するには  
  
1.  SMTP トランスポートの種類を使用する XSLT 変換コンポーネントの送信ポートを再構成します。  
  
2.  SMTP 構成に合わせてアドレス (URI) パラメーターを変更することで、SMTP 設定を構成します。  
  
## <a name="running-this-sample-with-output-to-an-smtp-port"></a>SMTP ポートに出力をこのサンプルを実行しています。  
 SMTP ポートに出力を XSLT 変換コンポーネント サンプルを実行するのにには、次の手順を使用します。  
  
#### <a name="to-run-this-sample-with-output-to-an-smtp-port"></a>SMTP ポートに出力をこのサンプルを実行するには  
  
1.  DocInstance.xml を \In フォルダにコピーします。  
  
2.  SMTP に構成されている受信者の電子メール クライアントで結果を確認を送信します。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)
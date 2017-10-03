---
title: "MIME (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines, MIME/SMIME Encoder [pipeline component]
- examples, send pipelines
- MIME/SMIME Encoder [pipeline component], send pipelines
- MIME/SMIME Encoder [pipeline component], examples
- examples, MIME/SMIME Encoder [pipeline component]
ms.assetid: f76c720d-3798-4f15-a5f9-885ddf421d57
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e948aeca31d3eb9908d6933f5ac375bce206761
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mime-biztalk-server-sample"></a>MIME (BizTalk Server サンプル)
MIME サンプルは、送信パイプラインで MIME エンコードが行われる方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、MIMEIn フォルダを受信場所として構成します。 このフォルダーにサンプル ファイル ImageInput.gif のようなファイルを置くと、このファイル内のメッセージが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって次の手順で処理されます。  
  
1.  受信場所フォルダ MIMEIn からメッセージ ファイルを取得します。  
  
2.  送信パイプラインを使用して、メッセージをそのまま渡します。  
  
3.  メッセージ ボックス データベースで、メッセージを送信パイプラインにルーティングします。  
  
4.  送信パイプラインで、MIME エンコードを実行し、そのファイルを送信アダプタ フォルダ MIMEOut に配置します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*> \Pipelines\MIME\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|ImageInput.GIF|サンプル入力ファイルです。|  
|SampleMimeEncoding.btproj<br /><br /> SampleMimeEncoding.sln|このサンプルのプロジェクト ファイルとソリューション ファイルです。|  
|SampleMimeEncodingBinding.xml|ポートのバインドなど、自動化されたセットアップに使用されます。|  
|SendMimePipeline.btp|MIME エンコーダー コンポーネントを含む [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信パイプライン ファイルです。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順に従って、MIME サンプルをビルドおよび初期化します。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*> \Pipelines\MIME  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   フォルダに、このサンプルの入力 (MIMEIn) フォルダと出力 (MIMEOut) フォルダを作成します。  
  
         \<*パスのサンプル*> \Pipelines\MIME  
  
    -   コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
        > [!NOTE]
        >  このサンプルでは、次の警告を作成して、ポートのバインド時に表示されます。  
  
        > [!NOTE]
        >  `Warning: Receive handler not specified for receive location "MIMEReceiveLocation"; updating with first receive handler with matching transport type.`  
  
        > [!NOTE]
        >  これらの警告は、無視してもかまいません  (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  
  
    -   受信場所を有効にし、送信ポートを開始します。  
  
> [!NOTE]
>  インストールされている別の場所からこのサンプルを実行する場合は、最初に参照を追加する必要があります、 **Microsoft.BizTalk.Pipeline.Components**アセンブリ。  
  
> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
> [!NOTE]
>  開き、Setup.bat ファイルを実行しなくてもこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。 Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順に従って、MIME サンプルを実行します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  ファイル ImageInput.gif を MIMEIn フォルダにコピーします。  
  
2.  テキスト ファイルが MIMEOut フォルダに作成されることを確認します。 このテキスト ファイルの名前はメッセージ ID の GUID に基づきます。 このファイルには、入力ファイル ImageInput.gif の MIME でエンコードされたコンテンツが含まれます。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダ)](../core/pipelines-biztalk-server-samples-folder.md)
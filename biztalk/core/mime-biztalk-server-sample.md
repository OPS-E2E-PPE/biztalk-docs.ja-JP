---
title: MIME (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, MIME/SMIME Encoder [pipeline component]
- examples, send pipelines
- MIME/SMIME Encoder [pipeline component], send pipelines
- MIME/SMIME Encoder [pipeline component], examples
- examples, MIME/SMIME Encoder [pipeline component]
ms.assetid: f76c720d-3798-4f15-a5f9-885ddf421d57
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4ea6cfa8f2d6b4c94f1e48531167688901132cb
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527568"
---
# <a name="mime-biztalk-server-sample"></a>MIME (BizTalk Server サンプル)
MIME サンプルは、MIME エンコードの送信パイプライン内でを実行する方法を示します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、受信場所として、MIMEIn フォルダを構成します。 サンプル ファイル ImageInput.gif、このフォルダーにファイルを配置すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の手順を使用してこのファイルにメッセージを処理します。  

1.  受信場所フォルダ MIMEIn からメッセージ ファイルを取得します。  

2.  受信パイプラインでメッセージをそのまま渡します。  

3.  メッセージ ボックス データベースには、送信パイプラインにメッセージをルーティングします。  

4.  送信パイプラインで MIME エンコードの実行し、送信アダプタ フォルダ MIMEOut にファイルを配置します。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Pipelines\MIME\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                           ファイル                            |                                                                                              説明                                                                                               |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                         Cleanup.bat                          | アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。 |
|                        ImageInput.GIF                        |                                                                                           サンプル入力ファイルです。                                                                                           |
| SampleMimeEncoding.btproj<br /><br /> SampleMimeEncoding.sln |                                                                              このサンプルのプロジェクト ファイルとソリューション ファイルです。                                                                               |
|                SampleMimeEncodingBinding.xml                 |                                                                             ポートのバインドなど、自動化されたセットアップに使用されます。                                                                             |
|                     SendMimePipeline.btp                     |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MIME エンコーダー コンポーネントとパイプライン ファイルを送信します。                                 |
|                          Setup.bat                           |                                                                               このサンプルをビルドおよび初期化するために使用されます。                                                                                |

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順を使用して、ビルドして、MIME サンプルを初期化します。  

#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    \<*パスのサンプル*\>\Pipelines\MIME  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - フォルダーには、入力 (mimein フォルダ) とこのサンプルの出力 (MIMEOut) フォルダを作成します。  

      \<*パスのサンプル*\>\Pipelines\MIME  

   - コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

     > [!NOTE]
     >  このサンプルでは、作成してポートをバインドするときに、次の警告が表示されます。  

     > [!NOTE]
     >  `Warning: Receive handler not specified for receive location "MIMEReceiveLocation"; updating with first receive handler with matching transport type.`  

     > [!NOTE]
     >  これらの警告は、無視してもかまいません  (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  

   - 受信場所を有効にし、送信ポートを開始します。  

> [!NOTE]
>  参照を追加する必要があります最初がインストールされている別の場所からこのサンプルを実行する場合、 **Microsoft.BizTalk.Pipeline.Components**アセンブリ。  
> 
> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
> 
> [!NOTE]
>  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。 Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

## <a name="running-this-sample"></a>このサンプルの実行  
 MIME サンプルを実行するのにには、次の手順を使用します。  

#### <a name="to-run-this-sample"></a>このサンプルを実行するには  

1.  ファイル ImageInput.gif のコピーを MIMEIn フォルダに配置します。  

2.  テキスト ファイルが MIMEOut フォルダに作成を確認します。 このテキスト ファイルの名前は、メッセージ ID の GUID に基づきます。 このファイルには、入力ファイル ImageInput.gif の MIME でエンコードされたコンテンツが含まれています。  

## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)
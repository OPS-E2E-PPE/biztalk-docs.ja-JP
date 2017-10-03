---
title: "CustomComponent (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- messages, streamed
- pipeline components [custom], configuring
ms.assetid: ed0da9f5-8cc7-4528-be8c-35b80744fd38
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e178faee3ed05d4d77eec8f4da182c7dcd21a67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="customcomponent-biztalk-server-sample"></a>CustomComponent (BizTalk Server サンプル)
CustomComponent サンプルは、ストリームされたメッセージを変更するカスタム パイプライン コンポーネントを作成して使用する方法を示します。 このサンプルは、パイプライン デザイナにおけるカスタム パイプライン コンポーネントの構成方法も示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、入力メッセージの前または後に文字列を追加するカスタム パイプライン コンポーネントを実装します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はストリーミング モードでメッセージを処理します。そのため、メッセージ全体がメモリに読み込まれることはありません。 カスタム パイプライン コンポーネントは、以下の順序で処理を実行します。  
  
1.  BizTalk が、特定のフォルダにあるファイルからテキスト メッセージを取り出します。  
  
2.  テキスト メッセージは、カスタム パイプライン コンポーネント FixMsg が含まれる受信パイプラインを通じて送信されます。 このコンポーネントを、メッセージの先頭に文字列を挿入するように構成します。  
  
3.  処理後のテキスト メッセージは、カスタム パイプライン コンポーネント FixMsg が含まれる送信パイプラインを通じて送信されます。 このコンポーネントを、メッセージの最後に文字列を追加するように構成します。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、特定のフォルダー内のファイルにテキスト メッセージを書き込みます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*> \Pipelines\CustomComponent\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|Input.txt|サンプル入力ファイルです。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|\FixMsg フォルダー内のファイル: <br /><br /> AssemblyInfo.cs、FixMsg.csproj、FixMsg.sln|このサンプルのカスタム パイプライン コンポーネント部分のプロジェクト、ソリューション、アセンブリ情報ファイルです。|  
|\FixMsg フォルダー内のファイル: <br /><br /> FixMsg.cs|パイプライン コンポーネント インターフェイスを実装します。|  
|\FixMsg フォルダー内のファイル: <br /><br /> FixMsgStream.cs|ラッパーを実装して、 **System.IO.Stream**クラス、データのストリーム処理を有効にします。|  
|\FixMsg フォルダー内のファイル: <br /><br /> FixMsgDescription.cs|パイプライン デザイナ内でコンポーネント UI リソースへのアクセスと表示を行うための手段を提供します。|  
|\FixMsg フォルダー内のファイル: <br /><br /> FixMsg.resx|プロパティ記述、アイコン、エラー メッセージが格納されています。|  
|\PipelineComponentSample フォルダー内のファイル: <br /><br /> PipelineComponentSample.btproj、PipelineComponentSample.sln|このサンプルの BizTalk プロジェクト部分のプロジェクト ファイルとソリューション ファイルです。|  
|\PipelineComponentSample フォルダー内のファイル: <br /><br /> PipelineComponentSampleBinding.xml|ポートのバインドなど、自動化されたセットアップに使用されます。|  
|\PipelineComponentSample フォルダー内のファイル: <br /><br /> FixMsgReceivePipeline.btp、FixMsgSendPipeline.btp|それぞれ受信パイプラインおよび送信パイプラインに対する、FixMsg カスタム パイプライン コンポーネントが含まれる [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプラインです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-customcomponent-sample"></a>CustomComponent サンプルをビルドおよび初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*> \Pipelines\CustomComponent  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   次のフォルダに、このサンプル用の入力 (In) フォルダと出力 (Out) フォルダを作成します。  
  
         \<*パスのサンプル*> \Pipelines\CustomComponent  
  
    -   このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、展開します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
        > [!NOTE]
        >  このサンプルは、ポートを作成してバインドする際に、以下の警告を表示します。  
        >   
        >  `Warning: Receive handler not specified for receive location "PCReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "CustomComponent"; updating with first available host.`  
        >   
        >  これらの警告は、無視してもかまいません  (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  
  
    -   受信場所を有効にし、送信ポートを開始します。  
  
> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
> [!NOTE]
>  開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。  
  
> [!NOTE]
>  Setup.bat が行った変更を元に戻すには、まず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理 MMC コンソールでホスト インスタンスを停止し、再起動する必要があります。 次に、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-customcomponent-sample"></a>CustomComponent サンプルを実行するには  
  
1.  テキスト ファイル Input1.txt のコピーを、フォルダ In に貼り付けます。  
  
2.  テキスト ファイルが Out フォルダに作成されることを確認します。このファイルには、ファイル Input.txt の内容が格納されますが、受信パイプラインによって先頭にテキストが挿入され、送信パイプラインによって最後にテキストが追加されます。 このファイルの名前の形式が\< *MessageID*> .xml、場所 *\<MessageID >*メッセージを一意に識別する GUID が生成されます。  
  
## <a name="comments"></a>コメント  
 以下の手順を実行すると、パイプライン デザイナで構成済みのパイプラインを表示することができます。  
  
1.  ソリューション エクスプローラで ReceivePipeline.btp をダブルクリックし、パイプライン デザイナで受信パイプラインを開きます。 確認に FixMsg コンポーネントが配置されている、**検証**受信パイプラインのステージ。  
  
2.  内の FixMsg コンポーネントをクリックして、**検証**デザイン サーフェイス上のステージ。 [プロパティ] ウィンドウで、パイプライン コンポーネントの構成プロパティを参照できます。 されることを確認、 **PrependData**プロパティに設定されている**受信パイプライン文字列の前に追加するデータ**です。  
  
3.  ソリューション エクスプローラで SendPipeline.btp をダブルクリックし、パイプライン デザイナで送信パイプラインを開きます。 確認に FixMsg コンポーネントが配置されている、**プリアセンブル**送信パイプラインのステージ。  
  
4.  内の FixMsg コンポーネントをクリックして**プリアセンブル**デザイン サーフェイス上のステージ。 なお、 **AppendData**プロパティに設定されている**で追加するデータの送信パイプライン文字列**です。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダ)](../core/pipelines-biztalk-server-samples-folder.md)
---
title: CustomComponent (BizTalk Server サンプル) |Microsoft Docs
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
- messages, streamed
- pipeline components [custom], configuring
ms.assetid: ed0da9f5-8cc7-4528-be8c-35b80744fd38
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b5d3e6f90184143b59fe8637b88352f610981b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353263"
---
# <a name="customcomponent-biztalk-server-sample"></a>CustomComponent (BizTalk Server サンプル)
CustomComponent サンプルでは、作成してストリーミングされたメッセージを変更するカスタム パイプライン コンポーネントを使用する方法を示します。 このサンプルでは、パイプライン デザイナーでのカスタム パイプライン コンポーネントの構成も示します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、プレフィックスまたは入力メッセージに文字列を追加できるカスタム パイプライン コンポーネントを実装します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ストリーミング モード、メッセージ全体がメモリに読み込まれていないことを意味のメッセージを処理します。 カスタム パイプライン コンポーネントは、次の一連の手順を使用して示されています。  

1. BizTalk は、特定のフォルダー内のファイルからテキスト メッセージを取得します。  

2. テキスト メッセージは、FixMsg カスタム パイプライン コンポーネントを含む受信パイプラインを通じて送信されます。 メッセージの先頭に文字列を挿入するには、このコンポーネントを構成します。  

3. FixMsg カスタム パイプライン コンポーネントで送信パイプラインを介して結果のテキスト メッセージを送信します。 メッセージの末尾に文字列を追加するコンポーネントを構成するとします。  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 特定のフォルダー内のファイルにテキスト メッセージを書き込みます。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Pipelines\CustomComponent\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                                                     ファイル                                                     |                                                                                              説明                                                                                               |
|-----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                   Cleanup.bat                                                   | アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。 |
|                                                    Input.txt                                                    |                                                                                           サンプル入力ファイルです。                                                                                           |
|                                                    Setup.bat                                                    |                                                                               このサンプルをビルドおよび初期化するために使用されます。                                                                                |
|                  \FixMsg フォルダー。<br /><br /> AssemblyInfo.cs、FixMsg.csproj、FixMsg.sln                  |                                              このサンプルのカスタム パイプライン コンポーネント部分のプロジェクト、ソリューション、およびアセンブリ情報ファイルです。                                               |
|                                  \FixMsg フォルダー。<br /><br /> FixMsg.cs                                   |                                                                             パイプライン コンポーネントのインターフェイスを実装します。                                                                              |
|                               \FixMsg フォルダー。<br /><br /> FixMsgStream.cs                                |                                                      実装のラッパー、 **System.IO.Stream**クラス、データのストリーム処理を有効にします。                                                      |
|                             \FixMsg フォルダー。<br /><br /> FixMsgDescription.cs                             |                                                       アクセスおよびパイプライン デザイナーでコンポーネント UI リソースをレンダリングするためのメソッドを提供します。                                                        |
|                                 \FixMsg フォルダー。<br /><br /> FixMsg.resx                                  |                                                                      プロパティの説明、アイコン、およびエラー メッセージが含まれています。                                                                      |
| \PipelineComponentSample フォルダー。<br /><br /> PipelineComponentSample.btproj、PipelineComponentSample.sln |                                                               このサンプルの BizTalk プロジェクト部分のプロジェクトおよびソリューション ファイル。                                                               |
|             \PipelineComponentSample フォルダー。<br /><br /> PipelineComponentSampleBinding.xml              |                                                                             ポートのバインドなど、自動化されたセットアップに使用されます。                                                                             |
|      \PipelineComponentSample フォルダー。<br /><br /> FixMsgReceivePipeline.btp, FixMsgSendPipeline.btp      |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FixMsg カスタム パイプライン コンポーネントの受信パイプラインおよび送信パイプラインに対するをそれぞれ含むパイプライン。   |

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

#### <a name="to-build-and-initialize-the-customcomponent-sample"></a>ビルドして初期化 CustomComponent サンプル  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    \<*パスのサンプル*\>\Pipelines\CustomComponent  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - 入力 (In) フォルダと出力 (Out) フォルダーに、このサンプル用のフォルダーを作成します。  

      \<*パスのサンプル*\>\Pipelines\CustomComponent  

   - このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、展開します。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

     > [!NOTE]
     >  このサンプルは、ポートを作成してバインドする際に、以下の警告を表示します。  
     >   
     >  `Warning: Receive handler not specified for receive location "PCReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "CustomComponent"; updating with first available host.`  
     >   
     >  これらの警告は、無視してもかまいません  (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  

   - 受信場所を有効にし、送信ポートを開始します。  

> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
> 
> [!NOTE]
>  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。  
> 
> [!NOTE]
>  Setup.bat による変更を元に戻したりするにはまず停止してから、ホスト インスタンスを再起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理 MMC コンソール。 次に、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

## <a name="running-this-sample"></a>このサンプルの実行  

#### <a name="to-run-the-customcomponent-sample"></a>CustomComponent サンプルを実行するには  

1.  テキストのコピーでは、Input.txt をファイルのフォルダーに貼り付けます。  

2.  テキスト ファイルが Out フォルダに作成されたことを確認します。このファイルには、(受信パイプライン) を先頭に、(送信パイプライン) によって最後に挿入される追加のテキスト ファイル Input.txt の内容が含まれています。 このファイルの名前の形式が\< *MessageID*\>、.xml、 *\<MessageID\>* メッセージを一意に識別するために生成される GUID.  

## <a name="comments"></a>コメント  
 次の手順に従って、パイプライン デザイナーで構成済みのパイプラインを表示できます。  

1.  ソリューション エクスプ ローラーで、パイプライン デザイナーで、受信パイプラインを開く ReceivePipeline.btp をダブルクリックします。 FixMsg コンポーネントが内に配置されるかを確認、**検証**受信パイプラインのステージ。  

2.  内の FixMsg コンポーネントをクリックして、**検証**デザイン サーフェイス上のステージ。 [プロパティ] ウィンドウで、パイプライン コンポーネントの構成プロパティを確認できます。 観察、 **PrependData**プロパティに設定されて**受信パイプライン文字列の前に追加するデータ**します。  

3.  ソリューション エクスプローラで、パイプライン デザイナーで、送信パイプラインを開く SendPipeline.btp をダブルクリックします。 FixMsg コンポーネントが内に配置されるかを確認、**プリアセンブル**送信パイプラインのステージ。  

4.  内の FixMsg コンポーネントをクリックします。**プリアセンブル**デザイン サーフェイス上のステージ。 なお、 **AppendData**プロパティに設定されて**送信パイプライン文字列の後に追加するデータ**します。  

## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)
---
title: "HelloWorld (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, messages
ms.assetid: 4416029a-ca76-45a4-b66c-b44cb71ded58
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e70271967086f530ce5421348c118a74019dd366
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="helloworld-biztalk-server-sample"></a>HelloWorld (BizTalk Server サンプル)
HelloWorld サンプルは、BizTalk オーケストレーションを使用して、XML メッセージ (注文書) を関連する別の種類のメッセージ (請求書) に変換する方法を示すものです。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは構成、**で**受信場所としてフォルダーです。 サンプル ファイルなど、ファイルを配置するときに**SamplePOInput.xml**をこのフォルダーに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を次の手順を使用してメッセージを処理します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は受信場所フォルダーから XML 注文書メッセージを取得します。  
  
2.  オーケストレーションで、マップ ファイルを使用して XML 注文書から XML 請求書を作成します。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信アダプターに、結果の XML 請求書メッセージを配置**アウト**フォルダーです。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 企業間のメッセージ交換シナリオでは、取引先から受信した受信メッセージを内部アプリケーションが認識できる形式に変換する作業が必要になる場合があります。 このサンプルでは、**受信**図形、**変換**図形、および**送信**この結果を実現するために図形。 **変換**図形がメッセージ形式の変換が発生したために、このサンプルで重要な役割を果たします。 ドラッグする、**変換**をオーケストレーションに図形し、の送信元メッセージ、マップ名、および送信先メッセージを構成します。 実行中、指定したマップによって送信元メッセージが送信先メッセージにマップされます。  
  
 詳細については、**変換**図形は、「[変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md)です。 マップのビルドの詳細については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)です。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Orchestrations\HelloWorld\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Cleanup.bat|アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|HelloOrchestration.odx|注文書から請求書への変換を行うオーケストレーションです。|  
|HelloWorld.btproj、HelloWorld.sln|このサンプルのプロジェクト ファイルとソリューション ファイルです。|  
|HelloWorldBinding.xml|ポートのバインドなど、自動化されたセットアップに使用されます。|  
|InvoiceSchema.xsd、POSchema.xsd|それぞれ、請求書メッセージと注文書メッセージのスキーマです。|  
|POToInvoice.btm|注文書を請求書に変換するためのマップです。|  
|SamplePOInput.xml|サンプル入力ファイルです。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-helloworld-sample"></a>HelloWorld サンプルをビルドおよび初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Orchestrations\HelloWorld  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   次のフォルダに、このサンプルの入力 (In) フォルダと出力 (Out) フォルダを作成します。  
  
         \<*パスのサンプル*\>\Orchestrations\HelloWorld  
  
    -   コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所と、オーケストレーションの送信ポートおよび受信ポートを作成しバインドします。  
  
    -   受信場所を有効にし、送信ポートを開始します。 オーケストレーションを参加させ、開始します。  
  
> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。 これはイベント ログで確認できます。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-helloworld-sample"></a>HelloWorld サンプルを実行するには  
  
1.  ファイル SamplePOInput.xml のコピーに、**で**フォルダーです。  
  
2.  作成した .xml ファイルを確認、**アウト**フォルダーです。 このファイルには、入力ファイル SamplePOInput.xml から作成された XML 請求書が格納されます。 このファイルの名前の形式が\< *MessageID*\>、.xml、  *\<MessageID\>* メッセージを一意に識別する GUID が生成.  
  
## <a name="uninstalling-this-sample"></a>このサンプルのアンインストール  
  
#### <a name="to-uninstall-the-helloworld-sample"></a>HelloWorld サンプルをアンインストールするには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Orchestrations\HelloWorld\  
  
2.  Cleanup.bat を実行します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション (BizTalk Server サンプル フォルダー)](../core/orchestrations-biztalk-server-samples-folder.md)
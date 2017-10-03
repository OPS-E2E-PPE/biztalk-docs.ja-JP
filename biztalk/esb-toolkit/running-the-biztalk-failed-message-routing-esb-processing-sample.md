---
title: "メッセージのルーティング ESB 処理サンプル BizTalk を実行できませんでした |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2a536a0-cfc8-4ba3-adcd-2b8b580bff85
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a19f8c29c22638be97ae62dfea88d0d2feca6c55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-biztalk-failed-message-routing-esb-processing-sample"></a>メッセージのルーティング ESB 処理サンプル BizTalk を実行できませんでした。
Microsoft BizTalk できませんでしたメッセージ ルーティング ESB 処理サンプルでは、使用する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を管理、シリアル化、および内のすべての条件下で発生する例外をレンダリングする汎用メカニズムとして例外管理フレームワーク[!INCLUDE[prague](../includes/prague-md.md)]. これには、BizTalk 失敗のメッセージのルーティング メカニズムとフォールトによって生成されたメッセージから、オーケストレーション内での例外管理フレームワークによって生成される例外が含まれます。  
  
 BizTalk 失敗のメッセージのルーティング メカニズムは、エラー処理機能の[!INCLUDE[prague](../includes/prague-md.md)]以外の場合は、それを使用して、デザイナーは、従来の代わりとしてのエラーのメッセージの自動処理を指定できます (ここで既定値) の動作失敗した配置するための「中断」キューにメッセージです。 これは、処理のルートに、送信ポートやオーケストレーションなど、サブスクライブしているルーティング先に、エラー メッセージを自動化できます。 エラー メッセージおよびメッセージ コンテキストに昇格する特定のメッセージング失敗に関連するプロパティを選択したすべての以前昇格させたプロパティが降格と元のメッセージのクローンであります。  
  
 受信ポートまたは送信ポートでメッセージのルーティングに失敗しました BizTalk メカニズムを有効にするを選択、**失敗したメッセージの有効化のルーティングを**チェック ボックス、図 1 に示すようにします。  
  
 ![有効にされたルーティング](../esb-toolkit/media/ch6-enabledrouting.gif "Ch6 EnabledRouting")  
  
 **図 1**  
  
 **BizTalk 失敗のメッセージのルーティング メカニズムを有効にします。**  
  
 ただし、エラーまたはオーケストレーションで発生した障害の同様のメカニズムはありません。 代わりに、オーケストレーションの例外ハンドラー内のコードを利用できませんでしたメッセージ ルーティングの BizTalk のメカニズムの機能をエミュレートするために例外管理フレームワーク API のできます。  
  
 このサンプルでは、EAIProcess.RequestPort_FILE をという名前の受信場所は、場所 \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.RequestPort にコピーされたファイルを取得します。  
  
 さらに、ALL という名前の汎用的な送信ポートがあります。Exceptions_FILE 例外管理フレームワークの一部としてインストールされている、GlobalFaultProcessor パイプラインを使用するように構成します。 このポートは、システムで発生しているすべての例外をサブスクライブ、図 2 に示すようにメッセージのメッセージをルーティングし、ESB フォールト メッセージを両方の BizTalk が失敗します。  
  
 ![送信ポート](../esb-toolkit/media/ch6-sendport.gif "Ch6 SendPort")  
  
 **図 2**  
  
 **ALL です。例外の送信ポートのサブスクリプションのすべての種類のエラーまたは例外**  
  
 例外管理フレームワークでは、1 つの形式にすべての例外を正規化し、場所 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions を Microsoft InfoPath 処理命令を使用してシリアル化します。  
  
## <a name="installation"></a>インストール  
 すべての例外管理サンプルは、同じコア サービスと BizTalk アプリケーションのアイテムのセットを使用します。 そのため、すべての例外の管理のサンプルを実行するために例外管理サンプル アイテム 1 回だけをインストールする必要があります。 例外の管理のサンプルをインストールする方法については、次を参照してください。[例外管理のサンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)です。  
  
## <a name="running-the-sample-application"></a>サンプル アプリケーションの実行  
 **BizTalk できませんでしたメッセージ ルーティング ESB 処理サンプルを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所と送信ポートの URL を指している \Source\Samples\Exception Handling\Test\Filedrop フォルダーに適切なディレクトリを確認します。 受信場所が EAIProcess.RequestPort、フォルダーを指定する必要があり、送信ポートの URL は All_Exceptions のフォルダーを指定する必要があります。  
  
2.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
3.  (フォルダーにある \Source\Samples\Exception Handling\Test\Filedrop) EAIProcess.RequestPort をという名前の受信場所フォルダにフォルダー \Source\Samples\Exception Handling\Test\Data から FlatFileReceive_in.txt をという名前のファイルをコピーします。  
  
4.  このメッセージは、テキスト ファイルであり、例外が発生します。 (フォルダーにある \Source\Samples\Exception Handling\Test\Filedrop)、All_Exceptions をという名前のフォルダーを開き、フォールト メッセージを適切なテンプレートを使用して InfoPath に開くをダブルクリックします。 いる ESB 例外処理メカニズムをシリアル化コンテンツ適切にそれを表示するために InfoPath を許可するが表示されます。  
  
5.  次に、コピー、EAIProcess.RequestPort にフォルダー \Source\Samples\Exception Handling\Test\Data から soapmessage [1] .xml という名前のファイルには、場所のフォルダーが表示されます。  
  
6.  このメッセージは、CDATA セクションを含む XML ドキュメントであり、例外が発生します。 All_Exceptions 出力フォルダーを開き、エラー メッセージを開くには、infopath をダブルクリックします。 いる ESB 例外処理メカニズムをシリアル化このコンテンツ適切にそれを表示するために InfoPath を許可するが表示されます。  
  
7.  最後に、コピー、EAIProcess.RequestPort にフォルダー \Source\Samples\Exception Handling\Test\Data から Csqzav01.pdf をという名前のファイルの受信場所。  
  
8.  このメッセージは、PDF ファイルであり、例外が発生します。 All_Exceptions 出力フォルダーを開き、InfoPath で開かフォールト メッセージをダブルクリックします。 ESB 例外処理メカニズムをシリアル化し、Base 64 エンコード、コンテンツをレンダリング InfoPath を許可することが表示されます。
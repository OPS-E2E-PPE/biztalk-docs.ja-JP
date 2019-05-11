---
title: BizTalk を実行するには、メッセージ ルーティング ESB 処理サンプルが失敗しました |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2a536a0-cfc8-4ba3-adcd-2b8b580bff85
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8181c426bac76885b7e06aea93c9c3bb32dc1564
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292562"
---
# <a name="running-the-biztalk-failed-message-routing-esb-processing-sample"></a>BizTalk を実行するには、メッセージ ルーティング ESB 処理サンプルが失敗しました。
Microsoft BizTalk できませんでしたメッセージ ルーティング ESB 処理サンプルでは、使用する方法を示します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]管理、シリアル化、および BizTalk ですべての条件下で発生した例外を表示する汎用メカニズムとして例外管理フレームワークサーバー。 これには、BizTalk 失敗のメッセージのルーティング メカニズムと障害によって生成されたメッセージから、オーケストレーション内で、例外管理フレームワークによって生成される例外が含まれます。  
  
 BizTalk 失敗のメッセージのルーティング メカニズムは、BizTalk Server のエラー処理の機能使用すると、デザイナーは、従来の代替手段としてのエラーのメッセージの自動処理を指定できます (ここで既定値) の動作を配置するには「保留」キューにメッセージが失敗しました。 これは、処理のルートに、エラー メッセージを送信ポートやオーケストレーションなど、サブスクライブしているルーティング先を自動化できます。 エラー メッセージは、元のメッセージとすべての以前昇格させたプロパティが降格とメッセージ コンテキストに昇格し、特定のメッセージング失敗に関連する選択したプロパティの複製です。  
  
 受信ポートまたは送信ポートでメッセージのルーティングに失敗しました BizTalk メカニズムを有効にするのには、選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスを図 1 に示すようにします。  
  
 ![ルーティングを有効になっている](../esb-toolkit/media/ch6-enabledrouting.gif "Ch6 EnabledRouting")  
  
 **図 1**  
  
 **BizTalk 失敗のメッセージのルーティング メカニズムを有効にします。**  
  
 ただし、エラーや障害のオーケストレーションで発生しているのと同様のメカニズムはありません。 代わりに、オーケストレーションの例外ハンドラー内のコードは、BizTalk 失敗のメッセージのルーティング メカニズムの機能をエミュレートするには、例外管理フレームワーク API を活用を実行することができます。  
  
 このサンプルで EAIProcess.RequestPort_FILE という名前の受信場所は、場所 \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.RequestPort にコピーされたファイルを取得します。  
  
 さらに、すべてをという名前の汎用的な送信ポートがあります。Exceptions_FILE 例外管理フレームワークの一部としてインストールされている、GlobalFaultProcessor パイプラインを使用するように構成します。 このポートは、システムで発生しているすべての例外をサブスクライブ、図 2 に示すように失敗したメッセージのメッセージをルーティングおよび ESB エラーのメッセージの両方の BizTalk します。  
  
 ![送信ポート](../esb-toolkit/media/ch6-sendport.gif "Ch6 SendPort")  
  
 **図 2**  
  
 **すべて。例外の送信ポートのサブスクリプションのすべての種類のエラーまたは例外**  
  
 例外管理フレームワークでは、1 つの形式をすべての例外を正規化し、場所 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions を Microsoft InfoPath 処理命令を使用してそれらをシリアル化します。  
  
## <a name="installation"></a>インストール  
 すべての例外管理サンプルでは、同じコア サービスと BizTalk アプリケーションのアイテムのセットを使用します。 そのため、すべての例外管理サンプルを実行できる例外管理サンプル アイテム 1 回だけをインストールする必要があります。 例外管理サンプルをインストールする方法については、次を参照してください。[例外管理サンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)します。  
  
## <a name="running-the-sample-application"></a>サンプル アプリケーションを実行します。  
 **BizTalk できませんでしたメッセージ ルーティング ESB 処理サンプルを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所と送信ポートの URL を指している \Source\Samples\Exception Handling\Test\Filedrop フォルダーに適切なディレクトリを確認します。 受信場所が EAIProcess.RequestPort、フォルダーを指定し、送信ポートの URL は All_Exceptions フォルダーを指定する必要があります。  
  
2.  GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  
  
3.  (\Source\Samples\Exception Handling\Test\Filedrop フォルダー) 内の EAIProcess.RequestPort をという名前の受信場所フォルダーにフォルダー \Source\Samples\Exception Handling\Test\Data から FlatFileReceive_in.txt をという名前のファイルをコピーします。  
  
4.  このメッセージは、テキスト ファイルであり、例外が発生します。 (\Source\Samples\Exception Handling\Test\Filedrop フォルダーにある) All_Exceptions という名前のフォルダーを開き、エラー メッセージを適切なテンプレートを使用して InfoPath に開くをダブルクリックします。 InfoPath のレンダリングを許可するにこと ESB 例外処理メカニズムが、コンテンツを適切にシリアルが表示されます。  
  
5.  次に、コピー、EAIProcess.RequestPort にフォルダー \Source\Samples\Exception Handling\Test\Data から soapmessage [1] .xml という名前のファイルには、場所のフォルダーが表示されます。  
  
6.  このメッセージは、CDATA セクションを含む XML ドキュメントであり、例外が発生します。 All_Exceptions 出力フォルダーを開き、エラー メッセージを InfoPath に開くをダブルクリックします。 InfoPath のレンダリングを許可するにこと ESB 例外処理メカニズムがこのコンテンツを適切にシリアルが表示されます。  
  
7.  最後に、コピー、EAIProcess.RequestPort にフォルダー \Source\Samples\Exception Handling\Test\Data から Csqzav01.pdf をという名前のファイルは受信場所です。  
  
8.  このメッセージは、PDF ファイルであり、例外が発生します。 All_Exceptions 出力フォルダーを開き、InfoPath で開かれることに、エラー メッセージをダブルクリックします。 ESB 例外処理メカニズムがシリアル化し、Base 64 エンコード、コンテンツのレンダリングの InfoPath を許可することが表示されます。
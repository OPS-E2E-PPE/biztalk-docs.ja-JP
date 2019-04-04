---
title: 修復と再送信のカスタム例外ハンドラーのサンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7363c440-44aa-4d08-8290-72787d17ac60
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34bb03565f7b044f9c6c2f29332862ae8aafef7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004483"
---
# <a name="running-the-repair-and-resubmit-custom-exception-handler-sample"></a>修復と再送信のカスタム例外ハンドラーのサンプルを実行します。
修復と再送信のカスタム例外ハンドラーのサンプルでは、ESB と Microsoft BizTalk ベースのアプリケーションを処理し、便利なデザイン パターンを実装に人間の介入を統合するために非常に効果的な方法を示します。 サンプル コードは、ESB 例外管理システムにシームレスに統合します。  
  
 サンプルでは、オーケストレーションでカスタム例外ハンドラーを使用する方法を示します。 オーケストレーション (EAIProcess.odx) でプロセスには、エラーが発生すると、例外ハンドラーが生成し、ESB エラー メッセージがパブリッシュされます。 このエラー メッセージにはでそのペイロードで (と、BizTalk に関連するコンテキスト プロパティを含む)"インフライト"に含まれていたメッセージが含まれます、例外が発生したときと、BizTalk オーケストレーション エンジンによってキャッチされた現在の System.Exception インスタンス。 この場合、「拒否」メッセージと"Approved"メッセージが、エラー メッセージを永続化されます。  
  
 EAIProcessHandler.odx、これが分離された方法で配置され、カスタム例外ハンドラーとして機能する、という名前の 2 番目のオーケストレーションは EAIProcess.odx オーケストレーションで生成された特定のエラー コードをサブスクライブし、エラー メッセージを使用します。 この例外ハンドラーは、元のメッセージ (として型指定されたドキュメント) を抽出し、System.Exception インスタンスは当初、エラー メッセージに永続化します。  
  
 元のメッセージが処理とすべての元のコンテキスト プロパティ使用可能になるようになりました。 カスタム例外ハンドラー (EAIProcessHandler.odx) では、次の場所にファイル システムに"Denied"と"Approved"メッセージの両方をし、書き込みます。  
  
- 承認済みのメッセージ:  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.PostApproval  
  
- 修復と再送信を拒否されたメッセージ:  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.RepairSubmit  
  
- 拒否されたメッセージ:  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.PostDecline  
  
  例外ハンドラーには、Microsoft InfoPath 処理命令を使用してファイル システムに修復と再送信の「拒否」メッセージがシリアル化します。 InfoPath テンプレートには、フォームを編集し、結果を再送信をできます (図 1 参照)、メッセージを検証する EAIProcess.odx オーケストレーションを開始します。  
  
  ![再送信の修復](../esb-toolkit/media/ch6-repairresubmit.gif "Ch6 RepairResubmit")  
  
  **図 1**  
  
  **InfoPath の修復と再送信のテンプレートによって生成されたテスト メッセージ**  
  
  さらに、すべてをという名前の汎用的な送信ポートがあります。GlobalFaultProcessor パイプラインを使用するように構成された Exceptions_FILE します。 このポートが、システムではすべての例外をサブスクライブ、両方の BizTalk は、メッセージのメッセージをルーティングし、ESB エラー メッセージが失敗しました。 例外管理フレームワークでは、それらすべてを 1 つの形式に正規化し、フォルダー \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions に InfoPath 処理命令を使用してシリアル化します。  
  
## <a name="installation"></a>インストール  
 すべての例外管理サンプルでは、同じコア サービスと BizTalk アプリケーションのアイテムのセットを使用します。 そのため、すべての例外管理サンプルを実行できる例外管理サンプル アイテム 1 回だけをインストールする必要があります。 例外管理サンプルをインストールする方法については、[例外管理サンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)を参照してください。  
  
## <a name="running-the-sample-application"></a>サンプル アプリケーションを実行します。  
 **修復と再送信のカスタム例外ハンドラーのサンプルを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所と送信ポートの Url が \Source\Samples\Exception Handling\Test\Filedrop フォルダーに適切なディレクトリを指していることを確認します。 受信場所が EAIProcess.RequestPort、フォルダーを指定し、送信ポートの Url は EAIProcess.PostApproval EAIProcessHandler.PostDecline のフォルダーを指定する必要があります。  
  
2.  GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  
  
3.  \Source\Samples\Exception Handling\Test\Data フォルダーの EAIProcess.RequestPort_FILE 受信場所の指定したフォルダーにある Request_EAIProcessHandler.xml をという名前のサンプル ファイルをコピーして、サンプルを開始する: \Source\Samples\例外 Handling\Test\Filedrop\EAIProcess.RequestPort します。  
  
4.  (\Source\Samples\Exception Handling\Test\Filedrop フォルダー) 内の EAIProcessHandler.PostDecline をという名前のフォルダーを開きます。 例外処理オーケストレーションによって生成された「拒否済み *」メッセージが表示されます。  
  
5.  (\Source\Samples\Exception Handling\Test\Filedrop フォルダー) 内の EAIProcessHandler.RepairSubmit をという名前のフォルダーを開きます。 例外処理オーケストレーションによって生成された"RepairSubmit"メッセージが表示されます。  
  
6.  適切な InfoPath テンプレートで開く RepairSubmit ファイルをダブルクリックします。 編集および再送信できる状態メッセージが表示されます。  
  
7.  値を変更、 **Unit Price**フィールドを**0**に**2**、 をクリックし、**送信**InfoPath のツールバーにあるボタンBizTalk 処理のために編集したドキュメントを送信するフォーム。 送信プロセスは、BizTalk 構成の HTTP 受信場所です。  
  
8.  (\Source\Samples\Exception Handling\Test\Filedrop フォルダー) に EAIProcess.PostApproval フォルダーに移動します。 単価の更新後の値を含む「承認 *」ドキュメントが表示されます。  
  
## <a name="how-the-sample-works"></a>サンプルのしくみ  
 メッセージを送信するには、EAIProcess オーケストレーションがアクティブにします。 では、EAIProcess オーケストレーションでメッセージを処理するときに、単価で 1 を除算しようとします。 単価はゼロであるため、0 除算の例外が発生します。 オーケストレーションのイベント ハンドラーのコードでは、この例外をキャッチし、エラー メッセージを作成します。 この例外にビジネス ロジックの決定、メッセージの注文数量は 10 より大きい、 **FaultCode**フィールドの値の**1000**します。  
  
 EAIProcess オーケストレーションをし、直接バインドされたポートを通じて BizTalk メッセージ ボックスに、エラー メッセージを発行し、オーケストレーションが終了します。  
  
 メッセージにサブスクライブする、EAIProcessHandler という名前のカスタム エラー ハンドラー オーケストレーション、 **FaultCode**フィールドの値の**1000**、新しいエラー メッセージを取得します。 オーケストレーション内のコードは、「拒否」メッセージと、InfoPath ファイルを作成します。 しに配置し、この EAIProcessHandler.PostDecline と EAIProcessHandler.RepairSubmit のフォルダーに人間の介入を備える。
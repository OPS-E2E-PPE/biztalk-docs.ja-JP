---
title: "修復と再送信のカスタム例外ハンドラーのサンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7363c440-44aa-4d08-8290-72787d17ac60
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8b33765cbe3ca1c8c0c7c3e7679e543678325af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-repair-and-resubmit-custom-exception-handler-sample"></a>修復と再送信のカスタム例外ハンドラーのサンプルを実行しています。
修復と再送信のカスタム例外ハンドラーのサンプルでは、人間の介入を ESB ベンダーおよび Microsoft BizTalk ベースのアプリケーションを処理し、便利なデザイン パターンを実装に統合するために非常に効果的な方法を示します。 サンプル コードは、ESB 例外管理システムにシームレスに統合します。  
  
 サンプルは、オーケストレーションでのカスタム例外ハンドラーを使用する方法を示します。 オーケストレーション (EAIProcess.odx) でプロセスには、エラーが発生すると、例外ハンドラーが生成し、ESB フォールト メッセージを公開します。 このエラー メッセージにはでそのペイロードに"インフライト"であった (と、BizTalk に関連するコンテキスト プロパティを含む) メッセージが含まれます、例外が発生したときと、現在 System.Exception インスタンス、BizTalk オーケストレーション エンジンによってキャッチされました。 この問題が発生すると、「拒否」メッセージと"Approved"メッセージが、エラー メッセージに永続化されます。  
  
 EAIProcessHandler.odx、分離された方法が展開されており、カスタム例外ハンドラーとして機能し、これをという名前の 2 番目のオーケストレーションは EAIProcess.odx オーケストレーションで生成された特定のエラー コードをサブスクライブし、エラー メッセージを使用します。 この例外ハンドラーは、元のメッセージ (として型指定されたドキュメント) を抽出し、System.Exception インスタンスは当初、エラー メッセージに永続化します。  
  
 元のメッセージは、ここで、元のすべてのコンテキスト プロパティと処理に使用できるになります。 カスタム例外ハンドラー (EAIProcessHandler.odx) では、次の場所にファイル システムに"Denied"と"Approved"メッセージの両方をし、書き込みます。  
  
-   承認済みメッセージ:  
  
    -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.PostApproval  
  
-   修復と再送信のメッセージを拒否:  
  
    -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.RepairSubmit  
  
-   拒否されたメッセージは:  
  
    -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.PostDecline  
  
 例外ハンドラーは、Microsoft InfoPath 処理命令を使用して、ファイル システムに再実行して修復の"Denied"メッセージをシリアル化します。 InfoPath テンプレートでは、フォームを編集し、結果を再送信するユーザー (図 1 を参照)、メッセージを検証する EAIProcess.odx オーケストレーションを開始します。  
  
 ![再送信の修復](../esb-toolkit/media/ch6-repairresubmit.gif "Ch6 RepairResubmit")  
  
 **図 1**  
  
 **InfoPath の修復と再送信テンプレートによって生成されたテスト メッセージ**  
  
 さらに、ALL という名前の汎用的な送信ポートがあります。GlobalFaultProcessor パイプラインを使用するように構成 Exceptions_FILE です。 このポートは、システム内のすべての例外をサブスクライブ、両方の BizTalk は、メッセージをルーティングするメッセージと ESB エラー メッセージが失敗しました。 例外管理フレームワークでは、それらをすべて 1 つの形式に正規化され、フォルダー \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions に InfoPath 処理命令を使用してシリアル化します。  
  
## <a name="installation"></a>インストール  
 すべての例外管理サンプルは、同じコア サービスと BizTalk アプリケーションのアイテムのセットを使用します。 そのため、すべての例外の管理のサンプルを実行するために例外管理サンプル アイテム 1 回だけをインストールする必要があります。 例外の管理のサンプルをインストールする方法については、次を参照してください。[例外管理のサンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)です。  
  
## <a name="running-the-sample-application"></a>サンプル アプリケーションの実行  
 **修復と再送信のカスタム例外ハンドラーのサンプルを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所と送信ポートの Url が \Source\Samples\Exception Handling\Test\Filedrop フォルダーに適切なディレクトリを指していることを確認してください。 受信場所が EAIProcess.RequestPort、フォルダーを指定する必要があり、送信ポートの Url は EAIProcess.PostApproval と EAIProcessHandler.PostDecline フォルダーを指定する必要があります。  
  
2.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
3.  EAIProcess.RequestPort_FILE 受信場所の指定されたフォルダーに、\Source\Samples\Exception Handling\Test\Data フォルダーにある Request_EAIProcessHandler.xml をという名前のサンプル ファイルをコピーして、サンプルを開始する: \Source\Samples\例外 Handling\Test\Filedrop\EAIProcess.RequestPort です。  
  
4.  (フォルダーにある \Source\Samples\Exception Handling\Test\Filedrop) EAIProcessHandler.PostDecline をという名前のフォルダーを開きます。 例外処理オーケストレーションによって生成された「拒否済み *」メッセージが表示されます。  
  
5.  (フォルダーにある \Source\Samples\Exception Handling\Test\Filedrop) EAIProcessHandler.RepairSubmit をという名前のフォルダーを開きます。 例外処理オーケストレーションによって生成された"RepairSubmit"メッセージが表示されます。  
  
6.  適切な InfoPath テンプレートで開く RepairSubmit ファイルをダブルクリックします。 編集して再送信の準備完了のメッセージが表示されます。  
  
7.  値を変更、 **Unit Price**からフィールド**0**に**2**、をクリックし、**送信**InfoPath のツールバーにボタンがありますBizTalk 処理のために編集したドキュメントを送信するフォーム。 受信場所が、送信プロセス HTTP を使用して、BizTalk 構成します。  
  
8.  (フォルダーにある \Source\Samples\Exception Handling\Test\Filedrop) EAIProcess.PostApproval フォルダーに移動します。 「承認 *」を含んだドキュメントは、単価の更新後の値が表示されます。  
  
## <a name="how-the-sample-works"></a>このサンプルのしくみ  
 メッセージを送信するには、EAIProcess オーケストレーションがアクティブにします。 では、EAIProcess オーケストレーションでは、メッセージを処理するとき、単価で 1 を除算しようとします。 単価はゼロであるため、0 除算の例外が発生します。 オーケストレーションのイベント ハンドラーのコードでは、この例外をキャッチし、エラー メッセージを作成します。 ビジネス ロジックでこの例外があるために、メッセージの注文数量は 10 より大きく、 **FaultCode**フィールドの値の**1000**です。  
  
 オーケストレーションが終了し、では、EAIProcess オーケストレーションが直接バインド ポートを通じて BizTalk メッセージ ボックスに、エラー メッセージを発行します。  
  
 メッセージをサブスクライブする EAIProcessHandler をという名前のカスタム エラー ハンドラー オーケストレーション、 **FaultCode**フィールドの値の**1000**、新しいエラー メッセージを取得します。 オーケストレーション内のコードは"Denied"メッセージと、InfoPath ファイルを作成しに配置し、この EAIProcessHandler.PostDecline と EAIProcessHandler.RepairSubmit フォルダーにユーザーが介入の準備ができてです。
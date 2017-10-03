---
title: "JMS MQRFH2 ヘッダーの保存のサンプルを実行して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65982dca-77e1-4267-9528-26c59237e9b1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab840ed1d319f8fd50d3a386e0ffc9b349f61b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-jms-mqrfh2-header-preservation-sample"></a>JMS MQRFH2 ヘッダーの保存のサンプルを実行します。
このサンプルのこの部分は、WebSphere キューにメッセージを展開します。 ESB は、このメッセージを取得し、送信 WebSphere キューにデポジットします。 これは、こと、ESB と Microsoft BizTalk を保持する完全に忠実な RFH2 ヘッダー メッセージが BizTalk Server を通過として示されます。  
  
 **ヘッダーの保存のサンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
2.  IBM RfhUtil ユーティリティを実行し、ESB をという名前のキュー マネージャーを選択します。JMS です。このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager です。  
  
3.  2 番目のドロップダウン リストで、ESB をという名前のターゲットの送信キューを選択します。JMS です。サンプルです。SENDTOBIZTALK、図 1 に示すようにします。  
  
     ![キュー マネージャー](../esb-toolkit/media/ch6-queuemanager.gif "Ch6 QueueManager")  
  
     **図 1**  
  
     **キュー マネージャーと RfhUtil で送信キューへの接続**  
  
4.  ドロップダウン リストにそのキューが含まれていない場合は、図 2 に示すように WebSphere MQ サービス項目をチェックして、キュー マネージャーが実行されていることを確認してください。  
  
     ![Web 球](../esb-toolkit/media/ch6-websphere.gif "Ch6 WebSphere")  
  
     **図 2**  
  
     **WebSphere サービス で、キュー マネージャーが実行されていることを確認しています**  
  
5.  クリックして、 **ReadFile** RfhUtil ユーティリティでボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS が \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\です。 このファイルには、128 テスト メッセージのバッチが含まれていますが、ユーティリティは、最初の 1 つのみを読み込みます。  
  
6.  クリックして、 **RFH**  タブの し、確認だけ、 **JMS**  チェック ボックスをオンします。  
  
7.  クリックして、 **jms** ] タブの [していることを確認、選択した**返信先**キューが ESB です。JMS です。サンプルです。DYNAMICQ1 ことと、選択した**送信先キュー** ESB がします。JMS です。サンプルです。DYNAMICQ2 です。  
  
8.  クリックして、 **Main**  タブをクリックして、**書き込み Q**ボタンをクリックして、キューにメッセージを書き込みます。  
  
9. 遅延後に、アプリケーションの実行中は、ESB に、ESB 出力メッセージが表示されます。JMS です。サンプルです。DYNAMICQ1 と ESB です。JMS です。サンプルです。DYNAMICQ1 キュー。 WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。  
  
10. RfhUtil ユーティリティに戻るし、メッセージをキューに接続します。 クリックして、 **MQMD、RFH、**と**jms** 、いる点を除き、入力と出力値が送信先キューにメッセージの変更されていないことと、応答をキューにメッセージが同じであることを確認するタブ標準 JMS メッセージするのではなく、メッセージは「その他」としてマークされます。
---
title: JMS MQRFH2 ヘッダー保存サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65982dca-77e1-4267-9528-26c59237e9b1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb03053169b815b01ff2f8a303d969c57bc4916
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242753"
---
# <a name="running-the-jms-mqrfh2-header-preservation-sample"></a>JMS MQRFH2 ヘッダー保存サンプルを実行しています。
このサンプルのこの部分により WebSphere キューにメッセージを保存します。 ESB は、このメッセージを取得し、によりを WebSphere の送信キューにします。 これは、ESB および Microsoft BizTalk 保持すること RFH2 ヘッダーを完全に忠実なメッセージが BizTalk Server を通過するよう示されます。  
  
 **ヘッダー保存サンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  
  
2.  IBM RfhUtil ユーティリティを実行し、ESB をという名前のキュー マネージャーを選択します。JMS します。このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager します。  
  
3.  2 番目のドロップダウン リストでは、ESB をという名前のターゲットの送信キューを選択します。JMS します。サンプルです。SENDTOBIZTALK、図 1 に示すようにします。  
  
     ![キュー マネージャー](../esb-toolkit/media/ch6-queuemanager.gif "Ch6 QueueManager")  
  
     **図 1**  
  
     **キュー マネージャーと RfhUtil で送信キューへの接続**  
  
4.  ドロップダウン リストに任意のキューが含まれていない場合は、図 2 に示すように、WebSphere MQ サービス アイテムをチェックして、キュー マネージャーが実行されていることを確認してください。  
  
     ![球を web](../esb-toolkit/media/ch6-websphere.gif "Ch6 WebSphere")  
  
     **図 2**  
  
     **WebSphere のサービス で、キュー マネージャーが実行されていることを確認します。**  
  
5.  をクリックして、 **ReadFile** RfhUtil ユーティリティでボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\します。 このファイルには、128 のテスト メッセージのバッチが含まれていますが、ユーティリティは、最初の 1 つのみを読み込みます。  
  
6.  をクリックして、 **RFH**  タブの し、確認しか、 **JMS**  チェック ボックスをオンします。  
  
7.  をクリックして、 **jms** ] タブの [、いることを確認し、選択した**返信先**キューが ESB。JMS します。サンプルです。DYNAMICQ1 ことと、選択した**送信先キュー** ESB は、します。JMS します。サンプルです。DYNAMICQ2 します。  
  
8.  をクリックして、 **Main**タブをクリックし、をクリックし、**書き込み Q**ボタンをクリックして、キューにメッセージを書き込みます。  
  
9. 遅延後に、アプリケーションの実行中に、ESB で、ESB の出力メッセージが表示されます。JMS します。サンプルです。DYNAMICQ1 ESB.JMS します。サンプルです。DYNAMICQ1 キュー。 WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。  
  
10. RfhUtil ユーティリティに戻るし、メッセージを表示するキューへの接続します。 をクリックして、 **MQMD、RFH、** と**jms**いる点を除いて、入力と出力の値が、送信先キューにメッセージの変更されないことと、応答をキューにメッセージが同じであることを確認するタブ標準的な JMS メッセージではなく、メッセージは「その他」としてマークされます。
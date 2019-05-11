---
title: コンテンツ ベース ルーティングのサンプルを読み込む一括を実行している |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e981567-7c6c-4c13-bd5b-597efdd3fb50
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2c9f3bac1c74ba867a4ef6570ff7c1b44e961d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292524"
---
# <a name="running-the-bulk-load-content-based-routing-sample"></a>サンプルを実行して、一括読み込みコンテンツ ベース ルーティング
サンプルのこの部分では、一括読み込みの ESB と Microsoft BizTalk は、各メッセージで指定されたキュー名に基づいて異なる送信先キューにルーティング、メッセージ キューを示します。 前の 2 つの部分で説明しているサンプルの機能を使用します。  
  
 **一括読み込みコンテンツ ベースのルーティング アクセスのサンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  
  
2.  IBM RfhUtil ユーティリティを実行し、ESB をという名前のキュー マネージャーを選択します。JMS します。このサンプルの第 2 部のように、このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager します。  
  
3.  2 番目のドロップダウン リストでは、ESB をという名前のターゲットの送信キューを選択します。JMS します。サンプルです。このサンプルの第 2 部のように、SENDTOBIZTALK します。  
  
4.  をクリックして、**ロード Q** RfhUtil ユーティリティでボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\します。 このファイルには、ESB にサンプルを送信する 128 のテスト メッセージのバッチが含まれています。  
  
5.  **ロード**ダイアログ ボックスで、すべての値が既定値に設定したままにします。  
  
6.  **ロード**ダイアログ ボックスで、をクリックして **[ok]** 入力キューにすべてのメッセージを追加します。  
  
7.  遅延後に、アプリケーションの実行中に、JMS ヘッダー内の値に応じて、さまざまな送信先キューで、ESB の出力メッセージが表示されます。 ただし、同じ返信先キューを指定すべて、ESB ですべての応答が表示されるようにします。JMS します。サンプルです。応答キューです。 WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。
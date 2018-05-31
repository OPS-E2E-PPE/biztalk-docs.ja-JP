---
title: コンテンツ ベース ルーティングのサンプルを読み込む一括を実行している |Microsoft ドキュメント
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
ms.openlocfilehash: 36c5348563cc52c31b14dbceddf35bdb3d5d94cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294946"
---
# <a name="running-the-bulk-load-content-based-routing-sample"></a>サンプルを実行して、一括読み込みコンテンツ ベース ルーティング
このサンプルの一部では、一括読み込み、ESB と Microsoft BizTalk は、各メッセージに指定されたキュー名に基づいて異なる送信先キューにルーティング、メッセージのキューについて説明します。 前の 2 つの部分できたように、サンプルの機能を使用します。  
  
 **一括読み込みコンテンツ ベースのルーティング アクセスのサンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
2.  IBM RfhUtil ユーティリティを実行し、ESB をという名前のキュー マネージャーを選択します。JMS です。このサンプルの第 2 部と同様に、このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager です。  
  
3.  2 番目のドロップダウン リストで、ESB をという名前のターゲットの送信キューを選択します。JMS です。サンプルです。このサンプルの第 2 部と同様に、SENDTOBIZTALK です。  
  
4.  クリックして、**ロード Q** RfhUtil ユーティリティ ボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS が \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\です。 このファイルには、ESB にサンプルを送信する 128 のテスト メッセージのバッチが含まれています。  
  
5.  **ロード** ダイアログ ボックスで、既定値に設定されたすべての値のままにします。  
  
6.  **ロード**ダイアログ ボックスで、をクリックして **[ok]** 入力キューにすべてのメッセージを追加します。  
  
7.  遅延後に、アプリケーションの実行中は、JMS ヘッダー内の値に応じて、さまざまな送信先キューに、ESB 出力メッセージが表示されます。 ただし、同じ返信先キューは、ので、ESB で表示されるすべての応答すべて指定します。JMS です。サンプルです。応答キューです。 WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。
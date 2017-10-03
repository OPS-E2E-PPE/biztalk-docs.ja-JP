---
title: "コンテンツ ベース ルーティングのサンプルを読み込む一括を実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e981567-7c6c-4c13-bd5b-597efdd3fb50
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36c5348563cc52c31b14dbceddf35bdb3d5d94cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-bulk-load-content-based-routing-sample"></a><span data-ttu-id="6b579-102">サンプルを実行して、一括読み込みコンテンツ ベース ルーティング</span><span class="sxs-lookup"><span data-stu-id="6b579-102">Running the Bulk Load Content-Based Routing Sample</span></span>
<span data-ttu-id="6b579-103">このサンプルの一部では、一括読み込み、ESB と Microsoft BizTalk は、各メッセージに指定されたキュー名に基づいて異なる送信先キューにルーティング、メッセージのキューについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6b579-103">This part of the sample demonstrates bulk loading a queue with messages that the ESB and Microsoft BizTalk will route to different destination queues based on the queue name specified in each message.</span></span> <span data-ttu-id="6b579-104">前の 2 つの部分できたように、サンプルの機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b579-104">It uses the features of the sample that you have seen in the previous two parts.</span></span>  
  
 <span data-ttu-id="6b579-105">**一括読み込みコンテンツ ベースのルーティング アクセスのサンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="6b579-105">**To run the Bulk Load Content-based Routing Access sample**</span></span>  
  
1.  <span data-ttu-id="6b579-106">GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="6b579-106">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="6b579-107">IBM RfhUtil ユーティリティを実行し、ESB をという名前のキュー マネージャーを選択します。JMS です。このサンプルの第 2 部と同様に、このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager です。</span><span class="sxs-lookup"><span data-stu-id="6b579-107">Run the IBM RfhUtil utility, and then select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager, as in Part 2 of this sample.</span></span>  
  
3.  <span data-ttu-id="6b579-108">2 番目のドロップダウン リストで、ESB をという名前のターゲットの送信キューを選択します。JMS です。サンプルです。このサンプルの第 2 部と同様に、SENDTOBIZTALK です。</span><span class="sxs-lookup"><span data-stu-id="6b579-108">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK, as in Part 2 of this sample.</span></span>  
  
4.  <span data-ttu-id="6b579-109">クリックして、**ロード Q** RfhUtil ユーティリティ ボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS が \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\です。</span><span class="sxs-lookup"><span data-stu-id="6b579-109">Click the **Load Q** button in the RfhUtil utility, and then navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="6b579-110">このファイルには、ESB にサンプルを送信する 128 のテスト メッセージのバッチが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b579-110">This file contains a batch of 128 test messages that the sample will send to the ESB.</span></span>  
  
5.  <span data-ttu-id="6b579-111">**ロード** ダイアログ ボックスで、既定値に設定されたすべての値のままにします。</span><span class="sxs-lookup"><span data-stu-id="6b579-111">In the **Load** dialog box, leave all values set to their default values.</span></span>  
  
6.  <span data-ttu-id="6b579-112">**ロード**ダイアログ ボックスで、をクリックして**[ok]**入力キューにすべてのメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="6b579-112">In the **Load** dialog box, click **OK** to add all the messages to the input queue.</span></span>  
  
7.  <span data-ttu-id="6b579-113">遅延後に、アプリケーションの実行中は、JMS ヘッダー内の値に応じて、さまざまな送信先キューに、ESB 出力メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b579-113">After a delay while the application executes, the ESB output messages appear in various destination queues, depending on the values in their JMS headers.</span></span> <span data-ttu-id="6b579-114">ただし、同じ返信先キューは、ので、ESB で表示されるすべての応答すべて指定します。JMS です。サンプルです。応答キューです。</span><span class="sxs-lookup"><span data-stu-id="6b579-114">However, all specify the same Reply To queue, so all the replies appear in the ESB.JMS.SAMPLE.REPLY queue.</span></span> <span data-ttu-id="6b579-115">WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="6b579-115">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>
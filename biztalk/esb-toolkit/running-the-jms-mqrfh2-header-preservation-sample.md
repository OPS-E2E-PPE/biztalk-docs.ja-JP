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
# <a name="running-the-jms-mqrfh2-header-preservation-sample"></a><span data-ttu-id="fee9b-102">JMS MQRFH2 ヘッダー保存サンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="fee9b-102">Running the JMS MQRFH2 Header Preservation Sample</span></span>
<span data-ttu-id="fee9b-103">このサンプルのこの部分により WebSphere キューにメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="fee9b-103">This part of this sample deposits a message into a WebSphere queue.</span></span> <span data-ttu-id="fee9b-104">ESB は、このメッセージを取得し、によりを WebSphere の送信キューにします。</span><span class="sxs-lookup"><span data-stu-id="fee9b-104">The ESB picks up this message and deposits it into an outbound WebSphere queue.</span></span> <span data-ttu-id="fee9b-105">これは、ESB および Microsoft BizTalk 保持すること RFH2 ヘッダーを完全に忠実なメッセージが BizTalk Server を通過するよう示されます。</span><span class="sxs-lookup"><span data-stu-id="fee9b-105">This demonstrates that the ESB and Microsoft BizTalk preserve full-fidelity RFH2 headers as a message travels through BizTalk Server.</span></span>  
  
 <span data-ttu-id="fee9b-106">**ヘッダー保存サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="fee9b-106">**To run the Header Preservation sample**</span></span>  
  
1.  <span data-ttu-id="fee9b-107">GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="fee9b-107">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="fee9b-108">IBM RfhUtil ユーティリティを実行し、ESB をという名前のキュー マネージャーを選択します。JMS します。このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager します。</span><span class="sxs-lookup"><span data-stu-id="fee9b-108">Run the IBM RfhUtil utility, and then select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager.</span></span>  
  
3.  <span data-ttu-id="fee9b-109">2 番目のドロップダウン リストでは、ESB をという名前のターゲットの送信キューを選択します。JMS します。サンプルです。SENDTOBIZTALK、図 1 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="fee9b-109">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK, as shown in Figure 1.</span></span>  
  
     <span data-ttu-id="fee9b-110">![キュー マネージャー](../esb-toolkit/media/ch6-queuemanager.gif "Ch6 QueueManager")</span><span class="sxs-lookup"><span data-stu-id="fee9b-110">![Queue Manager](../esb-toolkit/media/ch6-queuemanager.gif "Ch6-QueueManager")</span></span>  
  
     <span data-ttu-id="fee9b-111">**図 1**</span><span class="sxs-lookup"><span data-stu-id="fee9b-111">**Figure 1**</span></span>  
  
     <span data-ttu-id="fee9b-112">**キュー マネージャーと RfhUtil で送信キューへの接続**</span><span class="sxs-lookup"><span data-stu-id="fee9b-112">**Connecting to the queue manager and the outbound queue in RfhUtil**</span></span>  
  
4.  <span data-ttu-id="fee9b-113">ドロップダウン リストに任意のキューが含まれていない場合は、図 2 に示すように、WebSphere MQ サービス アイテムをチェックして、キュー マネージャーが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fee9b-113">If the drop-down list does not contain any queues, make sure that the queue manager is running by checking the WebSphere MQ Services item, as shown in Figure 2.</span></span>  
  
     <span data-ttu-id="fee9b-114">![球を web](../esb-toolkit/media/ch6-websphere.gif "Ch6 WebSphere")</span><span class="sxs-lookup"><span data-stu-id="fee9b-114">![Web Sphere](../esb-toolkit/media/ch6-websphere.gif "Ch6-WebSphere")</span></span>  
  
     <span data-ttu-id="fee9b-115">**図 2**</span><span class="sxs-lookup"><span data-stu-id="fee9b-115">**Figure 2**</span></span>  
  
     <span data-ttu-id="fee9b-116">**WebSphere のサービス で、キュー マネージャーが実行されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="fee9b-116">**Checking that the queue manager is running in the WebSphere Services item**</span></span>  
  
5.  <span data-ttu-id="fee9b-117">をクリックして、 **ReadFile** RfhUtil ユーティリティでボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\します。</span><span class="sxs-lookup"><span data-stu-id="fee9b-117">Click the **ReadFile** button in the RfhUtil utility and navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="fee9b-118">このファイルには、128 のテスト メッセージのバッチが含まれていますが、ユーティリティは、最初の 1 つのみを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="fee9b-118">This file contains a batch of 128 test messages, but the utility loads only the first one.</span></span>  
  
6.  <span data-ttu-id="fee9b-119">をクリックして、 **RFH**  タブの し、確認しか、 **JMS**  チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="fee9b-119">Click the **RFH** tab, and then make sure that only the **JMS** check box is selected.</span></span>  
  
7.  <span data-ttu-id="fee9b-120">をクリックして、 **jms** ] タブの [、いることを確認し、選択した**返信先**キューが ESB。JMS します。サンプルです。DYNAMICQ1 ことと、選択した**送信先キュー** ESB は、します。JMS します。サンプルです。DYNAMICQ2 します。</span><span class="sxs-lookup"><span data-stu-id="fee9b-120">Click the **jms** tab, and then make sure that the selected **Reply To** queue is ESB.JMS.SAMPLE.DYNAMICQ1 and that the selected **Destination Queue** is ESB.JMS.SAMPLE.DYNAMICQ2.</span></span>  
  
8.  <span data-ttu-id="fee9b-121">をクリックして、 **Main**タブをクリックし、をクリックし、**書き込み Q**ボタンをクリックして、キューにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="fee9b-121">Click the **Main** tab, and then click the **Write Q** button to write the message into the queue.</span></span>  
  
9. <span data-ttu-id="fee9b-122">遅延後に、アプリケーションの実行中に、ESB で、ESB の出力メッセージが表示されます。JMS します。サンプルです。DYNAMICQ1 ESB.JMS します。サンプルです。DYNAMICQ1 キュー。</span><span class="sxs-lookup"><span data-stu-id="fee9b-122">After a delay while the application executes, the ESB output message appears in the ESB.JMS.SAMPLE.DYNAMICQ1 and ESB.JMS.SAMPLE.DYNAMICQ1 queues.</span></span> <span data-ttu-id="fee9b-123">WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="fee9b-123">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>  
  
10. <span data-ttu-id="fee9b-124">RfhUtil ユーティリティに戻るし、メッセージを表示するキューへの接続します。</span><span class="sxs-lookup"><span data-stu-id="fee9b-124">Go back to the RfhUtil utility and connect to the queues to see the messages.</span></span> <span data-ttu-id="fee9b-125">をクリックして、 **MQMD、RFH、** と**jms**いる点を除いて、入力と出力の値が、送信先キューにメッセージの変更されないことと、応答をキューにメッセージが同じであることを確認するタブ標準的な JMS メッセージではなく、メッセージは「その他」としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="fee9b-125">Click the **MQMD, RFH,** and **jms** tabs to verify that the input and output values are unchanged for the message in the Destination Queue, and that the message in the Reply To queue is the same except that, instead of being a standard JMS message, the message is marked as "other".</span></span>
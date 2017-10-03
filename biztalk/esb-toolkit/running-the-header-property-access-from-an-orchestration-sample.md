---
title: "オーケストレーションのサンプルからのヘッダー プロパティへのアクセスを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2059eb2c-50a3-4618-a6ec-faa1a9e5d368
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2ddbb2ea7ef978c0e5eae07835d5a9c1320bbc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-header-property-access-from-an-orchestration-sample"></a><span data-ttu-id="c20d8-102">オーケストレーションのサンプルからヘッダー プロパティへのアクセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="c20d8-102">Running the Header Property Access from an Orchestration Sample</span></span>
<span data-ttu-id="c20d8-103">このサンプルの一部では、コードと Microsoft biztalk オーケストレーション内のコンポーネントにアクセスできるメッセージ コンテキストのプロパティに、ESB が JMS ヘッダーのメタデータを昇格する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c20d8-103">This part of the sample demonstrates how the ESB promotes JMS header metadata into message context properties, which code and components in orchestrations within Microsoft BizTalk can access.</span></span> <span data-ttu-id="c20d8-104">このサンプルには、JMS ヘッダーのメタデータをメッセージ コンテキスト プロパティに昇格する ESB JMS コンポーネントのインスタンスを含む受信パイプラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c20d8-104">The sample includes a receive pipeline that contains an instance of the ESB JMS component that promotes JMS header metadata into message context properties.</span></span>  
  
 <span data-ttu-id="c20d8-105">受信ポートは、メッセージのコンテキスト プロパティから、キューの名前を取得する名前付き JMSRouter RfhUtil ユーティリティによって割り当てられている (およびヘッダーのメタデータで送信される)、オーケストレーションにメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="c20d8-105">The receive port passes the message to an orchestration named JMSRouter that retrieves the queue name assigned by the RfhUtil utility (and sent in the header metadata) from the context properties of the message.</span></span> <span data-ttu-id="c20d8-106">オーケストレーションは、動的送信ポートをこのキュー名が割り当てられ、そのポートにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c20d8-106">The orchestration assigns this queue name to a dynamic send port and sends the message to that port.</span></span>  
  
 <span data-ttu-id="c20d8-107">ポートの送信パイプラインには、メッセージ コンテキスト プロパティは降格されますが、JMS ヘッダー メタデータに ESB JMS コンポーネントのインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c20d8-107">A send pipeline for the port contains an instance of the ESB JMS component that demotes the message context properties into the JMS header metadata.</span></span>  
  
 <span data-ttu-id="c20d8-108">**ヘッダー プロパティ アクセス サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="c20d8-108">**To run the Header Property Access sample**</span></span>  
  
1.  <span data-ttu-id="c20d8-109">GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="c20d8-109">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="c20d8-110">IBM RfhUtil ユーティリティ; を実行します。ESB という名前のキュー マネージャーを選択します。JMS です。このサンプルの第 1 部と同様に、このキュー マネージャーに接続する最初のドロップダウン リストで Sample.QueueManager です。</span><span class="sxs-lookup"><span data-stu-id="c20d8-110">Run the IBM RfhUtil utility; select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager, as in Part 1 of this sample.</span></span>  
  
3.  <span data-ttu-id="c20d8-111">2 番目のドロップダウン リストで、ESB をという名前のターゲットの送信キューを選択します。JMS です。サンプルです。SENDTOBIZTALK です。</span><span class="sxs-lookup"><span data-stu-id="c20d8-111">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK.</span></span>  
  
4.  <span data-ttu-id="c20d8-112">クリックして、 **ReadFile** RfhUtil ユーティリティ ボタンをクリックし、テスト 000128 をという名前のテスト メッセージ ファイルに移動します。JMS が \Source\Samples\JMS\Test\Data\Load をという名前のサブフォルダーにある\\です。</span><span class="sxs-lookup"><span data-stu-id="c20d8-112">Click the **ReadFile** button in the RfhUtil utility, and then navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="c20d8-113">このファイルには、128 テスト メッセージのバッチが含まれていますが、ユーティリティは、最初の 1 つのみを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c20d8-113">This file contains a batch of 128 test messages, but the utility loads only the first one.</span></span>  
  
5.  <span data-ttu-id="c20d8-114">クリックして、 **RFH**  タブの し、確認だけ、 **JMS**  チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="c20d8-114">Click the **RFH** tab, and then make sure that only the **JMS** check box is selected.</span></span>  
  
6.  <span data-ttu-id="c20d8-115">クリックして、 **jms** ] タブの [していることを確認、選択した**返信先**キューが ESB です。JMS です。サンプルです。応答と、選択した**送信先キュー** ESB は、します。JMS です。サンプルです。DYNAMICQ2 です。</span><span class="sxs-lookup"><span data-stu-id="c20d8-115">Click the **jms** tab, and then make sure that the selected **Reply To** queue is ESB.JMS.SAMPLE.REPLY and that the selected **Destination Queue** is ESB.JMS.SAMPLE.DYNAMICQ2.</span></span>  
  
7.  <span data-ttu-id="c20d8-116">クリックして、 **Main**  タブをクリックして、**書き込み Q**ボタンをクリックして、キューにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c20d8-116">Click the **Main** tab, and then click the **Write Q** button to write the message into the queue.</span></span>  
  
8.  <span data-ttu-id="c20d8-117">遅延後に、アプリケーションの実行中は、ESB に、ESB 出力メッセージが表示されます。JMS です。サンプルです。DYNAMICQ2 キューです。</span><span class="sxs-lookup"><span data-stu-id="c20d8-117">After a delay while the application executes, the ESB output message appears in the ESB.JMS.SAMPLE.DYNAMICQ2 queue.</span></span> <span data-ttu-id="c20d8-118">WebSphere キュー エクスプ ローラーを開き、これを確認するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="c20d8-118">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>  
  
## <a name="how-the-sample-works"></a><span data-ttu-id="c20d8-119">このサンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="c20d8-119">How the Sample Works</span></span>  
 <span data-ttu-id="c20d8-120">コード、オーケストレーション内に含まれていた JMS ヘッダーにメッセージを読み込むことにより、値がアクセスできる、 **XmlDocument**インスタンス、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="c20d8-120">Inside the orchestration, code can access the values that were in the JMS headers by loading the message into an **XmlDocument** instance, as shown in the following code.</span></span>  
  
```csharp  
if (null != InboundMsg(  
    Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData))  
{     
  jmsInfo.LoadXml(InboundMsg(  
     Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData));  
  if (null != jmsInfo)  
  {  
    if (null != jmsInfo.SelectSingleNode("//Dst"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Dst");  
      destinationQueue = xElement.InnerText.ToUpper(  
                         System.Globalization.CultureInfo.CurrentCulture);  
    }  
    if (null != jmsInfo.SelectSingleNode("//Rto"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Rto");  
      replyToQueue = xElement.InnerText.ToUpper(  
                     System.Globalization.CultureInfo.CurrentCulture);  
    }  
  }  
}  
```  
  
 <span data-ttu-id="c20d8-121">さらに、コードは、すべてのメッセージの MQMD コンテキスト プロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c20d8-121">In addition, the code can access all of the MQMD context properties of the message.</span></span>
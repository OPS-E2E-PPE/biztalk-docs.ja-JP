---
title: '手順 9: EDI ソリューションのテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a44e0f-496c-462f-bf03-1c2f842d13b6
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6e308ae230ea2d78ff03ed02a81310c38fbcabc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278650"
---
# <a name="step-9-test-the-edi-solution"></a><span data-ttu-id="18a5c-102">手順 9: EDI ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="18a5c-102">Step 9: Test the EDI Solution</span></span>
<span data-ttu-id="18a5c-103">![手順 9 の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="18a5c-103">![Step 9 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="18a5c-104">このトピックでは、受信処理をテストし、処理情報に関する EDI インターチェンジ状態レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="18a5c-104">In this topic you test your inbound processing and view the EDI-Interchange Status Report for processing information.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="18a5c-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="18a5c-105">Prerequisites</span></span>  
 <span data-ttu-id="18a5c-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="18a5c-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="testing-the-solution"></a><span data-ttu-id="18a5c-107">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="18a5c-107">Testing the solution</span></span>  
  
1.  <span data-ttu-id="18a5c-108">Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations に移動します。</span><span class="sxs-lookup"><span data-stu-id="18a5c-108">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="18a5c-109">コピー、 **SamplePO.txt**ファイル。</span><span class="sxs-lookup"><span data-stu-id="18a5c-109">Copy the **SamplePO.txt** file.</span></span>  
  
2.  <span data-ttu-id="18a5c-110">貼り付け、 **SamplePO.txt**ファイルを[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \fromthem フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="18a5c-110">Paste the **SamplePO.txt** file into the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM folder.</span></span>  
  
3.  <span data-ttu-id="18a5c-111">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="18a5c-111">Move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem folder.</span></span> <span data-ttu-id="18a5c-112">フォルダに出力テキスト ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="18a5c-112">Confirm that the folder contains an output txt file.</span></span>  
  
4.  <span data-ttu-id="18a5c-113">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem の出力ファイルと、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations の SamplePO.txt 入力ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="18a5c-113">Open the output file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem and the SamplePO.txt input file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="18a5c-114">出力メッセージのデータが元のデータに対応していることを確認**SamplePO.txt**ファイル。</span><span class="sxs-lookup"><span data-stu-id="18a5c-114">Verify that the data in the output message corresponds to the data in the original **SamplePO.txt** file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="18a5c-115">Visual Studio で Inbound4010850_to_OrderFile.btm ファイルを開いて、マッピングをチェックすることにより、出力ファイルのデータが入力ファイルのデータから変換されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="18a5c-115">You can verify that the data in the output file has been transformed from the data in the input file by opening the Inbound4010850_to_OrderFile.btm file in Visual Studio, and checking the mappings.</span></span>  
  
5.  <span data-ttu-id="18a5c-116">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="18a5c-116">Move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 folder.</span></span> <span data-ttu-id="18a5c-117">ST01 データ要素が "997" である出力 997 受信確認テキスト ファイルがこのフォルダに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="18a5c-117">Confirm that the folder contains an output 997 acknowledgment txt file in which the ST01 data element is "997".</span></span>  
  
6.  <span data-ttu-id="18a5c-118">コンソール ツリーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-118">In the console tree of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **BizTalk Group**.</span></span> <span data-ttu-id="18a5c-119">右側のペインの下部には、をクリックして**EDI インターチェンジと関連する ACK の状態**です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-119">At the bottom of the right pane, click **EDI Interchange and Correlated ACK Status**.</span></span>  
  
7.  <span data-ttu-id="18a5c-120">クエリ式内での演算子を変更する、**ステータス**フィールドを**Equals**を変更して、**値**フィールドを**ステータス**フィールドを**すべて**です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-120">In the query expression, change the operator for the **Status** field to **Equals** and change the **Value** field for the **Status** field to **All**.</span></span> <span data-ttu-id="18a5c-121">削除、**インターチェンジの日時フィールド**(行を選択し、キーのボード DEL キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="18a5c-121">Delete the **Interchange Date Time field** (select the row and press DELETE on the key board).</span></span>  
  
8.  <span data-ttu-id="18a5c-122">をクリックして**クエリを実行**です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-122">Click **Run Query**.</span></span>  
  
9. <span data-ttu-id="18a5c-123">状態レポートに 2 つのメッセージが表示されていることを確認します。1 つは THEM (Fabrikam) から US (OrderSystem) (850 メッセージ) への受信方向であり、もう 1 つは US (OrderSystem) から THEM (Fabrikam) (997 受信確認) への送信方向です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-123">Verify that two messages are displayed in the status report, one in the receive direction from THEM (Fabrikam) to US (OrderSystem) (the 850 message), the other in the send direction from the US (OrderSystem) to THEM (Fabrikam) (the 997 acknowledgment).</span></span>  
  
10. <span data-ttu-id="18a5c-124">THEM から US へのメッセージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="18a5c-124">Double-click the message from THEM to US.</span></span> <span data-ttu-id="18a5c-125">**インターチェンジの状態と確認の詳細** ダイアログ ボックスで、右側のウィンドウで、インターチェンジの詳細が表示されることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="18a5c-125">In the **Interchange status and ACK  details** dialog box, verify that details of the interchange are displayed in the right pane.</span></span>  
  
11. <span data-ttu-id="18a5c-126">をクリックして **[機能確認]** です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-126">Click **Functional ACK(s)**.</span></span> <span data-ttu-id="18a5c-127">受信確認のレポート詳細が右ペインに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="18a5c-127">Verify that the report details of the acknowledgment are displayed in the right pane.</span></span>  
  
12. <span data-ttu-id="18a5c-128">[インターチェンジの状態と確認の詳細] ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="18a5c-128">Close the Interchange status and ack details dialog box.</span></span>  
  
13. <span data-ttu-id="18a5c-129">**インターチェンジ/確認の状態** ウィンドウで、THEM から US へのメッセージを右クリックし、クリックして**トランザクション セットの詳細**です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-129">In the **Interchange/ACK Status** pane, right-click the message from THEM to US, and then click **Transaction Set Details**.</span></span> <span data-ttu-id="18a5c-130">内のエントリを右クリックし、**クエリの結果**] ウィンドウで、クリックして **[トランザクション セットのコンテンツ**です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-130">Right-click the entry in the **Query results** pane, and then click **View Transaction Set Content**.</span></span> <span data-ttu-id="18a5c-131">トランザクション セット データが表示されることを確認してください、**メッセージの詳細** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="18a5c-131">Verify that the transaction set data is displayed in the **Message Details** dialog box.</span></span> <span data-ttu-id="18a5c-132">Windows エクスプローラーを使用して、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations の SamplePO.txt ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="18a5c-132">In Windows Explorer, open the SamplePO.txt file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="18a5c-133">トランザクション セットが表示されていることを確認、**メッセージの詳細** ダイアログ ボックスは、インターチェンジとグループ ヘッダーとトレーラーせず、入力メッセージと同じです。</span><span class="sxs-lookup"><span data-stu-id="18a5c-133">Verify that the transaction set displayed in the **Message Details** dialog box is the same as that in the input message, without the interchange and group headers and trailers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="18a5c-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="18a5c-134">Next Steps</span></span>  
 <span data-ttu-id="18a5c-135">これで、EDI インターフェイス開発チュートリアルは完了です。</span><span class="sxs-lookup"><span data-stu-id="18a5c-135">You have completed the EDI Interface Developer Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a5c-136">参照</span><span class="sxs-lookup"><span data-stu-id="18a5c-136">See Also</span></span>  
 <span data-ttu-id="18a5c-137">[チュートリアル 2: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="18a5c-137">[Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md) </span></span>  
 [<span data-ttu-id="18a5c-138">手順 1: EDI インターフェイス開発チュートリアルの準備します。</span><span class="sxs-lookup"><span data-stu-id="18a5c-138">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)
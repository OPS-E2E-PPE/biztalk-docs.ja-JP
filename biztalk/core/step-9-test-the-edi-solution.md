---
title: 手順 9:EDI ソリューションのテスト |Microsoft Docs
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
ms.openlocfilehash: 2d07bc0d28bf7d983a70c2f5ec7ee5e0329da714
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244225"
---
# <a name="step-9-test-the-edi-solution"></a><span data-ttu-id="fb311-102">手順 9:EDI ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="fb311-102">Step 9: Test the EDI Solution</span></span>
<span data-ttu-id="fb311-103">![手順 9 の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="fb311-103">![Step 9 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="fb311-104">このトピックでは、受信、処理をテストし、情報を処理するため、EDI インターチェンジの状態レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="fb311-104">In this topic you test your inbound processing and view the EDI-Interchange Status Report for processing information.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fb311-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="fb311-105">Prerequisites</span></span>  
 <span data-ttu-id="fb311-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb311-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="testing-the-solution"></a><span data-ttu-id="fb311-107">ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="fb311-107">Testing the solution</span></span>  
  
1. <span data-ttu-id="fb311-108">Windows エクスプ ローラーで、移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations します。</span><span class="sxs-lookup"><span data-stu-id="fb311-108">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="fb311-109">コピー、 **SamplePO.txt**ファイル。</span><span class="sxs-lookup"><span data-stu-id="fb311-109">Copy the **SamplePO.txt** file.</span></span>  
  
2. <span data-ttu-id="fb311-110">貼り付け、 **SamplePO.txt**ファイルを[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \fromthem フォルダー。</span><span class="sxs-lookup"><span data-stu-id="fb311-110">Paste the **SamplePO.txt** file into the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM folder.</span></span>  
  
3. <span data-ttu-id="fb311-111">移動、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \toordersystem フォルダー。</span><span class="sxs-lookup"><span data-stu-id="fb311-111">Move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem folder.</span></span> <span data-ttu-id="fb311-112">フォルダーに出力テキスト ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb311-112">Confirm that the folder contains an output txt file.</span></span>  
  
4. <span data-ttu-id="fb311-113">出力ファイルを開き[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \toordersystem の SamplePO.txt 入力ファイル[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations します。</span><span class="sxs-lookup"><span data-stu-id="fb311-113">Open the output file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem and the SamplePO.txt input file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="fb311-114">出力メッセージのデータが元のデータに対応していることを確認**SamplePO.txt**ファイル。</span><span class="sxs-lookup"><span data-stu-id="fb311-114">Verify that the data in the output message corresponds to the data in the original **SamplePO.txt** file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fb311-115">出力ファイル内のデータが、Visual Studio で Inbound4010850_to_OrderFile.btm ファイルを開き、マッピングの確認入力ファイル内のデータから変換されたことを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="fb311-115">You can verify that the data in the output file has been transformed from the data in the input file by opening the Inbound4010850_to_OrderFile.btm file in Visual Studio, and checking the mappings.</span></span>  
  
5. <span data-ttu-id="fb311-116">移動、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi インターフェイス Developer tutorial \processedi_testlocations\scenario a \tothem_997 フォルダー。</span><span class="sxs-lookup"><span data-stu-id="fb311-116">Move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 folder.</span></span> <span data-ttu-id="fb311-117">ST01 データ要素の「997」出力 997 受信確認 txt ファイルがフォルダーに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb311-117">Confirm that the folder contains an output 997 acknowledgment txt file in which the ST01 data element is "997".</span></span>  
  
6. <span data-ttu-id="fb311-118">コンソール ツリーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="fb311-118">In the console tree of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **BizTalk Group**.</span></span> <span data-ttu-id="fb311-119">右側のウィンドウの下部には、次のようにクリックします。 **EDI インターチェンジと関連する ACK の状態**します。</span><span class="sxs-lookup"><span data-stu-id="fb311-119">At the bottom of the right pane, click **EDI Interchange and Correlated ACK Status**.</span></span>  
  
7. <span data-ttu-id="fb311-120">クエリ式での演算子を変更する、**状態**フィールドを**Equals**を変更して、**値**フィールドを**状態**フィールドを**すべて**します。</span><span class="sxs-lookup"><span data-stu-id="fb311-120">In the query expression, change the operator for the **Status** field to **Equals** and change the **Value** field for the **Status** field to **All**.</span></span> <span data-ttu-id="fb311-121">削除、**インターチェンジの日時フィールド**(行を選択し、キーのボードの DEL キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="fb311-121">Delete the **Interchange Date Time field** (select the row and press DELETE on the key board).</span></span>  
  
8. <span data-ttu-id="fb311-122">クリックして**クエリを実行**します。</span><span class="sxs-lookup"><span data-stu-id="fb311-122">Click **Run Query**.</span></span>  
  
9. <span data-ttu-id="fb311-123">THEM (Fabrikam) から US (OrderSystem) (850 メッセージ)、US (OrderSystem) から THEM (Fabrikam) (997 受信確認) への送信方向の受信の方向に 1 つの状態レポートに 2 つのメッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb311-123">Verify that two messages are displayed in the status report, one in the receive direction from THEM (Fabrikam) to US (OrderSystem) (the 850 message), the other in the send direction from the US (OrderSystem) to THEM (Fabrikam) (the 997 acknowledgment).</span></span>  
  
10. <span data-ttu-id="fb311-124">THEM から US へのメッセージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb311-124">Double-click the message from THEM to US.</span></span> <span data-ttu-id="fb311-125">**インターチェンジの状態と確認の詳細** ダイアログ ボックスで、右側のウィンドウで、インターチェンジの詳細が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb311-125">In the **Interchange status and ACK  details** dialog box, verify that details of the interchange are displayed in the right pane.</span></span>  
  
11. <span data-ttu-id="fb311-126">クリックして**機能確認**します。</span><span class="sxs-lookup"><span data-stu-id="fb311-126">Click **Functional ACK(s)**.</span></span> <span data-ttu-id="fb311-127">右側のウィンドウで、受信確認のレポートの詳細が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb311-127">Verify that the report details of the acknowledgment are displayed in the right pane.</span></span>  
  
12. <span data-ttu-id="fb311-128">インターチェンジ状態と確認の詳細 ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fb311-128">Close the Interchange status and ack details dialog box.</span></span>  
  
13. <span data-ttu-id="fb311-129">**インターチェンジ/確認の状態**ウィンドウで、THEM から US へのメッセージを右クリックし、クリックして**トランザクション セットの詳細**します。</span><span class="sxs-lookup"><span data-stu-id="fb311-129">In the **Interchange/ACK Status** pane, right-click the message from THEM to US, and then click **Transaction Set Details**.</span></span> <span data-ttu-id="fb311-130">エントリを右クリックして、**クエリ結果**ペイン、およびクリック**トランザクション セット**します。</span><span class="sxs-lookup"><span data-stu-id="fb311-130">Right-click the entry in the **Query results** pane, and then click **View Transaction Set Content**.</span></span> <span data-ttu-id="fb311-131">トランザクション セット データが表示されることを確認、**メッセージの詳細** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="fb311-131">Verify that the transaction set data is displayed in the **Message Details** dialog box.</span></span> <span data-ttu-id="fb311-132">Windows エクスプ ローラーの SamplePO.txt ファイルを開く[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \processedi_testlocations します。</span><span class="sxs-lookup"><span data-stu-id="fb311-132">In Windows Explorer, open the SamplePO.txt file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="fb311-133">トランザクション セットであることを確認、**メッセージの詳細** ダイアログ ボックスは、インターチェンジとグループ ヘッダーとトレーラーせず、入力メッセージと同じです。</span><span class="sxs-lookup"><span data-stu-id="fb311-133">Verify that the transaction set displayed in the **Message Details** dialog box is the same as that in the input message, without the interchange and group headers and trailers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fb311-134">次の手順</span><span class="sxs-lookup"><span data-stu-id="fb311-134">Next Steps</span></span>  
 <span data-ttu-id="fb311-135">EDI インターフェイス開発チュートリアルを完了しました。</span><span class="sxs-lookup"><span data-stu-id="fb311-135">You have completed the EDI Interface Developer Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb311-136">参照</span><span class="sxs-lookup"><span data-stu-id="fb311-136">See Also</span></span>  
 <span data-ttu-id="fb311-137">[チュートリアル 2: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="fb311-137">[Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md) </span></span>  
 [<span data-ttu-id="fb311-138">ステップ 1: EDI インターフェイス開発チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="fb311-138">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)
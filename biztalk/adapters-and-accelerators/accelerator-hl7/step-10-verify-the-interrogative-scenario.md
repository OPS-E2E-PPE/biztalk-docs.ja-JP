---
title: "手順 10: Interrogative シナリオを確認してください |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, verifying solution
ms.assetid: 1f28800b-4a1d-4f29-8123-5cdea4b4a365
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b932ab2f179faab1381609c007dcdd148f200f7e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-10-verify-the-interrogative-scenario"></a><span data-ttu-id="10fe1-102">手順 10: Interrogative シナリオを確認してください。</span><span class="sxs-lookup"><span data-stu-id="10fe1-102">Step 10: Verify the Interrogative Scenario</span></span>
<span data-ttu-id="10fe1-103">この手順では、このチュートリアルでは、エンド ツー エンド シナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-103">In this step, you verify the end-to-end scenario for this tutorial.</span></span>  
  
### <a name="to-send-the-query-message"></a><span data-ttu-id="10fe1-104">クエリ メッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="10fe1-104">To send the query message</span></span>  
  
1.  <span data-ttu-id="10fe1-105">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="10fe1-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="10fe1-106">コマンド プロンプトに移動  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>アクセラレータの HL7\SDK\MLLP ユーティリティ **.</span><span class="sxs-lookup"><span data-stu-id="10fe1-106">In the command prompt, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**.</span></span>  
  
3.  <span data-ttu-id="10fe1-107">コマンド プロンプトで次のように入力します。 **MllpReceive/P 24000**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="10fe1-107">In the command prompt, type **MllpReceive /P 24000**, and then press **Enter**.</span></span> <span data-ttu-id="10fe1-108">これにより、24000 のポートをリッスンしている MLLP リスナー アプリケーションを実行し、画面に受信メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-108">This runs the MLLP listener application listening to port 24000 and displays any messages received to the screen.</span></span> <span data-ttu-id="10fe1-109">このアプリケーションでは、病院情報システムをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="10fe1-109">This application is simulating the Hospital Information System.</span></span>  
  
4.  <span data-ttu-id="10fe1-110">追加のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="10fe1-110">Open an additional command prompt.</span></span>  
  
5.  <span data-ttu-id="10fe1-111">2 番目のコマンド プロンプト ウィンドウに移動  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータMLLP ユーティリティ * *。</span><span class="sxs-lookup"><span data-stu-id="10fe1-111">In the second Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**.</span></span>  
  
6.  <span data-ttu-id="10fe1-112">2 番目のコマンド プロンプトで次のように入力します **MllpSend/SB 11/EB 28/CR 13/TWOWAY/P 22000/F"\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン。\>HL7\SDK\Interrogative Tutorial\QRY^Q01.txt** を押してからのアクセラレータ**を入力してください。**</span><span class="sxs-lookup"><span data-stu-id="10fe1-112">In the second command prompt, type **MllpSend /SB 11 /EB 28 /CR 13 /TWOWAY /P 22000 /F "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial\QRY^Q01.txt**, and then press **Enter.**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10fe1-113">このコマンドは、MLLP ポート 22000 され (確認) の応答を待機するには、このチュートリアルの先頭で作成したクエリ メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-113">This command sends the query message you created at the beginning of this tutorial to MLLP port 22000 and waits for a response (acknowledgment).</span></span> <span data-ttu-id="10fe1-114">ADT では、受信ポートはこのメッセージを取得し、それを処理します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-114">The ADT receive port picks up this message and processes it.</span></span>  
  
7.  <span data-ttu-id="10fe1-115">次の結果があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-115">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="10fe1-116">MLLP リスナー アプリケーションには、次の値を持つメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10fe1-116">The MLLP listener application should display a message with the following values:</span></span>  
  
        ```  
        MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        ```  
  
    -   <span data-ttu-id="10fe1-117">MllpSend ユーティリティがさらでの受信確認応答ファイルを作成、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータInterrogative Tutorial フォルダには、QRY^Q01.txt.RESPONSE がという名前です。</span><span class="sxs-lookup"><span data-stu-id="10fe1-117">In addition, the MllpSend utility creates an acknowledgment file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder named QRY^Q01.txt.RESPONSE.</span></span> <span data-ttu-id="10fe1-118">このファイルには、受信確認として、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10fe1-118">This file contains the following information as the acknowledgment:</span></span>  
  
        ```  
        MSH|^~\&|HIS||ADT||20040331154031.2222-0800||ACK^Q01^ACK|10000GSM|P|2.4  
        MSA|CA|MSG00001  
        ****END ACK****  
        ```  
  
### <a name="to-send-the-response-message"></a><span data-ttu-id="10fe1-119">応答メッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="10fe1-119">To send the response message</span></span>  
  
1.  <span data-ttu-id="10fe1-120">MllpReceive アプリケーションを実行して、コマンド プロンプトでキーを押して**CTRL + C**を前の操作をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="10fe1-120">In the command prompt running the MllpReceive application, press **Ctrl-C** to cancel the previous operation.</span></span>  
  
2.  <span data-ttu-id="10fe1-121">コマンド プロンプトで次のように入力します。 **MllpReceive/P 25000**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="10fe1-121">At the command prompt, type **MllpReceive /P 25000**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10fe1-122">手順 2 では、リッスンするポート 25000 MLLP リスナー アプリケーションを実行し、画面への受信メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-122">Step 2 runs the MLLP listener application listening to port 25000 and displays any messages received to the screen.</span></span> <span data-ttu-id="10fe1-123">このアプリケーションでは、ADT システムをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="10fe1-123">This application is simulating the ADT system.</span></span>  
  
3.  <span data-ttu-id="10fe1-124">2 番目のコマンド プロンプトで次のように入力します **MllpSend/SB 11/EB 28/CR 13/P 23000/F"\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>。HL7\SDK\Interrogative Tutorial\DSR.txt"** のアクセラレータ キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="10fe1-124">In the second command prompt, type **MllpSend /SB 11 /EB 28 /CR 13 /P 23000 /F "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial\DSR.txt"**, then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10fe1-125">手順 3 では、MLLP ポート 23000 には、このチュートリアルの先頭で作成した応答メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-125">Step 3 sends the response message you created at the beginning of this tutorial to MLLP port 23000.</span></span> <span data-ttu-id="10fe1-126">HIS では、受信ポートはこのメッセージを取得し、それを処理します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-126">The HIS receive port picks up this message and processes it.</span></span>  
  
4.  <span data-ttu-id="10fe1-127">次の結果があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="10fe1-127">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="10fe1-128">MLLP リスナー アプリケーションには、次の値を持つメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10fe1-128">The MLLP listener application should display a message with the following values:</span></span>  
  
        ```  
        MSH|^~\&|HIS||ADT||19990505||DSR^Q01|ZXT23469|P|2.4  
        MSA|AA|MSG00003  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        DSP|||RESULTS FOR PATIENT#12233 SMITH, JOHN H. 07/23/03  
        DSP|||SPECIMEN#H85 COLLECTED 07/22/03 /07/0/0  
        DSP|||ELECTROLYTES  
        DSP||| SODIUM 136 [135-148] MEQ/L STAT  
        DSP||| POTASSIUM 4.2 [3.5-5.0] MEQ/L STAT  
        DSP||| CHLORIDE 91 [95-111] MEQ/L STAT  
        DSP||| CO2 25 [20-30] MEQ/L STAT  
        DSP|||CO2 25 [20-30] MEQ/L STAT|LB  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="10fe1-129">上記のメッセージが正しく表示されない場合は、状態と動作状況の追跡 (HAT) ツールを使用して、エラーをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="10fe1-129">If the messages above do not appear correctly, use the Health and Activity Tracking (HAT) tool to troubleshoot the error.</span></span>  
  
 <span data-ttu-id="10fe1-130">これで、</span><span class="sxs-lookup"><span data-stu-id="10fe1-130">Congratulations!</span></span> <span data-ttu-id="10fe1-131">BTAHL7 Interrogative チュートリアルが正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="10fe1-131">You have successfully completed the BTAHL7 Interrogative Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10fe1-132">参照</span><span class="sxs-lookup"><span data-stu-id="10fe1-132">See Also</span></span>  
 <span data-ttu-id="10fe1-133">[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="10fe1-133">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="10fe1-134">[エンド ツー エンドのチュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md) </span><span class="sxs-lookup"><span data-stu-id="10fe1-134">[End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md) </span></span>  
 [<span data-ttu-id="10fe1-135">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="10fe1-135">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)
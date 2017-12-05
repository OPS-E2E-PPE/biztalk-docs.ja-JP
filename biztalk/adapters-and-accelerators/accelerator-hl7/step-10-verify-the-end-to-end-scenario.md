---
title: "手順 10: エンド ツー エンド シナリオを確認してください |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: end-to-end tutorial, verifying solution
ms.assetid: 24b74ba6-e303-4ab1-8a93-25a430e4894d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d38f137625554bd689477964e3a969142eca0658
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-10-verify-the-end-to-end-scenario"></a><span data-ttu-id="69751-102">手順 10: エンド ツー エンド シナリオを確認してください。</span><span class="sxs-lookup"><span data-stu-id="69751-102">Step 10: Verify the End-to-End Scenario</span></span>
<span data-ttu-id="69751-103">この手順では、このチュートリアルでは、エンド ツー エンド シナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="69751-103">In this step, you verify the end-to-end scenario for this tutorial.</span></span>  
  
### <a name="to-verify-the-end-to-end-tutorial-scenario"></a><span data-ttu-id="69751-104">エンド ツー エンドのチュートリアルのシナリオを確認するには</span><span class="sxs-lookup"><span data-stu-id="69751-104">To verify the end-to-end tutorial scenario</span></span>  
  
1.  <span data-ttu-id="69751-105">をクリックして**開始**、 をポイント**プログラム**、 をポイント**アクセサリ**、順にクリック**コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="69751-105">Click **Start**, point to **Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="69751-106">コマンド プロンプト ウィンドウに移動  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP のアクセラレータ* *、ユーティリティを押してから**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="69751-106">In the Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69751-107">SDK フォルダーな MLLP ユーティリティ フォルダーが見つからない場合は、MLLP テスト ツールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="69751-107">If you cannot find an MLLP Utilities folder under the SDK folder, the MLLP test tools may not be installed.</span></span> <span data-ttu-id="69751-108">コントロール パネルを開き**プログラム追加と削除**です。</span><span class="sxs-lookup"><span data-stu-id="69751-108">Open the Control Panel, and then open **Add or Remove Programs**.</span></span> <span data-ttu-id="69751-109">選択**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、し、**変更**です。</span><span class="sxs-lookup"><span data-stu-id="69751-109">Select **Microsoft BizTalk \<version\> Accelerator for HL7**, and then select **Change**.</span></span> <span data-ttu-id="69751-110">BTAHL7 セットアップ ウィザードで、次のように選択します。**変更**です。</span><span class="sxs-lookup"><span data-stu-id="69751-110">In the BTAHL7 setup wizard, select **Modify**.</span></span> <span data-ttu-id="69751-111">展開、**アダプター**フォルダーを表示するかどうか、 **MLLP テスト ツール**がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="69751-111">Expand the **Adapter** folder to see whether the **MLLP Test Tool** has been installed.</span></span> <span data-ttu-id="69751-112">それ以外の場合は、インストールします。</span><span class="sxs-lookup"><span data-stu-id="69751-112">If not, install it.</span></span>  
  
3.  <span data-ttu-id="69751-113">コマンド プロンプト ウィンドウで次のように入力します。 **mllpreceive/p 14000**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="69751-113">In the Command Prompt window, type **mllpreceive /p 14000**, and then press **Enter**.</span></span> <span data-ttu-id="69751-114">これにより、14000 のポートをリッスンしていると、MLLP メッセージの既定の EB、SB、および CR の文字を指定する MLLP リスナー アプリケーションを実行し、画面に受信メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="69751-114">This runs the MLLP listener application listening to port 14000 and specifying the default EB, SB, and CR characters of the MLLP message, and displays any messages received to the screen.</span></span>  
  
4.  <span data-ttu-id="69751-115">クリックして、追加のコマンド プロンプトを開始**開始**、 をポイント**プログラム**、 をポイント**アクセサリ**、順にクリック**コマンド プロンプト**.</span><span class="sxs-lookup"><span data-stu-id="69751-115">Start an additional command prompt by clicking **Start**, point to **Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
5.  <span data-ttu-id="69751-116">2 番目のコマンド プロンプト ウィンドウに移動  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータMLLP ユーティリティ * を押してから**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="69751-116">In the second Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="69751-117">次の手順では、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="69751-117">The following step sends the message.</span></span>  
  
6.  <span data-ttu-id="69751-118">コマンド プロンプト ウィンドウで次のように入力します **mllpsend/SB 11/EB 28/CR 13/f"\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>。Accelerator HL7\SDK\End エンドツー エンド Tutorial\ADT^A03.txt for"**ここで、 \<*ドライブ*\>は、インストール ドライブ文字です。</span><span class="sxs-lookup"><span data-stu-id="69751-118">In the Command Prompt window, type **mllpsend /SB 11 /EB 28 /CR 13 /f "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\ADT^A03.txt"**, where \<*drive*\> is your installation drive letter.</span></span> <span data-ttu-id="69751-119">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="69751-119">Press **Enter**.</span></span>  
  
7.  <span data-ttu-id="69751-120">次の結果があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="69751-120">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="69751-121">MLLP リスナー アプリケーションでは、メッセージを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69751-121">The MLLP listener application should display a message.</span></span> <span data-ttu-id="69751-122">メッセージの最初の行には、次の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="69751-122">The first line of the message should have the following values:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7^IE^UUID|MCM|HI^System^GUID||199601121005||ADT^A04|000001|P|2.4|||SU|NE  
        ```  
  
    -   <span data-ttu-id="69751-123">メッセージが表示されます\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_sendMsg_RX のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="69751-123">A message appears in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX.</span></span> <span data-ttu-id="69751-124">このメッセージは、MLLP リスナー アプリケーションによって表示されるメッセージと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69751-124">This message should be the same as the message shown by the MLLP listener application.</span></span> <span data-ttu-id="69751-125">メッセージと同じ値を次のように、メッセージの最初の行を確認します。</span><span class="sxs-lookup"><span data-stu-id="69751-125">Verify that the first line of the message has the same message values as follows.</span></span> <span data-ttu-id="69751-126">次のコードに nd MSH5 を MSH3 の値が、Tutorial_RXSystem 用に指定した値を一致することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="69751-126">Note that the values for MSH3 a nd MSH5 in the following code match the values you specified for the Tutorial_RXSystem:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7|MCM|Tutorial_RXSystem||199601121005||ADT^A03|000001|P|2.3.1  
        ```  
  
    -   <span data-ttu-id="69751-127">2 つのメッセージが表示される\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_sendAck_ADT のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="69751-127">Two messages appear in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT.</span></span> <span data-ttu-id="69751-128">これらのメッセージの 1 つは、アプリケーションの受信確認です。もう 1 つは、コミットの確認です。</span><span class="sxs-lookup"><span data-stu-id="69751-128">One of these messages is an application acknowledgment; the other is a commit acknowledgment.</span></span> <span data-ttu-id="69751-129">アプリケーションの受信確認は、次の内容が必要です。</span><span class="sxs-lookup"><span data-stu-id="69751-129">The application acknowledgment should have the following content:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|000001|P|2.3.1|||AL  
        MSA|AA|000001  
        ```  
  
    -   <span data-ttu-id="69751-130">コミットの確認には、次の内容が必要です。</span><span class="sxs-lookup"><span data-stu-id="69751-130">The commit acknowledgment should have the following content:</span></span>  
  
        ```  
        MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|100000|P|2.3.1  
        MSA|CA|000001  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="69751-131">メッセージが正しく表示されない場合は、状態と動作状況の追跡 (HAT) ツールを使用して、エラーをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="69751-131">If the messages do not appear correctly, use the Health and Activity Tracking (HAT) tool to troubleshoot the error.</span></span>  
  
 <span data-ttu-id="69751-132">これで、</span><span class="sxs-lookup"><span data-stu-id="69751-132">Congratulations!</span></span> <span data-ttu-id="69751-133">BTAHL7 エンド ツー エンドのチュートリアルが正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="69751-133">You have successfully completed the BTAHL7 End-to-End Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69751-134">参照</span><span class="sxs-lookup"><span data-stu-id="69751-134">See Also</span></span>  
 [<span data-ttu-id="69751-135">エンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="69751-135">End-to-End Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)
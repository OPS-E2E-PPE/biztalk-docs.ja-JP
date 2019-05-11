---
title: 手順 10:エンド ツー エンド シナリオの確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, verifying solution
ms.assetid: 24b74ba6-e303-4ab1-8a93-25a430e4894d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 081f2e7f81c7ea293cac8717434a451d0d2ecd6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289057"
---
# <a name="step-10-verify-the-end-to-end-scenario"></a><span data-ttu-id="ae253-102">手順 10:エンド ツー エンド シナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae253-102">Step 10: Verify the End-to-End Scenario</span></span>
<span data-ttu-id="ae253-103">この手順では、このチュートリアルでは、エンド ツー エンド シナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae253-103">In this step, you verify the end-to-end scenario for this tutorial.</span></span>  
  
### <a name="to-verify-the-end-to-end-tutorial-scenario"></a><span data-ttu-id="ae253-104">エンド ツー エンドのチュートリアルのシナリオを確認するには</span><span class="sxs-lookup"><span data-stu-id="ae253-104">To verify the end-to-end tutorial scenario</span></span>  
  
1. <span data-ttu-id="ae253-105">をクリックして**開始**、 をポイント**プログラム**、 をポイント**アクセサリ**、順にクリックします**コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="ae253-105">Click **Start**, point to **Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2. <span data-ttu-id="ae253-106">コマンド プロンプト ウィンドウに移動します **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator HL7\SDK\MLLP ユーティリティfor**。、キーを押しますと**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="ae253-106">In the Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**, and then press **Enter**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ae253-107">SDK フォルダーの下の MLLP ユーティリティ フォルダーが見つからない場合 MLLP テスト ツールがインストールしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae253-107">If you cannot find an MLLP Utilities folder under the SDK folder, the MLLP test tools may not be installed.</span></span> <span data-ttu-id="ae253-108">コントロール パネル を開き、開きます**プログラム追加と削除**します。</span><span class="sxs-lookup"><span data-stu-id="ae253-108">Open the Control Panel, and then open **Add or Remove Programs**.</span></span> <span data-ttu-id="ae253-109">選択**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、し、**変更**します。</span><span class="sxs-lookup"><span data-stu-id="ae253-109">Select **Microsoft BizTalk \<version\> Accelerator for HL7**, and then select **Change**.</span></span> <span data-ttu-id="ae253-110">BTAHL7 セットアップ ウィザードで **変更**します。</span><span class="sxs-lookup"><span data-stu-id="ae253-110">In the BTAHL7 setup wizard, select **Modify**.</span></span> <span data-ttu-id="ae253-111">展開、**アダプター**フォルダーを表示するかどうか、 **MLLP テスト ツール**がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="ae253-111">Expand the **Adapter** folder to see whether the **MLLP Test Tool** has been installed.</span></span> <span data-ttu-id="ae253-112">それ以外の場合は、それをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae253-112">If not, install it.</span></span>  
  
3. <span data-ttu-id="ae253-113">コマンド プロンプト ウィンドウで次のように入力します。 **mllpreceive/p 14000**、し、キーを押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="ae253-113">In the Command Prompt window, type **mllpreceive /p 14000**, and then press **Enter**.</span></span> <span data-ttu-id="ae253-114">これにより、MLLP リスナー アプリケーション ポート 14000 にリッスンしていると、MLLP メッセージの既定 EB、SB、CR 文字を指定することを実行し、他の画面に受信メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="ae253-114">This runs the MLLP listener application listening to port 14000 and specifying the default EB, SB, and CR characters of the MLLP message, and displays any messages received to the screen.</span></span>  
  
4. <span data-ttu-id="ae253-115">クリックして、追加のコマンド プロンプトを開始**開始**、 をポイント**プログラム**、 をポイント**アクセサリ**、順にクリックします**コマンド プロンプト**.</span><span class="sxs-lookup"><span data-stu-id="ae253-115">Start an additional command prompt by clicking **Start**, point to **Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
5. <span data-ttu-id="ae253-116">2 番目のコマンド プロンプト ウィンドウに移動 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータ**、キーを押しますと**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="ae253-116">In the second Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**, and then press **Enter**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ae253-117">次の手順では、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="ae253-117">The following step sends the message.</span></span>  
  
6. <span data-ttu-id="ae253-118">コマンド プロンプト ウィンドウで次のように入力します**mllpsend/SB 11/EB 28/CR 13/f"\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータ。エンド ツー エンド Tutorial\ADT ^ A03.txt"** ここで、 \<*ドライブ*\>インストールのドライブ文字します。</span><span class="sxs-lookup"><span data-stu-id="ae253-118">In the Command Prompt window, type **mllpsend /SB 11 /EB 28 /CR 13 /f "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\ADT^A03.txt"**, where \<*drive*\> is your installation drive letter.</span></span> <span data-ttu-id="ae253-119">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ae253-119">Press **Enter**.</span></span>  
  
7. <span data-ttu-id="ae253-120">次の結果があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae253-120">Verify that you have the following results:</span></span>  
  
   -   <span data-ttu-id="ae253-121">MLLP リスナー アプリケーションには、メッセージを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae253-121">The MLLP listener application should display a message.</span></span> <span data-ttu-id="ae253-122">メッセージの最初の行には、次の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae253-122">The first line of the message should have the following values:</span></span>  
  
       ```  
       MSH|^~\&|BTAHL7^IE^UUID|MCM|HI^System^GUID||199601121005||ADT^A04|000001|P|2.4|||SU|NE  
       ```  
  
   -   <span data-ttu-id="ae253-123">メッセージが表示されます\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_sendMsg_RX のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="ae253-123">A message appears in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendMsg_RX.</span></span> <span data-ttu-id="ae253-124">このメッセージは、MLLP リスナー アプリケーションに表示されるメッセージと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae253-124">This message should be the same as the message shown by the MLLP listener application.</span></span> <span data-ttu-id="ae253-125">メッセージと同じ値を次のように、メッセージの最初の行を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae253-125">Verify that the first line of the message has the same message values as follows.</span></span> <span data-ttu-id="ae253-126">Nd MSH5、次のコードを MSH3 の値が一致、Tutorial_RXSystem の指定した値であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ae253-126">Note that the values for MSH3 a nd MSH5 in the following code match the values you specified for the Tutorial_RXSystem:</span></span>  
  
       ```  
       MSH|^~\&|BTAHL7|MCM|Tutorial_RXSystem||199601121005||ADT^A03|000001|P|2.3.1  
       ```  
  
   -   <span data-ttu-id="ae253-127">2 つのメッセージが表示される\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_sendAck_ADT のアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="ae253-127">Two messages appear in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT.</span></span> <span data-ttu-id="ae253-128">これらのメッセージの 1 つは、アプリケーションの受信確認です。もう 1 つは、コミットの確認です。</span><span class="sxs-lookup"><span data-stu-id="ae253-128">One of these messages is an application acknowledgment; the other is a commit acknowledgment.</span></span> <span data-ttu-id="ae253-129">アプリケーションの受信確認は、次の内容が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae253-129">The application acknowledgment should have the following content:</span></span>  
  
       ```  
       MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|000001|P|2.3.1|||AL  
       MSA|AA|000001  
       ```  
  
   -   <span data-ttu-id="ae253-130">コミットの確認には、次の内容が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae253-130">The commit acknowledgment should have the following content:</span></span>  
  
       ```  
       MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|100000|P|2.3.1  
       MSA|CA|000001  
       ```  
  
   > [!NOTE]
   >  <span data-ttu-id="ae253-131">メッセージが正しく表示されない場合、エラーのトラブルシューティングの状態と動作状況の追跡 (HAT) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae253-131">If the messages do not appear correctly, use the Health and Activity Tracking (HAT) tool to troubleshoot the error.</span></span>  
  
   <span data-ttu-id="ae253-132">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="ae253-132">Congratulations!</span></span> <span data-ttu-id="ae253-133">BTAHL7 のエンド ツー エンド チュートリアルを正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="ae253-133">You have successfully completed the BTAHL7 End-to-End Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae253-134">参照</span><span class="sxs-lookup"><span data-stu-id="ae253-134">See Also</span></span>  
 [<span data-ttu-id="ae253-135">エンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="ae253-135">End-to-End Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)
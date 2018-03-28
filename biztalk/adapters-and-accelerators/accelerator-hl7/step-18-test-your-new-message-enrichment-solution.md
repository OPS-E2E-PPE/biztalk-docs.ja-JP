---
title: '手順 18: 新しいメッセージの強化ソリューションのテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, testing solution
ms.assetid: 233fbf79-0ab1-4064-b828-6bbbb56cbec2
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 035925684617e74608246aed99fa98e16d0668a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="step-18-test-your-new-message-enrichment-solution"></a><span data-ttu-id="da8ff-102">手順 18: 新しいメッセージの強化ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="da8ff-102">Step 18: Test Your New Message Enrichment Solution</span></span>
<span data-ttu-id="da8ff-103">このステップでメッセージを送信するクライアント アプリケーションを使用して、ソリューションをテストする[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MLLPReceive アプリケーションが期待どおりに HL7 形式のメッセージを受け取るかどうかが表示されるとします。</span><span class="sxs-lookup"><span data-stu-id="da8ff-103">In this step, you test your solution by using the WSClient application to send a message to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and seeing if the MLLPReceive application receives an HL7-formatted message as expected.</span></span>  
  
### <a name="to-test-your-solution"></a><span data-ttu-id="da8ff-104">ソリューションをテストするには</span><span class="sxs-lookup"><span data-stu-id="da8ff-104">To test your solution</span></span>  
  
1.  <span data-ttu-id="da8ff-105">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="da8ff-105">Open a command prompt.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="da8ff-106">手順 2 では、カスタムのインストール手順を使用し、MLLP テスト ツールがインストールされていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="da8ff-106">Step 2 requires that you have installed the MLLP Test tool using the custom installation procedure.</span></span> <span data-ttu-id="da8ff-107">かどうか MllpReceive.exe と MllpSend.exe を含むディレクトリは、コンピューターに存在しません \MLLP ユーティリティをインストールにカスタム インストールを実行しています。</span><span class="sxs-lookup"><span data-stu-id="da8ff-107">If the \MLLP Utilities directory containing MllpReceive.exe and MllpSend.exe does not exist on your computer, install them by performing a custom installation.</span></span> <span data-ttu-id="da8ff-108">詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)です。</span><span class="sxs-lookup"><span data-stu-id="da8ff-108">For information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
2.  <span data-ttu-id="da8ff-109">コマンド プロンプトで次のように入力します**cd \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータ**(。ここで\<*ドライブ*\> 、インストールのドライブ文字は、)、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="da8ff-109">At the command prompt, type **cd \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities** (where \<*drive*\> is your installation drive letter), and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="da8ff-110">コマンド プロンプトで次のように入力します。 **mllpreceive/p 11000/eb 11/sb 28/cr 13**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="da8ff-110">At the command prompt, type **mllpreceive /p 11000 /eb 11 /sb 28 /cr 13**, and then press **Enter**.</span></span> <span data-ttu-id="da8ff-111">これにより、11000 のポートをリッスンしていると、MLLP メッセージの既定の EB、SB、および CR の文字を指定する MLLP リスナー アプリケーションを実行し、画面に受信メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="da8ff-111">This runs the MLLP listener application listening to port 11000 and specifying the default EB, SB, and CR characters of the MLLP message, and displays any messages received to the screen.</span></span>  
  
4.  <span data-ttu-id="da8ff-112">2 番目のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="da8ff-112">Open a second command prompt.</span></span>  
  
5.  <span data-ttu-id="da8ff-113">コマンド プロンプトで次のように入力します。 **cd \<*ドライブ*\>: \Tutorial\WSClient\bin\Debug**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="da8ff-113">At the command prompt, type **cd \<*drive*\>:\Tutorial\WSClient\bin\Debug**, and then press **Enter**.</span></span>  
  
6.  <span data-ttu-id="da8ff-114">コマンド プロンプトで次のように入力します。**クライアント john henry smith 123456789**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="da8ff-114">At the command prompt, type **wsclient john henry smith 123456789**, and then press **Enter**.</span></span> <span data-ttu-id="da8ff-115">Henry の John Smith の患者の名前と 123456789 サンプル社会保障番号を持つサンプル メッセージを含む Web サービスにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="da8ff-115">This sends a message to the Web service that contains a sample message with a patient name of John Henry Smith and a sample social security number of 123456789.</span></span>  
  
7.  <span data-ttu-id="da8ff-116">しばらくすると、MLLPReceive アプリケーションには、MLLP の受信メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da8ff-116">After a short pause, the MLLPReceive application displays the incoming MLLP message.</span></span> <span data-ttu-id="da8ff-117">メッセージは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="da8ff-117">The message should look similar to the following:</span></span>  
  
    ```  
    MSH|^~\&|TestTrailing^Delimiters|srcFac^srcFacUid|dstApp^dstAppUid|dstFac^dstFacUid|200307092343|sec|ADT^A04|msgid2134|P|2.2PID|||123456789||smith^john  
    ```  
  
     <span data-ttu-id="da8ff-118">場合は、数分後に応答を受け取りません、アプリケーション イベント ログのエラーをチェックしてトラブルシューティングを開始します。</span><span class="sxs-lookup"><span data-stu-id="da8ff-118">If you do not receive a response after a few minutes, you should check the Application event log for any errors and begin troubleshooting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da8ff-119">参照</span><span class="sxs-lookup"><span data-stu-id="da8ff-119">See Also</span></span>  
 [<span data-ttu-id="da8ff-120">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="da8ff-120">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)
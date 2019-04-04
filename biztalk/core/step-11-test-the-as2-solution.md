---
title: '手順 11: AS2 ソリューションのテスト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 184ed8ee-6778-4bb9-b265-a94a1fed03cb
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31fbb336d4fb6ba7184a7745520603923c67ce4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996243"
---
# <a name="step-11-test-the-as2-solution"></a><span data-ttu-id="e5a93-102">手順 11: AS2 ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="e5a93-102">Step 11: Test the AS2 Solution</span></span>
<span data-ttu-id="e5a93-103">![手順 11 の 11](../core/media/tut-step11-of-11.gif "Tut_Step11_of_11")</span><span class="sxs-lookup"><span data-stu-id="e5a93-103">![Step 11 of 11](../core/media/tut-step11-of-11.gif "Tut_Step11_of_11")</span></span>  
  
 <span data-ttu-id="e5a93-104">このステップでは、このチュートリアルの結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-104">In this step you verify the results of this tutorial.</span></span>  
  
 <span data-ttu-id="e5a93-105">EDI メッセージを受信場所の Receive_AS2 に (Contoso 仮想ディレクトリを介して) 送信するために使用する Sender.exe ファイルを構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5a93-105">You need to build the Sender.exe file that you use to send an EDI message to the Receive_AS2 receive location (through the Contoso virtual directory).</span></span> <span data-ttu-id="e5a93-106">Sender.exe は、非同期の MDN メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-106">Sender.exe returns an asynchronous MDN message.</span></span> <span data-ttu-id="e5a93-107">メッセージ ファイルは X12_00401_864.edi であり、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="e5a93-107">The message file is X12_00401_864.edi located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial folder.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e5a93-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="e5a93-108">Prerequisites</span></span>  
 <span data-ttu-id="e5a93-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5a93-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-test-the-solution-with-an-asynchronous-edi-message"></a><span data-ttu-id="e5a93-110">EDI メッセージが非同期ソリューションをテストするには</span><span class="sxs-lookup"><span data-stu-id="e5a93-110">To test the solution with an asynchronous EDI message</span></span>  
  
1. <span data-ttu-id="e5a93-111">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender フォルダーにある Sender.csproj プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5a93-111">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the Sender.csproj project in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender folder.</span></span> <span data-ttu-id="e5a93-112">Sender プロジェクトを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-112">Right-click the Sender project, and then click **Properties**.</span></span> <span data-ttu-id="e5a93-113">クリックして**署名**左側のコンソールでします。</span><span class="sxs-lookup"><span data-stu-id="e5a93-113">Click **Signing** in the left-hand console.</span></span> <span data-ttu-id="e5a93-114">いることを確認**アセンブリに署名**選択すると、および厳密な名前キー ファイルに設定が**Sender.snk**します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-114">Ensure that **Sign the assembly** is selected, and set the strong name key file to **Sender.snk**.</span></span> <span data-ttu-id="e5a93-115">必ず**遅延署名のみ**がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="e5a93-115">Make sure that **Delay sign only** is cleared.</span></span>  
  
2. <span data-ttu-id="e5a93-116">プロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="e5a93-116">Build the project.</span></span>  
  
3. <span data-ttu-id="e5a93-117">コマンド プロンプトを開き、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug に移動します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-117">Open a command prompt and navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug.</span></span> <span data-ttu-id="e5a93-118">Enter `Sender.exe`、押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-118">Enter `Sender.exe`, and then press **Enter**.</span></span> <span data-ttu-id="e5a93-119">AS2 メッセージが正常に送信されたことを示すメッセージを確認し、コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e5a93-119">Verify that you see a message indicating that an AS2 message was successfully sent, and then close the command prompt.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e5a93-120">Sender.exe ビルドを次を含む AS2 メッセージが実行されている EDI テスト インターチェンジ: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 \x12_00401_864.edi します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-120">Running Sender.exe builds an AS2 message containing the following EDI test interchange: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\X12_00401_864.edi.</span></span> <span data-ttu-id="e5a93-121">AS2 メッセージのビルド後、そのメッセージは Contoso 仮想ディレクトリに送られます。このディレクトリは、BTSHttpReceive.dll を使用してメッセージを受信場所にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e5a93-121">After building the AS2 message, it posts it to the Contoso virtual directory, which uses BTSHttpReceive.dll to route the message to the receive location.</span></span>  
  
4. <span data-ttu-id="e5a93-122">移動し、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_MDNToFabrikam フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e5a93-122">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_MDNToFabrikam folder.</span></span> <span data-ttu-id="e5a93-123">あることを確認、 \<GUID\>フォルダー内に <guid>.msg ファイル。</span><span class="sxs-lookup"><span data-stu-id="e5a93-123">Verify that there is a \<GUID\>.msg file in the folder.</span></span> <span data-ttu-id="e5a93-124">メモ帳でこのファイルを開き、メッセージが MDN で、AS2-From が Contoso に設定され、AS2-To が Fabrikam に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-124">Open the file in Notepad, and verify that the message is an MDN with AS2-From set to Contoso and AS2-To set to Fabrikam.</span></span>  
  
5. <span data-ttu-id="e5a93-125">移動し、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_EDIXMLToContoso フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e5a93-125">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="e5a93-126">あることを確認、 \<GUID\>フォルダーの .xml ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e5a93-126">Verify that there is a \<GUID\>.xml file in the folder.</span></span> <span data-ttu-id="e5a93-127">このファイルをダブルクリックし、メッセージの ST01 フィールドが 864 に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-127">Double-click the file, and verify that the ST01 field of the message is set to 864.</span></span>  
  
6. <span data-ttu-id="e5a93-128">移動し、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_ 997tofabrikam フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e5a93-128">Navigate to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_997ToFabrikam folder.</span></span> <span data-ttu-id="e5a93-129">あることを確認、 \<GUID\>フォルダー内に <guid>.msg ファイル。</span><span class="sxs-lookup"><span data-stu-id="e5a93-129">Verify that there is a \<GUID\>.msg file in the folder.</span></span> <span data-ttu-id="e5a93-130">メモ帳でこのファイルを開き、メッセージが、EDI ペイロードの上に AS2 ヘッダーがある 997 メッセージ (ST1 が 997) であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-130">Open the file in Notepad, and verify that the message is a 997 message (with an ST1 of 997) with AS2 headers over an EDI payload.</span></span> <span data-ttu-id="e5a93-131">AS2-From が Contoso で、AS2-To が Fabrikam であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-131">Verify that AS2-From is Contoso and AS2-To is Fabrikam.</span></span> <span data-ttu-id="e5a93-132">ISA6 (送信者 ID) が 1234567 (Contoso) に設定されていること、および ISA8 (受信者 ID) が 7654321 (Fabrikam) に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-132">Verify that ISA6 (Sender identifier) is set to 1234567 (Contoso) and ISA8 (Receiver identifier) is set to 7654321 (Fabrikam).</span></span>  
  
7. <span data-ttu-id="e5a93-133">AS2 および EDI 状態レポートを表示するには、**グループ ハブ**BizTalk Server 管理コンソールでページで、ページの一番下までスクロールし、状態レポートのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a93-133">To see the AS2 and EDI status reports, go to the **Group Hub** page in the BizTalk Server Administration Console, scroll to the bottom of the page, and click one of the status report links.</span></span> <span data-ttu-id="e5a93-134">詳細については、[EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5a93-134">For more information, see [EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e5a93-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="e5a93-135">Next Steps</span></span>  
 <span data-ttu-id="e5a93-136">これで、AS2 のチュートリアルを終了します。</span><span class="sxs-lookup"><span data-stu-id="e5a93-136">You have completed the AS2 Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a93-137">参照</span><span class="sxs-lookup"><span data-stu-id="e5a93-137">See Also</span></span>  
 <span data-ttu-id="e5a93-138">[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="e5a93-138">[Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md) </span></span>  
 [<span data-ttu-id="e5a93-139">手順 1: AS2 チュートリアルの準備</span><span class="sxs-lookup"><span data-stu-id="e5a93-139">Step 1: Prepare for the AS2 Tutorial</span></span>](../core/step-1-prepare-for-the-as2-tutorial.md)
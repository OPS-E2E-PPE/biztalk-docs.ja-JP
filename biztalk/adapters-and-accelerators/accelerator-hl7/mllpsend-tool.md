---
title: "MllpSend ツール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MllpSend tool
- MLLP-encoded messages, receive adapters
- MLLP-encoded messages, MllpSend tool
ms.assetid: b1723d52-4909-4543-8215-4f73802b6c4f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed9b666b019fe7dc415f28c0dd01522b728b149c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="mllpsend-tool"></a><span data-ttu-id="9ea16-102">MllpSend ツール</span><span class="sxs-lookup"><span data-stu-id="9ea16-102">MllpSend Tool</span></span>
<span data-ttu-id="9ea16-103">MllpSend ツールを使用すると、データを MLLP の受信場所を送信します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-103">You can use the MllpSend tool to send data to an MLLP receive location.</span></span>  
  
 <span data-ttu-id="9ea16-104">使用してこのツールをインストールする、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]カスタム インストール手順です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="9ea16-105">BTAHL7 をインストールする標準的なインストールを実行した場合必要があります、カスタム インストールを実行し、このチュートリアルでは正常に動作する順序でテスト ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9ea16-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="9ea16-106">カスタム セットアップ 画面で、次のように選択します**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**。フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="9ea16-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="9ea16-107">詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="9ea16-108">BTAHL7 セットアップでこのツールをインストールする*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="9ea16-108">BTAHL7 setup installs this tool in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="9ea16-109">このツールを使用する、[エンド ツー エンド チュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)、および[メッセージ強化チュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9ea16-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="9ea16-110">インストールした場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]して、既定のインストールが、チュートリアルの結果をテストすることはできません MLLP Testtools (含む MllpSend と MllpReceive) がインストールされていないとします。</span><span class="sxs-lookup"><span data-stu-id="9ea16-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLP Testtools (including MllpSend and MllpReceive), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="9ea16-111">ツールの使用方法</span><span class="sxs-lookup"><span data-stu-id="9ea16-111">Tool Usage</span></span>  
 <span data-ttu-id="9ea16-112">このコマンド ライン ツールの起動に使用する構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="9ea16-113">次の表では、MllpSend ツールを使用して、構文の各部について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-113">The following table describes each part of the syntax the MllpSend tool uses.</span></span>  
  
|<span data-ttu-id="9ea16-114">構文</span><span class="sxs-lookup"><span data-stu-id="9ea16-114">Syntax</span></span>|<span data-ttu-id="9ea16-115">Description</span><span class="sxs-lookup"><span data-stu-id="9ea16-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9ea16-116">**/?**</span><span class="sxs-lookup"><span data-stu-id="9ea16-116">**/?**</span></span>|<span data-ttu-id="9ea16-117">コマンド プロンプト ウィンドウでヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-117">Displays Help in the Command Prompt window.</span></span>|  
|<span data-ttu-id="9ea16-118">**/I \<IP\>**</span><span class="sxs-lookup"><span data-stu-id="9ea16-118">**/I \<IP\>**</span></span>|<span data-ttu-id="9ea16-119">送信するアドレスを表します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-119">Denotes the address to send to.</span></span> <span data-ttu-id="9ea16-120">既定値は localhost です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-120">The default value is localhost.</span></span>|  
|<span data-ttu-id="9ea16-121">**/P\<ポート\>**</span><span class="sxs-lookup"><span data-stu-id="9ea16-121">**/P \<PORT\>**</span></span>|<span data-ttu-id="9ea16-122">送信するポート番号を表します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-122">Denotes the port number to send to.</span></span> <span data-ttu-id="9ea16-123">既定値は**11000**です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-123">The default value is **11000**.</span></span>|  
|<span data-ttu-id="9ea16-124">**/F**</span><span class="sxs-lookup"><span data-stu-id="9ea16-124">**/F**</span></span>|<span data-ttu-id="9ea16-125">ファイル名、ファイルの内容を送信します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-125">Sends content of the file FILENAME.</span></span>|  
|<span data-ttu-id="9ea16-126">**/繰り返し\<n\>**</span><span class="sxs-lookup"><span data-stu-id="9ea16-126">**/REPEAT \<n\>**</span></span>|<span data-ttu-id="9ea16-127">同じメッセージを送信 *n* 回です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-127">Sends the same message *n* times.</span></span> <span data-ttu-id="9ea16-128">ラッパーの文字は、各メッセージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ea16-128">The wrapper characters will be applied to each message.</span></span>|  
|<span data-ttu-id="9ea16-129">**/TWOWAY**</span><span class="sxs-lookup"><span data-stu-id="9ea16-129">**/TWOWAY**</span></span>|<span data-ttu-id="9ea16-130">送信者、受信者からの応答を待機します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-130">The sender will wait for a response from the receiver.</span></span> <span data-ttu-id="9ea16-131">SB と EB を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ea16-131">SB and EB need to be specified.</span></span> <span data-ttu-id="9ea16-132">CR はオプションです。</span><span class="sxs-lookup"><span data-stu-id="9ea16-132">CR is optional.</span></span> <span data-ttu-id="9ea16-133">ファイル モードでは、応答は、ファイルに格納されます。応答です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-133">In File mode, the response is stored in the file FILE.RESPONSE.</span></span>|  
|<span data-ttu-id="9ea16-134">**/SB**</span><span class="sxs-lookup"><span data-stu-id="9ea16-134">**/SB**</span></span>|<span data-ttu-id="9ea16-135">ブロックの区切り記号の開始バイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-135">Sets the ASCII value of the Start Block Delimiter Byte.</span></span> <span data-ttu-id="9ea16-136">既定値は none です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-136">The default is none.</span></span>|  
|<span data-ttu-id="9ea16-137">**/EB**</span><span class="sxs-lookup"><span data-stu-id="9ea16-137">**/EB**</span></span>|<span data-ttu-id="9ea16-138">終了ブロックの区切り記号のバイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-138">Sets the ASCII value of the End Block Delimiter Byte.</span></span> <span data-ttu-id="9ea16-139">既定値は none です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-139">The default is none.</span></span>|  
|<span data-ttu-id="9ea16-140">**/CR**</span><span class="sxs-lookup"><span data-stu-id="9ea16-140">**/CR**</span></span>|<span data-ttu-id="9ea16-141">復帰を返す区切り文字バイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-141">Sets the ASCII value of the Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="9ea16-142">既定値は none です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-142">The default is none.</span></span>|  
  
## <a name="examples-of-tool-use"></a><span data-ttu-id="9ea16-143">ツールの使用方法の例</span><span class="sxs-lookup"><span data-stu-id="9ea16-143">Examples of Tool Use</span></span>  
 <span data-ttu-id="9ea16-144">次の例では、MllpSend ツールを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-144">The following examples demonstrate how you can use the MllpSend tool.</span></span>  
  
 <span data-ttu-id="9ea16-145">**例 1**</span><span class="sxs-lookup"><span data-stu-id="9ea16-145">**Example 1.**</span></span> <span data-ttu-id="9ea16-146">次のコマンドを使用すると、"myserver"をサーバー上のポート 13000 でリッスンしている一方向のアダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="9ea16-146">You can use the following command to send a message to a one-way adapter listening on port 13000 on server "myserver".</span></span> <span data-ttu-id="9ea16-147">ラッパーの文字の ASCII 値は SB 11、EB 28 および CR 13 です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-147">The ASCII values of the wrapper characters are SB 11, EB 28, and CR 13.</span></span>  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 <span data-ttu-id="9ea16-148">**例 2 です。**</span><span class="sxs-lookup"><span data-stu-id="9ea16-148">**Example 2.**</span></span> <span data-ttu-id="9ea16-149">11000"localhost"をサーバー上のポートでリッスンしている、双方向アダプターに 100 回のメッセージを送信するのに、次のコマンドを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9ea16-149">You can use the following command to send a message 100 times to a two-way adapter listening on port 11000 on server "localhost".</span></span> <span data-ttu-id="9ea16-150">ラッパーの文字の ASCII 値は SB 11、EB 28 および CR 13 です。</span><span class="sxs-lookup"><span data-stu-id="9ea16-150">The ASCII values of the wrapper characters are SB 11, EB 28, and CR 13.</span></span>  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ea16-151">参照</span><span class="sxs-lookup"><span data-stu-id="9ea16-151">See Also</span></span>  
 [<span data-ttu-id="9ea16-152">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="9ea16-152">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)
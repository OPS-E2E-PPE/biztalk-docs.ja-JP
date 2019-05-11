---
title: MllpSend ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MllpSend tool
- MLLP-encoded messages, receive adapters
- MLLP-encoded messages, MllpSend tool
ms.assetid: b1723d52-4909-4543-8215-4f73802b6c4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f86f814710f48aa0c8795e00bcf5c2f9be8e1a14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290199"
---
# <a name="mllpsend-tool"></a><span data-ttu-id="b94dc-102">MllpSend ツール</span><span class="sxs-lookup"><span data-stu-id="b94dc-102">MllpSend Tool</span></span>
<span data-ttu-id="b94dc-103">MllpSend ツールを使用して、データを MLLP 受信場所を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="b94dc-103">You can use the MllpSend tool to send data to an MLLP receive location.</span></span>  
  
 <span data-ttu-id="b94dc-104">使用してこのツールをインストールする、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]カスタム インストール手順。</span><span class="sxs-lookup"><span data-stu-id="b94dc-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="b94dc-105">コード型の BTAHL7 をインストールする一般的なインストールを実行した場合、カスタム インストールを実行テスト ツールを正常に動作するには、このチュートリアルの順序でインストールし、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b94dc-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="b94dc-106">カスタム セットアップ 画面で選択**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="b94dc-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="b94dc-107">詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="b94dc-108">BTAHL7 セットアップでは、このツールをインストールする*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="b94dc-108">BTAHL7 setup installs this tool in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="b94dc-109">このツールで使用する、[エンド ツー エンド チュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)、および[メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b94dc-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="b94dc-110">インストールした場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]既定のインストールで、チュートリアルの結果をテストすることはできません MLLP Testtools (含む MllpSend および MllpReceive) をインストールしていないとします。</span><span class="sxs-lookup"><span data-stu-id="b94dc-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLP Testtools (including MllpSend and MllpReceive), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="b94dc-111">ツールの使用方法</span><span class="sxs-lookup"><span data-stu-id="b94dc-111">Tool Usage</span></span>  
 <span data-ttu-id="b94dc-112">使用してこのコマンド ライン ツールを呼び出す構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="b94dc-113">次の表では、MllpSend ツールを使用して、構文の各部について説明します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-113">The following table describes each part of the syntax the MllpSend tool uses.</span></span>  
  
|<span data-ttu-id="b94dc-114">構文</span><span class="sxs-lookup"><span data-stu-id="b94dc-114">Syntax</span></span>|<span data-ttu-id="b94dc-115">説明</span><span class="sxs-lookup"><span data-stu-id="b94dc-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b94dc-116">**/?**</span><span class="sxs-lookup"><span data-stu-id="b94dc-116">**/?**</span></span>|<span data-ttu-id="b94dc-117">コマンド プロンプト ウィンドウでヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-117">Displays Help in the Command Prompt window.</span></span>|  
|<span data-ttu-id="b94dc-118">**/I \<IP\>**</span><span class="sxs-lookup"><span data-stu-id="b94dc-118">**/I \<IP\>**</span></span>|<span data-ttu-id="b94dc-119">送信するアドレスを表します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-119">Denotes the address to send to.</span></span> <span data-ttu-id="b94dc-120">既定値は、localhost です。</span><span class="sxs-lookup"><span data-stu-id="b94dc-120">The default value is localhost.</span></span>|  
|<span data-ttu-id="b94dc-121">**/P\<ポート\>**</span><span class="sxs-lookup"><span data-stu-id="b94dc-121">**/P \<PORT\>**</span></span>|<span data-ttu-id="b94dc-122">送信するポート番号を表します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-122">Denotes the port number to send to.</span></span> <span data-ttu-id="b94dc-123">既定値は**11000**します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-123">The default value is **11000**.</span></span>|  
|<span data-ttu-id="b94dc-124">**/F**</span><span class="sxs-lookup"><span data-stu-id="b94dc-124">**/F**</span></span>|<span data-ttu-id="b94dc-125">ファイル名のファイルの内容を送信します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-125">Sends content of the file FILENAME.</span></span>|  
|<span data-ttu-id="b94dc-126">**/REPEAT \<n\>**</span><span class="sxs-lookup"><span data-stu-id="b94dc-126">**/REPEAT \<n\>**</span></span>|<span data-ttu-id="b94dc-127">同じメッセージを送信*n*時間。</span><span class="sxs-lookup"><span data-stu-id="b94dc-127">Sends the same message *n* times.</span></span> <span data-ttu-id="b94dc-128">ラッパーの文字は、各メッセージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b94dc-128">The wrapper characters will be applied to each message.</span></span>|  
|<span data-ttu-id="b94dc-129">**/TWOWAY**</span><span class="sxs-lookup"><span data-stu-id="b94dc-129">**/TWOWAY**</span></span>|<span data-ttu-id="b94dc-130">送信者、受信者からの応答を待機します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-130">The sender will wait for a response from the receiver.</span></span> <span data-ttu-id="b94dc-131">SB と EB を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b94dc-131">SB and EB need to be specified.</span></span> <span data-ttu-id="b94dc-132">CR は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b94dc-132">CR is optional.</span></span> <span data-ttu-id="b94dc-133">ファイル モードでは、応答は、ファイルのファイルに格納されます。応答です。</span><span class="sxs-lookup"><span data-stu-id="b94dc-133">In File mode, the response is stored in the file FILE.RESPONSE.</span></span>|  
|<span data-ttu-id="b94dc-134">**/SB**</span><span class="sxs-lookup"><span data-stu-id="b94dc-134">**/SB**</span></span>|<span data-ttu-id="b94dc-135">ブロックの区切り記号の開始バイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-135">Sets the ASCII value of the Start Block Delimiter Byte.</span></span> <span data-ttu-id="b94dc-136">既定では none です。</span><span class="sxs-lookup"><span data-stu-id="b94dc-136">The default is none.</span></span>|  
|<span data-ttu-id="b94dc-137">**/EB**</span><span class="sxs-lookup"><span data-stu-id="b94dc-137">**/EB**</span></span>|<span data-ttu-id="b94dc-138">終了ブロックの区切り記号のバイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-138">Sets the ASCII value of the End Block Delimiter Byte.</span></span> <span data-ttu-id="b94dc-139">既定では none です。</span><span class="sxs-lookup"><span data-stu-id="b94dc-139">The default is none.</span></span>|  
|<span data-ttu-id="b94dc-140">**/CR**</span><span class="sxs-lookup"><span data-stu-id="b94dc-140">**/CR**</span></span>|<span data-ttu-id="b94dc-141">復帰返す区切り記号のバイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-141">Sets the ASCII value of the Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="b94dc-142">既定では none です。</span><span class="sxs-lookup"><span data-stu-id="b94dc-142">The default is none.</span></span>|  
  
## <a name="examples-of-tool-use"></a><span data-ttu-id="b94dc-143">ツールの使用方法の例</span><span class="sxs-lookup"><span data-stu-id="b94dc-143">Examples of Tool Use</span></span>  
 <span data-ttu-id="b94dc-144">次の例では、MllpSend ツールを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b94dc-144">The following examples demonstrate how you can use the MllpSend tool.</span></span>  
  
 <span data-ttu-id="b94dc-145">**例 1**</span><span class="sxs-lookup"><span data-stu-id="b94dc-145">**Example 1.**</span></span> <span data-ttu-id="b94dc-146">次のコマンドを使用して、サーバー"myserver"上のポート 13000 でリッスンしている一方向のアダプターにメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="b94dc-146">You can use the following command to send a message to a one-way adapter listening on port 13000 on server "myserver".</span></span> <span data-ttu-id="b94dc-147">SB 11、EB 28、CR 13、ラッパーの文字の ASCII 値。</span><span class="sxs-lookup"><span data-stu-id="b94dc-147">The ASCII values of the wrapper characters are SB 11, EB 28, and CR 13.</span></span>  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 <span data-ttu-id="b94dc-148">**例 2**</span><span class="sxs-lookup"><span data-stu-id="b94dc-148">**Example 2.**</span></span> <span data-ttu-id="b94dc-149">次のコマンドを使用して、ポート 11000"localhost"をサーバー上でリッスンして双方向アダプターに 100 回のメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="b94dc-149">You can use the following command to send a message 100 times to a two-way adapter listening on port 11000 on server "localhost".</span></span> <span data-ttu-id="b94dc-150">SB 11、EB 28、CR 13、ラッパーの文字の ASCII 値。</span><span class="sxs-lookup"><span data-stu-id="b94dc-150">The ASCII values of the wrapper characters are SB 11, EB 28, and CR 13.</span></span>  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a><span data-ttu-id="b94dc-151">参照</span><span class="sxs-lookup"><span data-stu-id="b94dc-151">See Also</span></span>  
 [<span data-ttu-id="b94dc-152">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="b94dc-152">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)
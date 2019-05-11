---
title: MllpReceive ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- MllpReceive tool
- MLLP-encoded messages, MllpReceive tool
ms.assetid: 7069444b-1412-40bf-b567-fa86f76cd007
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e2684ef0d2ae7ee678e11f7b03541499b5f4c7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290296"
---
# <a name="mllpreceive-tool"></a><span data-ttu-id="7a127-102">MllpReceive ツール</span><span class="sxs-lookup"><span data-stu-id="7a127-102">MllpReceive Tool</span></span>
<span data-ttu-id="7a127-103">MLLP 送信ポートからデータを受信するのに MllpReceive ツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7a127-103">You can use the MllpReceive tool to receive data from an MLLP send port.</span></span>  
  
 <span data-ttu-id="7a127-104">使用してこのツールをインストールする、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]カスタム インストール手順。</span><span class="sxs-lookup"><span data-stu-id="7a127-104">You install this tool through the [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Custom installation procedure.</span></span> <span data-ttu-id="7a127-105">コード型の BTAHL7 をインストールする一般的なインストールを実行した場合、カスタム インストールを実行テスト ツールを正常に動作するには、このチュートリアルの順序でインストールし、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a127-105">If you performed a Typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="7a127-106">カスタム セットアップ 画面で選択**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7a127-106">At the Custom Setup screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="7a127-107">詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)します。</span><span class="sxs-lookup"><span data-stu-id="7a127-107">For more information, see [Performing a Custom Installation](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).</span></span>  
  
 <span data-ttu-id="7a127-108">BTAHL7 セットアップでは、このツールをインストールする*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="7a127-108">BTAHL7 setup installs this tool in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span>  
  
 <span data-ttu-id="7a127-109">このツールで使用する、[エンド ツー エンド チュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)、および[メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="7a127-109">You use this tool in the [End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md), the [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md), the [Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md), and the [Message Enrichment Tutorial](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md).</span></span> <span data-ttu-id="7a127-110">インストールした場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]既定のインストールをインストールしていない、MLLPTest ツール (含む MllpReceive および MllpSend)、チュートリアルの結果をテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7a127-110">If you installed [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] through the default installation, and have not installed the MLLPTest tool (including MllpReceive and MllpSend), you will not be able to test your tutorial results.</span></span>  
  
## <a name="tool-usage"></a><span data-ttu-id="7a127-111">ツールの使用方法</span><span class="sxs-lookup"><span data-stu-id="7a127-111">Tool Usage</span></span>  
 <span data-ttu-id="7a127-112">使用してこのコマンド ライン ツールを呼び出す構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7a127-112">The following shows the syntax you use to invoke this command-line tool:</span></span>  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 <span data-ttu-id="7a127-113">次の表では、MllpReceive ツールを使用して、構文の各部について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a127-113">The following table describes each part of the syntax the MllpReceive tool uses.</span></span>  
  
|<span data-ttu-id="7a127-114">構文</span><span class="sxs-lookup"><span data-stu-id="7a127-114">Syntax</span></span>|<span data-ttu-id="7a127-115">説明</span><span class="sxs-lookup"><span data-stu-id="7a127-115">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="7a127-116">/?</span><span class="sxs-lookup"><span data-stu-id="7a127-116">/?</span></span>|<span data-ttu-id="7a127-117">このヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="7a127-117">Displays this help.</span></span>|  
|<span data-ttu-id="7a127-118">/I \<IP\></span><span class="sxs-lookup"><span data-stu-id="7a127-118">/I \<IP\></span></span>|<span data-ttu-id="7a127-119">リッスンするアドレスを表します。</span><span class="sxs-lookup"><span data-stu-id="7a127-119">Denotes the address to listen to.</span></span> <span data-ttu-id="7a127-120">既定では使用可能なすべての ip アドレスです。</span><span class="sxs-lookup"><span data-stu-id="7a127-120">The default is all available IPs.</span></span>|  
|<span data-ttu-id="7a127-121">/P\<ポート\></span><span class="sxs-lookup"><span data-stu-id="7a127-121">/P \<PORT\></span></span>|<span data-ttu-id="7a127-122">リッスンするポート番号を表します。</span><span class="sxs-lookup"><span data-stu-id="7a127-122">Denotes the port number to listen to.</span></span> <span data-ttu-id="7a127-123">既定値は、12000 です。</span><span class="sxs-lookup"><span data-stu-id="7a127-123">The default value is 12000.</span></span>|  
|<span data-ttu-id="7a127-124">/D\<ディレクトリ\></span><span class="sxs-lookup"><span data-stu-id="7a127-124">/D \<DIRECTORY\></span></span>|<span data-ttu-id="7a127-125">内のディレクトリにすべての受信メッセージを格納\<ディレクトリ\>します。</span><span class="sxs-lookup"><span data-stu-id="7a127-125">Stores all received message(s) in the directory in \<DIRECTORY\>.</span></span> <span data-ttu-id="7a127-126">指定しない場合\<ディレクトリ\>既定のディレクトリは %temp% です。</span><span class="sxs-lookup"><span data-stu-id="7a127-126">If you do not specify \<DIRECTORY\>, the default directory is %TEMP%.</span></span>|  
|<span data-ttu-id="7a127-127">/分割</span><span class="sxs-lookup"><span data-stu-id="7a127-127">/SPLIT</span></span>|<span data-ttu-id="7a127-128">区切り記号に基づいて個別のメッセージには、受信したデータを分割します。</span><span class="sxs-lookup"><span data-stu-id="7a127-128">Splits the received data into separate messages based on the delimiters.</span></span> <span data-ttu-id="7a127-129">SB と EB 必要です。</span><span class="sxs-lookup"><span data-stu-id="7a127-129">SB and EB are required.</span></span> <span data-ttu-id="7a127-130">CR は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7a127-130">CR is optional.</span></span>|  
|<span data-ttu-id="7a127-131">/STATICACK</span><span class="sxs-lookup"><span data-stu-id="7a127-131">/STATICACK</span></span>|<span data-ttu-id="7a127-132">静的受信確認の送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="7a127-132">The static acknowledgment returned to the sender.</span></span> <span data-ttu-id="7a127-133">分割モードが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a127-133">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="7a127-134">/HL7ACK</span><span class="sxs-lookup"><span data-stu-id="7a127-134">/HL7ACK</span></span>|<span data-ttu-id="7a127-135">HL7 の受信確認は、送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="7a127-135">The HL7 acknowledgment returned to the sender.</span></span> <span data-ttu-id="7a127-136">ファイル名は、HL7 ACK を含むファイルの名前を表します</span><span class="sxs-lookup"><span data-stu-id="7a127-136">FILENAME denotes the name of the file containing the HL7 ACK.</span></span> <span data-ttu-id="7a127-137">分割モードが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a127-137">Will enforce SPLIT mode.</span></span>|  
|<span data-ttu-id="7a127-138">/SB</span><span class="sxs-lookup"><span data-stu-id="7a127-138">/SB</span></span>|<span data-ttu-id="7a127-139">開始ブロックの区切り記号のバイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7a127-139">Sets the ASCII value of Start Block Delimiter Byte.</span></span> <span data-ttu-id="7a127-140">既定では none です。</span><span class="sxs-lookup"><span data-stu-id="7a127-140">The default is none.</span></span>|  
|<span data-ttu-id="7a127-141">/EB</span><span class="sxs-lookup"><span data-stu-id="7a127-141">/EB</span></span>|<span data-ttu-id="7a127-142">終了ブロックの区切り記号のバイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7a127-142">Sets the ASCII value of End Block Delimiter Byte.</span></span> <span data-ttu-id="7a127-143">既定では none です。</span><span class="sxs-lookup"><span data-stu-id="7a127-143">The default is none.</span></span>|  
|<span data-ttu-id="7a127-144">/CR</span><span class="sxs-lookup"><span data-stu-id="7a127-144">/CR</span></span>|<span data-ttu-id="7a127-145">復帰返す区切り文字のバイトの ASCII 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7a127-145">Sets the ASCII value of Carriage Return Delimiter Byte.</span></span> <span data-ttu-id="7a127-146">既定では none です。</span><span class="sxs-lookup"><span data-stu-id="7a127-146">The default is none.</span></span>|  
  
## <a name="example-of-tool-use"></a><span data-ttu-id="7a127-147">ツールの使用方法の例</span><span class="sxs-lookup"><span data-stu-id="7a127-147">Example of Tool Use</span></span>  
 <span data-ttu-id="7a127-148">ポート 10000、localhost 上でリッスンするように、次のコマンドを使用し、メッセージを別のファイルを C:\TEMP に保存することができます。</span><span class="sxs-lookup"><span data-stu-id="7a127-148">You can use the following command to listen to port 10000 on localhost, and save messages to separate files on C:\TEMP:</span></span>  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a127-149">参照</span><span class="sxs-lookup"><span data-stu-id="7a127-149">See Also</span></span>  
 [<span data-ttu-id="7a127-150">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="7a127-150">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)
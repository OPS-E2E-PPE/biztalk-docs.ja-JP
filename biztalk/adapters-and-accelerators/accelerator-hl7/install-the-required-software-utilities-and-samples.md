---
title: "必要なソフトウェア、ユーティリティ、およびサンプルのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 678037cd050ae8375b3c9ec465860d939d48cccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-required-software-utilities-and-samples"></a><span data-ttu-id="3ff9f-102">必要なソフトウェア、ユーティリティ、およびサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-102">Install the Required Software, Utilities, and Samples</span></span>
<span data-ttu-id="3ff9f-103">このチュートリアルに必要です[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server、およびカスタム[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] MLLP テスト ツールを含むインストールします。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-103">This tutorial requires [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Windows Server, and a custom [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation that includes the MLLP Test Tools.</span></span> <span data-ttu-id="3ff9f-104">さらは理解しておく[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で開発[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]と[HL7 アクセラレータと使用可能な BizTalk ツールの学習](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)です。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-104">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and [Learn the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>
  
 <span data-ttu-id="3ff9f-105">次のユーティリティとサンプルをコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-105">You must have the following utilities and samples installed on your computer:</span></span>  
  
-   <span data-ttu-id="3ff9f-106">**MllpSend ツール**</span><span class="sxs-lookup"><span data-stu-id="3ff9f-106">**MllpSend Tool**</span></span>  
  
     <span data-ttu-id="3ff9f-107">このコマンド ライン ユーティリティは、メッセージを送信経由で、最小下位層プロトコル (MLLP) プロトコルを MLLP の受信場所。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-107">This command-line utility sends a message over the Minimal Lower Layer Protocol (MLLP) protocol to an MLLP receive location.</span></span> <span data-ttu-id="3ff9f-108">これを使用するには、チュートリアルの結果をテストします。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-108">You use it to test your tutorial results.</span></span> <span data-ttu-id="3ff9f-109">詳細については、次を参照してください。 [MllpSend ツール](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md)です。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-109">For more information, see [MllpSend Tool](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md).</span></span>  
  
-   <span data-ttu-id="3ff9f-110">**MllpPReceive ツール**</span><span class="sxs-lookup"><span data-stu-id="3ff9f-110">**MllpPReceive Tool**</span></span>  
  
     <span data-ttu-id="3ff9f-111">このコマンド ライン ユーティリティは、受信場所のリスナーとして機能している、MLLP のプロトコルを介してメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-111">This command-line utility receives messages over the MLLP protocol, serving as a receive-location listener.</span></span> <span data-ttu-id="3ff9f-112">メッセージおよび受信した受信確認を表示する、テスト、チュートリアルの結果に使用するとします。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-112">You use it to test your tutorial results, displaying messages and acknowledgments received.</span></span> <span data-ttu-id="3ff9f-113">詳細については、次を参照してください。 [MllpReceive ツール](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md)です。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-113">For more information, see [MllpReceive Tool](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md).</span></span>  
  
-   <span data-ttu-id="3ff9f-114">**サンプル アプリケーションに同意 ACK.txt**</span><span class="sxs-lookup"><span data-stu-id="3ff9f-114">**Sample Application Accept ACK.txt**</span></span>  
  
     <span data-ttu-id="3ff9f-115">このサンプル ファイルのテキストを含む、受信確認メッセージのアプリケーション承諾します。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-115">This sample file contains the text of an application-accept acknowledgment message.</span></span> <span data-ttu-id="3ff9f-116">サンプルは、受信、メッセージを表示し、サンプル ファイルで、確認を返信する MllpReceive ツールと連携します。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-116">The sample works with the MllpReceive tool, which receives and displays messages, then sends back the acknowledgment(s) in the sample file.</span></span>  
  
 <span data-ttu-id="3ff9f-117">BTAHL7 カスタム インストール プロセスを使用して 2 つのツールとサンプル ファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-117">You need to install the two tools and the sample file by using the BTAHL7 Custom installation process.</span></span> <span data-ttu-id="3ff9f-118">通常のインストール プロセスでは、これらのツールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-118">The Typical installation process does not install these tools.</span></span> <span data-ttu-id="3ff9f-119">これらのツールをインストールするに BTAHL7 のカスタム インストールを実行、**カスタム セットアップ**画面で、 **MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-119">To install these tools, run the BTAHL7 custom installation, at the **Custom Setup** screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="3ff9f-120">詳細については、次を参照してください。 [BizTalk Accelerator 用 HL7 インストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)です。</span><span class="sxs-lookup"><span data-stu-id="3ff9f-120">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff9f-121">参照</span><span class="sxs-lookup"><span data-stu-id="3ff9f-121">See Also</span></span>  
 [<span data-ttu-id="3ff9f-122">バッチ処理のチュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="3ff9f-122">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)
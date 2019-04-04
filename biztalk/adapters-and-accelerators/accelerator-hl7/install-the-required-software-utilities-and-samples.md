---
title: 必要なソフトウェア、ユーティリティ、およびサンプルのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f92f4cc994b4139c1c33423cc7a94c9072e226
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965907"
---
# <a name="install-the-required-software-utilities-and-samples"></a><span data-ttu-id="f4ead-102">必要なソフトウェア、ユーティリティ、およびサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4ead-102">Install the Required Software, Utilities, and Samples</span></span>
<span data-ttu-id="f4ead-103">このチュートリアルは、Microsoft Windows Server、およびカスタムの Microsoft が必要です。 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] MLLP テスト ツールを含むインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4ead-103">This tutorial requires Microsoft Windows Server, and a custom Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] installation that includes the MLLP Test Tools.</span></span> <span data-ttu-id="f4ead-104">さらに、知っておくべきで[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Microsoft での開発[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]と[HL7 アクセラレータや使用可能な BizTalk ツールの学習](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-104">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and [Learn the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>
  
 <span data-ttu-id="f4ead-105">次のユーティリティとサンプルをコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4ead-105">You must have the following utilities and samples installed on your computer:</span></span>  
  
- <span data-ttu-id="f4ead-106">**MllpSend ツール**</span><span class="sxs-lookup"><span data-stu-id="f4ead-106">**MllpSend Tool**</span></span>  
  
   <span data-ttu-id="f4ead-107">このコマンド ライン ユーティリティは、メッセージを送信経由で、最小下位レイヤー プロトコル (MLLP) プロトコルを MLLP の受信場所。</span><span class="sxs-lookup"><span data-stu-id="f4ead-107">This command-line utility sends a message over the Minimal Lower Layer Protocol (MLLP) protocol to an MLLP receive location.</span></span> <span data-ttu-id="f4ead-108">これを使用するには、チュートリアルの結果をテストします。</span><span class="sxs-lookup"><span data-stu-id="f4ead-108">You use it to test your tutorial results.</span></span> <span data-ttu-id="f4ead-109">詳細については、[MllpSend ツール](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ead-109">For more information, see [MllpSend Tool](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md).</span></span>  
  
- <span data-ttu-id="f4ead-110">**MllpPReceive ツール**</span><span class="sxs-lookup"><span data-stu-id="f4ead-110">**MllpPReceive Tool**</span></span>  
  
   <span data-ttu-id="f4ead-111">このコマンド ライン ユーティリティでは、受信場所のリスナーとして機能、MLLP プロトコル経由でメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-111">This command-line utility receives messages over the MLLP protocol, serving as a receive-location listener.</span></span> <span data-ttu-id="f4ead-112">これを使用して、メッセージおよび受信した受信確認を表示する、チュートリアルの結果をテストします。</span><span class="sxs-lookup"><span data-stu-id="f4ead-112">You use it to test your tutorial results, displaying messages and acknowledgments received.</span></span> <span data-ttu-id="f4ead-113">詳細については、[MllpReceive ツール](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ead-113">For more information, see [MllpReceive Tool](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md).</span></span>  
  
- <span data-ttu-id="f4ead-114">**サンプル アプリケーションに同意 ACK.txt**</span><span class="sxs-lookup"><span data-stu-id="f4ead-114">**Sample Application Accept ACK.txt**</span></span>  
  
   <span data-ttu-id="f4ead-115">このサンプル ファイルのテキストを格納する、アプリケーションの受信確認メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f4ead-115">This sample file contains the text of an application-accept acknowledgment message.</span></span> <span data-ttu-id="f4ead-116">サンプルは、受信、メッセージを表示し、サンプル ファイルで、確認を返信 MllpReceive ツールと連携します。</span><span class="sxs-lookup"><span data-stu-id="f4ead-116">The sample works with the MllpReceive tool, which receives and displays messages, then sends back the acknowledgment(s) in the sample file.</span></span>  
  
  <span data-ttu-id="f4ead-117">BTAHL7 のカスタム インストール プロセスを使用して 2 つのツールとサンプル ファイルをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4ead-117">You need to install the two tools and the sample file by using the BTAHL7 Custom installation process.</span></span> <span data-ttu-id="f4ead-118">一般的なインストール プロセスでは、これらのツールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="f4ead-118">The Typical installation process does not install these tools.</span></span> <span data-ttu-id="f4ead-119">これらのツールをインストールするで、BTAHL7 のカスタム インストールを実行、**カスタム セットアップ**画面で、 **MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f4ead-119">To install these tools, run the BTAHL7 custom installation, at the **Custom Setup** screen, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="f4ead-120">詳細については、[BizTalk Accelerator for HL7 のインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ead-120">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ead-121">参照</span><span class="sxs-lookup"><span data-stu-id="f4ead-121">See Also</span></span>  
 [<span data-ttu-id="f4ead-122">バッチ処理のチュートリアルを使用するための準備</span><span class="sxs-lookup"><span data-stu-id="f4ead-122">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)
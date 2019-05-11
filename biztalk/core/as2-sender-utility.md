---
title: AS2 送信者ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e2a88fc-67fd-4801-a6f8-1e7c92098eaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37a6c7ea0500b24db9a99d94ea4044a0d645b134
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358857"
---
# <a name="as2-sender-utility"></a><span data-ttu-id="99cc3-102">AS2 送信者ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="99cc3-102">AS2 Sender Utility</span></span>
<span data-ttu-id="99cc3-103">AS2 送信者ユーティリティが付属[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 台のコンピューター上の Web サイトに AS2 メッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-103">The AS2 Sender utility shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to send an AS2 message to a Web site on a single computer.</span></span> <span data-ttu-id="99cc3-104">このユーティリティは、個別のコンピュータからの AS2 メッセージの送信をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="99cc3-104">This utility simulates the sending of an AS2 message from a separate computer.</span></span>  
  
 <span data-ttu-id="99cc3-105">AS2 送信者ユーティリティ ファイルにある[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 tutorial \sender します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-105">The AS2 Sender utility files are located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="99cc3-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="99cc3-106">Prerequisites</span></span>  
 <span data-ttu-id="99cc3-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99cc3-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="what-this-utility-does"></a><span data-ttu-id="99cc3-108">このユーティリティの処理</span><span class="sxs-lookup"><span data-stu-id="99cc3-108">What This Utility Does</span></span>  
 <span data-ttu-id="99cc3-109">AS2 送信者ユーティリティは、EDI ペイロードを持つ AS2 メッセージを構築し、BTSHTTPReceive ISAPI フィルタを使用する Web サイトにそのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-109">The AS2 Sender utility builds an AS2 message with an EDI payload, and sends that message to a Web site that uses the BTSHTTPReceive ISAPI filter.</span></span> <span data-ttu-id="99cc3-110">既定では、このチュートリアルは、次でください。</span><span class="sxs-lookup"><span data-stu-id="99cc3-110">By default the tutorial does the following:</span></span>  
  
- <span data-ttu-id="99cc3-111">864 X12 エンコードのペイロードを含む X12_00401_864.edi という名前の AS2 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-111">Sends an AS2 message named X12_00401_864.edi with an 864 X12-encoded payload.</span></span> <span data-ttu-id="99cc3-112">このメッセージにある、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial フォルダー。</span><span class="sxs-lookup"><span data-stu-id="99cc3-112">This message is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial folder.</span></span>  
  
- <span data-ttu-id="99cc3-113">AS2 メッセージへの応答として非同期 MDN メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-113">Prompts an asynchronous MDN in response to the AS2 message.</span></span> <span data-ttu-id="99cc3-114">これは、送信されるメッセージによって決定され、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-114">This is determined by the message sent, and can be changed.</span></span>  
  
- <span data-ttu-id="99cc3-115">Contoso 仮想ディレクトリ経由で受信場所には、AS2 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-115">Sends the AS2 message to a receive location through the Contoso virtual directory.</span></span>  
  
  <span data-ttu-id="99cc3-116">ユーティリティは、この特定の動作を変更するのには変更できます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-116">The utility can be modified to change this specific behavior.</span></span> <span data-ttu-id="99cc3-117">参照してください、 [AS2 送信者ユーティリティをカスタマイズする方法](../core/as2-sender-utility.md#BKMK_Custom)以下のセクション。</span><span class="sxs-lookup"><span data-stu-id="99cc3-117">See the [How to Customize the AS2 Sender Utility](../core/as2-sender-utility.md#BKMK_Custom) section below.</span></span>  
  
## <a name="how-to-set-up-a-solution-using-the-as2-sender-utility"></a><span data-ttu-id="99cc3-118">AS2 送信者ユーティリティを使用してソリューションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="99cc3-118">How to Set Up a Solution Using the AS2 Sender Utility</span></span>  
 <span data-ttu-id="99cc3-119">AS2 送信者ユーティリティを使用して、ソリューションを設定するには、次の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99cc3-119">To set up a solution to use the AS2 Sender utility, you need to do the following.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="99cc3-120">AS2 チュートリアルおよび AS2 送信側の 2 つのチュートリアルでは、次の手順が示されています。</span><span class="sxs-lookup"><span data-stu-id="99cc3-120">These steps are demonstrated in the AS2 Tutorial and two AS2 send-side walkthroughs.</span></span> <span data-ttu-id="99cc3-121">詳細については、次を参照してください。[チュートリアル 3。AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)、[チュートリアル (AS2)。同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)、および[チュートリアル (AS2)。非同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-121">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md), [Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md), and [Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).</span></span>  
  
-   <span data-ttu-id="99cc3-122">BTSHTTPReceive ISAPI フィルタを有効にします。</span><span class="sxs-lookup"><span data-stu-id="99cc3-122">Enable the BTSHTTPReceive ISAPI filter.</span></span>  
  
-   <span data-ttu-id="99cc3-123">Web ページと AS2 メッセージを受信する受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-123">Configure a Web page and a receive location to receive the AS2 message.</span></span> <span data-ttu-id="99cc3-124">既定の AS2 送信者ユーティリティでは、Web ページは、Contoso Web ページです。</span><span class="sxs-lookup"><span data-stu-id="99cc3-124">In the default AS2 Sender utility, the Web page is the Contoso Web page.</span></span>  
  
-   <span data-ttu-id="99cc3-125">AS2 メッセージのペイロードとして送信する EDI インターチェンジのスキーマをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="99cc3-125">Deploy the schema for the EDI interchange that you will send as a payload of the AS2 message.</span></span>  
  
-   <span data-ttu-id="99cc3-126">適切な AS2 および EDI パーティ プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-126">Set the appropriate AS2 and EDI party properties.</span></span>  
  
##  <a name="BKMK_Custom"></a> <span data-ttu-id="99cc3-127">AS2 送信者ユーティリティをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="99cc3-127">How to Customize the AS2 Sender Utility</span></span>  
 <span data-ttu-id="99cc3-128">既定の AS2 送信者ユーティリティは、テスト 864 EDI インターチェンジを AS2 経由で、BTSHTTPReceive ISAPI フィルタを使用して Contoso Web ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-128">The default AS2 Sender utility sends a test 864 EDI interchange over AS2 to a Contoso Web page using the BTSHTTPReceive ISAPI filter.</span></span> <span data-ttu-id="99cc3-129">X12_00401_864.edi という名前の AS2 メッセージには、非同期 MDN メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-129">The AS2 message, named X12_00401_864.edi, prompts an asynchronous MDN.</span></span> <span data-ttu-id="99cc3-130">AS2 送信者ユーティリティ コードは、HttpSender.cs 内にある、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 \sender フォルダー。</span><span class="sxs-lookup"><span data-stu-id="99cc3-130">The AS2 Sender utility code is located in HttpSender.cs in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]AS2 Tutorial\Sender folder.</span></span> <span data-ttu-id="99cc3-131">HttpSender.cs 内のコードは、次の行では、既定の 864 テスト ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-131">The following line of code in HttpSender.cs sends the default 864 test file:</span></span>  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
```  
  
> [!NOTE]
>  <span data-ttu-id="99cc3-132">別のファイル名と異なるパスを使用してこの行を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-132">You can modify this line with a different file name and different path.</span></span>  
  
 <span data-ttu-id="99cc3-133">HttpSender.cs 内の次の行では、x12_00401_864-sync.edi という名前の AS2 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-133">The following line in HttpSender.cs sends an AS2 message named X12_00401_864-Sync.edi.</span></span> <span data-ttu-id="99cc3-134">このメッセージは、同期 MDN を表示します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-134">This message prompts a synchronous MDN.</span></span> <span data-ttu-id="99cc3-135">既定では、HttpSender.cs 内のコード行がコメント アウトされて X12_00401_864.edi を送信する行を優先します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-135">By default, this line of code in HttpSender.cs is commented out in favor of the line that sends X12_00401_864.edi.</span></span> <span data-ttu-id="99cc3-136">X12_00401_864-sync.edi を送信するには、X12_00401_864.edi 行をコメント アウト、x12_00401_864-sync.edi 行をコメント解除します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-136">To send X12_00401_864-Sync.edi, uncomment the X12_00401_864-Sync.edi line and comment out the X12_00401_864.edi line.</span></span>  
  
```  
Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
```  
  
 <span data-ttu-id="99cc3-137">HttpSender.cs 内のコードは、次の行では、Contoso Web ページにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-137">The following line of code in HttpSender.cs sends the message to the Contoso Web page:</span></span>  
  
```  
HttpSender TestSender = new HttpSender("http://localhost/Contoso/BTSHttpReceive.dll");  
```  
  
> [!NOTE]
>  <span data-ttu-id="99cc3-138">別の仮想ディレクトリと ISAPI フィルターを使用してこの行を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-138">You can modify this line with a different virtual directory and ISAPI filter.</span></span>  
  
### <a name="to-build-the-as2-sender-sample"></a><span data-ttu-id="99cc3-139">AS2 送信者のサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="99cc3-139">To build the AS2 Sender sample</span></span>  
  
1. <span data-ttu-id="99cc3-140">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender フォルダーにある Sender.csproj プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-140">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the Sender.csproj project in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender folder.</span></span>  
  
2. <span data-ttu-id="99cc3-141">Sender プロジェクトでは、HttpSender.cs を開き、適切な受信側の Web ページと、適切な EDI ファイル名とパスを使用して送信者コードをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="99cc3-141">Open HttpSender.cs in the Sender project, and customize the Sender code with the appropriate receiving Web page and the appropriate EDI filename and path.</span></span>  
  
3. <span data-ttu-id="99cc3-142">Sender プロジェクトを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-142">Right-click the Sender project, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="99cc3-143">クリックして**署名**左側のコンソールでします。</span><span class="sxs-lookup"><span data-stu-id="99cc3-143">Click **Signing** in the left-hand console.</span></span> <span data-ttu-id="99cc3-144">いることを確認**アセンブリに署名**が選択されている厳密な名前キー ファイルに設定されていると**Sender.snk**します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-144">Ensure that **Sign the assembly** is selected, and the strong name key file is set to **Sender.snk**.</span></span> <span data-ttu-id="99cc3-145">必ず**遅延署名のみ**がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-145">Make sure that **Delay sign only** is cleared.</span></span>  
  
5. <span data-ttu-id="99cc3-146">プロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="99cc3-146">Build the project.</span></span>  
  
### <a name="to-run-the-as2-sender-sample"></a><span data-ttu-id="99cc3-147">AS2 送信者のサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="99cc3-147">To run the AS2 Sender sample</span></span>  
  
1. <span data-ttu-id="99cc3-148">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-148">Open a command prompt.</span></span> <span data-ttu-id="99cc3-149">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug に移動します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-149">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug.</span></span>  
  
2. <span data-ttu-id="99cc3-150">Enter **Sender.exe**、押します **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="99cc3-150">Enter **Sender.exe**, and then press **Enter**.</span></span>  
  
3. <span data-ttu-id="99cc3-151">AS2 メッセージが正常に送信されたことを示すメッセージを確認し、コマンド プロンプトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="99cc3-151">Verify that you see a message indicating that an AS2 message was successfully sent, and then close the command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99cc3-152">参照</span><span class="sxs-lookup"><span data-stu-id="99cc3-152">See Also</span></span>  
 <span data-ttu-id="99cc3-153">[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="99cc3-153">[Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md) </span></span>  
 <span data-ttu-id="99cc3-154">[チュートリアル (AS2):同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md) </span><span class="sxs-lookup"><span data-stu-id="99cc3-154">[Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md) </span></span>  
 [<span data-ttu-id="99cc3-155">チュートリアル (AS2):非同期 MDN による AS2 経由での EDI の送信</span><span class="sxs-lookup"><span data-stu-id="99cc3-155">Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN</span></span>](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)
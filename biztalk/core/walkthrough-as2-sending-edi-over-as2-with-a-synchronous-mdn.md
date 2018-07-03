---
title: 'チュートリアル (AS2): 同期 MDN による AS2 経由で EDI の送信 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21891d29-eb22-4b31-9258-14b72ae675dc
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b5417adfd53498891eccb2845b815f475e861a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982331"
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn"></a><span data-ttu-id="29cc2-102">チュートリアル (AS2): 同期 MDN による AS2 経由での EDI の送信</span><span class="sxs-lookup"><span data-stu-id="29cc2-102">Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN</span></span>
<span data-ttu-id="29cc2-103">このチュートリアルでは、同期 MDN による AS2 経由の EDI メッセージの送信用のソリューションを作成する一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending EDI messages over AS2, with a synchronous MDN.</span></span> <span data-ttu-id="29cc2-104">作成し、1 台のコンピューターには、このチュートリアルでは、完全なソリューションをテストできます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-104">You can create and test the full solution in this walkthrough on a single computer.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="29cc2-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="29cc2-105">Prerequisites</span></span>  
 <span data-ttu-id="29cc2-106">次に、このトピックの手順を実行するための前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="29cc2-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
- <span data-ttu-id="29cc2-108">チュートリアルを実行するコンピューターには、インターネット インフォメーション サービス (IIS) 7 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-108">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  
  
- <span data-ttu-id="29cc2-109">チュートリアルを実行するコンピューターに 64 ビット版の Windows がインストールされている場合は、BizTalk ホストが 32 ビットのみとマークされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-109">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="29cc2-110">IIS の [アプリケーション プールの 32 ビット アプリケーション設定を有効にする] を True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-110">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to True.</span></span> <span data-ttu-id="29cc2-111">詳細については、次を参照してください。[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-111">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-a-synchronous-mdn"></a><span data-ttu-id="29cc2-112">ソリューションにより EDI/AS2 メッセージを送信して同期 MDN を返す方法</span><span class="sxs-lookup"><span data-stu-id="29cc2-112">How the Solution Sends an EDI/AS2 Message and Returns a Synchronous MDN</span></span>  
 <span data-ttu-id="29cc2-113">このソリューションは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-113">The solution will do the following:</span></span>  
  
1. <span data-ttu-id="29cc2-114">一方向の FILE 受信ポートは、Contoso から EDI インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-114">A one-way FILE receive port receives an EDI interchange from Contoso.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-115">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="29cc2-115">The events in this list may not occur in the order shown.</span></span>  
  
2. <span data-ttu-id="29cc2-116">受信ポートは、パススルー受信パイプラインを使用して、テスト メッセージをそのまま MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-116">Using a passthrough receive pipeline, the receive port drops the test message into the MessageBox, unchanged.</span></span>  
  
3. <span data-ttu-id="29cc2-117">静的な双方向送信ポートは EDI インターチェンジを取得し、それを AS2 フォーマットにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-117">A static two-way send port picks up the EDI interchange and encodes it into AS2 format.</span></span>  
  
4. <span data-ttu-id="29cc2-118">送信ポートは、AS2 エンコード EDI インターチェンジを AS2 トランスポート経由で Fabrikam パーティに送信します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-118">The send port sends the AS2-encoded EDI interchange over AS2 transport to the Fabrikam party.</span></span>  
  
5. <span data-ttu-id="29cc2-119">Fabrikam の双方向受信ポートは、Fabrikam の仮想ディレクトリを使用して AS2 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-119">The two-way receive port at Fabrikam receives the AS2 message using the Fabrikam virtual directory.</span></span> <span data-ttu-id="29cc2-120">受信パイプラインは、AS2 からの EDI インターチェンジをデコードし、EDI インターチェンジをメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-120">The receive pipeline decodes the EDI interchange from AS2, and drops the EDI interchange into the MessageBox.</span></span>  
  
6. <span data-ttu-id="29cc2-121">双方向受信ポートに関連付けられている送信ポートは、同期 MDN を返します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-121">The send port associated with the two-way receive port returns a synchronous MDN.</span></span>  
  
7. <span data-ttu-id="29cc2-122">双方向送信ポートに関連付けられている受信ポートは、MDN を受信し、それをメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-122">The receive port associated with the two-way send port receives the MDN, and drops it in the MessageBox.</span></span>  
  
8. <span data-ttu-id="29cc2-123">パススルー送信パイプラインを持つ静的な一方向の送信ポートは、MDN を取得します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-123">A static one-way send port with a passthrough send pipeline picks up the MDN.</span></span>  
  
9. <span data-ttu-id="29cc2-124">一方向の送信ポートは、MDN をローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-124">The one-way send port sends the MDN to a local folder.</span></span>  
  
10. <span data-ttu-id="29cc2-125">パススルー送信パイプラインを持つ静的な一方向の送信ポートは、EDI メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-125">A static one-way send port with a passthrough send pipeline picks up the EDI message.</span></span>  
  
11. <span data-ttu-id="29cc2-126">一方向の送信ポートは、EDI メッセージをローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-126">The one-way send port sends the EDI message to a local folder.</span></span>  
  
    <span data-ttu-id="29cc2-127">次の図は、このソリューションのアーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-127">The following figure shows the architecture for this solution.</span></span>  
  
    <span data-ttu-id="29cc2-128">![同期 MDN による AS2 の送信](../core/media/270d24b7-3b5d-45cc-ba06-6c9f74717194.gif "270d24b7-3b5d-45cc-ba06-6c9f74717194")</span><span class="sxs-lookup"><span data-stu-id="29cc2-128">![AS2 sending with a Synchronous MDN](../core/media/270d24b7-3b5d-45cc-ba06-6c9f74717194.gif "270d24b7-3b5d-45cc-ba06-6c9f74717194")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="29cc2-129">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="29cc2-129">The Functionality in this Solution</span></span>  
 <span data-ttu-id="29cc2-130">このチュートリアルの機能には、以下の条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-130">The following applies to the functionality of this walkthrough:</span></span>  
  
-   <span data-ttu-id="29cc2-131">このチュートリアルでは、EDI 機能ではなく AS2 機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-131">This walkthrough deals with AS2 functionality, not EDI functionality.</span></span> <span data-ttu-id="29cc2-132">このため、AS2 処理に関連するすべてのポートでは、AS2EdiReceive または AS2EdiSend パイプラインでなく、AS2Receive または AS2Send パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-132">As a result, all ports involved in AS2 processing use either AS2Receive or AS2Send pipelines, not AS2EdiReceive or AS2EdiSend.</span></span> <span data-ttu-id="29cc2-133">AS2 処理に関連しないポートでは、PassThruReceive または PassThruTransmit パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-133">Ports that are not involved in AS2 processing use PassThruReceive or PassThruTransmit pipelines.</span></span>  
  
-   <span data-ttu-id="29cc2-134">状態レポートが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="29cc2-134">Status reporting is not enabled.</span></span>  
  
-   <span data-ttu-id="29cc2-135">このソリューションは、否認不可データベースに署名、圧縮、暗号化、およびメッセージ ストレージを構成しません。</span><span class="sxs-lookup"><span data-stu-id="29cc2-135">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="29cc2-136">これらのプロパティを構成する手順については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-136">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="29cc2-137">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="29cc2-137">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="29cc2-138">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29cc2-138">The procedures required for this solution include the following:</span></span>  
  
- <span data-ttu-id="29cc2-139">必要なメッセージ スキーマを使用して BizTalk プロジェクトをビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-139">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  
  
- <span data-ttu-id="29cc2-140">AS2 メッセージの受信に使用する BTS ISAPI フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-140">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  
  
- <span data-ttu-id="29cc2-141">Contoso からの AS2 メッセージを受信する Fabrikam 仮想ディレクトリを、受信場所で構成したとおりに作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-141">Create a Fabrikam virtual directory that receives the AS2 message from Contoso, as configured in the receive location.</span></span>  
  
- <span data-ttu-id="29cc2-142">Fabrikam 仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-142">Specify that the Fabrikam virtual directory is not managed by Windows SharePoint Services.</span></span>  
  
- <span data-ttu-id="29cc2-143">AS2 トランスポート経由で送信される EDI テスト メッセージを受信する一方向 FILE 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-143">Create a one-way FILE receive port to receive the EDI test message that will be sent via AS2 transport.</span></span> <span data-ttu-id="29cc2-144">テスト メッセージを受信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-144">Create the local folder to receive the test message.</span></span>  
  
- <span data-ttu-id="29cc2-145">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の静的な双方向 HTTP 送信ポートを作成して、EDI ビジネス ドキュメントが含まれた AS2 メッセージを Fabrikam に送信し、MDN 応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-145">Create a static two-way HTTP send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the AS2 message containing the EDI business document to Fabrikam, and to receive the MDN response.</span></span> <span data-ttu-id="29cc2-146">送信パイプラインとして AS2Send パイプラインを構成し、受信パイプラインとして AS2Receive パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-146">Configure the send pipeline to be the AS2Send pipeline and the receive pipeline to be the AS2Receive pipeline.</span></span>  
  
- <span data-ttu-id="29cc2-147">AS2 メッセージを受信し、MDN 応答を送信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の双方向 HTTP 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-147">Create a two-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message, and to send the MDN response.</span></span> <span data-ttu-id="29cc2-148">受信パイプラインとして AS2Receive パイプラインを構成し、送信パイプラインとして AS2Send パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-148">Configure the receive pipeline to be the AS2Receive pipeline and the send pipeline to be the AS2Send pipeline.</span></span> <span data-ttu-id="29cc2-149">Fabrikam 仮想ディレクトリ経由で AS2 メッセージを受信する受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-149">Configure the receive location to receive the AS2 message via the Fabrikam virtual directory.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="29cc2-150">このソリューションは 1 台のコンピューターを対象にしています。したがって、AS2 メッセージ (Contoso から) を送信する双方向送信ポート、および AS2 メッセージ (Fabrikam から) を受信する双方向受信ポートは、同一コンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-150">This solution is targeted for a single computer; as a result, the two-way send port sending the AS2 message (from Contoso) and the two-way receive port receiving the AS2 message (as Fabrikam) are on the same computer.</span></span>  
  
- <span data-ttu-id="29cc2-151">MDN をローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-151">Create a static one-way FILE send port (with a passthrough send pipeline) to route the MDN to a local folder.</span></span> <span data-ttu-id="29cc2-152">ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-152">Create the local folder.</span></span>  
  
- <span data-ttu-id="29cc2-153">メッセージ ペイロードをローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-153">Create a static one-way FILE send port (with a passthrough send pipeline) to route the message payload to a local folder.</span></span> <span data-ttu-id="29cc2-154">ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-154">Create the local folder.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="29cc2-155">メッセージ ペイロードをサブスクライブする送信ポートがない場合、メッセージ ボックスで中断されます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-155">If you do not have a send port to subscribe to the message payload, it will be suspended in the MessageBox.</span></span>  
  
- <span data-ttu-id="29cc2-156">Fabrikam および Contoso の両方にパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-156">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
- <span data-ttu-id="29cc2-157">両方の取引先に対して、それぞれビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-157">Create a business profile each for both the trading parties.</span></span>  
  
- <span data-ttu-id="29cc2-158">Fabrikam および Contoso のビジネス プロファイル間に AS2 アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-158">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="29cc2-159">AS2 アグリーメントには、AS2 メッセージを送信し、その応答として同期 MDN を受信するプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-159">The AS2 agreement would contain properties to send an AS2 message and receive a synchronous MDN in return.</span></span>  
  
- <span data-ttu-id="29cc2-160">テスト EDI インターチェンジを使用して、このチュートリアルをテストします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-160">Test the walkthrough using a test EDI interchange.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="29cc2-161">テスト メッセージには、EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-161">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="29cc2-162">そのファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ folder に保存して出荷されています。</span><span class="sxs-lookup"><span data-stu-id="29cc2-162">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ folder.</span></span> <span data-ttu-id="29cc2-163">これは、X12 850 メッセージです。</span><span class="sxs-lookup"><span data-stu-id="29cc2-163">This is an X12 850 message.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="29cc2-164">チュートリアルの構成</span><span class="sxs-lookup"><span data-stu-id="29cc2-164">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="29cc2-165">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-165">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="29cc2-166">メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-166">To deploy the message schema</span></span>  
  
1. <span data-ttu-id="29cc2-167">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-167">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-168">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="29cc2-168">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="29cc2-169">そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-169">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2. <span data-ttu-id="29cc2-170">プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-170">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="29cc2-171">SamplePO.txt ファイルを使用してソリューションをテストするには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-171">To use the SamplePO.txt file to test your solution, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="29cc2-172">X12_00401_850.xsd スキーマを選択し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-172">Select the X12_00401_850.xsd schema, and then click **Add**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-173">異なる EDI スキーマを使用するには、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI フォルダー。</span><span class="sxs-lookup"><span data-stu-id="29cc2-173">To use a different EDI schema, go to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI folder.</span></span> <span data-ttu-id="29cc2-174">EDI スキーマは、XSD_SchemaEDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe**スキーマを既定のフォルダーに解凍する XSD_SchemaEDI フォルダー内のファイル。</span><span class="sxs-lookup"><span data-stu-id="29cc2-174">If the EDI schemas have not been unzipped into the XSD_SchemaEDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the XSD_SchemaEDI folder to unzip the schemas into the default folder.</span></span>  
  
3. <span data-ttu-id="29cc2-175">アセンブリ キー ファイルを設定し、アセンブリをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-175">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="29cc2-176">BTS ISAPI フィルターを有効にするには</span><span class="sxs-lookup"><span data-stu-id="29cc2-176">To enable the BTS ISAPI Filter</span></span>  
  
1. <span data-ttu-id="29cc2-177">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="29cc2-177">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="29cc2-178">オペレーティング システムによっては、管理ツールの [スタート] メニュー オプションを利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-178">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="29cc2-179">このような場合は、次のようにクリックします。**開始**、 をクリック**実行**、入力と`inetmgr`をインターネット インフォメーション サービス (IIS) マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-179">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  
  
2. <span data-ttu-id="29cc2-180">ルート Web サーバーのエントリを選択し、**機能ビュー**をダブルクリックします**ハンドラー マッピング**しをクリックして、[操作] ウィンドウで、**スクリプト マップの追加**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-180">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the Actions pane click **Add Script Map**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-181">Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子の Web サイトに適用するには、このマッピングが発生します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-181">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="29cc2-182">特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-182">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  
  
3. <span data-ttu-id="29cc2-183">**スクリプト マップの追加** ダイアログ ボックスに、入力`BtsHttpReceive.dll`で、**要求パス**フィールド。</span><span class="sxs-lookup"><span data-stu-id="29cc2-183">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4. <span data-ttu-id="29cc2-184">**実行可能ファイル**フィールドに、をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-184">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="29cc2-185">BtsHttpReceive.dll を選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-185">Select BtsHttpReceive.dll and click **OK**.</span></span>  
  
5. <span data-ttu-id="29cc2-186">入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-186">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6. <span data-ttu-id="29cc2-187">**要求の制限**ダイアログ ボックスで、**動詞**タブを選び**次の動詞のいずれか**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-187">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="29cc2-188">入力`POST`動詞として。</span><span class="sxs-lookup"><span data-stu-id="29cc2-188">Enter `POST` as the verb.</span></span>  
  
7. <span data-ttu-id="29cc2-189">**アクセス**] タブで [**スクリプト**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-189">On the **Access** tab, select **Script** and then click **OK**.</span></span>  
  
8. <span data-ttu-id="29cc2-190">をクリックして **[ok]** ISAPI 拡張を許可するメッセージが表示されたら、クリックと**はい**。</span><span class="sxs-lookup"><span data-stu-id="29cc2-190">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
##### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="29cc2-191">Fabrikam Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-191">To configure the Fabrikam Web page</span></span>  
  
1. <span data-ttu-id="29cc2-192">IIS マネージャーで、右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-192">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2. <span data-ttu-id="29cc2-193">**アプリケーション プールの追加** ダイアログ ボックスに、入力**BizTalkAppPool**で**名前**、し、 **.NET Framework v4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="29cc2-193">In **the Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="29cc2-194">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-194">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-195">コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-195">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3. <span data-ttu-id="29cc2-196">選択**アプリケーション プール**の**機能ビュー**選択**BizTalkAppPool**、順にクリックします**詳細設定**で**アクション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="29cc2-196">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4. <span data-ttu-id="29cc2-197">**詳細設定**ダイアログ ボックスで、 **Identity**し、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-197">In the **Advanced Settings** dialog box, select **Identity** and then click the ellipsis (…) button.</span></span>  
  
5. <span data-ttu-id="29cc2-198">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-198">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
6. <span data-ttu-id="29cc2-199">入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力します**パスワードの確認入力**をクリックして **。OK** 3 回の IIS マネージャーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-199">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
7. <span data-ttu-id="29cc2-200">IIS マネージャーで、開く、**サイト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="29cc2-200">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="29cc2-201">右クリックし、**既定の Web サイト**ノードをクリックして**アプリケーションの追加**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-201">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  
  
8. <span data-ttu-id="29cc2-202">**アプリケーションの追加** ダイアログ ボックスに、入力**Fabrikam**で**エイリアス**、順にクリックします**選択**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-202">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
9. <span data-ttu-id="29cc2-203">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-203">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
10. <span data-ttu-id="29cc2-204">省略記号 (...) ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-204">Click the ellipsis (…) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
11. <span data-ttu-id="29cc2-205">をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="29cc2-205">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="29cc2-206">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-206">Click **Close**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="29cc2-207">IIS マネージャーでは、Fabrikam 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-207">In IIS Manager, select the Fabrikam virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
13. <span data-ttu-id="29cc2-208">**認証**] ページで、[**匿名認証**いることを確認し、**状態**は**有効**。</span><span class="sxs-lookup"><span data-stu-id="29cc2-208">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="29cc2-209">場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="29cc2-209">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="29cc2-210">仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-210">To specify that your virtual directory is not managed by Windows SharePoint Services</span></span>  
  
1.  <span data-ttu-id="29cc2-211">コンピューターに Windows SharePoint Services がインストールされて場合、 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**をクリックして**SharePoint 3.0 サーバーの全体管理**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-211">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29cc2-212">この手順は、チュートリアルを設定するコンピューター上に Windows SharePoint Server がインストールされている場合に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-212">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="29cc2-213">実行する場合は、IIS 仮想ディレクトリが Windows SharePoint Server の管理対象から除外されるように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-213">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  
  
2.  <span data-ttu-id="29cc2-214">**サーバーの全体管理** ページ **サーバーの全体管理**、 をクリックして**アプリケーション管理**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-214">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  
  
3.  <span data-ttu-id="29cc2-215">**アプリケーション管理**] ページで [**管理パスの定義**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-215">On the **Application Management** page, click **Define managed paths**.</span></span>  
  
4.  <span data-ttu-id="29cc2-216">**管理パスの定義**] ページ [**新しいパスを追加**の**パス**テキスト ボックスに、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-216">In the **Define Managed Paths** page, under **Add a New Path**, in the **Path** text box, enter `Fabrikam`.</span></span> <span data-ttu-id="29cc2-217">[**型**、] をクリックして**エクスクルード パス**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-217">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a><span data-ttu-id="29cc2-218">EDI テスト メッセージを受信する受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-218">To create a receive port to receive the EDI test message</span></span>  
  
1. <span data-ttu-id="29cc2-219">Windows エクスプローラーを使用して、Contoso から EDI インターチェンジを受信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-219">In Windows Explorer, create a local folder to receive the EDI interchange from Contoso.</span></span>  
  
2. <span data-ttu-id="29cc2-220">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**順にクリックします**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-220">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3. <span data-ttu-id="29cc2-221">受信ポートに名前を付けます**RecvISAFromCont**、 をクリックし、**受信場所**コンソール ツリーで。</span><span class="sxs-lookup"><span data-stu-id="29cc2-221">Name the receive port as **RecvISAFromCont**, and then click **Receive Locations** in the console tree.</span></span>  
  
4. <span data-ttu-id="29cc2-222">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-222">Click **New**.</span></span>  
  
5. <span data-ttu-id="29cc2-223">[受信場所の名前**ファイル**の**型**、] をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="29cc2-223">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6. <span data-ttu-id="29cc2-224">**受信フォルダー**、手順 1. で作成したフォルダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-224">For **Receive folder**, enter the name of the folder that you created in step 1.</span></span>  
  
7. <span data-ttu-id="29cc2-225">**ファイル マスク**ファイルの拡張子を入力します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-225">For **File mask**, enter the extension of your file.</span></span> <span data-ttu-id="29cc2-226">テスト メッセージとして SamplePO.txt ファイルを使用する場合は、入力 **\*.txt**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-226">If you are using the SamplePO.txt file as your test message, enter **\*.txt**.</span></span> <span data-ttu-id="29cc2-227">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-227">Click **OK**.</span></span>  
  
8. <span data-ttu-id="29cc2-228">**受信パイプライン**、既定値はそのまま使用**PassThruReceive**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-228">For **Receive pipeline**, accept the default of **PassThruReceive**.</span></span>  
  
9. <span data-ttu-id="29cc2-229">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="29cc2-229">Click **OK**, and then click **OK** again.</span></span>  
  
10. <span data-ttu-id="29cc2-230">をクリックして、**受信場所**ノードを右クリックし、受信場所をクリックして**を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="29cc2-230">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-two-way-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam-and-receive-an-mdn-response"></a><span data-ttu-id="29cc2-231">EDI インターチェンジを AS2 経由で Fabrikam に送信し、MDN 応答を受信する双方向の送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-231">To create a two-way send port to send the EDI interchange over AS2 to Fabrikam and receive an MDN response</span></span>  
  
1. > [!NOTE]
   >  <span data-ttu-id="29cc2-232">静的な双方向送信ポートは EDI インターチェンジを取得し、それを AS2 フォーマットにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-232">A static two-way send port picks up the EDI interchange and encodes it into AS2 format.</span></span> <span data-ttu-id="29cc2-233">次に、双方向送信ポートは、それを AS2 トランスポート経由で Fabrikam パーティに送信します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-233">It then sends the AS2-encoded EDI interchange over AS2 transport to the Fabrikam party.</span></span> <span data-ttu-id="29cc2-234">後で、双方向送信ポートに関連付けられている受信ポートは、Fabrikam から MDN を受信し、それを MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-234">Later, the receive port associated with the two-way send port receives the MDN from Fabrikam, and drops it in the MessageBox.</span></span>  
  
    <span data-ttu-id="29cc2-235">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-235">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
2. <span data-ttu-id="29cc2-236">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="29cc2-236">In the **Send Port Properties** dialog box, name the send port.</span></span> <span data-ttu-id="29cc2-237">このソリューションでは、名前、送信ポートに**SendISAToFab_RecMDN**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-237">For this solution, name the send port as **SendISAToFab_RecMDN**.</span></span>  
  
3. <span data-ttu-id="29cc2-238">**トランスポート**セクションで、 **HTTP**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-238">In the **Transport** section, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="29cc2-239">**HTTP トランスポートのプロパティ** ダイアログ ボックスの**送信先 URL**、入力 **http://localhost/Fabrikam/BTSHttpReceive.dll**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-239">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter **http://localhost/Fabrikam/BTSHttpReceive.dll**.</span></span>  
  
5. <span data-ttu-id="29cc2-240">クリア**チャンク エンコードを有効にする**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="29cc2-240">Clear **Enable Chunked Encoding**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="29cc2-241">**送信パイプライン**、 **AS2Send**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-241">In **Send pipeline**, select **AS2Send**.</span></span>  
  
7. <span data-ttu-id="29cc2-242">**受信パイプライン**、 **AS2Receive**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-242">In **Receive pipeline**, select **AS2Receive**.</span></span>  
  
8. <span data-ttu-id="29cc2-243">コンソール ツリーで、選択**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-243">In the console tree, select **Filters**.</span></span> <span data-ttu-id="29cc2-244">**プロパティ**、入力**BTS します。ReceivePortName**; の**演算子**、入力**==**; と**値**EDI を受信する受信ポートの名前を入力します。インターチェンジ (`RecvISAFromCont`)。</span><span class="sxs-lookup"><span data-stu-id="29cc2-244">For **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; and for **Value** enter the name of the receive port that will receive the EDI interchange (`RecvISAFromCont`).</span></span>  
  
9. <span data-ttu-id="29cc2-245">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-245">Click **OK**.</span></span>  
  
10. <span data-ttu-id="29cc2-246">をクリックして、**送信ポート**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、送信ポートを右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-246">Click the **Send Ports** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-two-way-receive-port-to-receive-the-as2-message-and-return-an-mdn"></a><span data-ttu-id="29cc2-247">AS2 メッセージを受信して MDN を返す双方向受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-247">To create a two-way receive port to receive the AS2 message and return an MDN</span></span>  
  
1. > [!NOTE]
   >  <span data-ttu-id="29cc2-248">Fabrikam の双方向受信ポートは、Fabrikam の仮想ディレクトリを使用して AS2 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-248">The two-way receive port at Fabrikam receives the AS2 message using the Fabrikam virtual directory.</span></span> <span data-ttu-id="29cc2-249">受信パイプラインは、AS2 からの EDI インターチェンジをデコードし、EDI インターチェンジをメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-249">The receive pipeline decodes the EDI interchange from AS2, and drops the EDI interchange into the MessageBox.</span></span> <span data-ttu-id="29cc2-250">双方向受信ポートに関連付けられている送信ポートは、同期 MDN を返します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-250">The send port associated with the two-way receive port returns a synchronous MDN.</span></span>  
  
    <span data-ttu-id="29cc2-251">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[、 **BizTalk アプリケーション 1**ノードを右クリックして**受信ポート**、] をポイント**新規**をクリックして**要求応答の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-251">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, under the **BizTalk Application 1** node, right-click **Receive Ports**, point to **New**, and then click **Request Response Receive Port**.</span></span>  
  
2. <span data-ttu-id="29cc2-252">受信ポートに名前を付けます**RecvAS2ForFab**、 をクリックし、**受信場所**コンソール ツリーで。</span><span class="sxs-lookup"><span data-stu-id="29cc2-252">Name the receive port as **RecvAS2ForFab**, and then click **Receive Locations** in the console tree.</span></span>  
  
3. <span data-ttu-id="29cc2-253">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-253">Click **New**.</span></span>  
  
4. <span data-ttu-id="29cc2-254">**受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所の選択、 **HTTP**の**型**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-254">In the **Receive Location Properties** dialog box, name your receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="29cc2-255">**HTTP トランスポートのプロパティ** ダイアログ ボックスに、入力 **/Fabrikam/BTSHttpReceive.dll**の**仮想ディレクトリと ISAPI 拡張**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-255">In the **HTTP Transport Properties** dialog box, enter **/Fabrikam/BTSHttpReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="29cc2-256">クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-256">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="29cc2-257">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-257">Click **OK**.</span></span>  
  
6. <span data-ttu-id="29cc2-258">選択**AS2Receive**の**受信パイプライン**、および**AS2Send**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-258">Select **AS2Receive** for the **Receive Pipeline**, and **AS2Send** for the **Send Pipeline**.</span></span> <span data-ttu-id="29cc2-259">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="29cc2-259">Click **OK**, and then click **OK** again.</span></span>  
  
7. <span data-ttu-id="29cc2-260">をクリックして、**受信場所**ノードを右クリックし、受信場所をクリックして**を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="29cc2-260">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a><span data-ttu-id="29cc2-261">EDI ペイロードをローカル フォルダーに送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-261">To create a send port to send the EDI payload to a local folder</span></span>  
  
1. <span data-ttu-id="29cc2-262">Windows エクスプローラーで、EDI インターチェンジを送信する先のローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-262">In Windows Explorer, create a local folder to send the EDI interchange to.</span></span>  
  
2. <span data-ttu-id="29cc2-263">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-263">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3. <span data-ttu-id="29cc2-264">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**SendEDIMsg**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-264">In the **Send Port Properties** dialog box, name your send port as **SendEDIMsg**.</span></span> <span data-ttu-id="29cc2-265">選択**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-265">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="29cc2-266">**FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**、EDI ペイロード用に作成したローカル フォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-266">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder that you created for the EDI payload.</span></span>  
  
5. <span data-ttu-id="29cc2-267">**ファイル名**ファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-267">For **File name**, enter the file name.</span></span> <span data-ttu-id="29cc2-268">テスト メッセージとして SamplePO.txt ファイルを使用する場合は、入力 **%MessageID%.txt**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-268">If you are using the SamplePO.txt file as your test message, enter **%MessageID%.txt**.</span></span> <span data-ttu-id="29cc2-269">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-269">Click **OK**.</span></span>  
  
6. <span data-ttu-id="29cc2-270">既定の**PassThruTransmit**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-270">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7. <span data-ttu-id="29cc2-271">をクリックして**フィルター**コンソールで、ツリーし、EDI ペイロードの集荷に対してフィルターのプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-271">Click **Filters** in the console tree, and add filter properties for picking up the EDI payload.</span></span> <span data-ttu-id="29cc2-272">最初の行での**プロパティ**、入力**BTS します。ReceivePortName**は**演算子**、入力 **==** は**値**AS2 を受信する受信ポートの名前を入力メッセージ (`RecvAS2ForFab`); と**でグループ化**、受け入れる**と**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-272">On the first line, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the AS2 message (`RecvAS2ForFab`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="29cc2-273">2 行目の**プロパティ**、入力**EdiIntAS.IsAS2PayloadMessage**は**演算子**、入力**==**; と**値**、入力**True**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-273">On the second line, for **Property**, enter **EdiIntAS.IsAS2PayloadMessage**; for **Operator**, enter **==**; and for **Value**, enter **True**.</span></span>  
  
8. <span data-ttu-id="29cc2-274">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-274">Click **OK**.</span></span>  
  
9. <span data-ttu-id="29cc2-275">をクリックして、**送信ポート**ノードは、送信ポートを右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-275">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a><span data-ttu-id="29cc2-276">MDN をローカル フォルダーに送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-276">To create a send port to send the MDN to a local folder</span></span>  
  
1. <span data-ttu-id="29cc2-277">Windows エクスプローラーを使用して、MDN を送信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-277">In Windows Explorer, create a local folder to send the MDN to.</span></span>  
  
2. <span data-ttu-id="29cc2-278">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-278">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3. <span data-ttu-id="29cc2-279">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**SendMDN**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-279">In the **Send Port Properties** dialog box, name your send port as **SendMDN**.</span></span> <span data-ttu-id="29cc2-280">選択**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-280">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="29cc2-281">**FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**MDN を送信するために作成したローカル フォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-281">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder you created to send the MDN to.</span></span>  
  
5. <span data-ttu-id="29cc2-282">**ファイル名**、入力 **%MessageID%.msg**します。クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-282">For **File name**, enter **%MessageID%.msg**. Click **OK**.</span></span>  
  
6. <span data-ttu-id="29cc2-283">既定の**PassThruTransmit**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-283">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7. <span data-ttu-id="29cc2-284">クリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-284">Click **Filters** in the console tree.</span></span> <span data-ttu-id="29cc2-285">**プロパティ**、入力**BTS します。SPName**は**演算子**、入力 **==** は**値**、AS2 メッセージを送信する送信ポートの名前を入力します (`SendISAToFab_RecMDN`);および**でグループ化**、受け入れる**と**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-285">For **Property**, enter **BTS.SPName**; for **Operator**, enter **==**; for **Value**, enter the name of the send port that sends the AS2 message (`SendISAToFab_RecMDN`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="29cc2-286">2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2MdnResponseMessage**は**演算子**、入力 **==** は**値**、入力**True**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-286">On a second line, for **Property**, enter **EdiIntAS.IsAS2MdnResponseMessage**; for **Operator**, enter **==**; for **Value**, enter **True**.</span></span>  
  
8. <span data-ttu-id="29cc2-287">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-287">Click **OK**.</span></span>  
  
9. <span data-ttu-id="29cc2-288">をクリックして、**送信ポート**ノードは、送信ポートを右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-288">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="29cc2-289">Fabrikam のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-289">To create a party and a business profile for Fabrikam</span></span>  
  
1. <span data-ttu-id="29cc2-290">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-290">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="29cc2-291">パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-291">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-292">選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29cc2-292">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="29cc2-293">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-293">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="29cc2-294">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="29cc2-294">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3. <span data-ttu-id="29cc2-295">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-295">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4. <span data-ttu-id="29cc2-296">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力 **[fabrikam_profile]** で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="29cc2-296">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-297">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-297">When you create a party, a profile is also created.</span></span> <span data-ttu-id="29cc2-298">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-298">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="29cc2-299">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-299">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="29cc2-300">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-300">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="29cc2-301">Contoso のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-301">To create a party and a business profile for Contoso</span></span>  
  
1. <span data-ttu-id="29cc2-302">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-302">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="29cc2-303">パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-303">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-304">選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29cc2-304">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="29cc2-305">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-305">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="29cc2-306">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="29cc2-306">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3. <span data-ttu-id="29cc2-307">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-307">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4. <span data-ttu-id="29cc2-308">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="29cc2-308">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="29cc2-309">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-309">When you create a party, a profile is also created.</span></span> <span data-ttu-id="29cc2-310">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-310">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="29cc2-311">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-311">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="29cc2-312">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-312">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="29cc2-313">2 つのビジネス プロファイル間で AS2 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="29cc2-313">To create an AS2 agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="29cc2-314">右クリック**Contoso_Profile**、 をポイント**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-314">Right-click **Contoso_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="29cc2-315">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-315">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="29cc2-316">**プロトコル**ドロップダウン リストで、 **AS2**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-316">From the **Protocol** drop-down list, select **AS2**.</span></span>  
  
4.  <span data-ttu-id="29cc2-317">**2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Fabrikam**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-317">In the **Second Partner** section, from the **Name** drop-down list, select **Fabrikam**.</span></span>  
  
5.  <span data-ttu-id="29cc2-318">**2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **[fabrikam_profile]** します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-318">In the **Second Partner** section, from the **Profile** drop-down list, select **Fabrikam_Profile**.</span></span>  
  
     <span data-ttu-id="29cc2-319">2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは、一方向の AS2 アグリーメントの構成用です。</span><span class="sxs-lookup"><span data-stu-id="29cc2-319">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  
  
6.  <span data-ttu-id="29cc2-320">次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。</span><span class="sxs-lookup"><span data-stu-id="29cc2-320">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="29cc2-321">**識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-321">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="29cc2-322">**AS2-から**、入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-322">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="29cc2-323">**AS2-To**、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-323">For **AS2- To**, enter `Fabrikam`.</span></span>  
  
    2.  <span data-ttu-id="29cc2-324">**受信確認 (Mdn)** ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="29cc2-324">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  
  
        1.  <span data-ttu-id="29cc2-325">選択、 **MessageBox にルーティング/配信の受信 MDN を処理する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-325">Select the **Process inbound MDN into MessageBox for routing/delivery options** check box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="29cc2-326">チェック、 **MessageBox にルーティング/配信の受信 MDN を処理する**のみが返された MDN の削除を MessageBox にために、このチュートリアルをテストするため必要です。</span><span class="sxs-lookup"><span data-stu-id="29cc2-326">Checking the **Process inbound MDN into MessageBox for routing/delivery options** is required for the testing of this walkthrough, because only then will the returned MDN be dropped into the MessageBox.</span></span> <span data-ttu-id="29cc2-327">これにより、MDN をサブスクライブする送信ポートを作成し、MDN をローカル ディレクトリに送信して、AS2 トランスミッションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-327">That enables you to create a send port to subscribe to the MDN, and to send the MDN to a local directory, so you can verify the AS2 transmission.</span></span>  
  
        2.  <span data-ttu-id="29cc2-328">選択、 **mdn を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-328">Select the **Request MDN** check box.</span></span>  
  
        3.  <span data-ttu-id="29cc2-329">必ず、**署名付き MDN を要求**チェック ボックスをオフします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-329">Make sure the **Request Signed MDN** check box is cleared.</span></span>  
  
        4.  <span data-ttu-id="29cc2-330">まま**非同期 MDN を要求する**オフにします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-330">Leave **Request asynchronous MDN** cleared.</span></span>  
  
        5.  <span data-ttu-id="29cc2-331">**ディス ポジション-通知-に**、任意の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-331">In **Disposition-Notification-To**, enter any value.</span></span> <span data-ttu-id="29cc2-332">このフィールドの値は AS2 処理中には使用されませんが、このフィールドに値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-332">The value of this field is not used during AS2 processing, but a value must be entered in the field.</span></span>  
  
    3.  <span data-ttu-id="29cc2-333">**送信ポート** ページで、EDI インターチェンジを Fabrikam に送信する双方向送信ポートを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="29cc2-333">On the **Send Ports** page, associate the two-way send port that will be sending the EDI interchange to Fabrikam.</span></span> <span data-ttu-id="29cc2-334">**送信ポート**グリッドで、**名前**列で空のセルしボックスの一覧から、送信ポートを選択します。 **SendISAToFab_RecMDN**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-334">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port **SendISAToFab_RecMDN**.</span></span>  
  
7.  <span data-ttu-id="29cc2-335">次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。</span><span class="sxs-lookup"><span data-stu-id="29cc2-335">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="29cc2-336">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-336">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="29cc2-337">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります **[as2_from]** と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-337">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2_From** and **AS2-To**.</span></span>  
  
    1.  <span data-ttu-id="29cc2-338">**識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-338">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="29cc2-339">**AS2-から**、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-339">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="29cc2-340">**AS2-To**、入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-340">For **AS2- To**, enter `Contoso`.</span></span>  
  
8.  <span data-ttu-id="29cc2-341">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-341">Click **Apply**.</span></span>  
  
9. <span data-ttu-id="29cc2-342">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29cc2-342">Click **OK**.</span></span> <span data-ttu-id="29cc2-343">新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="29cc2-343">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="29cc2-344">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="29cc2-344">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="29cc2-345">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="29cc2-345">Testing the Walkthrough</span></span>  
 <span data-ttu-id="29cc2-346">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-346">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-solution"></a><span data-ttu-id="29cc2-347">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="29cc2-347">To test the solution</span></span>  
  
1. <span data-ttu-id="29cc2-348">Windows エクスプローラーで [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial に移動します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-348">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial.</span></span> <span data-ttu-id="29cc2-349">コピー、 **SamplePO.txt**ファイル。</span><span class="sxs-lookup"><span data-stu-id="29cc2-349">Copy the **SamplePO.txt** file.</span></span>  
  
2. <span data-ttu-id="29cc2-350">貼り付け、 **SamplePO.txt** Contoso からテスト メッセージを受信するために作成したローカル フォルダーにファイル。</span><span class="sxs-lookup"><span data-stu-id="29cc2-350">Paste the **SamplePO.txt** file into the local folder that you created to receive the test message from Contoso.</span></span>  
  
3. <span data-ttu-id="29cc2-351">EDI ペイロードを送信するために作成したローカル フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-351">Move to the local folder that you created to send the EDI payload to.</span></span> <span data-ttu-id="29cc2-352">フォルダーに EDI ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-352">Confirm that the folder contains an EDI file.</span></span> <span data-ttu-id="29cc2-353">ファイルおよび元のテスト メッセージを開き、コンテンツが同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-353">Open the file and the original test message, and verify that they have the same content.</span></span>  
  
4. <span data-ttu-id="29cc2-354">結果の MDN を送信するために作成したローカル フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-354">Move to the local folder that you created to send the resulting MDN to.</span></span> <span data-ttu-id="29cc2-355">フォルダーにファイルが含まれていることを確認し、ファイルを開いてこれが MDN ファイルであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29cc2-355">Confirm that the folder contains a file; open the file and confirm that it is an MDN file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29cc2-356">参照</span><span class="sxs-lookup"><span data-stu-id="29cc2-356">See Also</span></span>  
 [<span data-ttu-id="29cc2-357">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="29cc2-357">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)
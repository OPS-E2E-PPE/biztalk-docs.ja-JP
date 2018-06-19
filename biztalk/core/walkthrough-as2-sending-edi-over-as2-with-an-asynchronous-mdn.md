---
title: 'チュートリアル (AS2): 非同期 MDN による AS2 経由で EDI の送信 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83644ac9-7023-4b09-966c-7c41d36f6b11
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e80d5429f109167a91297f69963f0fc46d6e7948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22292410"
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn"></a><span data-ttu-id="33a62-102">チュートリアル (AS2): 非同期 MDN による AS2 経由での EDI の送信</span><span class="sxs-lookup"><span data-stu-id="33a62-102">Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN</span></span>
<span data-ttu-id="33a62-103">このチュートリアルでは、非同期 MDN による AS2 経由での EDI メッセージの送信用のソリューションを作成する一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="33a62-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending EDI messages over AS2, with an asynchronous MDN.</span></span>  <span data-ttu-id="33a62-104">このチュートリアルでは、完全なソリューションを単一のコンピューター上で作成およびテストできます。</span><span class="sxs-lookup"><span data-stu-id="33a62-104">You can create and test the full solution in this walkthrough on a single computer</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="33a62-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="33a62-105">Prerequisites</span></span>  
 <span data-ttu-id="33a62-106">このトピックの手順を実行するための前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="33a62-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="33a62-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a62-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
-   <span data-ttu-id="33a62-108">チュートリアルを実行するコンピューターには、インターネット インフォメーション サービス (IIS) 7 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a62-108">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  
  
-   <span data-ttu-id="33a62-109">チュートリアルを実行するコンピューターに 64 ビット版の Windows がインストールされている場合は、BizTalk ホストが 32 ビットのみとマークされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a62-109">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="33a62-110">IIS の [アプリケーション プールの 32 ビット アプリケーション設定を有効にする] を True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a62-110">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to True.</span></span> <span data-ttu-id="33a62-111">詳細については、次を参照してください。[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)です。</span><span class="sxs-lookup"><span data-stu-id="33a62-111">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-an-asynchronous-mdn"></a><span data-ttu-id="33a62-112">ソリューションで EDI/AS2 メッセージを送信して非同期 MDN を返す方法</span><span class="sxs-lookup"><span data-stu-id="33a62-112">How the Solution Sends an EDI/AS2 Message and Returns an Asynchronous MDN</span></span>  
 <span data-ttu-id="33a62-113">このソリューションは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="33a62-113">The solution will do the following:</span></span>  
  
1.  <span data-ttu-id="33a62-114">一方向の FILE 受信ポートは、Contoso から EDI インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="33a62-114">A one-way FILE receive port receives an EDI interchange from Contoso.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-115">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="33a62-115">The events in this list may not occur in the order shown.</span></span>  
  
2.  <span data-ttu-id="33a62-116">受信ポートは、パススルー受信パイプラインを使用して、テスト メッセージをそのままメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="33a62-116">Using a passthrough receive pipeline, the receive port drops the test message into the MeassageBox unchanged.</span></span>  
  
3.  <span data-ttu-id="33a62-117">静的な一方向の送信ポートは EDI インターチェンジを取得し、それを AS2 フォーマットにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="33a62-117">A static one-way send port picks up the EDI interchange and encodes it into AS2 format.</span></span>  
  
4.  <span data-ttu-id="33a62-118">送信ポートは、EDI インターチェンジを AS2 トランスポート経由で Fabrikam パーティに送信します。</span><span class="sxs-lookup"><span data-stu-id="33a62-118">The send port sends the EDI interchange over AS2 transport to the Fabrikam party.</span></span>  
  
5.  <span data-ttu-id="33a62-119">Fabrikam の一方向の受信ポートは、Fabrikam のバーチャル ディレクトリを使用して AS2 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="33a62-119">The one-way receive port at Fabrikam receives the AS2 message using the Fabrikam virtual directory.</span></span> <span data-ttu-id="33a62-120">受信パイプラインは、AS2 からの EDI インターチェンジをデコードし、EDI インターチェンジをメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="33a62-120">The receive pipeline decodes the EDI interchange from AS2, and drops the EDI interchange into the MessageBox.</span></span>  
  
6.  <span data-ttu-id="33a62-121">また、同じ一方向の受信ポートも、MDN を生成してメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="33a62-121">The same one-way receive port also generates an MDN and drops the MDN into the MessageBox.</span></span>  
  
7.  <span data-ttu-id="33a62-122">静的な一方向の送信ポートは、EDI メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="33a62-122">A static one-way send port pick up the EDI message.</span></span>  
  
8.  <span data-ttu-id="33a62-123">静的な一方向の送信ポートは、EDI メッセージをローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="33a62-123">The static one-way send port sends the EDI message to a local folder.</span></span>  
  
9. <span data-ttu-id="33a62-124">動的な一方向の送信ポートは、非同期 MDN を取得します。</span><span class="sxs-lookup"><span data-stu-id="33a62-124">A one-way dynamic send port picks up the asynchronous MDN.</span></span>  
  
10. <span data-ttu-id="33a62-125">動的な一方向の送信ポートは、MDN を Contoso に送信します。</span><span class="sxs-lookup"><span data-stu-id="33a62-125">The one-way dynamic send port sends the MDN to Contoso.</span></span>  
  
11. <span data-ttu-id="33a62-126">一方向の受信ポートは、MDN を受信してメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="33a62-126">A one-way receive port receives the MDN, and drops it into the MessageBox.</span></span>  
  
12. <span data-ttu-id="33a62-127">パススルー送信パイプラインを持つ静的な一方向の送信ポートは、MDN を取得します。</span><span class="sxs-lookup"><span data-stu-id="33a62-127">A static one-way send port with a passthrough send pipeline picks up the MDN.</span></span>  
  
13. <span data-ttu-id="33a62-128">一方向の送信ポートは、MDN をローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="33a62-128">The one-way send port sends the MDN to a local folder.</span></span>  
  
 <span data-ttu-id="33a62-129">次の図では、このソリューションのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="33a62-129">The following figure shows the architecture for this solution.</span></span>  
  
 <span data-ttu-id="33a62-130">![非同期 MDN による AS2 の送信](../core/media/343bbfcc-5387-426c-8700-db9738816218.gif "343bbfcc-5387-426c-8700-db9738816218")</span><span class="sxs-lookup"><span data-stu-id="33a62-130">![AS2 sending with an asynchronous MDN](../core/media/343bbfcc-5387-426c-8700-db9738816218.gif "343bbfcc-5387-426c-8700-db9738816218")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="33a62-131">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="33a62-131">The Functionality in this Solution</span></span>  
 <span data-ttu-id="33a62-132">このチュートリアルの機能には、以下の条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="33a62-132">The following applies to the functionality of this walkthrough:</span></span>  
  
-   <span data-ttu-id="33a62-133">このチュートリアルでは、EDI 機能ではなく AS2 機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="33a62-133">This walkthrough deals with AS2 functionality, not EDI functionality.</span></span> <span data-ttu-id="33a62-134">このため、AS2 処理に関連するすべてのポートでは、AS2EdiReceive または AS2EdiSend パイプラインでなく、AS2Receive または AS2Send パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="33a62-134">As a result, all ports involved in AS2 processing use either AS2Receive or AS2Send pipelines, not AS2EdiReceive or AS2EdiSend.</span></span> <span data-ttu-id="33a62-135">AS2 処理に関連しないポートでは、PassThruReceive または PassThruTransmit パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="33a62-135">Ports that are not involved in AS2 processing use PassThruReceive or PassThruTransmit pipelines.</span></span>  
  
-   <span data-ttu-id="33a62-136">状態レポートが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="33a62-136">Status reporting is not enabled.</span></span>  
  
-   <span data-ttu-id="33a62-137">このソリューションは、否認不可データベースに署名、圧縮、暗号化、およびメッセージ ストレージを構成しません。</span><span class="sxs-lookup"><span data-stu-id="33a62-137">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="33a62-138">これらのプロパティを構成する手順については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="33a62-138">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="33a62-139">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="33a62-139">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="33a62-140">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33a62-140">The procedures required for this solution include the following:</span></span>  
  
-   <span data-ttu-id="33a62-141">必要なメッセージ スキーマを使用して BizTalk プロジェクトをビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="33a62-141">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  
  
-   <span data-ttu-id="33a62-142">AS2 メッセージの受信に使用する BTS ISAPI フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="33a62-142">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  
  
-   <span data-ttu-id="33a62-143">Contoso からの AS2 メッセージを受信する Fabrikam 仮想ディレクトリを、受信場所で構成したとおりに作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-143">Create a Fabrikam virtual directory that receives the AS2 message from Contoso, as configured in the receive location.</span></span>  
  
-   <span data-ttu-id="33a62-144">Fabrikam からの AS2 メッセージを受信する Contoso 仮想ディレクトリを、受信場所で構成したとおりに作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-144">Create a Contoso virtual directory that receives the AS2 message from Fabrikam, as configured in the receive location.</span></span>  
  
-   <span data-ttu-id="33a62-145">Fabrikam および Contoso 仮想ディレクトリが、Windows SharePoint Services の管理対象から除外されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="33a62-145">Specify that the Fabrikam and Contoso virtual directories are not managed by Windows SharePoint Services.</span></span>  
  
-   <span data-ttu-id="33a62-146">AS2 トランスポート経由で送信される EDI テスト メッセージを受信する一方向 FILE 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-146">Create a one-way FILE receive port to receive the EDI test message that will be sent via AS2 transport.</span></span> <span data-ttu-id="33a62-147">テスト メッセージを受信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-147">Create the local folder to receive the test message.</span></span>  
  
-   <span data-ttu-id="33a62-148">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の静的な一方向 HTTP 送信ポートを作成し、EDI ビジネス ドキュメントを含んでいる AS2 メッセージを Fabrikam に送信します。</span><span class="sxs-lookup"><span data-stu-id="33a62-148">Create a static one-way HTTP send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the AS2 message containing the EDI business document to Fabrikam.</span></span> <span data-ttu-id="33a62-149">送信パイプラインとして AS2Send パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-149">Configure the send pipeline to be the AS2Send pipeline.</span></span>  
  
-   <span data-ttu-id="33a62-150">AS2 メッセージを受信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の一方向の HTTP 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-150">Create a one-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message.</span></span> <span data-ttu-id="33a62-151">受信パイプラインとして AS2Receive パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-151">Configure the receive pipeline to be the AS2Receive pipeline.</span></span> <span data-ttu-id="33a62-152">Fabrikam 仮想ディレクトリ経由で AS2 メッセージを受信する受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-152">Configure the receive location to receive the AS2 message via the Fabrikam virtual directory.</span></span>  
  
-   <span data-ttu-id="33a62-153">メッセージ ペイロードをローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-153">Create a static one-way FILE send port (with a passthrough send pipeline) to route the message payload to a local folder.</span></span> <span data-ttu-id="33a62-154">ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-154">Create the local folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-155">メッセージ ペイロードをサブスクライブする送信ポートがない場合、メッセージ ボックスで中断されます。</span><span class="sxs-lookup"><span data-stu-id="33a62-155">If you do not have a send port to subscribe to the message payload, it will be suspended in the MessageBox.</span></span>  
  
-   <span data-ttu-id="33a62-156">MDN を Contoso に返す動的な一方向の HTTP 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-156">Create a dynamic one-way HTTP send port to return the MDN to Contoso.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-157">テスト ソリューションが 1 台のコンピューターにはその結果、(Contoso) から AS2 メッセージを送信する一方向の送信ポートと (Fabrikam) から MDN 応答を送信する一方向の送信ポートは、同一コンピューター上です。</span><span class="sxs-lookup"><span data-stu-id="33a62-157">The test solution is on a single computer; as a result, the one-way send port sending the AS2 message (from Contoso) and the one-way send port sending the MDN response (from Fabrikam) are on the same computer.</span></span>  
  
-   <span data-ttu-id="33a62-158">Fabrikam から MDN 応答を受信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の一方向受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-158">Create a one-way receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the MDN response from Fabrikam.</span></span>  
  
-   <span data-ttu-id="33a62-159">MDN をローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-159">Create a static one-way FILE send port (with a passthrough send pipeline) to route the MDN to a local folder.</span></span> <span data-ttu-id="33a62-160">ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-160">Create the local folder.</span></span>  
  
-   <span data-ttu-id="33a62-161">Fabrikam および Contoso の両方にパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-161">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
-   <span data-ttu-id="33a62-162">両方の取引先に対して、それぞれビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-162">Create a business profile each for both the trading parties.</span></span>  
  
-   <span data-ttu-id="33a62-163">Fabrikam および Contoso のビジネス プロファイル間に AS2 アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-163">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="33a62-164">AS2 アグリーメントには、AS2 メッセージを送信し、その応答として非同期 MDN を受信するためのプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="33a62-164">The AS2 agreement would contain properties to send an AS2 message and receive an asynchronous MDN in return.</span></span>  
  
-   <span data-ttu-id="33a62-165">テスト EDI インターチェンジを使用して、このチュートリアルをテストします。</span><span class="sxs-lookup"><span data-stu-id="33a62-165">Test the walkthrough using a test EDI interchange.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-166">テスト メッセージには、EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="33a62-166">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="33a62-167">そのファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ folder に保存して出荷されています。</span><span class="sxs-lookup"><span data-stu-id="33a62-167">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ folder.</span></span> <span data-ttu-id="33a62-168">これは、X12 850 メッセージです。</span><span class="sxs-lookup"><span data-stu-id="33a62-168">This is an X12 850 message.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="33a62-169">チュートリアルの構成</span><span class="sxs-lookup"><span data-stu-id="33a62-169">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="33a62-170">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="33a62-170">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="33a62-171">メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="33a62-171">To deploy the message schema</span></span>  
  
1.  <span data-ttu-id="33a62-172">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。</span><span class="sxs-lookup"><span data-stu-id="33a62-172">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-173">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="33a62-173">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="33a62-174">いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。</span><span class="sxs-lookup"><span data-stu-id="33a62-174">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2.  <span data-ttu-id="33a62-175">プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="33a62-175">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="33a62-176">SamplePO.txt ファイルを使用してソリューションをテストするには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="33a62-176">To use the SamplePO.txt file to test your solution, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="33a62-177">X12_00401_850.xsd スキーマを選択し、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-177">Select the X12_00401_850.xsd schema, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-178">異なる EDI スキーマを使用するには、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="33a62-178">To use a different EDI schema, go to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI folder.</span></span> <span data-ttu-id="33a62-179">EDI スキーマは、XSD_SchemaEDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe**スキーマを既定のフォルダーに解凍する XSD_SchemaEDI フォルダー内のファイルです。</span><span class="sxs-lookup"><span data-stu-id="33a62-179">If the EDI schemas have not been unzipped into the XSD_SchemaEDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the XSD_SchemaEDI folder to unzip the schemas into the default folder.</span></span>  
  
3.  <span data-ttu-id="33a62-180">アセンブリ キー ファイルを設定し、アセンブリをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="33a62-180">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="33a62-181">BTS ISAPI フィルターを有効にするには</span><span class="sxs-lookup"><span data-stu-id="33a62-181">To enable the BTS ISAPI Filter</span></span>  
  
1.  <span data-ttu-id="33a62-182">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="33a62-182">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="33a62-183">オペレーティング システムによっては、管理ツールの [スタート] メニュー オプションを利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="33a62-183">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="33a62-184">このような場合、をクリックして**開始**、 をクリックして**実行**、入力と`inetmgr`インターネット インフォメーション サービス (IIS) マネージャを開きます。</span><span class="sxs-lookup"><span data-stu-id="33a62-184">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  
  
2.  <span data-ttu-id="33a62-185">ルート Web サーバーのエントリを選択し、、**機能ビュー**、ダブルクリックして**ハンドラー マッピング**し、操作 ウィンドウでをクリックして**スクリプト マップの追加**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-185">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the Actions pane click **Add Script Map**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-186">Web サーバー レベルでスクリプト マッピングを構成すると、すべての子 Web サイトに適用するには、このマッピングが発生します。</span><span class="sxs-lookup"><span data-stu-id="33a62-186">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="33a62-187">特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="33a62-187">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  
  
3.  <span data-ttu-id="33a62-188">**スクリプト マップの追加** ダイアログ ボックスで、入力`BtsHttpReceive.dll`で、**要求パス**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="33a62-188">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4.  <span data-ttu-id="33a62-189">**実行可能ファイル**フィールドで、をクリックして、**省略記号 (...)** ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive です。</span><span class="sxs-lookup"><span data-stu-id="33a62-189">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="33a62-190">BtsHttpReceive.dll を選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-190">Select BtsHttpReceive.dll and click **OK**.</span></span>  
  
5.  <span data-ttu-id="33a62-191">入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-191">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6.  <span data-ttu-id="33a62-192">**要求の制限**ダイアログ ボックスで、**動詞**タブをクリックし**次の動詞のいずれかの**します。</span><span class="sxs-lookup"><span data-stu-id="33a62-192">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="33a62-193">入力`POST`動詞として。</span><span class="sxs-lookup"><span data-stu-id="33a62-193">Enter `POST` as the verb.</span></span>  
  
7.  <span data-ttu-id="33a62-194">**アクセス** タブで **スクリプト** をクリックし、 **ok**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-194">On the **Access** tab, select **Script** and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="33a62-195">をクリックして**OK** ISAPI 拡張を許可するメッセージが表示されたらをクリックし、**はい**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-195">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
##### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="33a62-196">Fabrikam Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-196">To configure the Fabrikam Web page</span></span>  
  
1.  <span data-ttu-id="33a62-197">IIS マネージャーを右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-197">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2.  <span data-ttu-id="33a62-198">**アプリケーション プールの追加**] ダイアログ ボックスで、入力**BizTalkAppPool**で**名前**、し、[ **.NET Framework V4.0.30210**で、**.NET framework のバージョン**ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="33a62-198">In the **Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** dropdown list.</span></span> <span data-ttu-id="33a62-199">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-199">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-200">コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="33a62-200">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3.  <span data-ttu-id="33a62-201">選択**アプリケーション プール**の**機能ビュー**選択**BizTalkAppPool**、順にクリック**詳細設定**で**アクション**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="33a62-201">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4.  <span data-ttu-id="33a62-202">**詳細設定**ダイアログ ボックスで、 **Identity**省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-202">In the **Advanced Settings** dialog box, select **Identity** and then click the ellipsis (…) button.</span></span>  
  
5.  <span data-ttu-id="33a62-203">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-203">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
6.  <span data-ttu-id="33a62-204">入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力で**パスワードの確認入力**をクリックして**OK** IIS マネージャーに戻りますを 3 回です。</span><span class="sxs-lookup"><span data-stu-id="33a62-204">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
7.  <span data-ttu-id="33a62-205">IIS マネージャーで、開く、**サイト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="33a62-205">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="33a62-206">[既定の Web サイト] を右クリックし、[アプリケーションの追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-206">Right-click the Default Web Site and then select Add Application.</span></span>  
  
8.  <span data-ttu-id="33a62-207">**アプリケーションの追加** ダイアログ ボックスで、入力**Fabrikam**で**エイリアス**、順にクリック**選択**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-207">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
9. <span data-ttu-id="33a62-208">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-208">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
10. <span data-ttu-id="33a62-209">省略記号 (...) ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-209">Click the ellipsis (…) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
11. <span data-ttu-id="33a62-210">をクリックして**テストの設定**に表示されるエラーがないことを確認し、**接続のテスト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="33a62-210">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="33a62-211">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-211">Click **Close**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="33a62-212">IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、、**機能ビュー**をダブルクリックして**認証**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-212">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
13. <span data-ttu-id="33a62-213">**認証**を選択**匿名認証**ことを確認し、**ステータス**は**有効**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-213">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="33a62-214">場合、**ステータス**は**無効になっている**、 をクリックして**を有効にする**で、**アクション**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="33a62-214">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-configure-the-contoso-web-page"></a><span data-ttu-id="33a62-215">Contoso Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-215">To configure the Contoso Web page</span></span>  
  
1.  <span data-ttu-id="33a62-216">IIS マネージャーで、開く、**サイト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="33a62-216">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="33a62-217">[既定の Web サイト] を右クリックし、[アプリケーションの追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-217">Right-click the Default Web Site and then select Add Application.</span></span>  
  
2.  <span data-ttu-id="33a62-218">**アプリケーションの追加** ダイアログ ボックスで、入力**Contoso**で**エイリアス**、順にクリック**選択**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-218">In the **Add Application** dialog box, enter **Contoso** in **Alias**, and then click **Select**.</span></span>  
  
3.  <span data-ttu-id="33a62-219">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-219">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
4.  <span data-ttu-id="33a62-220">省略記号 (...) ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-220">Click the ellipsis (…) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
5.  <span data-ttu-id="33a62-221">をクリックして**テストの設定**に表示されるエラーがないことを確認し、**接続のテスト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="33a62-221">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="33a62-222">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-222">Click **Close**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="33a62-223">IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、、**機能ビュー**をダブルクリックして**認証**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-223">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
7.  <span data-ttu-id="33a62-224">**認証**を選択**匿名認証**ことを確認し、**ステータス**は**有効**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-224">In **Authentication**, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="33a62-225">場合、**ステータス**は**無効になっている**、 をクリックして**を有効にする**で、**アクション**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="33a62-225">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-specify-that-the-fabrikam-and-contoso-virtual-directories-are-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="33a62-226">Fabrikam および Contoso 仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定するには</span><span class="sxs-lookup"><span data-stu-id="33a62-226">To specify that the Fabrikam and Contoso virtual directories are not managed by Windows SharePoint Services</span></span>  
  
1.  <span data-ttu-id="33a62-227">Windows SharePoint Services がコンピューターにインストールされている場合にをクリックして**開始**、をポイント**すべてのプログラム**、指す**管理ツール**をクリックして**SharePoint 3.0 サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-227">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-228">この手順は、チュートリアルを設定するコンピューター上に Windows SharePoint Server がインストールされている場合に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a62-228">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="33a62-229">実行する場合は、IIS 仮想ディレクトリが Windows SharePoint Server の管理対象から除外されるように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33a62-229">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  
  
2.  <span data-ttu-id="33a62-230">**サーバーの全体管理**] ページの [**サーバーの全体管理**をクリックして**アプリケーション管理**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-230">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  
  
3.  <span data-ttu-id="33a62-231">**アプリケーション管理**] ページで [**管理パスの定義**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-231">On the **Application Management** page, click **Define managed paths**.</span></span>  
  
4.  <span data-ttu-id="33a62-232">**管理パスの定義**] ページの [**新しいパスを追加**で、**パス**テキスト ボックスに、入力`Fabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="33a62-232">In the **Define Managed Paths** page, under **Add a New Path**, in the **Path** text box, enter `Fabrikam`.</span></span> <span data-ttu-id="33a62-233">[**型**、] をクリックして**エクスクルード パス**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-233">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="33a62-234">Contoso 仮想ディレクトリに対して手順 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="33a62-234">Repeat step 4 for the Contoso virtual directory.</span></span>  
  
6.  <span data-ttu-id="33a62-235">閉じる、**管理パスの定義**ページ。</span><span class="sxs-lookup"><span data-stu-id="33a62-235">Close the **Define Managed Paths** page.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a><span data-ttu-id="33a62-236">EDI テスト メッセージを受信する受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-236">To create a receive port to receive the EDI test message</span></span>  
  
1.  <span data-ttu-id="33a62-237">Windows エクスプローラーを使用して、Contoso から EDI インターチェンジを受信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-237">In Windows Explorer, create a local folder to receive the EDI interchange from Contoso.</span></span>  
  
2.  <span data-ttu-id="33a62-238">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-238">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="33a62-239">受信ポートに名前を付けます**RecvISAFromCont**、順にクリック**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="33a62-239">Name the receive port as **RecvISAFromCont**, and then click **Receive Locations** in the console tree.</span></span>  
  
4.  <span data-ttu-id="33a62-240">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-240">Click **New**.</span></span>  
  
5.  <span data-ttu-id="33a62-241">名前、受信場所は、select**ファイル**の**型**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-241">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="33a62-242">**受信フォルダー**、手順 1. で作成したフォルダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="33a62-242">For **Receive folder**, enter the name of the folder that you created in step 1.</span></span>  
  
7.  <span data-ttu-id="33a62-243">[ファイル マスク] にファイルの拡張子を入力します。</span><span class="sxs-lookup"><span data-stu-id="33a62-243">For File mask, enter the extension of your file.</span></span> <span data-ttu-id="33a62-244">テスト メッセージとして SamplePO.txt ファイルを使用する場合は、入力 **\*.txt**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-244">If you are using the SamplePO.txt file as your test message, enter **\*.txt**.</span></span> <span data-ttu-id="33a62-245">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-245">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="33a62-246">**受信パイプライン**、既定の**PassThruReceive**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-246">For **Receive pipeline**, accept the default of **PassThruReceive**.</span></span>  
  
9. <span data-ttu-id="33a62-247">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="33a62-247">Click **OK**, and then click **OK** again.</span></span>  
  
10. <span data-ttu-id="33a62-248">をクリックして、**受信場所** ノードを右クリックし、受信場所、およびをクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-248">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam"></a><span data-ttu-id="33a62-249">AS2 経由で Fabrikam に EDI インターチェンジを送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-249">To create a send port to send the EDI interchange over AS2 to Fabrikam</span></span>  
  
1.  <span data-ttu-id="33a62-250">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-250">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="33a62-251">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前として**SendISAToFab**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-251">In the **Send Port Properties** dialog box, name the send port as **SendISAToFab**.</span></span>  
  
3.  <span data-ttu-id="33a62-252">**トランスポート**セクションで、 **HTTP**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-252">In the **Transport** section, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="33a62-253">**HTTP トランスポートのプロパティ** ダイアログ ボックスの**送信先 URL**、入力**http://localhost/Fabrikam/BTSHttpReceive.dll**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-253">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter **http://localhost/Fabrikam/BTSHttpReceive.dll**.</span></span>  
  
5.  <span data-ttu-id="33a62-254">クリア**チャンク エンコードを有効にする**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-254">Clear **Enable Chunked Encoding**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="33a62-255">**送信パイプライン** **AS2Send**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-255">In **Send pipeline**, select **AS2Send**.</span></span>  
  
7.  <span data-ttu-id="33a62-256">コンソール ツリーで、次のように選択します。**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-256">In the console tree, select **Filters**.</span></span> <span data-ttu-id="33a62-257">**プロパティ**、入力**BTS です。ReceivePortName**;**演算子**、入力 **==** ; および**値**EDI を受信する受信ポートの名前を入力インターチェンジ (`RecvISAFromCont`)。</span><span class="sxs-lookup"><span data-stu-id="33a62-257">For **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; and for **Value** enter the name of the receive port that will receive the EDI interchange (`RecvISAFromCont`).</span></span>  
  
8.  <span data-ttu-id="33a62-258">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-258">Click **OK**.</span></span>  
  
9. <span data-ttu-id="33a62-259">クリックして、**送信ポート**管理コンソールで、ノードは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-259">Click the **Send Ports** node in the Administration Console, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-receive-port-for-fabrikam-to-receive-the-as2-message"></a><span data-ttu-id="33a62-260">AS2 メッセージを受信する Fabrikam 用の受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-260">To create a receive port for Fabrikam to receive the AS2 message</span></span>  
  
1.  <span data-ttu-id="33a62-261">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックし**受信ポート**、指す**新規**、順にクリック**一方向の受信ポート**.</span><span class="sxs-lookup"><span data-stu-id="33a62-261">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, under the BizTalk Application 1 node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="33a62-262">受信ポートに名前を付けます**RecvAS2ForFabrikam**、順にクリック**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="33a62-262">Name the receive port as **RecvAS2ForFabrikam**, and then click **Receive Locations** in the console tree.</span></span>  
  
3.  <span data-ttu-id="33a62-263">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-263">Click **New**.</span></span>  
  
4.  <span data-ttu-id="33a62-264">**受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所で、選択**HTTP**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-264">In the **Receive Location Properties** dialog box, name your receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="33a62-265">**HTTP トランスポートのプロパティ** ダイアログ ボックスで、入力 **/Fabrikam/BTSHttpReceive.dll**の**仮想ディレクトリと ISAPI 拡張**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-265">In the **HTTP Transport Properties** dialog box, enter **/Fabrikam/BTSHttpReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="33a62-266">クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-266">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="33a62-267">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-267">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="33a62-268">選択**AS2Receive**の**受信パイプライン**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-268">Select **AS2Receive** for the **Receive Pipeline**.</span></span> <span data-ttu-id="33a62-269">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="33a62-269">Click **OK**, and then click **OK** again.</span></span>  
  
7.  <span data-ttu-id="33a62-270">をクリックして、**受信場所** ノードを右クリックし、受信場所、およびをクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-270">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a><span data-ttu-id="33a62-271">EDI ペイロードをローカル フォルダーに送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-271">To create a send port to send the EDI payload to a local folder</span></span>  
  
1.  <span data-ttu-id="33a62-272">Windows エクスプローラーで、EDI インターチェンジを送信する先のローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-272">In Windows Explorer, create a local folder to send the EDI interchange to.</span></span>  
  
2.  <span data-ttu-id="33a62-273">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-273">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3.  <span data-ttu-id="33a62-274">**送信ポートのプロパティ** ダイアログ ボックスで、送信ポート名**SendEDIToFab**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-274">In the **Send Port Properties** dialog box, name your send port as **SendEDIToFab**.</span></span> <span data-ttu-id="33a62-275">選択**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-275">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="33a62-276">**FILE トランスポートのプロパティ** ダイアログ ボックスの**コピー先フォルダー**、EDI ペイロード用に作成したローカル フォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="33a62-276">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder that you created for the EDI payload.</span></span>  
  
5.  <span data-ttu-id="33a62-277">**ファイル名**ファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="33a62-277">For **File name**, enter the file name.</span></span> <span data-ttu-id="33a62-278">テスト メッセージとして SamplePO.txt ファイルを使用する場合は、入力 **%MessageID%.txt**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-278">If you are using the SamplePO.txt file as your test message, enter **%MessageID%.txt**.</span></span> <span data-ttu-id="33a62-279">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-279">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="33a62-280">既定の**PassThruTransmit**の**送信パイプライン**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-280">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7.  <span data-ttu-id="33a62-281">をクリックして**フィルター**コンソールのツリー、および EDI ペイロードを取得するフィルターのプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="33a62-281">Click **Filters** in the console tree, and add filter properties for picking up the EDI payload.</span></span> <span data-ttu-id="33a62-282">最初の行での**プロパティ**、入力**BTS です。ReceivePortName**; の**演算子**、入力 **==** ;**値**AS2 を受信する受信ポートの名前を入力してくださいメッセージ (`RecvAS2ForFabrikam`); および**Group by**、受け入れる**と**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-282">On the first line, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the AS2 message (`RecvAS2ForFabrikam`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="33a62-283">2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2PayloadMessage**; の**演算子**、入力 **==** ; との**値**、入力**True**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-283">On the second line, for **Property**, enter **EdiIntAS.IsAS2PayloadMessage**; for **Operator**, enter **==**; and for **Value**, enter **True**.</span></span>  
  
8.  <span data-ttu-id="33a62-284">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-284">Click **OK**.</span></span>  
  
9. <span data-ttu-id="33a62-285">クリックして、**送信ポート**ノードは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-285">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-dynamic-one-way-send-port-to-return-the-mdn"></a><span data-ttu-id="33a62-286">MDN を返す動的な一方向の送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-286">To create a dynamic one-way send port to return the MDN</span></span>  
  
1.  <span data-ttu-id="33a62-287">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、をポイント**新規**、クリックして**動的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-287">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Dynamic One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="33a62-288">**送信ポートのプロパティ** ダイアログ ボックスで、送信ポート名**Send_MDN**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-288">In the **Send Port Properties** dialog box, name your send port as **Send_MDN**.</span></span>  
  
3.  <span data-ttu-id="33a62-289">**送信パイプライン**AS2Send を入力します。</span><span class="sxs-lookup"><span data-stu-id="33a62-289">For **Send Pipeline**, enter AS2Send.</span></span>  
  
4.  <span data-ttu-id="33a62-290">をクリックして**フィルター**コンソールのツリー、および EDI ペイロードを取得するフィルターのプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="33a62-290">Click **Filters** in the console tree, and add filter properties for picking up the EDI payload.</span></span> <span data-ttu-id="33a62-291">最初の行での**プロパティ**、入力**BTS です。ReceivePortName**; の**演算子**、入力 **==** ;**値**AS2 を受信する受信ポートの名前を入力してくださいメッセージ (`RecvAS2ForFabrikam`); および**Group by**、受け入れる**と**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-291">On the first line, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the AS2 message (`RecvAS2ForFabrikam`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="33a62-292">2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2AsynchronousMDN**; の**演算子**、入力 **==** ; との**値**、入力**True**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-292">On the second line, for **Property**, enter **EdiIntAS.IsAS2AsynchronousMDN**; for **Operator**, enter **==**; and for **Value**, enter **True**.</span></span>  
  
5.  <span data-ttu-id="33a62-293">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-293">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="33a62-294">クリックして、**送信ポート**ノードは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-294">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-mdn-from-fabrikam"></a><span data-ttu-id="33a62-295">Fabrikam から MDN を受信する受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-295">To create a receive port to receive the MDN from Fabrikam</span></span>  
  
1.  <span data-ttu-id="33a62-296">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックし**受信ポート**、指す**新規**、順にクリック**一方向の受信ポート**.</span><span class="sxs-lookup"><span data-stu-id="33a62-296">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, under the BizTalk Application 1 node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="33a62-297">受信ポートに名前を付けます**RecvMDNFromFab**、順にクリック**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="33a62-297">Name the receive port as **RecvMDNFromFab**, and then click **Receive Locations** in the console tree.</span></span>  
  
3.  <span data-ttu-id="33a62-298">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-298">Click **New**.</span></span>  
  
4.  <span data-ttu-id="33a62-299">**受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所で、選択**HTTP**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-299">In the **Receive Location Properties** dialog box, name your receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="33a62-300">**HTTP トランスポートのプロパティ** ダイアログ ボックスで、入力 **/Contoso/BTSHTTPReceive.dll**の**仮想ディレクトリと ISAPI 拡張**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-300">In the **HTTP Transport Properties** dialog box, enter **/Contoso/BTSHTTPReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="33a62-301">クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-301">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="33a62-302">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-302">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="33a62-303">選択**AS2Receive**の**受信パイプライン**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-303">Select **AS2Receive** for the **Receive Pipeline**.</span></span> <span data-ttu-id="33a62-304">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="33a62-304">Click **OK**, and then click **OK** again.</span></span>  
  
7.  <span data-ttu-id="33a62-305">をクリックして、**受信場所** ノードを右クリックし、受信場所、およびをクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-305">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a><span data-ttu-id="33a62-306">MDN をローカル フォルダーに送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-306">To create a send port to send the MDN to a local folder</span></span>  
  
1.  <span data-ttu-id="33a62-307">Windows エクスプローラーを使用して、MDN を送信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="33a62-307">In Windows Explorer, create a local folder to send the MDN to.</span></span>  
  
2.  <span data-ttu-id="33a62-308">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-308">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3.  <span data-ttu-id="33a62-309">**送信ポートのプロパティ** ダイアログ ボックスに、送信ポートの名前します。</span><span class="sxs-lookup"><span data-stu-id="33a62-309">In the **Send Port Properties** dialog box, name your send port.</span></span> <span data-ttu-id="33a62-310">選択**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-310">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="33a62-311">**FILE トランスポートのプロパティ** ダイアログ ボックスの**コピー先フォルダー**MDN を送信するために作成したローカル フォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="33a62-311">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder you created to send the MDN to.</span></span>  
  
5.  <span data-ttu-id="33a62-312">**ファイル名**、入力 **%MessageID%.msg**です。をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-312">For **File name**, enter **%MessageID%.msg**. Click **OK**.</span></span>  
  
6.  <span data-ttu-id="33a62-313">既定の**PassThruTransmit**の**送信パイプライン**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-313">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7.  <span data-ttu-id="33a62-314">をクリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="33a62-314">Click **Filters** in the console tree.</span></span> <span data-ttu-id="33a62-315">**プロパティ**、入力**BTS です。ReceivePortName**; の**演算子**、入力 **==** ;**値**、(MDNを受信する受信ポートの名前を入力してください`RecvMDNFromFab`);および**Group by**、受け入れる**と**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-315">For **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the MDN (`RecvMDNFromFab`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="33a62-316">2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2MdnResponseMessage**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-316">On a second line, for **Property**, enter **EdiIntAS.IsAS2MdnResponseMessage**.</span></span> <span data-ttu-id="33a62-317">**演算子**、入力 **==** です。</span><span class="sxs-lookup"><span data-stu-id="33a62-317">For **Operator**, enter **==**.</span></span> <span data-ttu-id="33a62-318">**値**、入力**True**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-318">For **Value**, enter **True**.</span></span>  
  
8.  <span data-ttu-id="33a62-319">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-319">Click **OK**.</span></span>  
  
9. <span data-ttu-id="33a62-320">クリックして、**送信ポート**ノードは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-320">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="33a62-321">Fabrikam のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-321">To create a party and a business profile for Fabrikam</span></span>  
  
1.  <span data-ttu-id="33a62-322">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-322">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="33a62-323">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-323">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-324">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33a62-324">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="33a62-325">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="33a62-325">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="33a62-326">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="33a62-326">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="33a62-327">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-327">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="33a62-328">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**fabrikam_profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="33a62-328">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-329">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="33a62-329">When you create a party, a profile is also created.</span></span> <span data-ttu-id="33a62-330">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="33a62-330">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="33a62-331">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-331">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="33a62-332">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="33a62-332">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="33a62-333">Contoso のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-333">To create a party and a business profile for Contoso</span></span>  
  
1.  <span data-ttu-id="33a62-334">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-334">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="33a62-335">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-335">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-336">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33a62-336">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="33a62-337">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="33a62-337">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="33a62-338">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="33a62-338">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="33a62-339">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-339">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="33a62-340">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="33a62-340">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-341">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="33a62-341">When you create a party, a profile is also created.</span></span> <span data-ttu-id="33a62-342">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="33a62-342">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="33a62-343">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-343">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="33a62-344">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="33a62-344">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="33a62-345">2 つのビジネス プロファイル間で AS2 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="33a62-345">To create an AS2 agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="33a62-346">右クリック**Contoso_Profile**、をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-346">Right-click **Contoso_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="33a62-347">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="33a62-347">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="33a62-348">**プロトコル**ドロップダウン リストで、 **AS2**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-348">From the **Protocol** drop-down list, select **AS2**.</span></span>  
  
4.  <span data-ttu-id="33a62-349">**2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、 **Fabrikam**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-349">In the **Second Partner** section, from the **Name** drop-down list, select **Fabrikam**.</span></span>  
  
5.  <span data-ttu-id="33a62-350">**2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **Fabrikam_Profile**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-350">In the **Second Partner** section, from the **Profile** drop-down list, select **Fabrikam_Profile**.</span></span>  
  
     <span data-ttu-id="33a62-351">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブは、一方向の AS2 アグリーメントの構成用です。</span><span class="sxs-lookup"><span data-stu-id="33a62-351">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  
  
6.  <span data-ttu-id="33a62-352">次のタスクを実行、 **Contoso が Fabrikam ->** タブです。</span><span class="sxs-lookup"><span data-stu-id="33a62-352">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="33a62-353">**識別子** ページで、値を入力**AS2-から**と**AS2-に**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-353">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="33a62-354">**AS2-から**、入力`Contoso`です。</span><span class="sxs-lookup"><span data-stu-id="33a62-354">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="33a62-355">**AS2-To**、入力`Fabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="33a62-355">For **AS2- To**, enter `Fabrikam`.</span></span>  
  
    2.  <span data-ttu-id="33a62-356">**受信確認 (Mdn)**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="33a62-356">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  
  
        1.  <span data-ttu-id="33a62-357">選択、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="33a62-357">Select the **Process inbound MDN into MessageBox for routing/delivery options** check box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="33a62-358">チェック、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**のみが返された MDN 削除されるため、メッセージ ボックスには、このチュートリアルのテストに必要です。</span><span class="sxs-lookup"><span data-stu-id="33a62-358">Checking the **Process inbound MDN into MessageBox for routing/delivery options** is required for the testing of this walkthrough, because only then will the returned MDN be dropped into the MessageBox.</span></span> <span data-ttu-id="33a62-359">これにより、MDN をサブスクライブする送信ポートを作成し、MDN をローカル ディレクトリに送信して、AS2 トランスミッションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="33a62-359">That enables you to create a send port to subscribe to the MDN, and to send the MDN to a local directory, so you can verify the AS2 transmission.</span></span>  
  
        2.  <span data-ttu-id="33a62-360">選択、 **mdn を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="33a62-360">Select the **Request MDN** check box.</span></span>  
  
        3.  <span data-ttu-id="33a62-361">確認してください、**署名付き mdn を要求してもする**チェック ボックスはオフです。</span><span class="sxs-lookup"><span data-stu-id="33a62-361">Make sure the **Request Signed MDN** check box is cleared.</span></span>  
  
        4.  <span data-ttu-id="33a62-362">選択、**非同期 MDN を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="33a62-362">Select the **Request asynchronous MDN** check box.</span></span>  
  
        5.  <span data-ttu-id="33a62-363">**- Receipt-delivery-option (URL)**、入力**http://localhost/Contoso/BTSHttpReceive.dll**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-363">In **Receipt-Delivery-Option (URL)**, enter **http://localhost/Contoso/BTSHttpReceive.dll**.</span></span>  
  
        6.  <span data-ttu-id="33a62-364">**廃棄する**は既定値に設定に指定した **- Receipt-delivery-option (URL)** プロパティです。</span><span class="sxs-lookup"><span data-stu-id="33a62-364">The **Disposition-Notification-To** is by default set to the value you specified for **Receipt-Delivery-Option (URL)** property.</span></span> <span data-ttu-id="33a62-365">このフィールドの値は、AS2 処理時には使用されません。</span><span class="sxs-lookup"><span data-stu-id="33a62-365">The value of this field is not used during AS2 processing.</span></span>  
  
    3.  <span data-ttu-id="33a62-366">**送信ポート** ページで、EDI インターチェンジを Fabrikam に送信する双方向の送信ポートを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="33a62-366">On the **Send Ports** page, associate the two-way send port that will be sending the EDI interchange to Fabrikam.</span></span> <span data-ttu-id="33a62-367">**送信ポート**グリッド 、**名前**列は、空のセルをクリックし、ドロップダウン リストから送信ポートを選択**SendISAToFab**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-367">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port **SendISAToFab**.</span></span>  
  
7.  <span data-ttu-id="33a62-368">次のタスクを実行、 **Fabrikam が Contoso ->** タブです。</span><span class="sxs-lookup"><span data-stu-id="33a62-368">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33a62-369">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="33a62-369">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="33a62-370">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります **[as2_from]** と**AS2-に**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-370">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2_From** and **AS2-To**.</span></span>  
  
    1.  <span data-ttu-id="33a62-371">**識別子** ページで、値を入力**AS2-から**と**AS2-に**です。</span><span class="sxs-lookup"><span data-stu-id="33a62-371">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="33a62-372">**AS2-から**、入力`Fabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="33a62-372">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="33a62-373">**AS2-To**、入力`Contoso`です。</span><span class="sxs-lookup"><span data-stu-id="33a62-373">For **AS2- To**, enter `Contoso`.</span></span>  
  
8.  <span data-ttu-id="33a62-374">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-374">Click **Apply**.</span></span>  
  
9. <span data-ttu-id="33a62-375">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33a62-375">Click **OK**.</span></span> <span data-ttu-id="33a62-376">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="33a62-376">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="33a62-377">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="33a62-377">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="33a62-378">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="33a62-378">Testing the Walkthrough</span></span>  
 <span data-ttu-id="33a62-379">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33a62-379">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-solution"></a><span data-ttu-id="33a62-380">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="33a62-380">To test the solution</span></span>  
  
1.  <span data-ttu-id="33a62-381">Windows エクスプローラーで [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial に移動します。</span><span class="sxs-lookup"><span data-stu-id="33a62-381">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial.</span></span> <span data-ttu-id="33a62-382">コピー、 **SamplePO.txt**ファイル。</span><span class="sxs-lookup"><span data-stu-id="33a62-382">Copy the **SamplePO.txt** file.</span></span>  
  
2.  <span data-ttu-id="33a62-383">貼り付け、 **SamplePO.txt** Contoso からテスト メッセージを受信するために作成するローカル フォルダーにファイル。</span><span class="sxs-lookup"><span data-stu-id="33a62-383">Paste the **SamplePO.txt** file into the local folder that you created to receive the test message from Contoso.</span></span>  
  
3.  <span data-ttu-id="33a62-384">EDI ペイロードを送信するために作成したローカル フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="33a62-384">Move to the local folder that you created to send the EDI payload to.</span></span> <span data-ttu-id="33a62-385">フォルダーに EDI ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33a62-385">Confirm that the folder contains an EDI file.</span></span> <span data-ttu-id="33a62-386">ファイルおよび元のテスト メッセージを開き、コンテンツが同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33a62-386">Open the file and the original test message, and verify that they have the same content.</span></span>  
  
4.  <span data-ttu-id="33a62-387">結果の MDN を送信するために作成したローカル フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="33a62-387">Move to the local folder that you created to send the resulting MDN to.</span></span> <span data-ttu-id="33a62-388">フォルダーにテスト ファイルが含まれていることを確認し、ファイルを開いて、これが MDN ファイルであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33a62-388">Confirm that the folder contains a test file; open the file, and confirm that it is an MDN file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a62-389">参照</span><span class="sxs-lookup"><span data-stu-id="33a62-389">See Also</span></span>  
 [<span data-ttu-id="33a62-390">開発と BizTalk Server AS2 ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="33a62-390">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)
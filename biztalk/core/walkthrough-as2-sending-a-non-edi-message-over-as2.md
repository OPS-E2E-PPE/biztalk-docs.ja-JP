---
title: チュートリアル (AS2):AS2 経由で非 EDI メッセージの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6120b81e-bdd5-44ad-9040-26be88c71258
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8b00f1b78ac994dbd9e5208996c0b46309aa1b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398563"
---
# <a name="walkthrough-as2-sending-a-non-edi-message-over-as2"></a><span data-ttu-id="a7f97-102">チュートリアル (AS2):AS2 経由で非 EDI メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-102">Walkthrough (AS2): Sending a Non-EDI Message over AS2</span></span>
<span data-ttu-id="a7f97-103">このチュートリアルでは、AS2 経由で非 EDI メッセージを送信するためのソリューションを作成する一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending non-EDI messages over AS2.</span></span> <span data-ttu-id="a7f97-104">このチュートリアルでは、PIDX メッセージを AS2 経由で送信します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-104">In this walkthrough, a PIDX message is sent over AS2.</span></span> <span data-ttu-id="a7f97-105">このソリューションでは、AS2Send 送信パイプラインと AS2Receive 受信パイプラインを持つ双方向の送信ポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-105">This solution uses a two-way send port with an AS2Send send pipeline and an AS2Receive receive pipeline.</span></span> <span data-ttu-id="a7f97-106">作成し、1 台のコンピューターには、このチュートリアルでは、完全なソリューションをテストできます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-106">You can create and test the full solution in this walkthrough on a single computer.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a7f97-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a7f97-107">Prerequisites</span></span>  
 <span data-ttu-id="a7f97-108">次に、このトピックの手順を実行するための前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-108">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="a7f97-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
- <span data-ttu-id="a7f97-110">チュートリアルを実行するコンピューターには、インターネット インフォメーション サービス (IIS) 7 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-110">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  
  
- <span data-ttu-id="a7f97-111">チュートリアルを実行するコンピューターに 64 ビット版の Windows がインストールされている場合は、BizTalk ホストが 32 ビットのみとマークされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-111">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="a7f97-112">IIS の [アプリケーション プールの 32 ビット アプリケーション設定を有効にする] を True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-112">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to True.</span></span> <span data-ttu-id="a7f97-113">詳細については、次を参照してください。[チュートリアル 3。AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-113">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
## <a name="how-the-solution-sends-a-non-edias2-message-and-returns-a-synchronous-mdn"></a><span data-ttu-id="a7f97-114">ソリューションが非 EDI/AS2 メッセージを送信して同期 MDN を返す方法</span><span class="sxs-lookup"><span data-stu-id="a7f97-114">How the Solution Sends a non-EDI/AS2 Message and Returns a Synchronous MDN</span></span>  
 <span data-ttu-id="a7f97-115">このソリューションは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-115">The solution will do the following:</span></span>  
  
1. <span data-ttu-id="a7f97-116">一方向のファイル受信ポートは、Contoso から XML メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-116">A one-way FILE receive port receives an XML message from Contoso.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-117">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a7f97-117">The events in this list may not occur in the order shown.</span></span>  
  
2. <span data-ttu-id="a7f97-118">受信ポートは、XML 受信パイプラインを使用してメッセージをチェックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-118">Using the XML receive pipeline, the receive port checks the message.</span></span> <span data-ttu-id="a7f97-119">次に、受信ポートは、テスト メッセージをそのままメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-119">The receive port then drops the test message as-is into the MessageBox.</span></span>  
  
3. <span data-ttu-id="a7f97-120">静的な双方向送信ポートは XML メッセージを取得し、受信ポートが受信するすべてのメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-120">A static two-way send port picks up the XML message, subscribing to all messages received by the receive port.</span></span>  
  
4. <span data-ttu-id="a7f97-121">Fabrikam の双方向受信ポートは、Fabrikam の仮想ディレクトリを使用して AS2 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-121">The two-way receive port at Fabrikam receives the AS2 message using the Fabrikam virtual directory.</span></span> <span data-ttu-id="a7f97-122">受信パイプラインは、AS2 のメッセージをデコードし、そのメッセージをメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-122">The receive pipeline decodes the message from AS2, and drops the message into the MessageBox.</span></span>  
  
5. <span data-ttu-id="a7f97-123">パススルー送信パイプラインを持つ静的な一方向の送信ポートは、XML メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-123">A static one-way send port with a passthrough send pipeline picks up the XML message.</span></span>  
  
6. <span data-ttu-id="a7f97-124">一方向の送信ポートは、XML メッセージをローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-124">The one-way send port sends the XML message to a local folder.</span></span>  
  
7. <span data-ttu-id="a7f97-125">双方向受信ポートに関連付けられている送信ポートは、同期 MDN を返します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-125">The send port associated with the two-way receive port returns a synchronous MDN.</span></span>  
  
8. <span data-ttu-id="a7f97-126">双方向送信ポートに関連付けられている受信ポートは、MDN を受信し、それをメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-126">The receive port associated with the two-way send port receives the MDN, and drops it in the MessageBox.</span></span>  
  
9. <span data-ttu-id="a7f97-127">パススルー送信パイプラインを持つ静的な一方向の送信ポートは、MDN を取得します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-127">A static one-way send port with a passthrough send pipeline picks up the MDN.</span></span>  
  
10. <span data-ttu-id="a7f97-128">一方向の送信ポートは、MDN をローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-128">The one-way send port sends the MDN to a local folder.</span></span>  
  
    <span data-ttu-id="a7f97-129">次の図は、ソリューションのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="a7f97-129">The following figure shows the architecture for the solution.</span></span>  
  
    <span data-ttu-id="a7f97-130">![非送信&#45;AS2 経由で EDI メッセージ](../core/media/57b7dc54-b8e8-462e-98d1-9cddedd14107.gif "57b7dc54-b8e8-462e-98d1-9cddedd14107")</span><span class="sxs-lookup"><span data-stu-id="a7f97-130">![Sending a non&#45;EDI message over AS2](../core/media/57b7dc54-b8e8-462e-98d1-9cddedd14107.gif "57b7dc54-b8e8-462e-98d1-9cddedd14107")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="a7f97-131">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="a7f97-131">The Functionality in this Solution</span></span>  
 <span data-ttu-id="a7f97-132">このチュートリアルの機能には、以下の条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-132">The following applies to the functionality of this walkthrough:</span></span>  
  
-   <span data-ttu-id="a7f97-133">このチュートリアルでは、AS2 機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-133">This walkthrough deals with AS2 functionality.</span></span> <span data-ttu-id="a7f97-134">このため、AS2 処理に関連するすべてのポートは、AS2Receive パイプラインまたは AS2Send パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-134">As a result, all ports involved in AS2 processing use either AS2Receive or AS2Send pipelines.</span></span> <span data-ttu-id="a7f97-135">AS2 処理に関連しないポートは、XMLReceive パイプラインまたは PassThruTransmit パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-135">Ports that are not involved in AS2 processing use either the XMLReceive or PassThruTransmit pipelines.</span></span>  
  
-   <span data-ttu-id="a7f97-136">このチュートリアルでは、XML テスト メッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-136">This walkthrough uses an XML test message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7f97-137">XML テスト メッセージおよびテスト メッセージ用のスキーマを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-137">You must provide an XML test message and a schema for the test message.</span></span>  
  
-   <span data-ttu-id="a7f97-138">状態レポートが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="a7f97-138">Status reporting is not enabled.</span></span>  
  
-   <span data-ttu-id="a7f97-139">このソリューションは、否認不可データベースに署名、圧縮、暗号化、およびメッセージ ストレージを構成しません。</span><span class="sxs-lookup"><span data-stu-id="a7f97-139">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="a7f97-140">これらのプロパティを構成する手順については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-140">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="a7f97-141">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="a7f97-141">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="a7f97-142">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a7f97-142">The procedures required for this solution include the following:</span></span>  
  
- <span data-ttu-id="a7f97-143">必要なメッセージ スキーマを使用して BizTalk プロジェクトをビルドおよび展開し、受信したメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-143">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received message.</span></span>  
  
- <span data-ttu-id="a7f97-144">AS2 メッセージの受信に使用する BTS ISAPI フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-144">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  
  
- <span data-ttu-id="a7f97-145">Contoso からの AS2 メッセージを受信する Fabrikam 仮想ディレクトリを、受信場所で構成したとおりに作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-145">Create a Fabrikam virtual directory that receives the AS2 message from Contoso, as configured in the receive location.</span></span>  
  
- <span data-ttu-id="a7f97-146">Fabrikam 仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-146">Specify that the Fabrikam virtual directory is not managed by Windows SharePoint Services.</span></span>  
  
- <span data-ttu-id="a7f97-147">AS2 トランスポート経由で送信される XML テスト メッセージを受信する、一方向 FILE 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-147">Create a one-way FILE receive port to receive the XML test message that will be sent via AS2 transport.</span></span> <span data-ttu-id="a7f97-148">テスト メッセージを受信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-148">Create the local folder to receive the test message.</span></span>  
  
- <span data-ttu-id="a7f97-149">静的な送信請求 - 応答 HTTP 送信ポートを作成し、送信パイプラインとして AS2Send パイプラインを、および受信パイプラインとして AS2Receive パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-149">Create a static solicit-response HTTP send port, configuring the send pipeline to be the AS2Send pipeline and the receive pipeline to be the AS2Receive pipeline.</span></span> <span data-ttu-id="a7f97-150">ポートは、AS2 メッセージを Fabrikam に送信し、MDN 応答を Fabrikam から受信してメッセージ ボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-150">The port sends the AS2 message to Fabrikam and receives the MDN response from Fabrikam and drops it to the Message box.</span></span>  
  
- <span data-ttu-id="a7f97-151">AS2 メッセージを受信し、MDN 応答を送信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の双方向 HTTP 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-151">Create a two-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message, and to send the MDN response.</span></span> <span data-ttu-id="a7f97-152">受信パイプラインとして AS2Receive パイプラインを構成し、送信パイプラインとして AS2Send パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-152">Configure the receive pipeline to be the AS2Receive pipeline and the send pipeline to be the AS2Send pipeline.</span></span> <span data-ttu-id="a7f97-153">Fabrikam 仮想ディレクトリ経由で AS2 メッセージを受信する受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-153">Configure the receive location to receive the AS2 message via the Fabrikam virtual directory.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="a7f97-154">テスト ソリューションは 1 台のコンピューター上にあります。よって、AS2 メッセージ (Contoso から) を送信する双方向送信ポート、および AS2 メッセージ (Fabrikam から) を受信する双方向受信ポートは、同一コンピューター上にあります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-154">The test solution is on a single computer; as a result, the two-way send port sending the AS2 message (from Contoso) and the two-way receive port receiving the AS2 message (as Fabrikam) are on the same computer.</span></span>  
  
- <span data-ttu-id="a7f97-155">メッセージ XML ペイロードをローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-155">Create a static one-way FILE send port (with a passthrough send pipeline) to route the message XML payload to a local folder.</span></span> <span data-ttu-id="a7f97-156">ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-156">Create the local folder.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="a7f97-157">メッセージ ペイロードをサブスクライブする送信ポートがない場合、メッセージ ボックスで中断されます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-157">If you do not have a send port to subscribe to the message payload, it will be suspended in the MessageBox.</span></span>  
  
- <span data-ttu-id="a7f97-158">MDN をローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-158">Create a static one-way FILE send port (with a passthrough send pipeline) to route the MDN to a local folder.</span></span> <span data-ttu-id="a7f97-159">ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-159">Create the local folder.</span></span>  
  
- <span data-ttu-id="a7f97-160">Fabrikam および Contoso の両方にパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-160">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
- <span data-ttu-id="a7f97-161">両方の取引先に対して、それぞれビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-161">Create a business profile each for both the trading parties.</span></span>  
  
- <span data-ttu-id="a7f97-162">Fabrikam および Contoso のビジネス プロファイル間に AS2 アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-162">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="a7f97-163">AS2 アグリーメントには、AS2 メッセージを送信し、その応答として同期 MDN を受信するプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-163">The AS2 agreement would contain properties to send an AS2 message and receive a synchronous MDN in return.</span></span>  
  
- <span data-ttu-id="a7f97-164">XML テスト メッセージを使用してチュートリアルをテストします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-164">Test the walkthrough using an XML test message.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="a7f97-165">チュートリアルの構成</span><span class="sxs-lookup"><span data-stu-id="a7f97-165">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="a7f97-166">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-166">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-test-message-schema"></a><span data-ttu-id="a7f97-167">テスト メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-167">To deploy the test message schema</span></span>  
  
1. <span data-ttu-id="a7f97-168">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-168">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-169">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a7f97-169">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="a7f97-170">そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-170">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2. <span data-ttu-id="a7f97-171">プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-171">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="a7f97-172">XML ファイルを使用してソリューションをテストするには、XML テスト メッセージ用の XSD スキーマを含むローカル フォルダーに移動し、XSD ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-172">To use an XML file to test your solution, move to the local folder that contains the XSD schema for the XML test message, and select the XSD file.</span></span> <span data-ttu-id="a7f97-173">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-173">Click **Add**.</span></span>  
  
3. <span data-ttu-id="a7f97-174">アセンブリ キー ファイルを設定し、アセンブリをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-174">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="a7f97-175">BTS ISAPI フィルターを有効にするには</span><span class="sxs-lookup"><span data-stu-id="a7f97-175">To enable the BTS ISAPI Filter</span></span>  
  
1. <span data-ttu-id="a7f97-176">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="a7f97-176">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
   > [!TIP]
   >  <span data-ttu-id="a7f97-177">オペレーティング システムによっては、管理ツールの [スタート] メニュー オプションを利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-177">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="a7f97-178">このような場合は、次のようにクリックします。**開始**、 をクリック**実行**、入力と`inetmgr`をインターネット インフォメーション サービス (IIS) マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-178">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  
  
2. <span data-ttu-id="a7f97-179">ルート Web サーバーのエントリを選択し、**機能ビュー**をダブルクリックします**ハンドラー マッピング**しをクリックして、[操作] ウィンドウで、**スクリプト マップの追加**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-179">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the Actions pane click **Add Script Map**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-180">Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子の Web サイトに適用するには、このマッピングが発生します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-180">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="a7f97-181">特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-181">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  
  
3. <span data-ttu-id="a7f97-182">**スクリプト マップの追加** ダイアログ ボックスに、入力`BtsHttpReceive.dll`で、**要求パス**フィールド。</span><span class="sxs-lookup"><span data-stu-id="a7f97-182">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4. <span data-ttu-id="a7f97-183">**実行可能ファイル**フィールドに、をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-183">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="a7f97-184">BtsHttpReceive.dll を選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-184">Select BtsHttpReceive.dll and click **OK**.</span></span>  
  
5. <span data-ttu-id="a7f97-185">入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-185">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6. <span data-ttu-id="a7f97-186">**要求の制限**ダイアログ ボックスで、**動詞**タブを選び**次の動詞のいずれか**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-186">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="a7f97-187">入力`POST`動詞として。</span><span class="sxs-lookup"><span data-stu-id="a7f97-187">Enter `POST` as the verb.</span></span>  
  
7. <span data-ttu-id="a7f97-188">**アクセス**] タブで [**スクリプト**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-188">On the **Access** tab, select **Script** and then click **OK**.</span></span>  
  
8. <span data-ttu-id="a7f97-189">をクリックして **[ok]** ISAPI 拡張を許可するメッセージが表示されたら、クリックと**はい**。</span><span class="sxs-lookup"><span data-stu-id="a7f97-189">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
##### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="a7f97-190">Fabrikam Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-190">To configure the Fabrikam Web page</span></span>  
  
1. <span data-ttu-id="a7f97-191">IIS マネージャーで、右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-191">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2. <span data-ttu-id="a7f97-192">**アプリケーション プールの追加** ダイアログ ボックスに、入力**BizTalkAppPool**で**名前**、し、 **.NET Framework v4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="a7f97-192">In **the Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="a7f97-193">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-193">Click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-194">コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-194">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3. <span data-ttu-id="a7f97-195">選択**アプリケーション プール**の**機能ビュー**選択**BizTalkAppPool**、順にクリックします**詳細設定**で**アクション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a7f97-195">Select **Application Pools**, in the **Features View** select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4. <span data-ttu-id="a7f97-196">**詳細設定**ダイアログ ボックスで、 **Identity**し、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-196">In the **Advanced Settings** dialog box, select **Identity** and then click the ellipsis (…) button.</span></span>  
  
5. <span data-ttu-id="a7f97-197">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-197">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
6. <span data-ttu-id="a7f97-198">入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力します**パスワードの確認入力**をクリックして **。OK** 3 回の IIS マネージャーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-198">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
7. <span data-ttu-id="a7f97-199">IIS マネージャーで、開く、**サイト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="a7f97-199">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="a7f97-200">右クリックし、**既定の Web サイト**ノードをクリックして**アプリケーションの追加**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-200">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  
  
8. <span data-ttu-id="a7f97-201">**アプリケーションの追加** ダイアログ ボックスに、入力**Fabrikam**で**エイリアス**、順にクリックします**選択**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-201">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
9. <span data-ttu-id="a7f97-202">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-202">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
10. <span data-ttu-id="a7f97-203">省略記号 (...) ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-203">Click the ellipsis (…) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
11. <span data-ttu-id="a7f97-204">をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a7f97-204">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="a7f97-205">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-205">Click **Close**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="a7f97-206">IIS マネージャーでは、Fabrikam 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-206">In IIS Manager, select the Fabrikam virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
13. <span data-ttu-id="a7f97-207">**認証**] ページで、[**匿名認証**いることを確認し、**状態**は**有効**。</span><span class="sxs-lookup"><span data-stu-id="a7f97-207">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="a7f97-208">場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a7f97-208">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="a7f97-209">仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-209">To specify that your virtual directory is not managed by Windows SharePoint Services</span></span>  
  
1.  <span data-ttu-id="a7f97-210">コンピューターに Windows SharePoint Services がインストールされて場合、 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**をクリックして**SharePoint 3.0 サーバーの全体管理**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-210">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7f97-211">この手順は、チュートリアルを設定するコンピューター上に Windows SharePoint Server がインストールされている場合に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-211">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="a7f97-212">実行する場合は、IIS 仮想ディレクトリが Windows SharePoint Server の管理対象から除外されるように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-212">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  
  
2.  <span data-ttu-id="a7f97-213">**サーバーの全体管理** ページ **サーバーの全体管理**、 をクリックして**アプリケーション管理**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-213">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  
  
3.  <span data-ttu-id="a7f97-214">**アプリケーション管理**] ページで [**管理パスの定義**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-214">On the **Application Management** page, click **Define managed paths**.</span></span>  
  
4.  <span data-ttu-id="a7f97-215">**管理パスの定義**] ページ [**新しいパスを追加**の**パス**テキスト ボックスに、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-215">In the **Define Managed Paths** page, under **Add a New Path**, in the **Path** text box, enter `Fabrikam`.</span></span> <span data-ttu-id="a7f97-216">[**型**、] をクリックして**エクスクルード パス**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-216">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-test-message"></a><span data-ttu-id="a7f97-217">テスト メッセージを受信する受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-217">To create a receive port to receive the test message</span></span>  
  
1. <span data-ttu-id="a7f97-218">Windows エクスプローラーを使用して、Contoso から EDI インターチェンジを受信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-218">In Windows Explorer, create a local folder to receive the EDI interchange from Contoso.</span></span>  
  
2. <span data-ttu-id="a7f97-219">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-219">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3. <span data-ttu-id="a7f97-220">**受信ポートのプロパティ**ダイアログ ボックスで、受信ポートの名前として**RecvXMLFromCont**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-220">In the **Receive Port Properties** dialog box, name the receive port as **RecvXMLFromCont**.</span></span>  
  
4. <span data-ttu-id="a7f97-221">をクリックして**受信場所**コンソール ツリーをクリックで**新規**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-221">Click **Receive Locations** in the console tree, and then click **New**.</span></span>  
  
5. <span data-ttu-id="a7f97-222">[受信場所の名前**ファイル**の**型**、] をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="a7f97-222">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6. <span data-ttu-id="a7f97-223">**受信フォルダー**、手順 1. で作成したフォルダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-223">For **Receive folder**, enter the name of the folder that you created in step 1.</span></span>  
  
7. <span data-ttu-id="a7f97-224">**ファイル マスク**、入力 **\*.xml**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-224">In **File mask**, enter **\*.xml**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="a7f97-225">受信パイプラインで選択**XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-225">In Receive pipeline, select **XMLReceive**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-226">XML 以外の別の非 EDI ファイル タイプを使用している場合は、入力**PassThruTranmit**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-226">If you are using another non-EDI file type, other than XML, enter **PassThruTranmit**.</span></span>  
  
9. <span data-ttu-id="a7f97-227">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="a7f97-227">Click **OK**, and then click **OK** again.</span></span>  
  
10. <span data-ttu-id="a7f97-228">をクリックして、**受信場所**ノードを右クリックし、受信場所をクリックして**を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="a7f97-228">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-as2-message-to-fabrikam"></a><span data-ttu-id="a7f97-229">AS2 メッセージを Fabrikam に送信するための送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-229">To create a send port to send the AS2 message to Fabrikam</span></span>  
  
1. <span data-ttu-id="a7f97-230">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-230">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-231">BizTalk アプリケーション 1 を使用する場合は、BizTalk EDI アプリケーションのアイテムを使用できるようにするために、BizTalk EDI アプリケーションへの参照を BizTalk アプリケーション 1 に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-231">If you use BizTalk Application 1, you must add a reference in BizTalk Application 1 to the BizTalk EDI Application, so your application can use its artifacts.</span></span> <span data-ttu-id="a7f97-232">詳細については、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-232">For more information, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2. <span data-ttu-id="a7f97-233">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前として**SendToFab_RecvMDN**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-233">In the **Send Port Properties** dialog box, name the send port as **SendToFab_RecvMDN**.</span></span>  
  
3. <span data-ttu-id="a7f97-234">**トランスポート**セクションで、 **HTTP**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-234">In the **Transport** section, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="a7f97-235">**HTTP トランスポートのプロパティ** ダイアログ ボックスの**送信先 URL**、入力 **http://localhost/Fabrikam/BTSHttpReceive.dll**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-235">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter **http://localhost/Fabrikam/BTSHttpReceive.dll**.</span></span>  
  
5. <span data-ttu-id="a7f97-236">クリア**チャンク エンコードを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-236">Clear **Enable chunked encoding**.</span></span> <span data-ttu-id="a7f97-237">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-237">Click **OK**.</span></span>  
  
6. <span data-ttu-id="a7f97-238">**送信パイプライン**、 **AS2Send**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-238">For **Send pipeline**, select **AS2Send**.</span></span>  
  
7. <span data-ttu-id="a7f97-239">**受信パイプライン**、 **AS2Receive**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-239">For **Receive pipeline**, select **AS2Receive**.</span></span>  
  
8. <span data-ttu-id="a7f97-240">コンソール ツリーで、選択**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-240">In the console tree, select **Filters**.</span></span> <span data-ttu-id="a7f97-241">**プロパティ**、入力**BTS します。ReceivePortName**; の**演算子**、入力**==**; と**値**EDI を受信する受信ポートの名前を入力します。インターチェンジ (`RecvXMLFromCont`)。</span><span class="sxs-lookup"><span data-stu-id="a7f97-241">For **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; and for **Value** enter the name of the receive port that will receive the EDI interchange (`RecvXMLFromCont`).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-242">PIDX メッセージを送信する場合は、メッセージの種類をフィルター処理するフィルター式を作成できます (**PIDX**)。</span><span class="sxs-lookup"><span data-stu-id="a7f97-242">If you are sending a PIDX message, you can create a filter expression that filters on the type of the message (**PIDX**).</span></span>  
  
9. <span data-ttu-id="a7f97-243">XML ドキュメントを変換するマップを適用する**送信マップ**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-243">If you want to apply a map to transform the XML document, click **Outbound Maps** in the console tree.</span></span> <span data-ttu-id="a7f97-244">入力、**ソース ドキュメント**送信マップの選択、**マップ**、し、入力、**ターゲット ドキュメント**。</span><span class="sxs-lookup"><span data-stu-id="a7f97-244">Enter the **Source Document** for the outbound map, select the **Map**, and then enter the **Target Document**.</span></span> <span data-ttu-id="a7f97-245">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-245">Click **OK**.</span></span>  
  
10. <span data-ttu-id="a7f97-246">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-246">Click **OK**.</span></span>  
  
11. <span data-ttu-id="a7f97-247">をクリックして、**送信ポート**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、送信ポートを右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-247">Click the **Send Ports** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-as2-message-and-return-an-acknowledgment"></a><span data-ttu-id="a7f97-248">AS2 メッセージを受信して確認を返す受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-248">To create a receive port to receive the AS2 message and return an acknowledgment</span></span>  
  
1. <span data-ttu-id="a7f97-249">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[、 **BizTalk アプリケーション 1**ノードを右クリックして**受信ポート**、] をポイント**新規**をクリックして**要求応答の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-249">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **BizTalk Application 1** node, right-click **Receive Ports**, point to **New**, and then click **Request Response Receive Port**.</span></span>  
  
2. <span data-ttu-id="a7f97-250">受信ポートに名前を付けます**RecvAS2Msg**、 をクリックし、**受信場所**コンソール ツリーで。</span><span class="sxs-lookup"><span data-stu-id="a7f97-250">Name the receive port as **RecvAS2Msg**, and then click **Receive Locations** in the console tree.</span></span>  
  
3. <span data-ttu-id="a7f97-251">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-251">Click **New**.</span></span>  
  
4. <span data-ttu-id="a7f97-252">**受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所の選択、 **HTTP**の**型**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-252">In the **Receive Location Properties** dialog box, name your receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="a7f97-253">**HTTP トランスポートのプロパティ** ダイアログ ボックスに、入力 **/Fabrikam/BTSHttpReceive.dll**の**仮想ディレクトリと ISAPI 拡張**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-253">In the **HTTP Transport Properties** dialog box, enter **/Fabrikam/BTSHttpReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="a7f97-254">クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-254">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="a7f97-255">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-255">Click **OK**.</span></span>  
  
6. <span data-ttu-id="a7f97-256">選択**AS2Receive**の**受信パイプライン**、および**AS2Send**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-256">Select **AS2Receive** for the **Receive Pipeline**, and **AS2Send** for the **Send Pipeline**.</span></span> <span data-ttu-id="a7f97-257">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="a7f97-257">Click **OK**, and then click **OK** again.</span></span>  
  
7. <span data-ttu-id="a7f97-258">をクリックして、**受信場所**ノードを右クリックし、受信場所をクリックして**を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="a7f97-258">Click the **Receive Locations** node, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-test-xml-payload-to-a-local-folder"></a><span data-ttu-id="a7f97-259">テスト XML ペイロードをローカル フォルダーに送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-259">To create a send port to send the test XML payload to a local folder</span></span>  
  
1. <span data-ttu-id="a7f97-260">Windows エクスプローラーで、EDI インターチェンジを送信する先のローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-260">In Windows Explorer, create a local folder to send the EDI interchange to.</span></span>  
  
2. <span data-ttu-id="a7f97-261">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-261">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3. <span data-ttu-id="a7f97-262">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**SendXMLPayload**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-262">In the **Send Port Properties** dialog box, name your send port as **SendXMLPayload**.</span></span> <span data-ttu-id="a7f97-263">選択**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-263">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="a7f97-264">**FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**、EDI ペイロード用に作成したローカル フォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-264">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder that you created for the EDI payload.</span></span>  
  
5. <span data-ttu-id="a7f97-265">**ファイル名**ファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-265">For **File name**, enter the file name.</span></span> <span data-ttu-id="a7f97-266">テスト メッセージとして XML ファイルを使用する場合は、入力 **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-266">If you are using an XML file as your test message, enter **%MessageID%.xml**.</span></span> <span data-ttu-id="a7f97-267">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-267">Click **OK**.</span></span>  
  
6. <span data-ttu-id="a7f97-268">既定の**PassThruTransmit**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-268">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7. <span data-ttu-id="a7f97-269">をクリックして**フィルター**コンソールで、ツリーし、EDI ペイロードの集荷に対してフィルターのプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-269">Click **Filters** in the console tree, and add filter properties for picking up the EDI payload.</span></span> <span data-ttu-id="a7f97-270">最初の行での**プロパティ**、入力**BTS します。ReceivePortName**は**演算子**、入力 **==** は**値**AS2 を受信する受信ポートの名前を入力メッセージ (`RecvAS2Msg`); と**でグループ化**、受け入れる**と**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-270">On the first line, for **Property**, enter **BTS.ReceivePortName**; for **Operator**, enter **==**; for **Value**, enter the name of the receive port that receives the AS2 message (`RecvAS2Msg`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="a7f97-271">2 行目の**プロパティ**、入力**EdiIntAS.IsAS2PayloadMessage**は**演算子**、入力**==**; と**値**、入力**True**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-271">On the second line, for **Property**, enter **EdiIntAS.IsAS2PayloadMessage**; for **Operator**, enter **==**; and for **Value**, enter **True**.</span></span>  
  
8. <span data-ttu-id="a7f97-272">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-272">Click **OK**.</span></span>  
  
9. <span data-ttu-id="a7f97-273">をクリックして、**送信ポート**ノードは、送信ポートを右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-273">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a><span data-ttu-id="a7f97-274">MDN をローカル フォルダーに送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-274">To create a send port to send the MDN to a local folder</span></span>  
  
1. <span data-ttu-id="a7f97-275">Windows エクスプローラーを使用して、MDN を送信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-275">In Windows Explorer, create a local folder to send the MDN to.</span></span>  
  
2. <span data-ttu-id="a7f97-276">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-276">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3. <span data-ttu-id="a7f97-277">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**SendMDNToContoso**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-277">In the **Send Port Properties** dialog box, name your send port as **SendMDNToContoso**.</span></span> <span data-ttu-id="a7f97-278">選択**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-278">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="a7f97-279">**FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**MDN を送信するために作成したローカル フォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-279">In the **FILE Transport Properties** dialog box, for **Destination folder**, enter the local folder you created to send the MDN to.</span></span>  
  
5. <span data-ttu-id="a7f97-280">**ファイル名**、入力 **%MessageID%.msg**します。**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-280">For **File name**, enter **%MessageID%.msg**. Click **OK**.</span></span>  
  
6. <span data-ttu-id="a7f97-281">既定の**PassThruTransmit**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-281">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
7. <span data-ttu-id="a7f97-282">クリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-282">Click **Filters** in the console tree.</span></span> <span data-ttu-id="a7f97-283">**プロパティ**、入力**BTS します。SPName**は**演算子**、入力 **==** は**値**、AS2 メッセージを送信する送信ポートの名前を入力します (`SendToFab_RecvMDN`);および**でグループ化**、受け入れる**と**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-283">For **Property**, enter **BTS.SPName**; for **Operator**, enter **==**; for **Value**, enter the name of the send port that sends the AS2 message (`SendToFab_RecvMDN`); and for **Group by**, accept **And**.</span></span> <span data-ttu-id="a7f97-284">2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2MdnResponseMessage**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-284">On a second line, for **Property**, enter **EdiIntAS.IsAS2MdnResponseMessage**.</span></span> <span data-ttu-id="a7f97-285">**演算子**、入力 **==** します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-285">For **Operator**, enter **==**.</span></span> <span data-ttu-id="a7f97-286">**値**、入力**True**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-286">For **Value**, enter **True**.</span></span>  
  
8. <span data-ttu-id="a7f97-287">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-287">Click **OK**.</span></span>  
  
9. <span data-ttu-id="a7f97-288">をクリックして、**送信ポート**ノードは、送信ポートを右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-288">Click the **Send Ports** node, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="a7f97-289">Fabrikam のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-289">To create a party and a business profile for Fabrikam</span></span>  
  
1. <span data-ttu-id="a7f97-290">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-290">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="a7f97-291">パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-291">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-292">選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7f97-292">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a7f97-293">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-293">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="a7f97-294">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="a7f97-294">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3. <span data-ttu-id="a7f97-295">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-295">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4. <span data-ttu-id="a7f97-296">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力 **[fabrikam_profile]** で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a7f97-296">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-297">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-297">When you create a party, a profile is also created.</span></span> <span data-ttu-id="a7f97-298">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-298">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="a7f97-299">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-299">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="a7f97-300">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-300">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="a7f97-301">Contoso のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-301">To create a party and a business profile for Contoso</span></span>  
  
1. <span data-ttu-id="a7f97-302">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-302">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="a7f97-303">パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-303">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-304">選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7f97-304">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a7f97-305">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-305">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="a7f97-306">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="a7f97-306">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3. <span data-ttu-id="a7f97-307">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-307">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4. <span data-ttu-id="a7f97-308">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a7f97-308">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a7f97-309">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-309">When you create a party, a profile is also created.</span></span> <span data-ttu-id="a7f97-310">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-310">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="a7f97-311">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-311">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="a7f97-312">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-312">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="a7f97-313">2 つのビジネス プロファイル間で AS2 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="a7f97-313">To create an AS2 agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="a7f97-314">右クリック**Contoso_Profile**、 をポイント**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-314">Right-click **Contoso_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="a7f97-315">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-315">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="a7f97-316">**プロトコル**ドロップダウン リストで、 **AS2**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-316">From the **Protocol** drop-down list, select **AS2**.</span></span>  
  
4.  <span data-ttu-id="a7f97-317">**2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Fabrikam**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-317">In the **Second Partner** section, from the **Name** drop-down list, select **Fabrikam**.</span></span>  
  
5.  <span data-ttu-id="a7f97-318">**2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **[fabrikam_profile]** します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-318">In the **Second Partner** section, from the **Profile** drop-down list, select **Fabrikam_Profile**.</span></span>  
  
     <span data-ttu-id="a7f97-319">2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは、一方向の AS2 アグリーメントの構成用です。</span><span class="sxs-lookup"><span data-stu-id="a7f97-319">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  
  
6.  <span data-ttu-id="a7f97-320">次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。</span><span class="sxs-lookup"><span data-stu-id="a7f97-320">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="a7f97-321">**識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-321">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="a7f97-322">**AS2-から**、入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-322">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="a7f97-323">**AS2-To**、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-323">For **AS2- To**, enter `Fabrikam`.</span></span>  
  
    2.  <span data-ttu-id="a7f97-324">**受信確認 (Mdn)** ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a7f97-324">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  
  
        1.  <span data-ttu-id="a7f97-325">選択、 **MessageBox にルーティング/配信の受信 MDN を処理する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-325">Select the **Process inbound MDN into MessageBox for routing/delivery options** check box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="a7f97-326">チェック、 **MessageBox にルーティング/配信の受信 MDN を処理する**のみが返された MDN の削除を MessageBox にために、このチュートリアルをテストするため必要です。</span><span class="sxs-lookup"><span data-stu-id="a7f97-326">Checking the **Process inbound MDN into MessageBox for routing/delivery options** is required for the testing of this walkthrough, because only then will the returned MDN be dropped into the MessageBox.</span></span> <span data-ttu-id="a7f97-327">これにより、MDN をサブスクライブする送信ポートを作成し、MDN をローカル ディレクトリに送信して、AS2 トランスミッションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-327">That enables you to create a send port to subscribe to the MDN, and to send the MDN to a local directory, so you can verify the AS2 transmission.</span></span>  
  
        2.  <span data-ttu-id="a7f97-328">選択、 **mdn を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-328">Select the **Request MDN** check box.</span></span>  
  
        3.  <span data-ttu-id="a7f97-329">必ず、**署名付き MDN を要求**チェック ボックスをオフします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-329">Make sure the **Request Signed MDN** check box is cleared.</span></span>  
  
        4.  <span data-ttu-id="a7f97-330">まま**非同期 MDN を要求する**オフにします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-330">Leave **Request asynchronous MDN** cleared.</span></span>  
  
        5.  <span data-ttu-id="a7f97-331">**ディス ポジション-通知-に**、任意の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-331">In **Disposition-Notification-To**, enter any value.</span></span> <span data-ttu-id="a7f97-332">このフィールドの値は AS2 処理中には使用されませんが、このフィールドに値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-332">The value of this field is not used during AS2 processing, but a value must be entered in the field.</span></span>  
  
    3.  <span data-ttu-id="a7f97-333">**送信ポート** ページで、EDI インターチェンジを Fabrikam に送信する双方向送信ポートを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-333">On the **Send Ports** page, associate the two-way send port that will be sending the EDI interchange to Fabrikam.</span></span> <span data-ttu-id="a7f97-334">**送信ポート**グリッドで、**名前**列で空のセルしボックスの一覧から、送信ポートを選択します。 **SendToFab_RecvMDN**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-334">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port **SendToFab_RecvMDN**.</span></span>  
  
7.  <span data-ttu-id="a7f97-335">次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。</span><span class="sxs-lookup"><span data-stu-id="a7f97-335">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7f97-336">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-336">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="a7f97-337">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります **[as2_from]** と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-337">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2_From** and **AS2-To**.</span></span>  
  
    1.  <span data-ttu-id="a7f97-338">**識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-338">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="a7f97-339">**AS2-から**、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-339">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="a7f97-340">**AS2-To**、入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-340">For **AS2- To**, enter `Contoso`.</span></span>  
  
8.  <span data-ttu-id="a7f97-341">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-341">Click **Apply**.</span></span>  
  
9. <span data-ttu-id="a7f97-342">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7f97-342">Click **OK**.</span></span> <span data-ttu-id="a7f97-343">新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a7f97-343">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="a7f97-344">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="a7f97-344">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="a7f97-345">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="a7f97-345">Testing the Walkthrough</span></span>  
 <span data-ttu-id="a7f97-346">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-346">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-solution"></a><span data-ttu-id="a7f97-347">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a7f97-347">To test the solution</span></span>  
  
1.  <span data-ttu-id="a7f97-348">Windows エクスプローラーで、XML テスト ファイルを、Contoso からテスト メッセージを受信するために作成したローカル フォルダーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a7f97-348">In Windows Explorer, paste your XML test file into the local folder that you created to receive the test message from Contoso.</span></span>  
  
2.  <span data-ttu-id="a7f97-349">XML ペイロードを送信するために作成したローカル フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-349">Move to the local folder that you created to send the XML payload to.</span></span> <span data-ttu-id="a7f97-350">フォルダーに XML ファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-350">Confirm that the folder contains an XML file.</span></span> <span data-ttu-id="a7f97-351">ファイルおよび元のテスト メッセージを開き、コンテンツが同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-351">Open the file and the original test message, and verify that they have the same content.</span></span>  
  
3.  <span data-ttu-id="a7f97-352">結果の MDN を送信するために作成したローカル フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-352">Move to the local folder that you created to send the resulting MDN to.</span></span> <span data-ttu-id="a7f97-353">フォルダーにファイルが含まれていることを確認し、ファイルを開いてこれが MDN ファイルであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7f97-353">Confirm that the folder contains a file; open the file and confirm that it is an MDN file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f97-354">参照</span><span class="sxs-lookup"><span data-stu-id="a7f97-354">See Also</span></span>  
 <span data-ttu-id="a7f97-355">[開発と BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="a7f97-355">[Developing and Configuring BizTalk Server AS2 Solutions](../core/developing-and-configuring-biztalk-server-as2-solutions.md) </span></span>  
 [<span data-ttu-id="a7f97-356">AS2 経由での送信非 EDI メッセージの送信側の処理</span><span class="sxs-lookup"><span data-stu-id="a7f97-356">Send-Side Processing of an Outgoing Non-EDI Message over AS2</span></span>](../core/send-side-processing-of-an-outgoing-non-edi-message-over-as2.md)
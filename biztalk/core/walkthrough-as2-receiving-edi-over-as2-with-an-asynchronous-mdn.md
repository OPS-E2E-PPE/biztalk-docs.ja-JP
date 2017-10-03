---
title: "チュートリアル (AS2): 非同期 MDN による AS2 経由で EDI の受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac3962e4-0525-4194-8cf1-b90664f1a139
caps.latest.revision: "40"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0dd9e94ff74adb4419f95b386861376bb424fd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-as2-receiving-edi-over-as2-with-an-asynchronous-mdn"></a><span data-ttu-id="e0ba2-102">チュートリアル (AS2): 非同期 MDN による AS2 経由での EDI の受信</span><span class="sxs-lookup"><span data-stu-id="e0ba2-102">Walkthrough (AS2): Receiving EDI over AS2 with an Asynchronous MDN</span></span>
<span data-ttu-id="e0ba2-103">このチュートリアルでは、AS2 トランスポート経由で EDI メッセージを受信して同期 MDN を返すソリューションを作成する、一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDI messages over AS2 transport, returning synchronous MDNs.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e0ba2-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="e0ba2-104">Prerequisites</span></span>  
 <span data-ttu-id="e0ba2-105">このトピックの手順を実行するための前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-105">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="e0ba2-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
-   <span data-ttu-id="e0ba2-107">チュートリアルを実行するコンピューターには、インターネット インフォメーション サービス (IIS) 7 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-107">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  
  
-   <span data-ttu-id="e0ba2-108">チュートリアルを実行するコンピューターに 64 ビット版の Windows がインストールされている場合は、BizTalk ホストが 32 ビットのみとマークされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-108">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="e0ba2-109">IIS の [アプリケーション プールの 32 ビット アプリケーション設定を有効にする] を True に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-109">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to True.</span></span> <span data-ttu-id="e0ba2-110">詳細については、次を参照してください。[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-110">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  
  
## <a name="how-the-solution-receives-an-edi-interchange-and-returns-an-asynchronous-mdn"></a><span data-ttu-id="e0ba2-111">ソリューションで EDI インターチェンジを受信して非同期 MDN を返す方法</span><span class="sxs-lookup"><span data-stu-id="e0ba2-111">How the Solution Receives an EDI Interchange and Returns an Asynchronous MDN</span></span>  
 <span data-ttu-id="e0ba2-112">このソリューションは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-112">The solution will do the following:</span></span>  
  
1.  <span data-ttu-id="e0ba2-113">取引先から HTTP 経由で、EDI インターチェンジが含まれた AS2 メッセージを受信し、EDIINT/AS2 からインターチェンジをデコードします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-113">Receive an AS2 message containing an EDI interchange over HTTP from the trading partner, and decode the interchange from EDIINT/AS2.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-114">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-114">The events in this list may not occur in the order shown.</span></span>  
  
2.  <span data-ttu-id="e0ba2-115">MDN 応答を生成して、MessageBox に配置します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-115">Generate an MDN response, and drop it in the MessageBox.</span></span>  
  
3.  <span data-ttu-id="e0ba2-116">動的送信ポートによるメッセージ MDN を取得します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-116">Pick up the message MDN by a dynamic send port.</span></span>  
  
4.  <span data-ttu-id="e0ba2-117">非同期メッセージ MDN を取引先に返します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-117">Return the asynchronous message MDN to the trading partner.</span></span>  
  
5.  <span data-ttu-id="e0ba2-118">インターチェンジの EDI 形式を内部 XML 形式に変換し、メッセージ ボックスに格納します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-118">Convert the EDI format of the interchange to internal XML format, and drop it in the MessageBox.</span></span>  
  
6.  <span data-ttu-id="e0ba2-119">PassThruTransmit パイプラインを持つ送信ポートが、メッセージ XML ファイルを MessageBox から取得します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-119">A send port with a PassThruTransmit pipeline picks up the message XML file from the MessageBox.</span></span>  
  
7.  <span data-ttu-id="e0ba2-120">送信ポートが、EDI インターチェンジ XML ファイルを Contoso というパーティのフォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-120">The send port sends EDI interchange XML file to a folder at the Contoso party.</span></span>  
  
 <span data-ttu-id="e0ba2-121">次の図では、このソリューションのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-121">The following figure shows the architecture for this solution.</span></span>  
  
 <span data-ttu-id="e0ba2-122">![非同期 MDN による AS2 の受信](../core/media/bts-configuring-the-receiving-of-edi-over-as2-with-an-asynchronous-mdnc.gif "bts_Configuring_the_Receiving_of_EDI_Over_AS2_with_an_Asynchronous_MDNc")</span><span class="sxs-lookup"><span data-stu-id="e0ba2-122">![AS2 receiving with an asynchronous MDN](../core/media/bts-configuring-the-receiving-of-edi-over-as2-with-an-asynchronous-mdnc.gif "bts_Configuring_the_Receiving_of_EDI_Over_AS2_with_an_Asynchronous_MDNc")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="e0ba2-123">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="e0ba2-123">The Functionality in this Solution</span></span>  
 <span data-ttu-id="e0ba2-124">このチュートリアルの機能には、以下の条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-124">The following applies to the functionality of this walkthrough:</span></span>  
  
-   <span data-ttu-id="e0ba2-125">EDI 受信確認は生成されません。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-125">An EDI acknowledgment is not generated.</span></span> <span data-ttu-id="e0ba2-126">EDI 受信確認の生成はではデモンストレーション[チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認をバックアップ](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-126">Generating an EDI acknowledgment is demonstrated in [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span> <span data-ttu-id="e0ba2-127">「AS2 トランスポート経由で EDI 受信確認を送信する[チュートリアル (AS2): 非同期 MDN による AS2 経由で送信する EDI](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-127">Sending an EDI acknowledgment over AS2 transport is described in [Walkthrough (AS2): Sending EDI over AS2 with an Asynchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md).</span></span>  
  
-   <span data-ttu-id="e0ba2-128">このソリューションは、EDIFACT エンコードではなく X12 エンコードを使用するインターチェンジを対象に設計されています。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-128">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-129">EDIFACT エンコードに使用される構成は、X12 エンコードに使用される構成とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-129">The configuration used for EDIFACT encoding is closely parallel to that used for X12 encoding.</span></span>  
  
-   <span data-ttu-id="e0ba2-130">EDI の種類の検証および拡張された検証は、受信インターチェンジに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-130">EDI type and extended validation will be performed on the incoming interchange.</span></span>  
  
-   <span data-ttu-id="e0ba2-131">AS2 レポートおよび EDI レポートが有効になり、インターチェンジの状態レポートに表示するトランザクション セットが保存されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-131">AS2 and EDI reporting will be enabled, and transaction sets will be saved for viewing from the interchange status report.</span></span>  
  
-   <span data-ttu-id="e0ba2-132">このソリューションは、否認不可データベースに署名、圧縮、暗号化、およびメッセージ ストレージを構成しません。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-132">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="e0ba2-133">これらのプロパティを構成する手順については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-133">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="e0ba2-134">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="e0ba2-134">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="e0ba2-135">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-135">The procedures required for this solution include the following:</span></span>  
  
-   <span data-ttu-id="e0ba2-136">必要なメッセージ スキーマを使用して BizTalk プロジェクトをビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-136">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  
  
-   <span data-ttu-id="e0ba2-137">AS2 メッセージの受信に使用する BTS ISAPI フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-137">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  
  
-   <span data-ttu-id="e0ba2-138">Fabrikam からの AS2 メッセージを受信する Contoso 仮想ディレクトリを、受信場所で構成したとおりに作成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-138">Create a Contoso virtual directory that receives the AS2 message from Fabrikam, as configured in the receive location.</span></span>  
  
-   <span data-ttu-id="e0ba2-139">MDN を Contoso から受信する Fabrikam 仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-139">Create a Fabrikam virtual directory that receives the MDN from Contoso.</span></span>  
  
-   <span data-ttu-id="e0ba2-140">Contoso および Fabrikam 仮想ディレクトリが、Windows SharePoint Services の管理対象から除外されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-140">Specify that the Contoso and Fabrikam virtual directories are not managed by Windows SharePoint Services.</span></span>  
  
-   <span data-ttu-id="e0ba2-141">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の静的な一方向 HTTP 受信ポートを作成し、EDI ビジネス ドキュメントを含んでいる AS2 メッセージを取引先から受信します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-141">Create a static one-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message containing the EDI business document from the trading partner.</span></span> <span data-ttu-id="e0ba2-142">受信パイプラインとして AS2EDIReceive パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-142">Configure the receive pipeline to be the AS2EDIReceive pipeline.</span></span>  
  
-   <span data-ttu-id="e0ba2-143">受信した AS2 メッセージに応答して MDN を送信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の動的な一方向 HTTP 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-143">Create a dynamic one-way HTTP send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the MDN responding to the received AS2 message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-144">この送信ポートは、EdiIntAS.IsAS2AsynchronousMDN プロパティ (AS2EdiReceive パイプラインにより True に設定されている) および関連付けトークンに基づいて、MDN をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-144">This send port subscribes to the MDN based on the EdiIntAS.IsAS2AsynchronousMDN property (which was set to True by the AS2EdiReceive pipeline) and correlation tokens.</span></span> <span data-ttu-id="e0ba2-145">メッセージのヘッダーにある Receipt-Delivery-Notification 行のアドレスに MDN を送信するには、送信ポートが動的になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-145">The send port must be dynamic, so it will send the MDN to the address in the Receipt-Delivery-Notification line in the header of the message.</span></span>  
  
-   <span data-ttu-id="e0ba2-146">静的な一方向 FILE 送信ポートを作成し、EDI ペイロード (XML 形式) をローカル フォルダーにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-146">Create a static one-way FILE send port to route the EDI payload (in XML format) to a local folder.</span></span> <span data-ttu-id="e0ba2-147">ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-147">Create the local folder.</span></span>  
  
-   <span data-ttu-id="e0ba2-148">Fabrikam および Contoso の両方にパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-148">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
-   <span data-ttu-id="e0ba2-149">両方の取引先に対して、それぞれビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-149">Create a business profile each for both the trading parties.</span></span>  
  
-   <span data-ttu-id="e0ba2-150">Fabrikam および Contoso のビジネス プロファイル間に AS2 アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-150">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="e0ba2-151">AS2 アグリーメントには、AS2 メッセージを送信し、その応答として非同期 MDN を受信するためのプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-151">The AS2 agreement would contain properties to send an AS2 message and receive an asynchronous MDN in return.</span></span>  
  
-   <span data-ttu-id="e0ba2-152">Fabrikam および Contoso のビジネス プロファイル間に、X12 メッセージを受信する X12 アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-152">Create an X12 agreement between the business profiles for Fabrikam and Contoso to receive X12 messages.</span></span>  
  
-   <span data-ttu-id="e0ba2-153">AS2 チュートリアル ファイルの一部として同梱されている HTTP 送信者ユーティリティを使用して、このソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-153">Test the solution by using the HTTP Sender utility that is shipped as part of the AS2 tutorial files.</span></span> <span data-ttu-id="e0ba2-154">このユーティリティは、EDI インターチェンジを含むテスト用 AS2 メッセージを、AS2 トランスポートを経由して送信します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-154">This utility sends a test AS2 message containing an EDI interchange over AS2 transport.</span></span> <span data-ttu-id="e0ba2-155">このユーティリティは、AS2 トランスポートを経由して、EDI インターチェンジが含まれた AS2 テスト メッセージを送信します (この X12_00401_864.edi は AS2 チュートリアルにも付属しています)。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-155">This utility sends a test AS2 message containing an EDI interchange over AS2 transport (X12_00401_864.edi, also shipped with the AS2 tutorial).</span></span> <span data-ttu-id="e0ba2-156">このチュートリアルに使用する HTTP 送信者とテスト メッセージは、チュートリアルに付属しているバージョンと同じです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-156">The HTTP Sender and the test message that you use for this walkthrough are the same as the versions that shipped for the tutorial.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="e0ba2-157">チュートリアルの構成</span><span class="sxs-lookup"><span data-stu-id="e0ba2-157">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="e0ba2-158">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-158">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="e0ba2-159">メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-159">To deploy the message schema</span></span>  
  
1.  <span data-ttu-id="e0ba2-160">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-160">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the project [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-161">このプロジェクトは AS2 チュートリアルに付属し、テスト メッセージと共に使用する 864 スキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-161">This project, which is shipped for the AS2 tutorial, includes an 864 schema for use with the test message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-162">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-162">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="e0ba2-163">いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-163">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2.  <span data-ttu-id="e0ba2-164">右クリックし、**スキーマ**ソリューション エクスプ ローラーでプロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-164">Right-click the **Schemas** project in the Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="e0ba2-165">をクリックして、**署名**プロジェクト デザイナーのチェック タブ、**アセンブリに署名**、チェック ボックスをオンし、ドロップダウン リストから選択**新規**を作成するために必要な値を指定し、厳密な名前キー ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-165">Click the **Signing** tab in the project designer, check the **Sign the Assembly** checkbox, and from the drop-down, select **New** and provide the necessary values to create a strong name key file.</span></span> <span data-ttu-id="e0ba2-166">変更を保存し、プロジェクトのプロパティ ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-166">Save the changes and close the project properties window.</span></span>  
  
3.  <span data-ttu-id="e0ba2-167">Schemas.btproj をビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-167">Build and deploy Schemas.btproj.</span></span>  
  
##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="e0ba2-168">BTS ISAPI フィルターを有効にするには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-168">To enable the BTS ISAPI Filter</span></span>  
  
1.  <span data-ttu-id="e0ba2-169">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="e0ba2-169">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e0ba2-170">オペレーティング システムによっては、管理ツールの [スタート] メニュー オプションを利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-170">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="e0ba2-171">このような場合、をクリックして**開始**、 をクリックして**実行**、入力と`inetmgr`インターネット インフォメーション サービス (IIS) マネージャを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-171">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  
  
2.  <span data-ttu-id="e0ba2-172">ルート Web サーバーのエントリを選択し、、**機能ビュー**、ダブルクリックして**ハンドラー マッピング**し、操作 ウィンドウでをクリックして**スクリプト マップの追加**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-172">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the Actions pane click **Add Script Map**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-173">Web サーバー レベルでスクリプト マッピングを構成すると、すべての子 Web サイトに適用するには、このマッピングが発生します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-173">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="e0ba2-174">特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-174">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  
  
3.  <span data-ttu-id="e0ba2-175">**スクリプト マップの追加** ダイアログ ボックスで、入力`BtsHttpReceive.dll`で、**要求パス**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-175">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  
  
4.  <span data-ttu-id="e0ba2-176">**実行可能ファイル**フィールドで、をクリックして、**省略記号 (...)**ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-176">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="e0ba2-177">BtsHttpReceive.dll を選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-177">Select BtsHttpReceive.dll and click **OK**.</span></span>  
  
5.  <span data-ttu-id="e0ba2-178">入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-178">Enter `BizTalk HTTP Receive` in the `Name` field, and then click **Request Restrictions**.</span></span>  
  
6.  <span data-ttu-id="e0ba2-179">要求の制限 ダイアログ ボックスで、選択、**動詞**タブをクリックし**次の動詞のいずれかの**します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-179">In the Request Restrictions dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="e0ba2-180">入力`POST`動詞として。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-180">Enter `POST` as the verb .</span></span>  
  
7.  <span data-ttu-id="e0ba2-181">**アクセス** タブで **スクリプト** をクリックし、 **ok**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-181">On the **Access** tab, select **Script** and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="e0ba2-182">をクリックして**OK** ISAPI 拡張を許可するメッセージが表示されたらをクリックし、**はい**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-182">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
##### <a name="to-configure-the-contoso-web-page"></a><span data-ttu-id="e0ba2-183">Contoso Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-183">To configure the Contoso Web page</span></span>  
  
1.  <span data-ttu-id="e0ba2-184">IIS マネージャーを右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-184">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  
  
2.  <span data-ttu-id="e0ba2-185">**アプリケーション プールの追加**] ダイアログ ボックスで、入力**BizTalkAppPool**で**名前**、し、[ **.NET Framework V4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-185">In the **Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** drop-down list.</span></span> <span data-ttu-id="e0ba2-186">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-186">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-187">コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-187">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  
  
3.  <span data-ttu-id="e0ba2-188">選択**アプリケーション プール**、機能ビューの選択で**BizTalkAppPool**、順にクリック**詳細設定**で、**アクション**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-188">Select **Application Pools**, in the Features View select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  
  
4.  <span data-ttu-id="e0ba2-189">**詳細設定**ダイアログ ボックスで、 **Identity**をクリックし、**省略記号 (...)**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-189">In the **Advanced Settings** dialog box, select **Identity** and then click the **ellipsis (…)** button.</span></span>  
  
5.  <span data-ttu-id="e0ba2-190">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-190">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  
  
6.  <span data-ttu-id="e0ba2-191">入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力で**パスワードの確認入力**をクリックして**OK** IIS マネージャーに戻りますを 3 回です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-191">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  
  
7.  <span data-ttu-id="e0ba2-192">IIS マネージャーで、開く、**サイト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-192">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="e0ba2-193">右クリックし、 **Default Web Site**ノードをクリックして**アプリケーションの追加**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-193">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  
  
8.  <span data-ttu-id="e0ba2-194">**アプリケーションの追加** ダイアログ ボックスに、入力**Contoso**で、**エイリアス**テキスト ボックス、およびクリック**選択**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-194">In the **Add Application** dialog box, enter **Contoso** in the **Alias** text box, and then click **Select**.</span></span>  
  
9. <span data-ttu-id="e0ba2-195">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-195">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
10. <span data-ttu-id="e0ba2-196">**物理パス**をクリックして、**省略記号 (...)**ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-196">For the **Physical Path**, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span>  
  
11. <span data-ttu-id="e0ba2-197">をクリックして**テストの設定**に表示されるエラーがないことを確認し、**接続のテスト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-197">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="e0ba2-198">**[閉じる]**をクリックし、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-198">Click **Close**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="e0ba2-199">IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、、**機能ビュー**をダブルクリックして**認証**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-199">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
13. <span data-ttu-id="e0ba2-200">**認証**] ページで、[**匿名認証**ことを確認し、**ステータス**は**有効**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-200">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="e0ba2-201">場合、**ステータス**は**無効になっている**、 をクリックして**を有効にする**で、**アクション**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-201">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-configure-the-fabrikam-web-page"></a><span data-ttu-id="e0ba2-202">Fabrikam Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-202">To configure the Fabrikam Web page</span></span>  
  
1.  <span data-ttu-id="e0ba2-203">IIS マネージャーで、開く、**サイト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-203">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="e0ba2-204">右クリックし、 **Default Web Site**ノードをクリックして**アプリケーションの追加**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-204">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  
  
2.  <span data-ttu-id="e0ba2-205">**アプリケーションの追加** ダイアログ ボックスで、入力**Fabrikam**で**エイリアス**、順にクリック**選択**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-205">In the **Add Application** dialog box, enter **Fabrikam** in **Alias**, and then click **Select**.</span></span>  
  
3.  <span data-ttu-id="e0ba2-206">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-206">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-207">**物理パス**をクリックして、**省略記号 (...)**ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 \fabrikam です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-207">For the **Physical Path**, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Fabrikam.</span></span>  
  
5.  <span data-ttu-id="e0ba2-208">をクリックして**テストの設定**に表示されるエラーがないことを確認し、**接続のテスト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-208">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="e0ba2-209">**[閉じる]**をクリックし、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-209">Click **Close**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="e0ba2-210">IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、、**機能ビュー**をダブルクリックして**認証**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-210">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  
  
7.  <span data-ttu-id="e0ba2-211">**認証**] ページで、[**匿名認証**ことを確認し、**ステータス**は**有効**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-211">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="e0ba2-212">場合、**ステータス**は**無効になっている**、 をクリックして**を有効にする**で、**アクション**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-212">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  
  
##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="e0ba2-213">仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-213">To specify that your virtual directory is not managed by Windows SharePoint Services</span></span>  
  
1.  <span data-ttu-id="e0ba2-214">Windows SharePoint Services がコンピューターにインストールされている場合にをクリックして**開始**、 をポイント**すべてのプログラム**、指す**管理ツール**をクリックして**SharePoint 3.0 サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-214">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-215">この手順は、チュートリアルを設定するコンピューター上に Windows SharePoint Server がインストールされている場合に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-215">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="e0ba2-216">実行する場合は、IIS 仮想ディレクトリが Windows SharePoint Server の管理対象から除外されるように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-216">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  
  
2.  <span data-ttu-id="e0ba2-217">**サーバーの全体管理**] ページの [**サーバーの全体管理**をクリックして**アプリケーション管理**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-217">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  
  
3.  <span data-ttu-id="e0ba2-218">**アプリケーション管理**] ページで [**管理パスの定義**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-218">On the **Application Management** page, click **Define managed paths**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-219">**管理パスの定義**] ページの [**新しいパスを追加**で、**パス**テキスト ボックスに、入力**Contoso**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-219">In the **Define Managed Paths** page, under **Add a New Path**, in the **Path** text box, enter **Contoso**.</span></span> <span data-ttu-id="e0ba2-220">[**型**、] をクリックして**エクスクルード パス**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-220">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e0ba2-221">Fabrikam 仮想ディレクトリに対して手順 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-221">Repeat step 4 for the Fabrikam virtual directory.</span></span>  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-interchange-over-as2-from-fabrikam"></a><span data-ttu-id="e0ba2-222">Fabrikam から AS2 経由で EDI インターチェンジを受信する受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-222">To create a receive port to receive the EDI interchange Over AS2 from Fabrikam</span></span>  
  
1.  <span data-ttu-id="e0ba2-223">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-223">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="e0ba2-224">受信ポートの名前を指定し、をクリックして**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-224">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  
  
3.  <span data-ttu-id="e0ba2-225">**[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-225">Click **New**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-226">名前、受信場所は、select **HTTP**の**型**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-226">Name the receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="e0ba2-227">**仮想ディレクトリと ISAPI 拡張**、入力`/Contoso/BTSHTTPReceive.dll`です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-227">For **Virtual directory plus ISAPI extension**, enter `/Contoso/BTSHTTPReceive.dll`.</span></span>  
  
6.  <span data-ttu-id="e0ba2-228">選択、**失敗した要求を中断**チェック ボックスをオンし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-228">Select the **Suspend failed requests** check box, and click **OK**.</span></span>  
  
7.  <span data-ttu-id="e0ba2-229">**受信パイプライン** **AS2EDIReceive**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-229">For **Receive pipeline**, select **AS2EDIReceive**.</span></span>  
  
8.  <span data-ttu-id="e0ba2-230">をクリックして**[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-230">Click **OK**, and then click **OK** again.</span></span>  
  
9. <span data-ttu-id="e0ba2-231">**受信場所**のペイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、受信場所を右クリックし、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-231">In the **Receive Locations** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-dynamic-send-port-to-send-the-mdn-to-fabrikam"></a><span data-ttu-id="e0ba2-232">MDN を Fabrikam に送信するための動的な送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-232">To create a dynamic send port to send the MDN to Fabrikam</span></span>  
  
1.  <span data-ttu-id="e0ba2-233">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**動的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-233">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Dynamic One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="e0ba2-234">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-234">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
3.  <span data-ttu-id="e0ba2-235">**送信パイプライン** **AS2Send**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-235">For **Send Pipeline**, select **AS2Send**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-236">コンソール ツリーで、次のように選択します。**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-236">In the console tree, select **Filters**.</span></span> <span data-ttu-id="e0ba2-237">**プロパティ**、入力**EdiIntAS.IsAS2AsynchronousMDN**; の**演算子**、入力 **==** ; および**値**、入力**True**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-237">For **Property**, enter **EdiIntAS.IsAS2AsynchronousMDN**; for **Operator**, enter **==**; and for **Value** , enter **True**.</span></span>  
  
5.  <span data-ttu-id="e0ba2-238">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-238">Click **OK**.</span></span>  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a><span data-ttu-id="e0ba2-239">EDI ペイロードをローカル フォルダーに送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-239">To create a send port to send the EDI payload to a local folder</span></span>  
  
1.  <span data-ttu-id="e0ba2-240">Windows エクスプローラで、という名前の Contoso ローカル フォルダーを作成する**EDI_to_Contoso** EDI ペイロードを送信します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-240">In Windows Explorer, create a Contoso local folder named **EDI_to_Contoso** to send the EDI payload to.</span></span>  
  
2.  <span data-ttu-id="e0ba2-241">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-241">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
3.  <span data-ttu-id="e0ba2-242">**送信ポートのプロパティ**ダイアログ ボックスで、名前、送信ポートにたとえば、 **Send_Payload**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-242">In the **Send Port Properties** dialog box, name your send port, for example, **Send_Payload**.</span></span> <span data-ttu-id="e0ba2-243">選択**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-243">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-244">**FILE トランスポートのプロパティ** ダイアログ ボックスの**コピー先フォルダー**を参照して選択、 **EDI_to_Contoso**手順 1. で作成したフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-244">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select the **EDI_to_Contoso** folder that you created in step 1.</span></span> <span data-ttu-id="e0ba2-245">ままにして**ファイル名**として**%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-245">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="e0ba2-246">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-246">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="e0ba2-247">既定の**PassThruTransmit**の**送信パイプライン**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-247">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
6.  <span data-ttu-id="e0ba2-248">をクリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-248">Click **Filters** in the console tree.</span></span> <span data-ttu-id="e0ba2-249">**プロパティ**、入力**BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-249">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="e0ba2-250">**演算子**、入力 **==**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-250">For **Operator**, enter **==**.</span></span> <span data-ttu-id="e0ba2-251">**値**、メッセージのメッセージの種類を入力`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-251">For **Value**, enter the message type for your message, `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  
  
7.  <span data-ttu-id="e0ba2-252">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-252">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="e0ba2-253">**送信ポート**のペイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-253">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="e0ba2-254">Fabrikam のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-254">To create a party and a business profile for Fabrikam</span></span>  
  
1.  <span data-ttu-id="e0ba2-255">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-255">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="e0ba2-256">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-256">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-257">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0ba2-257">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e0ba2-258">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-258">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="e0ba2-259">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-259">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="e0ba2-260">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-260">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-261">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**fabrikam_profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-261">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-262">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-262">When you create a party, a profile is also created.</span></span> <span data-ttu-id="e0ba2-263">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-263">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="e0ba2-264">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-264">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="e0ba2-265">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-265">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="e0ba2-266">Contoso のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-266">To create a party and a business profile for Contoso</span></span>  
  
1.  <span data-ttu-id="e0ba2-267">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-267">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="e0ba2-268">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-268">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-269">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0ba2-269">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e0ba2-270">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-270">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="e0ba2-271">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-271">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="e0ba2-272">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-272">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-273">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-273">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-274">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-274">When you create a party, a profile is also created.</span></span> <span data-ttu-id="e0ba2-275">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-275">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="e0ba2-276">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-276">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="e0ba2-277">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-277">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="e0ba2-278">2 つのビジネス プロファイル間で AS2 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-278">To create an AS2 agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="e0ba2-279">右クリック**fabrikam_profile**、 をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-279">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="e0ba2-280">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-280">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="e0ba2-281">**プロトコル**ドロップダウン リストで、 **AS2**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-281">From the **Protocol** drop-down list, select **AS2**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-282">**2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、 **Contoso**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-282">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  
  
5.  <span data-ttu-id="e0ba2-283">**2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-283">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  
  
     <span data-ttu-id="e0ba2-284">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブは、一方向の AS2 アグリーメントの構成用です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-284">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  
  
6.  <span data-ttu-id="e0ba2-285">**全般** タブで、**全般プロパティ** ページの 、**共通のホスト設定**セクションで、**レポートをオンに**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-285">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**.</span></span>  
  
7.  <span data-ttu-id="e0ba2-286">次のタスクを実行、 **Fabrikam が Contoso ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-286">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    1.  <span data-ttu-id="e0ba2-287">**識別子** ページで、値を入力**AS2-から**と**AS2-に**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-287">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="e0ba2-288">**AS2-から**、入力`Fabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-288">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="e0ba2-289">**AS2-To**、入力`Contoso`です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-289">For **AS2- To**, enter `Contoso`.</span></span>  
  
    2.  <span data-ttu-id="e0ba2-290">**検証** ページで、、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="e0ba2-290">On the **Validation** page, select the **Use agreement settings for validation and MDN instead of message header** check box</span></span>  
  
    3.  <span data-ttu-id="e0ba2-291">**受信確認 (Mdn)**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-291">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  
  
        1.  <span data-ttu-id="e0ba2-292">選択、 **mdn を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-292">Select the **Request MDN** check box.</span></span>  
  
        2.  <span data-ttu-id="e0ba2-293">確認してください、**署名付き mdn を要求してもする**チェック ボックスはオフです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-293">Make sure the **Request Signed MDN** check box is cleared.</span></span>  
  
        3.  <span data-ttu-id="e0ba2-294">選択、**非同期 MDN を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-294">Select the **Request asynchronous MDN** check box.</span></span>  
  
        4.  <span data-ttu-id="e0ba2-295">**- Receipt-delivery-option (URL)**テキスト ボックスに、入力`http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-295">In the **Receipt-Delivery-Option (URL)** text box, enter `http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`.</span></span>  
  
8.  <span data-ttu-id="e0ba2-296">次のタスクを実行、 **Contoso が Fabrikam ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-296">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-297">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-297">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="e0ba2-298">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**AS2-から**と**AS2-に**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-298">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2-From** and **AS2-To**.</span></span>  
  
    1.  <span data-ttu-id="e0ba2-299">**識別子** ページで、値を入力**AS2-から**と**AS2-に**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-299">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="e0ba2-300">**AS2-から**、入力`Contoso`です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-300">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="e0ba2-301">**AS2-To**、入力`Fabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-301">For **AS2- To**, enter `Fabrikam`.</span></span>  
  
9. <span data-ttu-id="e0ba2-302">**[適用]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-302">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="e0ba2-303">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-303">Click **OK**.</span></span> <span data-ttu-id="e0ba2-304">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-304">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="e0ba2-305">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-305">The newly added agreement is enabled by default.</span></span>  
  
##### <a name="to-create-an-x12-agreement-between-the-two-business-profiles"></a><span data-ttu-id="e0ba2-306">2 つのビジネス プロファイルの間に X12 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0ba2-306">To create an X12 agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="e0ba2-307">右クリック**fabrikam_profile**、 をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-307">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="e0ba2-308">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-308">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="e0ba2-309">**プロトコル**ドロップダウン リストで、 **X12**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-309">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
4.  <span data-ttu-id="e0ba2-310">**2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、 **Contoso**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-310">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  
  
5.  <span data-ttu-id="e0ba2-311">**2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-311">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  
  
     <span data-ttu-id="e0ba2-312">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブは一方向 X12 アグリーメントを構成するためのものです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-312">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way X12 agreement.</span></span>  
  
6.  <span data-ttu-id="e0ba2-313">**全般** タブで、**全般プロパティ** ページの 、**共通のホスト設定**セクションで、**レポートをオンに**、し、選択**reporting 用メッセージ ペイロードを格納**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-313">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
7.  <span data-ttu-id="e0ba2-314">次のタスクを実行、 **Fabrikam が Contoso ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-314">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    1.  <span data-ttu-id="e0ba2-315">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-315">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e0ba2-316"> では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-316"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="e0ba2-317">値と照合**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**とアグリーメントのプロパティで、インターチェンジ ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-317">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="e0ba2-318">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-318">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="e0ba2-319">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-319">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e0ba2-320">このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**7654321**、 **ISA7**に**ZZ。**、および**ISA8**に**1234567**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-320">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **7654321**, **ISA7** to **ZZ**, and **ISA8** to **1234567**.</span></span>  
  
    2.  <span data-ttu-id="e0ba2-321">**検証**ページで、、**インターチェンジの設定**セクションで、確認してください**重複している isa13 を確認**オプションがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-321">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e0ba2-322">オフにすると、**重複している isa13 を確認して**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-322">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    3.  <span data-ttu-id="e0ba2-323">使用するかどうかに付属する標準スキーマのいずれかの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の**ローカル ホストの設定**ページで、**トランザクション セットの設定**セクションで、選択するために使用するスキーマの名前空間受信インターチェンジを処理します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-323">If you are using one of the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], on the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span>  
  
        |<span data-ttu-id="e0ba2-324">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e0ba2-324">Use this</span></span>|<span data-ttu-id="e0ba2-325">目的</span><span class="sxs-lookup"><span data-stu-id="e0ba2-325">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="e0ba2-326">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-326">**Default**</span></span>|<span data-ttu-id="e0ba2-327">列のチェック ボックスをオンにします</span><span class="sxs-lookup"><span data-stu-id="e0ba2-327">Select the checkbox in the column</span></span>|  
        |<span data-ttu-id="e0ba2-328">**Target Namespace**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-328">**Target Namespace**</span></span>|<span data-ttu-id="e0ba2-329">[ `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-329">Select `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`.</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="e0ba2-330">プロパティを設定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、受信 850 インターチェンジの処理に使用するスキーマを決定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-330">Setting the properties enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to determine the schema to be used in processing the incoming 850 interchange.</span></span> <span data-ttu-id="e0ba2-331">グリッド内の行に入力された [GS02] と [ST01] の値がインターチェンジに設定されている場合は、同じ行にあるターゲットの名前空間により、使用するスキーマが決定されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-331">If an interchange has the values of GS02 and ST01 that are entered on a line of the grid, then the target namespace for the same line will be used to determine the schema to be used.</span></span>  
  
    4.  <span data-ttu-id="e0ba2-332">**エンベロープ**ページで、**トランザクション セットの設定**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-332">On the **Envelopes** page under the **Transaction Set Settings** section, do the following:</span></span>  
  
        |<span data-ttu-id="e0ba2-333">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e0ba2-333">Use this</span></span>|<span data-ttu-id="e0ba2-334">目的</span><span class="sxs-lookup"><span data-stu-id="e0ba2-334">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="e0ba2-335">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-335">**Default**</span></span>|<span data-ttu-id="e0ba2-336">選択**既定**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-336">Select **Default**.</span></span> <span data-ttu-id="e0ba2-337">**注:** 、既定の値は、この行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**が使用される場合でもの値は、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**の一致するものではありません、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-337">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="e0ba2-338">**トランザクションの種類**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-338">**Transaction Type**</span></span>|<span data-ttu-id="e0ba2-339">たとえば、テスト メッセージのメッセージの種類を選択**864 – テキスト メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-339">Select the message type of your test message, for example, **864 – Text Message**.</span></span>|  
        |<span data-ttu-id="e0ba2-340">**バージョン/リリース**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-340">**Version/Release**</span></span>|<span data-ttu-id="e0ba2-341">入力**00401**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-341">Enter **00401**.</span></span>|  
        |<span data-ttu-id="e0ba2-342">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-342">**Target namespace**</span></span>|<span data-ttu-id="e0ba2-343">選択**http://schemas.microsoft.com/BizTalk/EDI/X12/2006**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-343">Select **http://schemas.microsoft.com/BizTalk/EDI/X12/2006**.</span></span>|  
        |<span data-ttu-id="e0ba2-344">**GS1**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-344">**GS1**</span></span>|<span data-ttu-id="e0ba2-345">テスト メッセージのメッセージの種類が選択されているなどを確認してください。 **TX - テキスト メッセージ (864)**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-345">Verify that the message type of the test message is selected, for example, **TX - Text Message (864)**.</span></span>|  
        |<span data-ttu-id="e0ba2-346">**[GS2]**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-346">**GS2**</span></span>|<span data-ttu-id="e0ba2-347">入力**01**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-347">Enter **01**.</span></span>|  
        |<span data-ttu-id="e0ba2-348">**[GS3]**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-348">**GS3**</span></span>|<span data-ttu-id="e0ba2-349">入力**7654321**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-349">Enter **7654321**.</span></span>|  
        |<span data-ttu-id="e0ba2-350">**GS4**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-350">**GS4**</span></span>|<span data-ttu-id="e0ba2-351">日付の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-351">Select the date format that you want.</span></span> <span data-ttu-id="e0ba2-352">選択**CCYYMMDD**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-352">Select **CCYYMMDD**.</span></span> <span data-ttu-id="e0ba2-353">**注:**ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-353">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="e0ba2-354">ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-354">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="e0ba2-355">**GS5**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-355">**GS5**</span></span>|<span data-ttu-id="e0ba2-356">時刻の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-356">Select the time format that you want.</span></span> <span data-ttu-id="e0ba2-357">選択**HHMMSSdd**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-357">Select **HHMMSSdd**.</span></span>|  
        |<span data-ttu-id="e0ba2-358">**GS7**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-358">**GS7**</span></span>|<span data-ttu-id="e0ba2-359">選択**T - 運輸データ調整委員会 (TDCC)**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-359">Select **T - Transportation Data Coordinating Committee (TDCC)**.</span></span>|  
        |<span data-ttu-id="e0ba2-360">**GS8**</span><span class="sxs-lookup"><span data-stu-id="e0ba2-360">**GS8**</span></span>|<span data-ttu-id="e0ba2-361">EDI のバージョンとして入力されたことを確認してください。 **00401**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-361">Verify that the EDI version has been entered as **00401**.</span></span>|  
  
8.  <span data-ttu-id="e0ba2-362">次のタスクを実行、 **Contoso が Fabrikam ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-362">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-363">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-363">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="e0ba2-364">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-364">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  
  
    1.  <span data-ttu-id="e0ba2-365">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-365">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e0ba2-366">このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**1234567**、 **ISA7**に**ZZ。**、および**ISA8**に**7654321**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-366">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **1234567**, **ISA7** to **ZZ**, and **ISA8** to **7654321**.</span></span>  
  
9. <span data-ttu-id="e0ba2-367">**[適用]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-367">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="e0ba2-368">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-368">Click **OK**.</span></span> <span data-ttu-id="e0ba2-369">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-369">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="e0ba2-370">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-370">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="e0ba2-371">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="e0ba2-371">Testing the Walkthrough</span></span>  
 <span data-ttu-id="e0ba2-372">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-372">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-solution"></a><span data-ttu-id="e0ba2-373">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-373">To test the solution</span></span>  
  
1.  <span data-ttu-id="e0ba2-374">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender フォルダーにある Sender.csproj プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-374">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the Sender.csproj project in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender folder.</span></span>  
  
2.  <span data-ttu-id="e0ba2-375">HttpSender.cs で、次の行がコメント アウトされていないことを確認します (//Request Asynchronous MDN コメント行のすぐ下)。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-375">In HttpSender.cs, make sure that the following line is not commented out (immediately below the //Request Asynchronous MDN comment line):</span></span>  
  
    ```  
    Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
    ```  
  
3.  <span data-ttu-id="e0ba2-376">次の行がコメント アウトされていることを確認します (//Request Synchronous MDN コメント行のすぐ下)。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-376">Make sure that the following line is commented out (immediately below the //Request Synchronous MDN comment line):</span></span>  
  
    ```  
    Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
    ```  
  
4.  <span data-ttu-id="e0ba2-377">このプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-377">Build this project.</span></span>  
  
5.  <span data-ttu-id="e0ba2-378">Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-378">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial.</span></span> <span data-ttu-id="e0ba2-379">メモ帳で X12_00401_864.edi を開きます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-379">Open X12_00401_864.edi in Notepad.</span></span> <span data-ttu-id="e0ba2-380">Disposition-Notification-Options ヘッダーを定義している行を削除し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-380">Delete the line defining the Disposition-Notification-Options header, and then save the file.</span></span>  
  
6.  <span data-ttu-id="e0ba2-381">Windows エクスプローラで、移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 tutorial \sender\bin\debug 実行と**Sender.exe**です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-381">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug and execute **Sender.exe**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ba2-382">このインスタンスで Sender.exe を実行すると、メッセージ X12_00401_864.edi が Contoso 仮想ディレクトリ (BTS http 受信場所) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-382">Running Sender.exe in this instance posts the message X12_00401_864.edi to the Contoso virtual directory (the BTS http receive location).</span></span>  
  
7.  <span data-ttu-id="e0ba2-383">作成した Contoso ローカル フォルダーを開き、EDI ペイロードを (\EDI_to_Contoso) に送信します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-383">Open the Contoso local folder that you created to send the EDI payload to (\EDI_to_Contoso).</span></span> <span data-ttu-id="e0ba2-384">フォルダーに .XML ファイルがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-384">Verify that there is a .XML file in the folder.</span></span> <span data-ttu-id="e0ba2-385">XML ファイルを開き、そのファイルに 864 トランザクション セットが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-385">Open the XML file and verify that it contains an 864 transaction set.</span></span>  
  
8.  <span data-ttu-id="e0ba2-386">Fabrikam ローカル フォルダーを開きます。MDN はここに返されます。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-386">Open the Fabrikam local folder to which the MDN is returned.</span></span> <span data-ttu-id="e0ba2-387">Windows エクスプローラで、移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_MDNToFabrikam です。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-387">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_MDNToFabrikam.</span></span> <span data-ttu-id="e0ba2-388">メモ帳でメッセージ ファイルを開き、MDN を確認します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-388">Open the message file in a notepad and verify the MDN.</span></span> <span data-ttu-id="e0ba2-389">MDN AS2-From が Contoso で、AS2-To が Fabrikam であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-389">Verify that in the MDN AS2-From is Contoso and AS2-To is Fabrikam.</span></span>  
  
9. <span data-ttu-id="e0ba2-390">メモ帳でテスト メッセージ X12_00401_864.edi を開き、\EDI_to_Contoso ローカル フォルダー内の出力メッセージのトランザクション セットが、X12_00401_864.edi 入力メッセージのトランザクション セットに対応していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0ba2-390">Open the test message X12_00401_864.edi in Notepad, and verify that the transaction set in the output message in the \EDI_to_Contoso local folder corresponds to the transaction set in the X12_00401_864.edi input message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ba2-391">参照</span><span class="sxs-lookup"><span data-stu-id="e0ba2-391">See Also</span></span>  
 [<span data-ttu-id="e0ba2-392">開発と BizTalk Server AS2 ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="e0ba2-392">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)
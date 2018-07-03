---
title: 'チュートリアル (AS2): 同期 MDN による AS2 経由で EDI の受信 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b63395f-03f4-45e8-a68a-9bbbd8dfa344
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 971620284a8058663f7c054cd6286cbd01d81d84
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024016"
---
# <a name="walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn"></a><span data-ttu-id="052b8-102">チュートリアル (AS2): 同期 MDN による AS2 経由での EDI の受信</span><span class="sxs-lookup"><span data-stu-id="052b8-102">Walkthrough (AS2): Receiving EDI over AS2 with a Synchronous MDN</span></span>
<span data-ttu-id="052b8-103">このチュートリアルでは、AS2 トランスポート経由で EDI メッセージを受信して同期 MDN を返すソリューションを作成する、一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="052b8-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDI messages over AS2 transport, returning synchronous MDNs.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="052b8-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="052b8-104">Prerequisites</span></span>  
 <span data-ttu-id="052b8-105">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="052b8-105">The following are prerequisites for performing the procedures in this topic:</span></span>  

- <span data-ttu-id="052b8-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  

- <span data-ttu-id="052b8-107">チュートリアルを実行するコンピューターには、インターネット インフォメーション サービス (IIS) 7 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-107">The computer that runs the walkthrough must have Internet Information Services (IIS) 7 installed.</span></span>  

- <span data-ttu-id="052b8-108">チュートリアルを実行するコンピューターに 64 ビット版の Windows がインストールされている場合は、BizTalk ホストが 32 ビットのみとマークされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-108">If the computer that runs the walkthrough is installed with a 64-bit version of Windows, you must ensure that the BizTalk hosts are marked as 32-bit only.</span></span> <span data-ttu-id="052b8-109">アプリケーション プールの設定、IIS が有効にする 32 ビット アプリケーションの設定を確認する必要がありますも**True**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-109">You must also ensure IIS has the Enable 32-Bit Application Setting for the Application Pools set to **True**.</span></span> <span data-ttu-id="052b8-110">詳細については、次を参照してください。[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="052b8-110">For more information, see [Tutorial 3: AS2 Tutorial](../core/tutorial-3-as2-tutorial.md).</span></span>  

## <a name="how-the-solution-receives-an-edias2-message-and-returns-a-synchronous-mdn"></a><span data-ttu-id="052b8-111">ソリューションで EDI/AS2 メッセージを受信して同期 MDN を返す方法</span><span class="sxs-lookup"><span data-stu-id="052b8-111">How the Solution Receives an EDI/AS2 Message and Returns a Synchronous MDN</span></span>  
 <span data-ttu-id="052b8-112">このソリューションが実行する内容は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="052b8-112">The solution does the following:</span></span>  

1. <span data-ttu-id="052b8-113">EDI が Fabrikam 取引先から HTTP 経由でインターチェンジし、ediint/as2 からインターチェンジをデコード含まれている AS2 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="052b8-113">Receives an AS2 message containing an EDI interchange over HTTP from the trading partner Fabrikam, and decode the interchange from EDIINT/AS2.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-114">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="052b8-114">The events in this list may not occur in the order shown.</span></span>  

2. <span data-ttu-id="052b8-115">要求 - 応答の受信ポートを使用して取引先に同期 MDN を返します。</span><span class="sxs-lookup"><span data-stu-id="052b8-115">Returns a synchronous MDN to the trading partner using the request-response receive port.</span></span>  

3. <span data-ttu-id="052b8-116">内部 XML 形式で、インターチェンジの EDI 形式を変換し、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="052b8-116">Converts the EDI format of the interchange to internal XML format, and drops it in the MessageBox.</span></span>  

4. <span data-ttu-id="052b8-117">PassThruTransmit パイプラインを持つ FILE 送信ポートが、メッセージ XML ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="052b8-117">A FILE send port with a PassThruTransmit pipeline picks up the message XML file.</span></span>  

5. <span data-ttu-id="052b8-118">送信ポートは、Contoso パーティのフォルダーに EDI インターチェンジの XML ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="052b8-118">The send port sends the EDI interchange XML file to a folder at the Contoso party.</span></span>  

   <span data-ttu-id="052b8-119">次の図は、このソリューションのアーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="052b8-119">The following figure shows the architecture for this solution.</span></span>  

   <span data-ttu-id="052b8-120">![同期 MDN による AS2 の受信](../core/media/4ff20070-1c36-42e5-af14-832771d63b88.gif "4ff20070-1c36-42e5-af14-832771d63b88")</span><span class="sxs-lookup"><span data-stu-id="052b8-120">![AS2 receiving with a synchronous MDN](../core/media/4ff20070-1c36-42e5-af14-832771d63b88.gif "4ff20070-1c36-42e5-af14-832771d63b88")</span></span>  

## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="052b8-121">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="052b8-121">The Functionality in this Solution</span></span>  
 <span data-ttu-id="052b8-122">このチュートリアルの機能には、以下の条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-122">The following applies to the functionality of this walkthrough:</span></span>  

-   <span data-ttu-id="052b8-123">EDI 受信確認は生成されません。</span><span class="sxs-lookup"><span data-stu-id="052b8-123">An EDI acknowledgment is not generated.</span></span> <span data-ttu-id="052b8-124">方法については、EDI 受信確認を生成する[チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認を返す](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)します。</span><span class="sxs-lookup"><span data-stu-id="052b8-124">Generating an EDI acknowledgment is demonstrated in [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span> <span data-ttu-id="052b8-125">「AS2 トランスポート経由で EDI 受信確認を送信する[チュートリアル (AS2): 同期 MDN による AS2 経由で送信する EDI](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md)します。</span><span class="sxs-lookup"><span data-stu-id="052b8-125">Sending an EDI acknowledgment over AS2 transport is described in [Walkthrough (AS2): Sending EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-sending-edi-over-as2-with-a-synchronous-mdn.md).</span></span>  

-   <span data-ttu-id="052b8-126">このソリューションは、EDIFACT エンコードではなく X12 エンコードを使用するインターチェンジを対象に設計されています。</span><span class="sxs-lookup"><span data-stu-id="052b8-126">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="052b8-127">EDIFACT エンコードに使用される構成は、X12 エンコードに使用される構成とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="052b8-127">The configuration used for EDIFACT encoding is closely parallel to that used for X12 encoding.</span></span>  

-   <span data-ttu-id="052b8-128">EDI の種類の検証および拡張された検証は、受信インターチェンジに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-128">EDI type and extended validation will be performed on the incoming interchange.</span></span>  

-   <span data-ttu-id="052b8-129">AS2 レポートおよび EDI レポートが有効になり、インターチェンジの状態レポートに表示するトランザクション セットが保存されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-129">AS2 and EDI reporting will be enabled, and transaction sets will be saved for viewing from the interchange status report.</span></span>  

-   <span data-ttu-id="052b8-130">このソリューションは、否認不可データベースに署名、圧縮、暗号化、およびメッセージ ストレージを構成しません。</span><span class="sxs-lookup"><span data-stu-id="052b8-130">This solution does not configure signing, compression, encryption, or message storage in the non-repudiation database.</span></span> <span data-ttu-id="052b8-131">これらのプロパティを構成する手順については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="052b8-131">For procedures on configuring those properties, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  

## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="052b8-132">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="052b8-132">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="052b8-133">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="052b8-133">The procedures required for this solution include the following:</span></span>  

- <span data-ttu-id="052b8-134">必要なメッセージ スキーマを使用して BizTalk プロジェクトをビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="052b8-134">Build and deploy a BizTalk project with the required message schema, making the schema available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  

- <span data-ttu-id="052b8-135">AS2 メッセージの受信に使用する BTS ISAPI フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="052b8-135">Enable the BTS ISAPI filter used in receiving the AS2 message.</span></span>  

- <span data-ttu-id="052b8-136">Fabrikam からの AS2 メッセージを受信する Contoso 仮想ディレクトリを、受信場所で構成したとおりに作成します。</span><span class="sxs-lookup"><span data-stu-id="052b8-136">Create a Contoso virtual directory that receives the AS2 message from Fabrikam, as configured in the receive location.</span></span>  

- <span data-ttu-id="052b8-137">Contoso 仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="052b8-137">Specify that the Contoso virtual directory is not managed by Windows SharePoint Services.</span></span>  

- <span data-ttu-id="052b8-138">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の静的な双方向 HTTP 受信ポートを作成して、取引先から EDI インターチェンジが含まれた AS2 メッセージを受信し、MDN 応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="052b8-138">Create a static two-way HTTP receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the AS2 message containing the EDI interchange from the trading partner, and send the MDN response.</span></span> <span data-ttu-id="052b8-139">受信パイプラインとして AS2EDIReceive パイプラインを構成し、送信パイプラインとして AS2Send パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="052b8-139">Configure the receive pipeline to be the AS2EDIReceive pipeline and the send pipeline to be the AS2Send pipeline.</span></span>  

- <span data-ttu-id="052b8-140">静的な一方向 FILE 送信ポートを作成し、EDI ペイロード (XML 形式) をローカル フォルダーにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="052b8-140">Create a static one-way FILE send port to route the EDI payload (in XML format) to a local folder.</span></span> <span data-ttu-id="052b8-141">ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="052b8-141">Create the local folder.</span></span>  

- <span data-ttu-id="052b8-142">Fabrikam および Contoso の両方にパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="052b8-142">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  

- <span data-ttu-id="052b8-143">両方の取引先に対して、それぞれビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="052b8-143">Create a business profile each for both the trading parties.</span></span>  

- <span data-ttu-id="052b8-144">Fabrikam および Contoso のビジネス プロファイル間に AS2 アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="052b8-144">Create an AS2 agreement between the business profiles for Fabrikam and Contoso.</span></span> <span data-ttu-id="052b8-145">AS2 アグリーメントには AS2 メッセージを送信するためのプロパティが設定されており、AS2 アグリーメントは応答として同期 MDN を受信します。</span><span class="sxs-lookup"><span data-stu-id="052b8-145">The AS2 agreement would contain properties to send an AS2 message, and receive a synchronous MDN in return.</span></span>  

- <span data-ttu-id="052b8-146">Fabrikam および Contoso のビジネス プロファイル間に、X12 メッセージを受信する X12 アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="052b8-146">Create an X12 agreement between the business profiles for Fabrikam and Contoso to receive X12 messages.</span></span>  

- <span data-ttu-id="052b8-147">AS2 チュートリアル ファイルの一部として同梱されている HTTP 送信者ユーティリティを使用して、このソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="052b8-147">Test the solution by using the HTTP Sender utility that is shipped as part of the AS2 tutorial files.</span></span> <span data-ttu-id="052b8-148">このユーティリティは、AS2 トランスポートを経由して、EDI インターチェンジが含まれた AS2 テスト メッセージを送信します (この X12_00401_864-Sync.edi は AS2 チュートリアルにも同梱されています)。</span><span class="sxs-lookup"><span data-stu-id="052b8-148">This utility sends a test AS2 message containing an EDI interchange over AS2 transport (X12_00401_864-Sync.edi, also shipped with the AS2 tutorial).</span></span> <span data-ttu-id="052b8-149">HTTP 送信者とテスト メッセージは、チュートリアル内のバージョンから新しいバージョンに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-149">You must modify both the HTTP Sender and the test message from the versions that are in the tutorial.</span></span> <span data-ttu-id="052b8-150">これらの変更については、関連する以下のセクションで説明しています。</span><span class="sxs-lookup"><span data-stu-id="052b8-150">These changes are described in the relevant sections below.</span></span>  

### <a name="configuring-the-walkthrough"></a><span data-ttu-id="052b8-151">チュートリアルの構成</span><span class="sxs-lookup"><span data-stu-id="052b8-151">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="052b8-152">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="052b8-152">This section describes the procedures to configure the walkthrough.</span></span>  

##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="052b8-153">メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="052b8-153">To deploy the message schema</span></span>  

1. <span data-ttu-id="052b8-154">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="052b8-154">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the project [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-155">このプロジェクトは AS2 チュートリアルに付属し、テスト メッセージと共に使用する 864 スキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="052b8-155">This project, which is shipped for the AS2 tutorial, includes an 864 schema for use with the test message.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-156">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="052b8-156">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="052b8-157">そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。</span><span class="sxs-lookup"><span data-stu-id="052b8-157">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  

2. <span data-ttu-id="052b8-158">右クリックし、**スキーマ**ソリューション エクスプ ローラーでプロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-158">Right-click the **Schemas** project in the Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="052b8-159">をクリックして、**署名** タブで、プロジェクト デザイナー、**アセンブリに署名**チェック ボックスをオンし、ドロップダウン リストから選択します**新規**を作成するために必要な値を指定し、厳密な名前キー ファイルです。</span><span class="sxs-lookup"><span data-stu-id="052b8-159">Click the **Signing** tab in the project designer, check the **Sign the Assembly** checkbox, and from the drop-down, select **New** and provide the necessary values to create a strong name key file.</span></span> <span data-ttu-id="052b8-160">変更を保存し、プロジェクトのプロパティ ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="052b8-160">Save the changes and close the project properties window.</span></span>  

3. <span data-ttu-id="052b8-161">Schemas.btproj をビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="052b8-161">Build and deploy Schemas.btproj.</span></span>  

##### <a name="to-enable-the-bts-isapi-filter"></a><span data-ttu-id="052b8-162">BTS ISAPI フィルターを有効にするには</span><span class="sxs-lookup"><span data-stu-id="052b8-162">To enable the BTS ISAPI Filter</span></span>  

1. <span data-ttu-id="052b8-163">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="052b8-163">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  

   > [!TIP]
   >  <span data-ttu-id="052b8-164">オペレーティング システムによっては、管理ツールの [スタート] メニュー オプションを利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-164">Depending on the operating system, the Administrative Tools start menu option may not be available.</span></span> <span data-ttu-id="052b8-165">このような場合は、次のようにクリックします。**開始**、 をクリック**実行**、入力と`inetmgr`をインターネット インフォメーション サービス (IIS) マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="052b8-165">In such cases, click **Start**, click **Run**, and enter `inetmgr` to open Internet Information Services (IIS) Manager.</span></span>  

2. <span data-ttu-id="052b8-166">ルート Web サーバーのエントリを選択し、[、**機能ビュー**、ダブルクリック**ハンドラー マッピング**し、**アクション**ペイン] をクリックします**スクリプトマップの追加**.</span><span class="sxs-lookup"><span data-stu-id="052b8-166">Select the root Web Server entry and in the **Features View**, double click **Handler Mappings** and then in the **Actions** pane click **Add Script Map**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-167">Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子の Web サイトに適用するには、このマッピングが発生します。</span><span class="sxs-lookup"><span data-stu-id="052b8-167">Configuring the script mapping at the Web Server level will cause this mapping to apply to all child Web Sites.</span></span> <span data-ttu-id="052b8-168">特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="052b8-168">If you wish to restrict the mapping to a specific Web Site or Virtual Folder, select the target site or folder instead of the Web Server.</span></span>  

3. <span data-ttu-id="052b8-169">**スクリプト マップの追加** ダイアログ ボックスに、入力`BtsHttpReceive.dll`で、**要求パス**フィールド。</span><span class="sxs-lookup"><span data-stu-id="052b8-169">In the **Add Script Map** dialog box, enter `BtsHttpReceive.dll` in the **Request path** field.</span></span>  

4. <span data-ttu-id="052b8-170">**実行可能ファイル**フィールドに、をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive します。</span><span class="sxs-lookup"><span data-stu-id="052b8-170">In the **Executable** field, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="052b8-171">BtsHttpReceive.dll を選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-171">Select BtsHttpReceive.dll and click **OK**.</span></span>  

5. <span data-ttu-id="052b8-172">入力`BizTalk HTTP Receive`で、**名前**フィールドをクリックして**要求の制限**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-172">Enter `BizTalk HTTP Receive` in the **Name** field, and then click **Request Restrictions**.</span></span>  

6. <span data-ttu-id="052b8-173">**要求の制限**ダイアログ ボックスで、**動詞**タブを選び**次の動詞のいずれか**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-173">In the **Request Restrictions** dialog box, select the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="052b8-174">入力`POST`動詞として。</span><span class="sxs-lookup"><span data-stu-id="052b8-174">Enter `POST` as the verb .</span></span>  

7. <span data-ttu-id="052b8-175">**アクセス**] タブで [**スクリプト**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-175">On the **Access** tab, select **Script** and then click **OK**.</span></span>  

8. <span data-ttu-id="052b8-176">をクリックして **[ok]** ISAPI 拡張を許可するメッセージが表示されたら、クリックと**はい**。</span><span class="sxs-lookup"><span data-stu-id="052b8-176">Click **OK** and when prompted to allow the ISAPI extension, click **Yes**.</span></span>  

##### <a name="to-configure-the-contoso-web-page"></a><span data-ttu-id="052b8-177">Contoso Web ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="052b8-177">To configure the Contoso Web page</span></span>  

1. <span data-ttu-id="052b8-178">IIS マネージャーで、右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-178">In IIS Manager, right-click **Application Pools** and select **Add Application Pool**.</span></span>  

2. <span data-ttu-id="052b8-179">**アプリケーション プールの追加** ダイアログ ボックスに、入力**BizTalkAppPool**で**名前**、し、 **.NET Framework v4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="052b8-179">In the **Add Application Pool** dialog box, enter **BizTalkAppPool** in **Name**, and then select **.NET Framework V4.0.30210** in the **.NET Framework version** dropdown list.</span></span> <span data-ttu-id="052b8-180">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-180">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-181">コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-181">The version number may vary depending on the version of [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] installed on the machine.</span></span>  

3. <span data-ttu-id="052b8-182">選択**アプリケーション プール**、機能ビューの選択で**BizTalkAppPool**、順にクリックします**詳細設定**で、**アクション**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="052b8-182">Select **Application Pools**, in the Features View select **BizTalkAppPool**, and then click **Advanced Settings** in the **Actions** pane.</span></span>  

4. <span data-ttu-id="052b8-183">**詳細設定**ダイアログ ボックスで、 **Identity**  をクリックし、**省略記号 (...)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-183">In the **Advanced Settings** dialog box, select **Identity** and then click the **ellipsis (…)** button.</span></span>  

5. <span data-ttu-id="052b8-184">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-184">In the **Application Pool Identity** dialog box, select **Custom account** and then click **Set**.</span></span>  

6. <span data-ttu-id="052b8-185">入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力します**パスワードの確認入力**をクリックして **。OK** 3 回の IIS マネージャーに戻ります。</span><span class="sxs-lookup"><span data-stu-id="052b8-185">Enter the **User name** and **Password** for a user account that is a member of the administrators group, enter the password in **Confirm password** and then click **OK** three times to return to the IIS Manager.</span></span>  

7. <span data-ttu-id="052b8-186">IIS マネージャーで、開く、**サイト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="052b8-186">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="052b8-187">右クリックし、**既定の Web サイト**ノードをクリックして**アプリケーションの追加**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-187">Right-click the **Default Web Site** node, and then select **Add Application**.</span></span>  

8. <span data-ttu-id="052b8-188">**アプリケーションの追加** ダイアログ ボックスに、入力**Contoso**で、**エイリアス**テキスト ボックス、およびクリック**選択**。</span><span class="sxs-lookup"><span data-stu-id="052b8-188">In the **Add Application** dialog box, enter **Contoso** in the **Alias** text box, and then click **Select**.</span></span>  

9. <span data-ttu-id="052b8-189">**アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-189">In the **Select Application Pool** dialog box, select **BizTalkAppPool** and click **OK**.</span></span>  

10. <span data-ttu-id="052b8-190">**物理パス**、クリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive します。</span><span class="sxs-lookup"><span data-stu-id="052b8-190">For the **Physical Path**, click the **ellipsis (…)** button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span>  

11. <span data-ttu-id="052b8-191">をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="052b8-191">Click **Test Settings** and verify that there are no errors displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="052b8-192">**[閉じる]** をクリックし、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-192">Click **Close**, and then click **OK**.</span></span>  

12. <span data-ttu-id="052b8-193">IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-193">In IIS Manager, select the Contoso virtual directory and in the **Features View**, double-click **Authentication**.</span></span>  

13. <span data-ttu-id="052b8-194">**認証**] ページで、[**匿名認証**いることを確認し、**状態**は**有効**。</span><span class="sxs-lookup"><span data-stu-id="052b8-194">In the **Authentication** page, select **Anonymous Authentication** and verify that the **Status** is **Enabled**.</span></span> <span data-ttu-id="052b8-195">場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="052b8-195">If the **Status** is **Disabled**, click **Enable** in the **Actions** pane.</span></span>  

##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a><span data-ttu-id="052b8-196">仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定するには</span><span class="sxs-lookup"><span data-stu-id="052b8-196">To specify that your virtual directory is not managed by Windows SharePoint Services</span></span>  

1.  <span data-ttu-id="052b8-197">コンピューターに Windows SharePoint Services がインストールされて場合、 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**をクリックして**SharePoint 3.0 サーバーの全体管理**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-197">If Windows SharePoint Services is installed on your computer, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint 3.0 Central Administration**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="052b8-198">この手順は、チュートリアルを設定するコンピューター上に Windows SharePoint Server がインストールされている場合に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-198">This procedure is required if Windows SharePoint Server is installed on the same computer that you are setting the walkthrough up on.</span></span> <span data-ttu-id="052b8-199">実行する場合は、IIS 仮想ディレクトリが Windows SharePoint Server の管理対象から除外されるように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-199">In that case, you must specify that your IIS virtual directory is not being managed by Windows SharePoint Server.</span></span>  

2.  <span data-ttu-id="052b8-200">**サーバーの全体管理** ページ **サーバーの全体管理**、 をクリックして**アプリケーション管理**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-200">On the **Central Administration** page, under **Central Administration**, click **Application Management**.</span></span>  

3.  <span data-ttu-id="052b8-201">**アプリケーション管理**] ページで [**管理パスの定義**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-201">On the **Application Management** page, click **Define managed paths**.</span></span>  

4.  <span data-ttu-id="052b8-202">**管理パスの定義**] ページ [**新しいパスを追加**、し、**パス**テキスト ボックスに、入力**Contoso**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-202">In the **Define Managed Paths** page, under **Add a New Path**, and in the **Path** text box, enter **Contoso**.</span></span> <span data-ttu-id="052b8-203">[**型**、] をクリックして**エクスクルード パス**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-203">Under **Type**, click **Excluded Path**, and then click **OK**.</span></span>  

##### <a name="to-create-a-receive-port-to-receive-the-edi-over-as2-message-and-return-an-mdn"></a><span data-ttu-id="052b8-204">EDI over AS2 メッセージを受信して MDN を返す受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="052b8-204">To create a receive port to receive the EDI over AS2 message and return an MDN</span></span>  

1. <span data-ttu-id="052b8-205">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**順にクリックします**要求-応答の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-205">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Request-Response Receive Port**.</span></span>  

2. <span data-ttu-id="052b8-206">受信ポートの名前を指定し、をクリックし、**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="052b8-206">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  

3. <span data-ttu-id="052b8-207">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-207">Click **New**.</span></span>  

4. <span data-ttu-id="052b8-208">[受信場所の名前**HTTP**の**型**、] をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="052b8-208">Name the receive location, select **HTTP** for **Type**, and then click **Configure**.</span></span>  

5. <span data-ttu-id="052b8-209">**仮想ディレクトリと ISAPI 拡張**、入力`/Contoso/BTSHTTPReceive.dll`します。</span><span class="sxs-lookup"><span data-stu-id="052b8-209">For **Virtual directory plus ISAPI extension**, enter `/Contoso/BTSHTTPReceive.dll`.</span></span>  

6. <span data-ttu-id="052b8-210">選択、**失敗した要求を中断**チェック ボックスをオンにして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-210">Select the **Suspend failed requests** check box, and click **OK**.</span></span>  

7. <span data-ttu-id="052b8-211">**受信パイプライン**、 **AS2EDIReceive**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-211">For **Receive pipeline**, select **AS2EDIReceive**.</span></span>  

8. <span data-ttu-id="052b8-212">**送信パイプライン**、 **AS2Send**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-212">For **Send pipeline**, select **AS2Send**.</span></span>  

9. <span data-ttu-id="052b8-213">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="052b8-213">Click **OK**, and then click **OK** again.</span></span>  

10. <span data-ttu-id="052b8-214">**受信場所**、BizTalk Server 管理コンソールのウィンドウは、受信場所を右クリックし、をクリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-214">In the **Receive Locations** pane of the BizTalk Server Administration Console, right-click the receive location, and then click **Enable**.</span></span>  

##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a><span data-ttu-id="052b8-215">EDI ペイロードをローカル フォルダーに送信する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="052b8-215">To create a send port to send the EDI payload to a local folder</span></span>  

1. <span data-ttu-id="052b8-216">Windows エクスプ ローラーでという名前のローカル フォルダーを作成**EDI_to_Contoso** EDI ペイロードを送信します。</span><span class="sxs-lookup"><span data-stu-id="052b8-216">In Windows Explorer, create a local folder named **EDI_to_Contoso** to send the EDI payload to.</span></span>  

2. <span data-ttu-id="052b8-217">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-217">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  

3. <span data-ttu-id="052b8-218">**送信ポートのプロパティ**ダイアログ ボックスで、名前、送信ポートにたとえば、 **Send_Payload**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-218">In the **Send Port Properties** dialog box, name your send port, for example, **Send_Payload**.</span></span> <span data-ttu-id="052b8-219">選択**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-219">Select **FILE** for **Type**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="052b8-220">**FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**を参照して選択、 **EDI_to_Contoso**手順 1. で作成したフォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="052b8-220">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select the **EDI_to_Contoso** folder that you created in step 1.</span></span> <span data-ttu-id="052b8-221">まま**ファイル名**として **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-221">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="052b8-222">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-222">Click **OK**.</span></span>  

5. <span data-ttu-id="052b8-223">**送信パイプライン**ドロップダウン リストで、既定**PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-223">For the **Send Pipeline** drop-down, accept the default **PassThruTransmit**.</span></span>  

6. <span data-ttu-id="052b8-224">クリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="052b8-224">Click **Filters** in the console tree.</span></span> <span data-ttu-id="052b8-225">**プロパティ**、入力**BTS します。MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-225">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="052b8-226">**演算子**、入力 **==** します。</span><span class="sxs-lookup"><span data-stu-id="052b8-226">For **Operator**, enter **==**.</span></span> <span data-ttu-id="052b8-227">**値**、メッセージのメッセージの種類を入力`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`します。</span><span class="sxs-lookup"><span data-stu-id="052b8-227">For **Value**, enter the message type for your message, `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  

7. <span data-ttu-id="052b8-228">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-228">Click **OK**.</span></span>  

8. <span data-ttu-id="052b8-229">**送信ポート**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、送信ポートを右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-229">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the send port, and then click **Start**.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="052b8-230">Fabrikam のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="052b8-230">To create a party and a business profile for Fabrikam</span></span>  

1. <span data-ttu-id="052b8-231">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-231">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="052b8-232">パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="052b8-232">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-233">選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="052b8-233">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="052b8-234">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="052b8-234">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="052b8-235">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="052b8-235">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="052b8-236">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-236">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="052b8-237">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力 **[fabrikam_profile]** で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="052b8-237">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-238">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-238">When you create a party, a profile is also created.</span></span> <span data-ttu-id="052b8-239">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="052b8-239">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="052b8-240">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-240">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="052b8-241">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="052b8-241">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="052b8-242">Contoso のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="052b8-242">To create a party and a business profile for Contoso</span></span>  

1. <span data-ttu-id="052b8-243">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-243">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="052b8-244">パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="052b8-244">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-245">選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="052b8-245">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="052b8-246">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="052b8-246">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="052b8-247">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="052b8-247">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="052b8-248">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-248">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="052b8-249">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="052b8-249">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-250">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-250">When you create a party, a profile is also created.</span></span> <span data-ttu-id="052b8-251">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="052b8-251">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="052b8-252">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-252">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="052b8-253">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="052b8-253">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a><span data-ttu-id="052b8-254">2 つのビジネス プロファイル間で AS2 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="052b8-254">To create an AS2 agreement between the two business profiles</span></span>  

1.  <span data-ttu-id="052b8-255">右クリック**fabrikam_profile**、 をポイント**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-255">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2.  <span data-ttu-id="052b8-256">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="052b8-256">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3.  <span data-ttu-id="052b8-257">**プロトコル**ドロップダウン リストで、 **AS2**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-257">From the **Protocol** drop-down list, select **AS2**.</span></span>  

4.  <span data-ttu-id="052b8-258">**2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Contoso**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-258">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5.  <span data-ttu-id="052b8-259">**2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-259">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

     <span data-ttu-id="052b8-260">2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは、一方向の AS2 アグリーメントの構成用です。</span><span class="sxs-lookup"><span data-stu-id="052b8-260">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  

6.  <span data-ttu-id="052b8-261">**全般** タブで、**全般プロパティ**ページで、**共通のホスト設定**セクションで、**レポートをオン**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-261">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**.</span></span>  

7.  <span data-ttu-id="052b8-262">次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。</span><span class="sxs-lookup"><span data-stu-id="052b8-262">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

    1.  <span data-ttu-id="052b8-263">**識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-263">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="052b8-264">**AS2-から**、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="052b8-264">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="052b8-265">**AS2-To**、入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="052b8-265">For **AS2- To**, enter `Contoso`.</span></span>  

8.  <span data-ttu-id="052b8-266">次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。</span><span class="sxs-lookup"><span data-stu-id="052b8-266">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="052b8-267">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="052b8-267">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="052b8-268">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります **[as2_from]** と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-268">To successfully create an agreement, both one-way agreement tabs must have values defined for **AS2_From** and **AS2-To**.</span></span>  

    1.  <span data-ttu-id="052b8-269">**識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-269">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="052b8-270">**AS2-から**、入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="052b8-270">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="052b8-271">**AS2-To**、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="052b8-271">For **AS2- To**, enter `Fabrikam`.</span></span>  

9. <span data-ttu-id="052b8-272">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-272">Click **Apply**.</span></span>  

10. <span data-ttu-id="052b8-273">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-273">Click **OK**.</span></span> <span data-ttu-id="052b8-274">新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="052b8-274">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="052b8-275">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="052b8-275">The newly added agreement is enabled by default.</span></span>  

##### <a name="to-create-an-x12-agreement-between-the-two-business-profiles"></a><span data-ttu-id="052b8-276">2 つのビジネス プロファイルの間に X12 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="052b8-276">To create an X12 agreement between the two business profiles</span></span>  

1. <span data-ttu-id="052b8-277">右クリック**fabrikam_profile**、 をポイント**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-277">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="052b8-278">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="052b8-278">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3. <span data-ttu-id="052b8-279">**プロトコル**ドロップダウン リストで、 **X12**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-279">From the **Protocol** drop-down list, select **X12**.</span></span>  

4. <span data-ttu-id="052b8-280">**2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Contoso**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-280">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5. <span data-ttu-id="052b8-281">**2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-281">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="052b8-282">2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは一方向 X12 アグリーメントを構成するためのものです。</span><span class="sxs-lookup"><span data-stu-id="052b8-282">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way X12 agreement.</span></span>  

6. <span data-ttu-id="052b8-283">**全般** タブで、**全般プロパティ**ページで、**共通のホスト設定**セクションで、**レポートをオン**、し、選択**メッセージ ペイロードを格納するレポートの**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-283">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  

7. <span data-ttu-id="052b8-284">次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。</span><span class="sxs-lookup"><span data-stu-id="052b8-284">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1. <span data-ttu-id="052b8-285">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応しています。</span><span class="sxs-lookup"><span data-stu-id="052b8-285">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="052b8-286"> では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="052b8-286"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="052b8-287">値と一致します**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**をアグリーメントのプロパティと、インターチェンジ ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="052b8-287">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="052b8-288">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="052b8-288">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="052b8-289">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-289">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="052b8-290">このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**7654321**、 **ISA7**に**ZZ。**、および**ISA8**に**1234567**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-290">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **7654321**, **ISA7** to **ZZ**, and **ISA8** to **1234567**.</span></span>  

   2. <span data-ttu-id="052b8-291">**検証**ページで、**インターチェンジの設定**セクションをご確認ください**重複している isa13 を確認**オプションが選択されていません。</span><span class="sxs-lookup"><span data-stu-id="052b8-291">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="052b8-292">オフにすると、**重複している isa13 を確認**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="052b8-292">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  

   3. <span data-ttu-id="052b8-293">使用するかどうかに付属する標準スキーマのいずれかの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の**ローカル ホスト設定**ページで、**トランザクション セットの設定**セクションでを使用するスキーマの名前空間を選択します。受信インターチェンジを処理します。</span><span class="sxs-lookup"><span data-stu-id="052b8-293">If you are using one of the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], on the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span>  


      |       <span data-ttu-id="052b8-294">プロパティ</span><span class="sxs-lookup"><span data-stu-id="052b8-294">Use this</span></span>       |                           <span data-ttu-id="052b8-295">目的</span><span class="sxs-lookup"><span data-stu-id="052b8-295">To do this</span></span>                            |
      |----------------------|-----------------------------------------------------------------|
      |     <span data-ttu-id="052b8-296">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="052b8-296">**Default**</span></span>      |                <span data-ttu-id="052b8-297">列のチェック ボックスをオンにします</span><span class="sxs-lookup"><span data-stu-id="052b8-297">Select the checkbox in the column</span></span>                |
      | <span data-ttu-id="052b8-298">**Target Namespace**</span><span class="sxs-lookup"><span data-stu-id="052b8-298">**Target Namespace**</span></span> | <span data-ttu-id="052b8-299">選択 **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>** します。</span><span class="sxs-lookup"><span data-stu-id="052b8-299">Select **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**.</span></span> |

      > [!NOTE]
      >  <span data-ttu-id="052b8-300">プロパティを設定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、受信 850 インターチェンジの処理に使用するスキーマを決定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="052b8-300">Setting the properties enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to determine the schema to be used in processing the incoming 850 interchange.</span></span> <span data-ttu-id="052b8-301">グリッド内の行に入力された [GS02] と [ST01] の値がインターチェンジに設定されている場合は、同じ行にあるターゲットの名前空間により、使用するスキーマが決定されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-301">If an interchange has the values of GS02 and ST01 that are entered on a line of the grid, then the target namespace for the same line will be used to determine the schema to be used.</span></span>  

8. <span data-ttu-id="052b8-302">次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。</span><span class="sxs-lookup"><span data-stu-id="052b8-302">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-303">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="052b8-303">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="052b8-304">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-304">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  

   1.  <span data-ttu-id="052b8-305">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応しています。</span><span class="sxs-lookup"><span data-stu-id="052b8-305">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="052b8-306">このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**1234567**、 **ISA7**に**ZZ。**、および**ISA8**に**7654321**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-306">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **1234567**, **ISA7** to **ZZ**, and **ISA8** to **7654321**.</span></span>  

9. <span data-ttu-id="052b8-307">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-307">Click **Apply**.</span></span>  

10. <span data-ttu-id="052b8-308">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="052b8-308">Click **OK**.</span></span> <span data-ttu-id="052b8-309">新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="052b8-309">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="052b8-310">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="052b8-310">The newly added agreement is enabled by default.</span></span>  

### <a name="testing-the-walkthrough"></a><span data-ttu-id="052b8-311">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="052b8-311">Testing the Walkthrough</span></span>  
 <span data-ttu-id="052b8-312">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="052b8-312">This section provides information on how to test the walkthrough.</span></span>  

##### <a name="to-test-the-solution"></a><span data-ttu-id="052b8-313">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="052b8-313">To test the solution</span></span>  

1. <span data-ttu-id="052b8-314">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender フォルダーにある Sender.csproj プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="052b8-314">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the Sender.csproj project in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender folder.</span></span>  

2. <span data-ttu-id="052b8-315">HttpSender.cs で、次の行をコメント アウトします (//Request Asynchronous MDN コメント行のすぐ下)。</span><span class="sxs-lookup"><span data-stu-id="052b8-315">In HttpSender.cs, comment out the following line (immediately below the //Request Asynchronous MDN comment line):</span></span>  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
   ```  

3. <span data-ttu-id="052b8-316">次の行のコメント アウトを解除します (//Request Synchronous MDN コメント行のすぐ下)。</span><span class="sxs-lookup"><span data-stu-id="052b8-316">Uncomment out the following line (immediately below the //Request Synchronous MDN comment line):</span></span>  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
   ```  

4. <span data-ttu-id="052b8-317">このプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="052b8-317">Build this project.</span></span>  

5. <span data-ttu-id="052b8-318">Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial に移動します。</span><span class="sxs-lookup"><span data-stu-id="052b8-318">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial.</span></span> <span data-ttu-id="052b8-319">メモ帳で X12_00401_864-Sync.edi を開きます。</span><span class="sxs-lookup"><span data-stu-id="052b8-319">Open X12_00401_864-Sync.edi in Notepad.</span></span> <span data-ttu-id="052b8-320">Disposition-Notification-Options ヘッダーを定義している行を削除し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="052b8-320">Delete the line defining the Disposition-Notification-Options header, and then save the file.</span></span>  

6. <span data-ttu-id="052b8-321">コマンド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="052b8-321">Open a command window.</span></span> <span data-ttu-id="052b8-322">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug に移動します。</span><span class="sxs-lookup"><span data-stu-id="052b8-322">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug.</span></span> <span data-ttu-id="052b8-323">実行**Sender.exe**します。</span><span class="sxs-lookup"><span data-stu-id="052b8-323">Run **Sender.exe**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-324">このインスタンスで Sender.exe を実行すると、メッセージ X12_00401_864-sync.edi が Contoso 仮想ディレクトリ (BTS HTTP 受信場所) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-324">Running Sender.exe in this instance posts the message X12_00401_864-sync.edi to the Contoso virtual directory (the BTS HTTP receive location).</span></span>  

7. <span data-ttu-id="052b8-325">コマンド ウィンドウに MDN が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="052b8-325">Verify that an MDN is displayed in the command window.</span></span> <span data-ttu-id="052b8-326">MDN AS2-From が Contoso で、AS2-To が Fabrikam であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="052b8-326">Verify that in the MDN AS2-From is Contoso and AS2-To is Fabrikam.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="052b8-327">Sender.exe によってコマンド ウィンドウに MDN が表示されます。</span><span class="sxs-lookup"><span data-stu-id="052b8-327">Sender.exe displays the MDN in the command window.</span></span>  

8. <span data-ttu-id="052b8-328">EDI ペイロードを作成した Contoso ローカル フォルダーを開きます (**\EDI_to_Contoso**)。</span><span class="sxs-lookup"><span data-stu-id="052b8-328">Open the Contoso local folder that you create to send the EDI payload to (**\EDI_to_Contoso**).</span></span> <span data-ttu-id="052b8-329">フォルダーに .XML ファイルがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="052b8-329">Verify that there is a .XML file in the folder.</span></span> <span data-ttu-id="052b8-330">XML ファイルを開き、そのファイルに 864 トランザクション セットが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="052b8-330">Open the XML file and verify that it contains an 864 transaction set.</span></span>  

9. <span data-ttu-id="052b8-331">メモ帳でテスト メッセージ x12_00401_864-sync.edi を開き、トランザクション セット内の出力メッセージのことを確認、 **\EDI_to_Contoso**ローカル フォルダーは、トランザクションでは、x12_00401_864-sync.edi 入力セットに対応していますメッセージ。</span><span class="sxs-lookup"><span data-stu-id="052b8-331">Open the test message X12_00401_864-Sync.edi in Notepad, and verify that the transaction set in the output message in the **\EDI_to_Contoso** local folder corresponds to the transaction set in the X12_00401_864-Sync.edi input message.</span></span>  

## <a name="see-also"></a><span data-ttu-id="052b8-332">参照</span><span class="sxs-lookup"><span data-stu-id="052b8-332">See Also</span></span>  
 [<span data-ttu-id="052b8-333">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="052b8-333">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)
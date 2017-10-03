---
title: "チュートリアル (X12): EDI インターチェンジの受信と受信確認を送信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25d2b5f3-6bd1-413c-aace-e4dd71f80403
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79eb16ac77f2f1573735c36b19fa6aa68c001c76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-x12-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a><span data-ttu-id="0351d-102">チュートリアル (X12): EDI インターチェンジの受信と受信確認の送信</span><span class="sxs-lookup"><span data-stu-id="0351d-102">Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement</span></span>
<span data-ttu-id="0351d-103">このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して EDI インターチェンジの受信用のソリューションを作成する一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0351d-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDI interchanges using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0351d-104">このソリューションでは、ある取引先 (Fabrikam) から別の取引先 (Contoso) に EDI インターチェンジが送信されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-104">In this solution, an EDI interchange is sent from a trading partner, Fabrikam, to another trading partner, Contoso.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0351d-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="0351d-105">Prerequisites</span></span>  
 <span data-ttu-id="0351d-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0351d-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="how-the-solution-receives-edi-interchanges"></a><span data-ttu-id="0351d-107">ソリューションにより EDI インターチェンジを受信する方法</span><span class="sxs-lookup"><span data-stu-id="0351d-107">How the Solution Receives EDI Interchanges</span></span>  
 <span data-ttu-id="0351d-108">このソリューションは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="0351d-108">The solution will do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0351d-109">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0351d-109">The events in this list may not occur in the order shown.</span></span>  
  
1.  <span data-ttu-id="0351d-110">Fabrikam という取引先からフラット ファイル EDI インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="0351d-110">Receive a flat-file EDI interchange from the trading partner Fabrikam.</span></span>  
  
2.  <span data-ttu-id="0351d-111">EDI インターチェンジをそのスキーマに対して検証し、メッセージを XML に逆アセンブルして、メッセージ XML を MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="0351d-111">Validate the EDI interchange against its schema, disassemble the message into XML, and drop the message XML into the MessageBox.</span></span>  
  
3.  <span data-ttu-id="0351d-112">受信した EDI インターチェンジに対する 997 受信確認を生成して、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="0351d-112">Generate a 997 acknowledgment to the received EDI interchange, and drop it in the MessageBox.</span></span>  
  
4.  <span data-ttu-id="0351d-113">受信した EDI インターチェンジに対する TA1 受信確認を生成して、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="0351d-113">Generate a TA1 acknowledgment to the received EDI interchange, and drop it in the MessageBox.</span></span>  
  
5.  <span data-ttu-id="0351d-114">一方向の送信ポートでメッセージ XML を取得し、メッセージ EDI インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="0351d-114">Pick up the message XML by a one-way send port, and assemble the message EDI interchange.</span></span>  
  
6.  <span data-ttu-id="0351d-115">EDI インターチェンジを Contoso に送信します。</span><span class="sxs-lookup"><span data-stu-id="0351d-115">Send the EDI interchange to Contoso.</span></span>  
  
7.  <span data-ttu-id="0351d-116">一方向の送信ポートで 997 XML を取得し、997 EDI インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="0351d-116">Pick up the 997 XML by a one-way send port, and assemble the 997 EDI interchange.</span></span>  
  
8.  <span data-ttu-id="0351d-117">997 インターチェンジを Fabrikam に送信します。</span><span class="sxs-lookup"><span data-stu-id="0351d-117">Send the 997 interchange to Fabrikam.</span></span>  
  
9. <span data-ttu-id="0351d-118">一方向の送信ポートで TA1 XML を取得し、TA1 EDI インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="0351d-118">Pick up the TA1 XML by a one-way send port, and assemble the TA1 EDI interchange.</span></span>  
  
10. <span data-ttu-id="0351d-119">TA1 インターチェンジを Fabrikam に送信します。</span><span class="sxs-lookup"><span data-stu-id="0351d-119">Send the TA1 interchange to Fabrikam.</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="0351d-120">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="0351d-120">The Functionality in this Solution</span></span>  
 <span data-ttu-id="0351d-121">このチュートリアルを実行するために、以下の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0351d-121">For the purposes of this walkthrough, the following functionality will be enabled:</span></span>  
  
-   <span data-ttu-id="0351d-122">このソリューションは、EDIFACT エンコードではなく X12 エンコードを使用するインターチェンジを対象に設計されています。</span><span class="sxs-lookup"><span data-stu-id="0351d-122">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-123">HIPAA に使用される構成は、X12 エンコードに使用される構成によく似ています。</span><span class="sxs-lookup"><span data-stu-id="0351d-123">The configuration used for HIPAA closely parallel to that used for X12 encoding.</span></span> <span data-ttu-id="0351d-124">EDIFACT の場合と同様のソリューションを作成する方法の手順については、次を参照してください。[チュートリアル (EDIFACT): EDI インターチェンジの受信と送信、受信確認をバックアップ](../core/walkthrough-edifact--receive-edi-interchanges-and-send-an-acknowledgement.md)です。</span><span class="sxs-lookup"><span data-stu-id="0351d-124">For instructions on how to create a similar solution for EDIFACT, see [Walkthrough (EDIFACT): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-edifact--receive-edi-interchanges-and-send-an-acknowledgement.md).</span></span>  
  
-   <span data-ttu-id="0351d-125">EDI の種類の検証および拡張された検証は、受信インターチェンジに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-125">EDI type and extended validation will be performed on the incoming interchange.</span></span>  
  
-   <span data-ttu-id="0351d-126">インターチェンジの送信者に返す技術確認および機能確認が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-126">Technical and functional acknowledgments will be generated for returning to the sender of the interchange.</span></span>  
  
-   <span data-ttu-id="0351d-127">このソリューションでは、トランスポートの種類が FILE である一方向の受信場所が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-127">The solution uses a one-way receive location with a FILE transport type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-128">双方向の送信請求応答の受信ポートと受信場所を使用してメッセージを受信できますが、この方法で受信する場合、種類が FILE のトランスポートは受信場所に対して使用できません。</span><span class="sxs-lookup"><span data-stu-id="0351d-128">You can use a two-way solicit response receive port and location to receive the message, but if you do so, you will not be able to use a FILE transport type for the receive location.</span></span> <span data-ttu-id="0351d-129">詳細については、次を参照してください。 [EDI メッセージを受信および確認するためのポートを構成する](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)です。</span><span class="sxs-lookup"><span data-stu-id="0351d-129">For more information, see [Configuring a Port to Receive EDI Messages and Acknowledgments](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md).</span></span>  
  
-   <span data-ttu-id="0351d-130">EDI レポートが有効になり、インターチェンジの状態レポートに表示するトランザクション セットが保存されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-130">EDI reporting will be enabled, and transaction sets will be saved for viewing from the interchange status report.</span></span>  
  
-   <span data-ttu-id="0351d-131">テストを実行するために、ソリューションは 3 つの送信ポートを使用して、作成した EDI インターチェンジと ACK をローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="0351d-131">For testing purposes, the solution uses three send ports to send the EDI interchange and the ACKs created to local folders.</span></span>  
  
 <span data-ttu-id="0351d-132">次の図は、このソリューションのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="0351d-132">The following figure shows the architecture for this solution:</span></span>  
  
 <span data-ttu-id="0351d-133">![EDI インターチェンジの受信](../core/media/c54cca56-c658-4081-9e2f-bf28ba647cda.gif "c54cca56-c658-4081-9e2f-bf28ba647cda")</span><span class="sxs-lookup"><span data-stu-id="0351d-133">![Receiving EDI interchanges](../core/media/c54cca56-c658-4081-9e2f-bf28ba647cda.gif "c54cca56-c658-4081-9e2f-bf28ba647cda")</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="0351d-134">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="0351d-134">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="0351d-135">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0351d-135">The procedures required for this solution include the following:</span></span>  
  
-   <span data-ttu-id="0351d-136">BizTalk プロジェクトに必要なメッセージ スキーマを追加してビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0351d-136">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schema(s) available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  
  
-   <span data-ttu-id="0351d-137">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の一方向受信ポートを作成して、取引先から EDI インターチェンジを受信し、受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-137">Create a one-way receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDI interchange from the trading partner and generate an acknowledgment.</span></span> <span data-ttu-id="0351d-138">この受信場所は、Fabrikam が Contoso に送信する EDI インターチェンジをドロップするファイル フォルダーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="0351d-138">This receive location is tied to the file folder where Fabrikam drops the EDI interchange to be sent to Contoso.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-139">使用することができます、双方向の送信請求応答の受信ポートとメッセージを受信場所が、受信場所のトランスポートの種類が FILE を使用していないする場合は、します。</span><span class="sxs-lookup"><span data-stu-id="0351d-139">You can use a two-way solicit response receive port and location to receive the message, but if you do, you will not be able to use a FILE transport type for the receive location.</span></span>  
  
-   <span data-ttu-id="0351d-140">EDI インターチェンジをローカル Contoso フォルダーに送信する送信ポート、997 ACK をローカル Fabrikam フォルダーに送信する送信ポート、および TA1 ACK をローカル Fabrikam フォルダーに送信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-140">Create one send port that sends the EDI interchange to a local Contoso folder, another that sends the 997 ACK to a local Fabrikam folder, and another that sends the TA1 ACK to a local Fabrikam folder.</span></span>  
  
-   <span data-ttu-id="0351d-141">Fabrikam および Contoso の両方にパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-141">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  
  
-   <span data-ttu-id="0351d-142">両方の取引先それぞれにビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-142">Create a business profile each for both the trading partners.</span></span>  
  
-   <span data-ttu-id="0351d-143">受信するメッセージおよび送信する受信確認の EDI プロパティを構成して、2 つのプロファイル間のアグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-143">Create an agreement between the two profiles by configuring the EDI properties for the message to be received and the acknowledgment to be sent.</span></span>  
  
-   <span data-ttu-id="0351d-144">テスト EDI インターチェンジを使用して、このチュートリアルをテストします。</span><span class="sxs-lookup"><span data-stu-id="0351d-144">Test the walkthrough using a test EDI interchange.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-145">テスト メッセージには、EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0351d-145">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="0351d-146">このファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="0351d-146">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ folder.</span></span> <span data-ttu-id="0351d-147">これは、X12 850 メッセージです。</span><span class="sxs-lookup"><span data-stu-id="0351d-147">This is an X12 850 message.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="0351d-148">チュートリアルの構成</span><span class="sxs-lookup"><span data-stu-id="0351d-148">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="0351d-149">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0351d-149">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="0351d-150">メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="0351d-150">To deploy the message schema</span></span>  
  
1.  <span data-ttu-id="0351d-151">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。</span><span class="sxs-lookup"><span data-stu-id="0351d-151">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-152">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0351d-152">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="0351d-153">いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。</span><span class="sxs-lookup"><span data-stu-id="0351d-153">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2.  <span data-ttu-id="0351d-154">プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="0351d-154">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="0351d-155">スキーマが [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI にあるフォルダーに移動し、スキーマをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-155">Move to the folder that your schema is in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI, and then double-click your schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-156">EDI スキーマが \XSD_Schema\EDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI フォルダーに既定のフォルダーにして、スキーマ内のファイルです。</span><span class="sxs-lookup"><span data-stu-id="0351d-156">If the EDI schemas have not been unzipped into the \XSD_Schema\EDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the \XSD_Schema\EDI folder to unzip the schemas into the default folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-157">EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用する場合は、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI フォルダーにある X12_00401_850.xsd スキーマを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0351d-157">If you use the SamplePO.txt file that is used in the EDI Interface Developer tutorial, you must use the X12_00401_850.xsd schema that is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="0351d-158">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema フォルダーにある X12 850 スキーマは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0351d-158">You must not use the X12 850 schema in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema folder.</span></span>  
  
3.  <span data-ttu-id="0351d-159">アセンブリ キー ファイルをプロジェクトに追加し、アセンブリをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="0351d-159">Add the assembly key file to the project, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a><span data-ttu-id="0351d-160">EDI インターチェンジを受信するための一方向の受信ポート (Fabrikam 用) を作成するには</span><span class="sxs-lookup"><span data-stu-id="0351d-160">To create a one-way receive port (for Fabrikam) to receive the EDI interchange</span></span>  
  
1.  <span data-ttu-id="0351d-161">Windows エクスプローラーを使用して、インターチェンジを受信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-161">In Windows Explorer, create a local folder to receive the interchange.</span></span>  
  
2.  <span data-ttu-id="0351d-162">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-162">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
3.  <span data-ttu-id="0351d-163">受信ポートの名前を指定し、をクリックして**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="0351d-163">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  
  
4.  <span data-ttu-id="0351d-164">**[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-164">Click **New**.</span></span>  
  
5.  <span data-ttu-id="0351d-165">名前、受信場所は、select**ファイル**の**型**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-165">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="0351d-166">フォルダーを参照**受信フォルダー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="0351d-166">Browse to a folder for **Receive folder** text box.</span></span> <span data-ttu-id="0351d-167">このフォルダーは、この手順のステップ 1. で作成したフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0351d-167">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="0351d-168">ファイル マスクを入力します。  **\*.edi**または **\*.txt**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-168">Enter a file mask, such as **\*.edi** or **\*.txt**.</span></span>  
  
7.  <span data-ttu-id="0351d-169">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-169">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="0351d-170">**受信パイプライン** **EdiReceive**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-170">For **Receive pipeline**, select **EdiReceive**.</span></span>  
  
9. <span data-ttu-id="0351d-171">をクリックして**OK**で、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0351d-171">Click **OK** in the **Receive Location Properties** dialog box.</span></span> <span data-ttu-id="0351d-172">をクリックして**OK**で再度、**受信ポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0351d-172">Click **OK** again in the **Receive Port Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="0351d-173">コンソール ツリーでクリックして**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-173">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="0351d-174">**受信場所** ウィンドウで、右クリックし、受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-174">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a><span data-ttu-id="0351d-175">EDI インターチェンジを送信するための静的な一方向の送信ポート (Contoso 用) を作成するには</span><span class="sxs-lookup"><span data-stu-id="0351d-175">To create a static one-way send port (for Contoso) to send the EDI interchange</span></span>  
  
1.  <span data-ttu-id="0351d-176">Windows エクスプローラーを使用して、テスト インターチェンジを送信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-176">In Windows Explorer, create a local folder to send the test interchange to.</span></span>  
  
2.  <span data-ttu-id="0351d-177">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-177">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="0351d-178">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="0351d-178">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
4.  <span data-ttu-id="0351d-179">**トランスポート**セクションで、**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-179">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="0351d-180">**コピー先フォルダー**インターチェンジを受信するフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="0351d-180">For **Destination folder**, browse to the folder to receive the interchange.</span></span> <span data-ttu-id="0351d-181">このフォルダーは、この手順のステップ 1. で作成したフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0351d-181">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="0351d-182">**ファイル マスク**、インターチェンジの形式を入力します。  **\*.edi**または **\*.xml**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-182">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.xml**.</span></span>  
  
6.  <span data-ttu-id="0351d-183">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-183">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0351d-184">**送信パイプライン** **EdiSend**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-184">In **Send pipeline**, select **EdiSend**.</span></span>  
  
8.  <span data-ttu-id="0351d-185">コンソール ツリーで、次のように選択します。**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-185">In the console tree, select **Filters**.</span></span> <span data-ttu-id="0351d-186">EDI インターチェンジをサブスクライブするフィルターを入力します。</span><span class="sxs-lookup"><span data-stu-id="0351d-186">Enter a filter to subscribe to the EDI interchange.</span></span> <span data-ttu-id="0351d-187">たとえば、**プロパティ**、入力**BTS です。MessageType**;**演算子**、入力 **==** ; および**値**http:// など、インターチェンジのスキーマを入力してくださいschemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_850 です。</span><span class="sxs-lookup"><span data-stu-id="0351d-187">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the interchange, for example, http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_850.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-188">前のフィルター設定では、この送信ポートに関連付けられたフォルダーに、受信確認ではなくインターチェンジが送信されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-188">The above filter setting ensures that interchanges, not acknowledgments, will be sent to the folder associated with this send port.</span></span>  
  
9. <span data-ttu-id="0351d-189">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-189">Click **OK**.</span></span>  
  
10. <span data-ttu-id="0351d-190">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-190">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="0351d-191">**送信ポート** ウィンドウは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-191">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-997n-acknowledgment"></a><span data-ttu-id="0351d-192">静的な一方向の送信ポートを作成して 997 受信確認を送信するには</span><span class="sxs-lookup"><span data-stu-id="0351d-192">To create a static one-way send port to send the 997n acknowledgment</span></span>  
  
1.  <span data-ttu-id="0351d-193">Windows エクスプローラーを使用して、997 受信確認を送信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-193">In Windows Explorer, create a local folder to send the 997 acknowledgment to.</span></span>  
  
2.  <span data-ttu-id="0351d-194">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-194">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="0351d-195">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="0351d-195">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
4.  <span data-ttu-id="0351d-196">**トランスポート**セクションで、**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-196">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="0351d-197">**コピー先フォルダー**、997 受信確認を受信するフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="0351d-197">For **Destination folder**, browse to a folder to receive the 997 acknowledgment.</span></span> <span data-ttu-id="0351d-198">このフォルダーは、この手順のステップ 1. で作成したフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0351d-198">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="0351d-199">**ファイル マスク**、インターチェンジの形式を入力します。  **\*.edi**または **\*.txt**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-199">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.txt**.</span></span>  
  
6.  <span data-ttu-id="0351d-200">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-200">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0351d-201">**送信パイプライン** **EdiSend**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-201">In **Send pipeline**, select **EdiSend**.</span></span>  
  
8.  <span data-ttu-id="0351d-202">コンソール ツリーで、次のように選択します。**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-202">In the console tree, select **Filters**.</span></span> <span data-ttu-id="0351d-203">997 受信確認をサブスクライブするフィルターを入力します。</span><span class="sxs-lookup"><span data-stu-id="0351d-203">Enter a filter to subscribe to the 997 acknowledgment.</span></span> <span data-ttu-id="0351d-204">たとえば、**プロパティ**、入力**BTS です。MessageType**;**演算子**、入力 **==** ; および**値**など、受信確認のスキーマを入力`http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span><span class="sxs-lookup"><span data-stu-id="0351d-204">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the acknowledgment, for example, `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span></span>  
  
9. <span data-ttu-id="0351d-205">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-205">Click **OK**.</span></span>  
  
10. <span data-ttu-id="0351d-206">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-206">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="0351d-207">**送信ポート** ウィンドウは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-207">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-ta1-acknowledgment"></a><span data-ttu-id="0351d-208">静的な一方向の送信ポートを作成して TA1 受信確認を送信するには</span><span class="sxs-lookup"><span data-stu-id="0351d-208">To create a static one-way send port to send the TA1 acknowledgment</span></span>  
  
1.  <span data-ttu-id="0351d-209">Windows エクスプローラーを使用して、TA1 受信確認を送信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-209">In Windows Explorer, create a local folder to send the TA1 acknowledgment to.</span></span>  
  
2.  <span data-ttu-id="0351d-210">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-210">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="0351d-211">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="0351d-211">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
4.  <span data-ttu-id="0351d-212">**トランスポート**セクションで、**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-212">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="0351d-213">**コピー先フォルダー**、TA1 受信確認を受信するフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="0351d-213">For **Destination folder**, browse to a folder to receive the TA1 acknowledgment.</span></span> <span data-ttu-id="0351d-214">このフォルダーは、この手順のステップ 1. で作成したフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0351d-214">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="0351d-215">**ファイル マスク**、インターチェンジの形式を入力します。  **\*.edi**または **\*.txt**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-215">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.txt**.</span></span>  
  
6.  <span data-ttu-id="0351d-216">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-216">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0351d-217">**送信パイプライン** **EdiSend**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-217">In **Send pipeline**, select **EdiSend**.</span></span>  
  
8.  <span data-ttu-id="0351d-218">コンソール ツリーで、次のように選択します。**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-218">In the console tree, select **Filters**.</span></span> <span data-ttu-id="0351d-219">TA1 受信確認をサブスクライブするフィルターを入力します。</span><span class="sxs-lookup"><span data-stu-id="0351d-219">Enter a filter to subscribe to the TA1 acknowledgment.</span></span> <span data-ttu-id="0351d-220">たとえば、**プロパティ**、入力**BTS です。MessageType**;**演算子**、入力 **==** ; および**値**http:// など、受信確認のスキーマを入力schemas.microsoft.com/Edi/X12#X12_TA1_Root です。</span><span class="sxs-lookup"><span data-stu-id="0351d-220">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the acknowledgment, for example, http://schemas.microsoft.com/Edi/X12#X12_TA1_Root.</span></span>  
  
9. <span data-ttu-id="0351d-221">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-221">Click **OK**.</span></span>  
  
10. <span data-ttu-id="0351d-222">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-222">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="0351d-223">**送信ポート** ウィンドウは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-223">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="0351d-224">Fabrikam のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="0351d-224">To create a party and a business profile for Fabrikam</span></span>  
  
1.  <span data-ttu-id="0351d-225">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-225">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="0351d-226">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-226">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-227">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0351d-227">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0351d-228">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="0351d-228">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="0351d-229">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="0351d-229">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="0351d-230">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-230">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="0351d-231">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**fabrikam_profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="0351d-231">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-232">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-232">When you create a party, a profile is also created.</span></span> <span data-ttu-id="0351d-233">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="0351d-233">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="0351d-234">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-234">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="0351d-235">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0351d-235">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="0351d-236">Contoso のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="0351d-236">To create a party and a business profile for Contoso</span></span>  
  
1.  <span data-ttu-id="0351d-237">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-237">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="0351d-238">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-238">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-239">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0351d-239">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0351d-240">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="0351d-240">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="0351d-241">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="0351d-241">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="0351d-242">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-242">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="0351d-243">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="0351d-243">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-244">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-244">When you create a party, a profile is also created.</span></span> <span data-ttu-id="0351d-245">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="0351d-245">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="0351d-246">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-246">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="0351d-247">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0351d-247">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="0351d-248">2 つのビジネス プロファイル間のアグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="0351d-248">To create an agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="0351d-249">右クリック**fabrikam_profile**、 をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-249">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="0351d-250">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0351d-250">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="0351d-251">**プロトコル**ドロップダウン リストで、 **X12**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-251">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
4.  <span data-ttu-id="0351d-252">**2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、 **Contoso**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-252">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  
  
5.  <span data-ttu-id="0351d-253">**2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-253">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  
  
     <span data-ttu-id="0351d-254">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブに 1 つの一方向のアグリーメントを構成するようになっており、一方向の各アグリーメントが 1 つの完全なメッセージ トランザクション (メッセージの送信と受信確認の送信を含む) を表します。</span><span class="sxs-lookup"><span data-stu-id="0351d-254">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  
  
6.  <span data-ttu-id="0351d-255">**全般** タブで、**全般プロパティ** ページの 、**共通のホスト設定**セクションで、**レポートをオンに**、し、選択**reporting 用メッセージ ペイロードを格納**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-255">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
7.  <span data-ttu-id="0351d-256">次のタスクを実行、 **Fabrikam が Contoso ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="0351d-256">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    1.  <span data-ttu-id="0351d-257">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="0351d-257">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0351d-258"> では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0351d-258"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="0351d-259">値と照合**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**とアグリーメントのプロパティで、インターチェンジ ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="0351d-259">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="0351d-260">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="0351d-260">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="0351d-261">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-261">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0351d-262">テスト メッセージとして「EDI インターフェイス開発チュートリアル」の SamplePO.txt ファイルを使用する場合は、設定**ISA5**に**ZZ**、 **ISA6**に**THEM**、 **ISA7**に**ZZ**、および**ISA8**に**米国**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-262">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **THEM**, **ISA7** to **ZZ**, and **ISA8** to **US**.</span></span>  
  
    2.  <span data-ttu-id="0351d-263">**受信確認**ページで、**インターチェンジの設定** セクションで、チェック**TA1 が必要**と**997 が必要**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-263">On the **Acknowledgement** page under the **Interchange Settings** section, check **TA1 Expected** and **997 Expected**.</span></span>  
  
    3.  <span data-ttu-id="0351d-264">**検証**ページで、、**インターチェンジの設定**セクションで、確認してください**重複している isa13 を確認**オプションがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="0351d-264">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0351d-265">オフにすると、**重複している isa13 を確認して**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="0351d-265">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    4.  <span data-ttu-id="0351d-266">**文字セットと区切り記号**ページで、**インターチェンジの設定** セクションで、選択、 **CR LF**オプション。</span><span class="sxs-lookup"><span data-stu-id="0351d-266">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option.</span></span>  
  
    5.  <span data-ttu-id="0351d-267">**ローカル ホストの設定**ページで、**インターチェンジの設定** セクションで、クリア、**要求-応答で送信パイプラインに確認をルーティングの受信ポート**オプション。</span><span class="sxs-lookup"><span data-stu-id="0351d-267">On the **Local Host Settings** page under the **Interchange Settings** section, clear the **Route ACK to send pipeline on request-response receive port** option.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0351d-268">使用していた場合、双方向の受信ポートをインターチェンジを受信し、受信確認を返す、ことを確認**要求-応答で送信パイプラインに確認をルーティングの受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-268">If you were using a two-way receive port to receive the interchange and return the acknowledgment, you would check **Route ACK to send pipeline on request-response receive port**.</span></span>  
  
    6.  <span data-ttu-id="0351d-269">**送信ポート**ページで、**インターチェンジの設定**セクションには、Fabrikam からインターチェンジを受信する送信ポートおよび受信する送信ポートを関連付ける、Contoso から送信される確認します。</span><span class="sxs-lookup"><span data-stu-id="0351d-269">On the **Send Ports** page under the **Interchange Settings** section, associate the send ports that will be receiving the interchange from Fabrikam and the send ports that will be receiving the acknowledgements from Contoso.</span></span> <span data-ttu-id="0351d-270">**送信ポート**グリッド 、**名前**列は、空のセルをクリックし、ドロップダウン リストから Fabrikam から EDI インターチェンジを受信するために作成した送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="0351d-270">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port created for receiving the EDI interchange from Fabrikam.</span></span> <span data-ttu-id="0351d-271">TA1 受信確認の受信用に作成した送信ポート、および 997 受信確認の受信用に作成した送信ポートに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0351d-271">Repeat the step for the send port created for receiving the TA1 acknowledgement and the send port created for receiving the 997 acknowledgement.</span></span>  
  
    7.  <span data-ttu-id="0351d-272">**検証**ページで、**トランザクション セットの設定**セクションのままにして**EDI 型の検証**に、チェック**拡張された検証**.</span><span class="sxs-lookup"><span data-stu-id="0351d-272">On the **Validation** page under the **Transaction Set Settings** section, leave **EDI Type Validation** checked and check **Extended validation**.</span></span>  
  
    8.  <span data-ttu-id="0351d-273">使用するかどうかに付属する標準スキーマのいずれかの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の**ローカル ホストの設定**ページで、**トランザクション セットの設定**セクションで、選択するために使用するスキーマの名前空間受信インターチェンジを処理します。</span><span class="sxs-lookup"><span data-stu-id="0351d-273">If you are using one of the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], on the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span> <span data-ttu-id="0351d-274">カスタム スキーマを使用する場合に値を入力、**をカスタマイズするターゲットの名前空間**グリッド、ように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループおよびトランザクションを使用して名前空間のセットのヘッダー値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0351d-274">If using a custom schema, enter values in the **Customize Target namespace** grid, so that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can determine the namespace using group and transaction set header values.</span></span>  
  
    9. <span data-ttu-id="0351d-275">**エンベロープ**ページで、**トランザクション セットの設定**セクションで、グリッドの最初の行のすべての列の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="0351d-275">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  
  
        |<span data-ttu-id="0351d-276">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0351d-276">Use this</span></span>|<span data-ttu-id="0351d-277">目的</span><span class="sxs-lookup"><span data-stu-id="0351d-277">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0351d-278">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="0351d-278">**Default**</span></span>|<span data-ttu-id="0351d-279">選択**既定**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-279">Select **Default**.</span></span> <span data-ttu-id="0351d-280">**注:** 、既定の値は、この行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**が使用される場合でもの値は、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**の一致するものではありません、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="0351d-280">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and  **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="0351d-281">**トランザクションの種類**</span><span class="sxs-lookup"><span data-stu-id="0351d-281">**Transaction Type**</span></span>|<span data-ttu-id="0351d-282">テスト メッセージのメッセージの種類を選択して**850 - 注文**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-282">Select the message type of your test message, **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="0351d-283">**バージョン/リリース**</span><span class="sxs-lookup"><span data-stu-id="0351d-283">**Version/Release**</span></span>|<span data-ttu-id="0351d-284">EDI のバージョンを入力**00401**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-284">Enter the EDI version, **00401**.</span></span>|  
        |<span data-ttu-id="0351d-285">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="0351d-285">**Target namespace**</span></span>|<span data-ttu-id="0351d-286">選択**http://schemas.microsoft.com/Edi/X12**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-286">Select **http://schemas.microsoft.com/Edi/X12**.</span></span>|  
        |<span data-ttu-id="0351d-287">**GS1**</span><span class="sxs-lookup"><span data-stu-id="0351d-287">**GS1**</span></span>|<span data-ttu-id="0351d-288">テスト メッセージのメッセージの種類が選択されていることを確認**PO - 注文書 (850)**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-288">Verify that the message type of the test message is selected, **PO - Purchase Order (850)**.</span></span>|  
        |<span data-ttu-id="0351d-289">**[GS2]**</span><span class="sxs-lookup"><span data-stu-id="0351d-289">**GS2**</span></span>|<span data-ttu-id="0351d-290">アプリケーション送信者を表す値を入力します。</span><span class="sxs-lookup"><span data-stu-id="0351d-290">Enter a value for the Application sender.</span></span>|  
        |<span data-ttu-id="0351d-291">**[GS3]**</span><span class="sxs-lookup"><span data-stu-id="0351d-291">**GS3**</span></span>|<span data-ttu-id="0351d-292">アプリケーション受信者を表す値を入力します。</span><span class="sxs-lookup"><span data-stu-id="0351d-292">Enter a value for the Application receiver.</span></span>|  
        |<span data-ttu-id="0351d-293">**GS4**</span><span class="sxs-lookup"><span data-stu-id="0351d-293">**GS4**</span></span>|<span data-ttu-id="0351d-294">日付の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="0351d-294">Select the date format that you want.</span></span> <span data-ttu-id="0351d-295">**注:**ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0351d-295">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="0351d-296">ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。</span><span class="sxs-lookup"><span data-stu-id="0351d-296">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="0351d-297">**GS5**</span><span class="sxs-lookup"><span data-stu-id="0351d-297">**GS5**</span></span>|<span data-ttu-id="0351d-298">時刻の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="0351d-298">Select the time format that you want.</span></span>|  
        |<span data-ttu-id="0351d-299">**GS7**</span><span class="sxs-lookup"><span data-stu-id="0351d-299">**GS7**</span></span>|<span data-ttu-id="0351d-300">選択**X の間に認可 Standards Committee X12**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-300">Select **X - Accredited Standards Committee X12**.</span></span>|  
        |<span data-ttu-id="0351d-301">**GS8**</span><span class="sxs-lookup"><span data-stu-id="0351d-301">**GS8**</span></span>|<span data-ttu-id="0351d-302">EDI のバージョンが入力されていることを確認**00401**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-302">Verify that the EDI version has been entered, **00401**.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0351d-303">GS01、GS02、GS03、GS04、GS05、GS07、および入力した値に基づいて、送信する受信確認の GS08 の値が設定されます**トランザクション タイプ**、**バージョン/リリース**、および**ターゲット名前空間**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-303"> will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="0351d-304">送信パイプラインは、トランザクション セットの種類、X12 バージョン、およびターゲットの名前空間と、メッセージ ヘッダー内の対応する値との照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="0351d-304">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="0351d-305">成功すると、その値が使用 GS に関連付けられている、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**値。</span><span class="sxs-lookup"><span data-stu-id="0351d-305">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  
  
8.  <span data-ttu-id="0351d-306">次のタスクを実行、 **Contoso が Fabrikam ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="0351d-306">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-307">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0351d-307">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="0351d-308">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-308">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-309">受信確認の生成方法に関連するプロパティを構成、受信確認、同じメッセージ トランザクションの一部である場合でも、 **Contoso が Fabrikam ->**タブです。これが必要な受信確認コンテキスト プロパティで指定した値の逆に、送信者および受信者の修飾子を設定、 **Contoso が Fabrikam ->**タブです。たとえば場合、送信者と受信者の識別子が THEM および US に設定されて、 **Fabrikam が Contoso ->**  タブでは、送信者と受信者のコンテキスト プロパティは、受信確認で US および THEM に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-309">Even though the acknowledgement is part of the same message transaction, the properties related to how the acknowledgement should be generated are configured in the **Contoso->Fabrikam** tab. This is required because the acknowledgement context properties for the sender and receiver qualifiers are set to the opposite of the values you specified in the **Contoso->Fabrikam** tab. For example, if sender and receiver identifiers are set to THEM and US in the **Fabrikam->Contoso** tab, the sender and receiver context properties will be set to US and THEM in the acknowledgement.</span></span> <span data-ttu-id="0351d-310">通常、他の一方向のアグリーメント タブでも、送信者および受信者の識別子はそれぞれ US および THEM に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-310">Typically, the other one-way agreement tab would also have the sender and receiver identifiers set to US and THEM respectively.</span></span> <span data-ttu-id="0351d-311">そのため、受信確認メッセージは、そのアグリーメントに従って解決され、プロパティの設定が取得されます。</span><span class="sxs-lookup"><span data-stu-id="0351d-311">Hence, the acknowledgement message would resolve to that agreement and the properties setting will be picked.</span></span> <span data-ttu-id="0351d-312">別の要素の区切り記号 CR LF を使用する受信確認をするかどうかまたはを使用する受信確認がある場合は、のプロパティを指定するなど、 **Contoso が Fabrikam ->**タブ。</span><span class="sxs-lookup"><span data-stu-id="0351d-312">So, if you want to have the acknowledgement to use different element separators or if you want to have the acknowledgement to use CR LF, specify the properties in the **Contoso->Fabrikam** tab.</span></span>  
    >   
    >  <span data-ttu-id="0351d-313">概念的には、受信確認のプロパティを同じセンダを持つ任意の一方向アグリーメント タブから取得され、として受信者の修飾子は、受信確認のコンテキスト プロパティで設定します。</span><span class="sxs-lookup"><span data-stu-id="0351d-313">Conceptually, the properties for the acknowledgement will be picked from any one-way agreement tab that has the same sender and receiver qualifiers as set in the acknowledgement’s context properties.</span></span> <span data-ttu-id="0351d-314">ただし、実際に使いやすいように、一般的には、インターチェンジの解決用に作成したアグリーメントのもう 1 つの一方向のアグリーメント タブでこの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="0351d-314">However, for ease of practical use, you would typically set this in the other one-way agreement tab of the agreement that you created to which the interchange would have resolved.</span></span>  
  
    1.  <span data-ttu-id="0351d-315">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="0351d-315">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0351d-316">テスト メッセージとして「EDI インターフェイス開発チュートリアル」の SamplePO.txt ファイルを使用する場合は、設定**ISA5**に**ZZ**、 **ISA6**に**米国**、 **ISA7**に**ZZ**、および**ISA8**に**THEM**です。</span><span class="sxs-lookup"><span data-stu-id="0351d-316">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **US**, **ISA7** to **ZZ**, and **ISA8** to **THEM**.</span></span>  
  
9. <span data-ttu-id="0351d-317">**[適用]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-317">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="0351d-318">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0351d-318">Click **OK**.</span></span> <span data-ttu-id="0351d-319">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="0351d-319">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="0351d-320">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="0351d-320">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="0351d-321">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="0351d-321">Testing the Walkthrough</span></span>  
 <span data-ttu-id="0351d-322">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0351d-322">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-walkthrough"></a><span data-ttu-id="0351d-323">チュートリアルをテストするには</span><span class="sxs-lookup"><span data-stu-id="0351d-323">To test the walkthrough</span></span>  
  
1.  <span data-ttu-id="0351d-324">Windows エクスプローラーで、テスト EDI インターチェンジをローカル受信フォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="0351d-324">In Windows Explorer, drop the test EDI interchange into your local receive folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0351d-325">テスト メッセージには、EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0351d-325">For a test message, you can use the SamplePO.txt file that is used in the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="0351d-326">このファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="0351d-326">That file is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial folder.</span></span> <span data-ttu-id="0351d-327">これは、X12 850 メッセージです。</span><span class="sxs-lookup"><span data-stu-id="0351d-327">This is an X12 850 message.</span></span> <span data-ttu-id="0351d-328">このメッセージを使用する場合は、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI フォルダーにある X12_00401_850.xsd スキーマを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0351d-328">If you use this message, you must have deployed the X12_00401_850.xsd schema that is shipped in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI folder.</span></span> <span data-ttu-id="0351d-329">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema フォルダーにある X12 850 スキーマは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0351d-329">You must not use the X12 850 schema in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema folder.</span></span>  
  
2.  <span data-ttu-id="0351d-330">インターチェンジ用の送信ポートに関連付けられたフォルダーを開き、そのフォルダーに EDI インターチェンジが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0351d-330">Open the folder that you associated with the send port for interchanges, and verify that it contains the EDI interchange.</span></span>  
  
3.  <span data-ttu-id="0351d-331">997 受信確認用の送信ポートに関連付けられたフォルダーを開き、そのフォルダーに 997 受信確認が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0351d-331">Open the folder that you associated with the send port for the 997 acknowledgment, and verify that it contains a 997 acknowledgment.</span></span>  
  
4.  <span data-ttu-id="0351d-332">TA1 受信確認用の送信ポートに関連付けられたフォルダーを開き、そのフォルダーに TA1 受信確認が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0351d-332">Open the folder that you associated with the send port for the TA1 acknowledgment, and verify that it contains a TA1 acknowledgment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0351d-333">参照</span><span class="sxs-lookup"><span data-stu-id="0351d-333">See Also</span></span>  
 [<span data-ttu-id="0351d-334">開発および BizTalk Server EDI ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0351d-334">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)
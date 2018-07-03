---
title: 'チュートリアル (EDIFACT): EDI インターチェンジの受信と受信確認の送信 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02751f0c-8e7e-4879-93e4-8bc475640756
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b221d47a64f603db697b99c7e5a60b1cb1a67bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018892"
---
# <a name="walkthrough-edifact-receiving-edi-interchanges-and-sending-back-an-acknowledgement"></a><span data-ttu-id="aa0a3-102">チュートリアル (EDIFACT): EDI インターチェンジの受信と受信確認の送信</span><span class="sxs-lookup"><span data-stu-id="aa0a3-102">Walkthrough (EDIFACT): Receiving EDI Interchanges and Sending Back an Acknowledgement</span></span>
<span data-ttu-id="aa0a3-103">このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して EDIFACT インターチェンジの受信用のソリューションを作成する一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDIFACT interchanges using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="aa0a3-104">このソリューションでは、ある取引先 (Fabrikam) から別の取引先 (Contoso) に EDIFACT インターチェンジが送信されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-104">In this solution, an EDIFACT interchange is sent from a trading partner, Fabrikam, to another trading partner, Contoso.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="aa0a3-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="aa0a3-105">Prerequisites</span></span>  
 <span data-ttu-id="aa0a3-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  

## <a name="how-the-solution-receives-edifact-interchanges"></a><span data-ttu-id="aa0a3-107">ソリューションにより EDIFACT インターチェンジを受信する方法</span><span class="sxs-lookup"><span data-stu-id="aa0a3-107">How the Solution Receives EDIFACT Interchanges</span></span>  
 <span data-ttu-id="aa0a3-108">このソリューションは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-108">The solution will do the following:</span></span>  

> [!NOTE]
>  <span data-ttu-id="aa0a3-109">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-109">The events in this list may not occur in the order shown.</span></span>  

1.  <span data-ttu-id="aa0a3-110">Fabrikam という取引先から EDIFACT フラット ファイル インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-110">Receive a flat-file EDIFACT interchange from the trading partner Fabrikam.</span></span>  

2.  <span data-ttu-id="aa0a3-111">EDIFACT インターチェンジをそのスキーマに対して検証し、メッセージを XML に逆アセンブルして、メッセージ XML を MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-111">Validate the EDIFACT interchange against its schema, disassemble the message into XML, and drop the message XML into the MessageBox.</span></span>  

3.  <span data-ttu-id="aa0a3-112">受信した EDI インターチェンジに対する技術確認 (メッセージの受信) を生成して、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-112">Generate a technical acknowledgement (receipt of message) to the received EDI interchange, and drop it in the MessageBox.</span></span>  

4.  <span data-ttu-id="aa0a3-113">機能確認 (受信した EDI インターチェンジの受理または拒否) を生成して、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-113">Generate a functional acknowledgment (acceptance or rejection of the received EDI interchange), and drop it in the MessageBox.</span></span>  

5.  <span data-ttu-id="aa0a3-114">一方向の FILE 送信ポートでメッセージ XML を取得し、メッセージ EDI インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-114">Pick up the message XML by a one-way FILE send port, and assemble the message EDI interchange.</span></span>  

6.  <span data-ttu-id="aa0a3-115">EDI インターチェンジを Contoso ローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-115">Send the EDI interchange to Contoso local folder.</span></span>  

7.  <span data-ttu-id="aa0a3-116">一方向の FILE 送信ポートで技術確認を取得し、インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-116">Pick up the technical acknowledgement by a one-way FILE send port, and assemble the interchange.</span></span>  

8.  <span data-ttu-id="aa0a3-117">技術確認を Fabrikam ローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-117">Send the technical acknowledgement to the Fabrikam local folder.</span></span>  

9. <span data-ttu-id="aa0a3-118">一方向の FILE 送信ポートで機能確認を取得し、インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-118">Pick up the functional acknowledgement by a one-way FILE send port, and assemble the interchange.</span></span>  

10. <span data-ttu-id="aa0a3-119">機能確認を Fabrikam に送信します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-119">Send the functional acknowledgement to Fabrikam.</span></span>  

## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="aa0a3-120">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="aa0a3-120">The Functionality in this Solution</span></span>  
 <span data-ttu-id="aa0a3-121">このチュートリアルを実行するために、以下の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-121">For the purposes of this walkthrough, the following functionality will be enabled:</span></span>  

- <span data-ttu-id="aa0a3-122">ソリューションは EDIFACT エンコードを使用したインターチェンジ用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-122">The solution is designed for interchanges using EDIFACT encoding</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="aa0a3-123">X12 インターチェンジの場合は、同様のソリューションを作成する方法については、次を参照してください。[チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認を返す](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-123">For instructions on how to create a similar solution for X12 interchanges, see [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span>  

- <span data-ttu-id="aa0a3-124">EDI の種類の検証および拡張された検証は、受信インターチェンジに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-124">EDI type and extended validation will be performed on the incoming interchange.</span></span>  

- <span data-ttu-id="aa0a3-125">インターチェンジの送信者に返す技術確認および機能確認が生成されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-125">Technical and functional acknowledgments will be generated for returning to the sender of the interchange.</span></span>  

- <span data-ttu-id="aa0a3-126">このソリューションでは、トランスポートの種類が FILE である一方向の受信場所が使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-126">The solution uses a one-way receive location with a FILE transport type.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="aa0a3-127">双方向の送信請求応答の受信ポートと受信場所を使用してメッセージを受信できますが、この方法で受信する場合、種類が FILE のトランスポートは受信場所に対して使用できません。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-127">You can use a two-way solicit response receive port and location to receive the message, but if you do so, you will not be able to use a FILE transport type for the receive location.</span></span> <span data-ttu-id="aa0a3-128">詳細については、次を参照してください。[受信確認と EDI メッセージを受信するポートの構成](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-128">For more information, see [Configuring a Port to Receive EDI Messages and Acknowledgments](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md).</span></span>  

- <span data-ttu-id="aa0a3-129">EDI レポートが有効になり、インターチェンジの状態レポートに表示するトランザクション セットが保存されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-129">EDI reporting will be enabled, and transaction sets will be saved for viewing from the interchange status report.</span></span>  

- <span data-ttu-id="aa0a3-130">テストを実行するために、ソリューションは 3 つの送信ポートを使用して、作成した EDIFACT インターチェンジと ACK をローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-130">For testing purposes, the solution uses three send ports to send the EDIFACT interchange and the ACKs created to local folders.</span></span>  

  <span data-ttu-id="aa0a3-131">次の図は、このソリューションのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-131">The following figure shows the architecture for this solution:</span></span>  

  <span data-ttu-id="aa0a3-132">![EDIFACT インターチェンジの受信と ACK の送信](../core/media/edifact-walkthrough.gif "EDIFACT_Walkthrough")</span><span class="sxs-lookup"><span data-stu-id="aa0a3-132">![Receiving EDIFACT interchange and sending an ACK](../core/media/edifact-walkthrough.gif "EDIFACT_Walkthrough")</span></span>  

## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="aa0a3-133">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="aa0a3-133">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="aa0a3-134">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-134">The procedures required for this solution include the following:</span></span>  

- <span data-ttu-id="aa0a3-135">BizTalk プロジェクトに必要なメッセージ スキーマを追加してビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-135">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schema(s) available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the received interchange.</span></span>  

- <span data-ttu-id="aa0a3-136">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の一方向受信ポートを作成して、取引先から EDIFACT インターチェンジを受信し、受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-136">Create a one-way receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDIFACT interchange from the trading partner and generate an acknowledgment.</span></span> <span data-ttu-id="aa0a3-137">この受信場所は、Fabrikam が Contoso に送信する EDIFACT インターチェンジをドロップするローカル フォルダーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-137">This receive location is tied to the file folder where Fabrikam drops the EDIFACT interchange to be sent to Contoso.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="aa0a3-138">使用することができます、双方向の送信請求応答の受信ポートと、メッセージを受信する場所が、受信場所のトランスポートの種類が FILE を使用することはできませんを行った場合。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-138">You can use a two-way solicit response receive port and location to receive the message, but if you do, you will not be able to use a FILE transport type for the receive location.</span></span>  

- <span data-ttu-id="aa0a3-139">EDI インターチェンジをローカル Contoso フォルダーに送信する送信ポート、技術確認と機能確認をローカル Fabrikam フォルダーに送信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-139">Create one send port that sends the EDI interchange to a local Contoso folder and another that sends the technical and functional acknowledgements to a local Fabrikam folder.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="aa0a3-140">X12 の確認とは異なり、機能確認と技術確認の両方でメッセージの種類は同じです。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-140">Unlike X12 acknowledgements, the message types for both the functional and technical acknowledgements are same.</span></span> <span data-ttu-id="aa0a3-141">したがって、`BTS.MessageType` コンテキスト プロパティを使用して作成した送信ポート フィルターは、両方の確認をフィルター処理し、それらを同じフォルダーに配信します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-141">Hence, the send port filter created using the `BTS.MessageType` context property filters both the acknowledgements and delivers them to the same folder.</span></span>  

- <span data-ttu-id="aa0a3-142">Fabrikam および Contoso の両方にパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-142">Create a party (trading partner) for both Fabrikam and Contoso.</span></span>  

- <span data-ttu-id="aa0a3-143">両方の取引先それぞれにビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-143">Create a business profile each for both the trading partners.</span></span>  

- <span data-ttu-id="aa0a3-144">受信するメッセージおよび送信する受信確認の EDI プロパティを構成して、2 つのプロファイル間のアグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-144">Create an agreement between the two profiles by configuring the EDI properties for the message to be received and the acknowledgment to be sent.</span></span>  

- <span data-ttu-id="aa0a3-145">テスト EDIFACT インターチェンジを使用して、このチュートリアルをテストします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-145">Test the walkthrough using a test EDIFACT interchange.</span></span> <span data-ttu-id="aa0a3-146">このチュートリアルでは、以下の内容をコピーしてテキスト ファイルに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-146">For this walkthrough, you can copy-paste the following into a text file.</span></span> <span data-ttu-id="aa0a3-147">このファイルのスキーマは EFACT_D98A_APERAK.xsd です。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-147">The schema for this file is EFACT_D98A_APERAK.xsd.</span></span>  

  ```  
  UNA:+,?*'  
  UNB+UNOB:1+7654321:ZZZ+1234567:ZZZ+353501:3023+UNB5'  
  UNG+INVOIC+UNG2.1:ZZZ+UNG3.1:ZZZ+060413:2314+UNG5+UN+D:98B'  
  UNH+UNH1+APERAK:D:98A:UN++13+UNH5.1+UNH6.1+UNH7.1'  
  BGM+1+C10601'  
  DTM+10'  
  FTX+AAA++C10701+C10801'  
  CNT+1:14'  
  RFF+AAA'  
  DTM+10'  
  NAD+AA+C08201+C05801+C08001+C05901'  
  CTA++C05601'  
  COM+C07601:AA'  
  ERC+C90101'  
  FTX+AAA++C10701+C10801'  
  RFF+AAA'  
  FTX+AAA++C10701+C10801'  
  UNT+15+UNH1'  
  UNE+1+UNG5'  
  UNZ+1+UNB5'  
  ```  

### <a name="configuring-the-walkthrough"></a><span data-ttu-id="aa0a3-148">チュートリアルの構成</span><span class="sxs-lookup"><span data-stu-id="aa0a3-148">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="aa0a3-149">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-149">This section describes the procedures to configure the walkthrough.</span></span>  

##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="aa0a3-150">メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="aa0a3-150">To deploy the message schema</span></span>  

1. <span data-ttu-id="aa0a3-151">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-151">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-152">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-152">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="aa0a3-153">そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-153">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  

2. <span data-ttu-id="aa0a3-154">プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-154">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="aa0a3-155">スキーマがフォルダーに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]xsd_schema \edi\edifact\d98a, し、スキーマをダブルクリックします (**EFACT_D98A_APERAK.xsd**)。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-155">Move to the folder that your schema is in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A, and then double-click your schema (**EFACT_D98A_APERAK.xsd**).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-156">使用する必要がありますこのトピックで提供されるサンプルのテスト メッセージを使用している場合、 **EFACT_D98A_APERAK.xsd**スキーマ。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-156">If you are using the sample test message provided in this topic, you must use the **EFACT_D98A_APERAK.xsd** schema.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-157">EDI スキーマが \XSD_Schema\EDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI フォルダーにスキーマを既定のフォルダーに解凍内のファイル。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-157">If the EDI schemas have not been unzipped into the \XSD_Schema\EDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the \XSD_Schema\EDI folder to unzip the schemas into the default folder.</span></span>  

3. <span data-ttu-id="aa0a3-158">アセンブリ キー ファイルをプロジェクトに追加し、アセンブリをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-158">Add the assembly key file to the project, and then build and deploy the assembly.</span></span>  

##### <a name="to-create-a-one-way-receive-port-for-fabrikam-to-receive-the-edi-interchange"></a><span data-ttu-id="aa0a3-159">EDI インターチェンジを受信するための一方向の受信ポート (Fabrikam 用) を作成するには</span><span class="sxs-lookup"><span data-stu-id="aa0a3-159">To create a one-way receive port (for Fabrikam) to receive the EDI interchange</span></span>  

1. <span data-ttu-id="aa0a3-160">Windows エクスプローラーを使用して、インターチェンジを受信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-160">In Windows Explorer, create a local folder to receive the interchange.</span></span>  

2. <span data-ttu-id="aa0a3-161">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-161">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port**.</span></span>  

3. <span data-ttu-id="aa0a3-162">受信ポートの名前を指定し、をクリックし、**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-162">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  

4. <span data-ttu-id="aa0a3-163">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-163">Click **New**.</span></span>  

5. <span data-ttu-id="aa0a3-164">[受信場所の名前**ファイル**の**型**、] をクリックし、**構成**。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-164">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="aa0a3-165">フォルダーを参照**受信フォルダー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-165">Browse to a folder for **Receive folder** text box.</span></span> <span data-ttu-id="aa0a3-166">このフォルダーは、この手順のステップ 1. で作成したフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-166">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="aa0a3-167">ファイル マスクを入力します。  **\*.edi**または **\*.txt**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-167">Enter a file mask, such as **\*.edi** or **\*.txt**.</span></span>  

7. <span data-ttu-id="aa0a3-168">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-168">Click **OK**.</span></span>  

8. <span data-ttu-id="aa0a3-169">**受信パイプライン**、 **EdiReceive**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-169">For **Receive pipeline**, select **EdiReceive**.</span></span>  

9. <span data-ttu-id="aa0a3-170">クリックして**OK**で、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-170">Click **OK** in the **Receive Location Properties** dialog box.</span></span> <span data-ttu-id="aa0a3-171">クリックして**OK**で再度、**受信ポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-171">Click **OK** again in the **Receive Port Properties** dialog box.</span></span>  

10. <span data-ttu-id="aa0a3-172">コンソール ツリーで、クリックして**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-172">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="aa0a3-173">**受信場所**ウィンドウを右クリックし、受信場所をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-173">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  

##### <a name="to-create-a-static-one-way-send-port-for-contoso-to-send-the-edi-interchange"></a><span data-ttu-id="aa0a3-174">EDI インターチェンジを送信するための静的な一方向の送信ポート (Contoso 用) を作成するには</span><span class="sxs-lookup"><span data-stu-id="aa0a3-174">To create a static one-way send port (for Contoso) to send the EDI interchange</span></span>  

1. <span data-ttu-id="aa0a3-175">Windows エクスプローラーを使用して、テスト インターチェンジを送信するローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-175">In Windows Explorer, create a local folder to send the test interchange to.</span></span>  

2. <span data-ttu-id="aa0a3-176">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-176">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  

3. <span data-ttu-id="aa0a3-177">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-177">In the **Send Port Properties** dialog box, name the send port.</span></span>  

4. <span data-ttu-id="aa0a3-178">**トランスポート**セクションで、**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-178">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  

5. <span data-ttu-id="aa0a3-179">**先フォルダー**インターチェンジを受信するフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-179">For **Destination folder**, browse to the folder to receive the interchange.</span></span> <span data-ttu-id="aa0a3-180">このフォルダーは、この手順のステップ 1. で作成したフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-180">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="aa0a3-181">**ファイル マスク**、インターチェンジの形式を入力します。  **\*.edi**または **\*.txt**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-181">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.txt**.</span></span>  

6. <span data-ttu-id="aa0a3-182">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-182">Click **OK**.</span></span>  

7. <span data-ttu-id="aa0a3-183">**送信パイプライン**、 **EdiSend**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-183">In **Send pipeline**, select **EdiSend**.</span></span>  

8. <span data-ttu-id="aa0a3-184">コンソール ツリーで、選択**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-184">In the console tree, select **Filters**.</span></span> <span data-ttu-id="aa0a3-185">EDI インターチェンジをサブスクライブするフィルターを入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-185">Enter a filter to subscribe to the EDI interchange.</span></span> <span data-ttu-id="aa0a3-186">たとえば、**プロパティ**、入力**BTS します。MessageType**は**演算子**、入力**==**; と**値**、インターチェンジのスキーマを入力します。 `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006#EFACT_D98A_APERAK`。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-186">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the interchange, `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006#EFACT_D98A_APERAK`.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-187">前のフィルター設定では、この送信ポートに関連付けられたフォルダーに、受信確認ではなくインターチェンジが送信されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-187">The above filter setting ensures that interchanges, not acknowledgments, will be sent to the folder associated with this send port.</span></span>  

9. <span data-ttu-id="aa0a3-188">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-188">Click **OK**.</span></span>  

10. <span data-ttu-id="aa0a3-189">コンソール ツリーで、クリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-189">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="aa0a3-190">**送信ポート**ウィンドウは、送信ポートを右クリックし をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-190">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-acknowledgments"></a><span data-ttu-id="aa0a3-191">静的な一方向の送信ポートを作成して確認を送信するには</span><span class="sxs-lookup"><span data-stu-id="aa0a3-191">To create a static one-way send port to send the acknowledgments</span></span>  

1. <span data-ttu-id="aa0a3-192">Windows エクスプローラーで、技術確認と機能確認の送信先となるローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-192">In Windows Explorer, create a local folder to send the technical and functional acknowledgments to.</span></span>  

2. <span data-ttu-id="aa0a3-193">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-193">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port**.</span></span>  

3. <span data-ttu-id="aa0a3-194">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-194">In the **Send Port Properties** dialog box, name the send port.</span></span>  

4. <span data-ttu-id="aa0a3-195">**トランスポート**セクションで、**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-195">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  

5. <span data-ttu-id="aa0a3-196">**先フォルダー**、2 つの受信確認を受信するフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-196">For **Destination folder**, browse to a folder to receive the two acknowledgments.</span></span> <span data-ttu-id="aa0a3-197">このフォルダーは、この手順のステップ 1. で作成したフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-197">You created this folder in step 1 of this procedure.</span></span> <span data-ttu-id="aa0a3-198">**ファイル マスク**、インターチェンジの形式を入力します。  **\*.edi**または **\*.txt**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-198">For **File mask**, enter the interchange format, such as **\*.edi** or **\*.txt**.</span></span>  

6. <span data-ttu-id="aa0a3-199">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-199">Click **OK**.</span></span>  

7. <span data-ttu-id="aa0a3-200">**送信パイプライン**、 **EdiSend**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-200">In **Send pipeline**, select **EdiSend**.</span></span>  

8. <span data-ttu-id="aa0a3-201">コンソール ツリーで、選択**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-201">In the console tree, select **Filters**.</span></span> <span data-ttu-id="aa0a3-202">確認をサブスクライブするフィルターを入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-202">Enter a filter to subscribe to acknowledgments.</span></span> <span data-ttu-id="aa0a3-203">たとえば、**プロパティ**、入力**BTS します。MessageType**は**演算子**、入力**==**; と**値**、受信確認のスキーマを入力します。 `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-203">For example, for **Property**, enter **BTS.MessageType**; for **Operator**, enter **==**; and for **Value** enter the schema for the acknowledgment, `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`.</span></span>  

9. <span data-ttu-id="aa0a3-204">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-204">Click **OK**.</span></span>  

10. <span data-ttu-id="aa0a3-205">コンソール ツリーで、クリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-205">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="aa0a3-206">**送信ポート**ウィンドウは、送信ポートを右クリックし をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-206">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a><span data-ttu-id="aa0a3-207">Fabrikam のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="aa0a3-207">To create a party and a business profile for Fabrikam</span></span>  

1. <span data-ttu-id="aa0a3-208">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-208">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="aa0a3-209">パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-209">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-210">選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa0a3-210">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="aa0a3-211">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-211">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="aa0a3-212">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-212">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="aa0a3-213">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-213">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="aa0a3-214">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力 **[fabrikam_profile]** で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-214">In the **Profile Properties** dialog box, on the **General** page, enter **Fabrikam_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-215">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-215">When you create a party, a profile is also created.</span></span> <span data-ttu-id="aa0a3-216">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-216">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="aa0a3-217">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-217">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="aa0a3-218">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-218">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a><span data-ttu-id="aa0a3-219">Contoso のパーティとビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="aa0a3-219">To create a party and a business profile for Contoso</span></span>  

1. <span data-ttu-id="aa0a3-220">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-220">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="aa0a3-221">パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-221">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-222">選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa0a3-222">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="aa0a3-223">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-223">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="aa0a3-224">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-224">However, for this walkthrough, you can leave this check box selected.</span></span>  

3. <span data-ttu-id="aa0a3-225">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-225">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  

4. <span data-ttu-id="aa0a3-226">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-226">In the **Profile Properties** dialog box, on the **General** page, enter **Contoso_Profile** in the **Name** text box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-227">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-227">When you create a party, a profile is also created.</span></span> <span data-ttu-id="aa0a3-228">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-228">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="aa0a3-229">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-229">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="aa0a3-230">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-230">In the **General** page, specify a name for the profile.</span></span>  

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="aa0a3-231">2 つのビジネス プロファイル間のアグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="aa0a3-231">To create an agreement between the two business profiles</span></span>  

1. <span data-ttu-id="aa0a3-232">右クリック**fabrikam_profile**、 をポイント**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-232">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="aa0a3-233">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-233">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3. <span data-ttu-id="aa0a3-234">**プロトコル**ドロップダウン リストで、 **EDIFACT**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-234">From the **Protocol** drop-down list, select **EDIFACT**.</span></span>  

4. <span data-ttu-id="aa0a3-235">**2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Contoso**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-235">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5. <span data-ttu-id="aa0a3-236">**2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-236">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="aa0a3-237">2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブに 1 つの一方向のアグリーメントを構成するようになっており、一方向の各アグリーメントが 1 つの完全なメッセージ トランザクション (メッセージの送信と受信確認の送信を含む) を表します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-237">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  

6. <span data-ttu-id="aa0a3-238">**全般** タブで、**全般プロパティ**ページで、**共通のホスト設定**セクションで、**レポートをオン**、し、選択**メッセージ ペイロードを格納するレポートの**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-238">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  

7. <span data-ttu-id="aa0a3-239">次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-239">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1. <span data-ttu-id="aa0a3-240">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**UNB2.1**、 **[unb2.2]**、 **UNB3.1**、および**UNB3.2**) テスト メッセージのヘッダー フィールドの値に対応しています。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-240">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**UNB2.1**, **UNB2.2**, **UNB3.1**, and **UNB3.2**) that correspond to the values for those header fields in your test message.</span></span>  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="aa0a3-241"> では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-241"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="aa0a3-242">値と一致します**UNB2.1**、 **UNB2.2**、 **UNB3.1**、および**UNB3.2**のプロパティで、インターチェンジ ヘッダーで、契約です。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-242">It will match the values of **UNB2.1**, **UNB2.2**, **UNB3.1**, and **UNB3.2** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="aa0a3-243">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-243">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="aa0a3-244">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-244">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="aa0a3-245">テスト メッセージとして、このトピックの前に示したサンプル メッセージを使用している場合は、設定**UNB2.1**に**7654321**、 **UNB2.2**に**ZZZ-相互定義**、 **UNB3.1**に**1234567**、および**UNB3.2**に**ZZZ-相互定義**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-245">If you are using the sample message provided earlier in this topic as your test message, set **UNB2.1** to **7654321**, **UNB2.2** to **ZZZ – Mutually Defined**, **UNB3.1** to **1234567**, and **UNB3.2** to **ZZZ – Mutually Defined**.</span></span>  

   2. <span data-ttu-id="aa0a3-246">**受信確認**ページで、**インターチェンジの設定** セクションで、チェック**メッセージの受信 (CONTRL が必要です)** と**受信確認 (CONTRL) が必要**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-246">On the **Acknowledgements** page under the **Interchange Settings** section, check **Receipt of message (CONTRL) expected** and **Acknowledgement (CONTRL) expected**.</span></span>  

   3. <span data-ttu-id="aa0a3-247">**エンベロープ**ページで、**インターチェンジの設定** セクションで、チェック**適用の UNA セグメント (文字列サービス通知)** と**適用の UNG セグメント (機能グループ ヘッダー)** します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-247">On the **Envelopes** page under the **Interchange Settings** section, check **Apply UNA segment (String service advice)** and **Apply UNG segments (Functional group header)**.</span></span>  

   4. <span data-ttu-id="aa0a3-248">**検証**ページで、**インターチェンジの設定**セクションをご確認ください**インターチェンジ制御番号 (UNB5)** オプションが選択されていません。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-248">On the **Validation** page under the **Interchange Settings** section, make sure **Interchange Control Number (UNB5)** option is unchecked.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="aa0a3-249">オフにすると、**インターチェンジ制御番号 (UNB5)** プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-249">Clearing the **Interchange Control Number (UNB5)** property enables you to receive multiple instances of the same message.</span></span>  

   5. <span data-ttu-id="aa0a3-250">**文字セットと区切り記号**ページで、**インターチェンジの設定**セクションで、 **CR LF**オプション**UNA6 サフィックス**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-250">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option for **UNA6 Suffix**.</span></span>  

   6. <span data-ttu-id="aa0a3-251">**ローカル ホスト設定**ページで、**インターチェンジの設定** セクションで、クリア、**受信ポートで要求-応答送信パイプラインに確認をルーティング**オプション。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-251">On the **Local Host Settings** page under the **Interchange Settings** section, clear the **Route ACK to send pipeline on request-response receive port** option.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="aa0a3-252">使用していた場合は、双方向の受信ポートをインターチェンジを受信し、受信確認を返す、ことを確認**受信ポートで要求-応答送信パイプラインに確認をルーティング**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-252">If you were using a two-way receive port to receive the interchange and return the acknowledgment, you would check **Route ACK to send pipeline on request-response receive port**.</span></span>  

   7. <span data-ttu-id="aa0a3-253">**送信ポート**ページで、**インターチェンジの設定**セクションで、Fabrikam からインターチェンジを受信する送信ポートおよび受信する送信ポートを関連付けます、Contoso から受信確認。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-253">On the **Send Ports** page under the **Interchange Settings** section, associate the send ports that will be receiving the interchange from Fabrikam and the send ports that will be receiving the acknowledgements from Contoso.</span></span> <span data-ttu-id="aa0a3-254">**送信ポート**グリッドで、**名前**列が空のセルをクリックし、ボックスの一覧から、Fabrikam から EDI インターチェンジを受信するために作成した送信ポートを選択します。 します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-254">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port created for receiving the EDI interchange from Fabrikam.</span></span> <span data-ttu-id="aa0a3-255">技術確認と機能確認の受信用に作成した送信ポートに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-255">Repeat the step for the send port created for receiving the technical and functional acknowledgements.</span></span>  

   8. <span data-ttu-id="aa0a3-256">**検証**ページで、**トランザクション セットの設定**セクションで、そのまま使用**EDI の種類の検証**に、チェック**型の検証を拡張する**.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-256">On the **Validation** page under the **Transaction Set Settings** section, leave **EDI type Validation** checked and check **Extended Type Validation**.</span></span>  

   9. <span data-ttu-id="aa0a3-257">使用するかどうかに付属する標準スキーマのいずれかの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の**ローカル ホスト設定**ページで、**トランザクション セットの設定**セクションでを使用するスキーマの名前空間を選択します。受信インターチェンジを処理します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-257">If you are using one of the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], on the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span> <span data-ttu-id="aa0a3-258">カスタム スキーマを使用している場合は、値を入力します。、**カスタマイズのターゲットの名前空間**グリッド、ように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループおよびトランザクションを使用して名前空間のセットのヘッダー値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-258">If using a custom schema, enter values in the **Customize Target namespace** grid, so that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can determine the namespace using group and transaction set header values.</span></span>  

   10. <span data-ttu-id="aa0a3-259">**エンベロープ**ページで、**トランザクション セットの設定**セクションで、グリッドの最初の行のすべての列の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-259">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  


       |          <span data-ttu-id="aa0a3-260">プロパティ</span><span class="sxs-lookup"><span data-stu-id="aa0a3-260">Use this</span></span>           |                                <span data-ttu-id="aa0a3-261">目的</span><span class="sxs-lookup"><span data-stu-id="aa0a3-261">To do this</span></span>                                 |
       |-----------------------------|---------------------------------------------------------------------------|
       |         <span data-ttu-id="aa0a3-262">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-262">**Default**</span></span>         |                            <span data-ttu-id="aa0a3-263">選択**既定**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-263">Select **Default**.</span></span>                            |
       | <span data-ttu-id="aa0a3-264">**メッセージの種類 UNH2.1 の**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-264">**For message type UNH2.1**</span></span> |         <span data-ttu-id="aa0a3-265">テスト メッセージのメッセージの種類を選択します。 **APERAK**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-265">Select the message type of your test message, **APERAK**.</span></span>         |
       |         <span data-ttu-id="aa0a3-266">**UNH2.2**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-266">**UNH2.2**</span></span>          |                       <span data-ttu-id="aa0a3-267">EDI のバージョンを入力**D**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-267">Enter the EDI version, **D**.</span></span>                       |
       |         <span data-ttu-id="aa0a3-268">**UNH2.3**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-268">**UNH2.3**</span></span>          |                    <span data-ttu-id="aa0a3-269">リリース番号を入力**98 a**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-269">Enter the release number, **98A**.</span></span>                     |
       |         <span data-ttu-id="aa0a3-270">**UNH2.5**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-270">**UNH2.5**</span></span>          |                         <span data-ttu-id="aa0a3-271">空白のままにできます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-271">You can leave this blank.</span></span>                         |
       |    <span data-ttu-id="aa0a3-272">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-272">**Target namespace**</span></span>     |          <span data-ttu-id="aa0a3-273">選択 **<http://schemas.microsoft.com/Edi/Edifact>** します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-273">Select **<http://schemas.microsoft.com/Edi/Edifact>**.</span></span>           |
       |          <span data-ttu-id="aa0a3-274">**UNG1**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-274">**UNG1**</span></span>           |               <span data-ttu-id="aa0a3-275">機能グループ ID を指定**INVOIC**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-275">Specify the functional group ID, **INVOIC**.</span></span>                |
       |         <span data-ttu-id="aa0a3-276">**UNG2.1**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-276">**UNG2.1**</span></span>          |         <span data-ttu-id="aa0a3-277">アプリケーション送信者 ID を表す値を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-277">Enter a value for the application sender identification.</span></span>          |
       |         <span data-ttu-id="aa0a3-278">**UNG2.1**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-278">**UNG2.1**</span></span>          | <span data-ttu-id="aa0a3-279">アプリケーション送信者コードの修飾子の値を入力**ZZZ**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-279">Enter a value for the application sender code qualifier, such as **ZZZ**.</span></span> |
       |         <span data-ttu-id="aa0a3-280">**UNG3.1**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-280">**UNG3.1**</span></span>          |          <span data-ttu-id="aa0a3-281">アプリケーション受信者 ID を表す値を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-281">Enter a value for application receiver identification.</span></span>           |
       |         <span data-ttu-id="aa0a3-282">**[UNG3.2]**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-282">**UNG3.2**</span></span>          |  <span data-ttu-id="aa0a3-283">アプリケーション受信者コードの修飾子の値を入力**ZZZ**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-283">Enter a value for application receiver code qualifier, such as **ZZZ**.</span></span>  |
       |          <span data-ttu-id="aa0a3-284">**UNG6**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-284">**UNG6**</span></span>           |        <span data-ttu-id="aa0a3-285">制御機関の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-285">Enter a value for the controlling agency.</span></span> <span data-ttu-id="aa0a3-286">例では、**解除**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-286">Example, **UN**.</span></span>         |
       |         <span data-ttu-id="aa0a3-287">**UNG7.1**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-287">**UNG7.1**</span></span>          |          <span data-ttu-id="aa0a3-288">メッセージの種類のバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-288">Enter the message type version number.</span></span> <span data-ttu-id="aa0a3-289">例では、 **D**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-289">Example, **D**.</span></span>           |
       |         <span data-ttu-id="aa0a3-290">**UNG7.2**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-290">**UNG7.2**</span></span>          |         <span data-ttu-id="aa0a3-291">メッセージの種類のリリース番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-291">Enter the message type release number.</span></span> <span data-ttu-id="aa0a3-292">例では、 **98 a**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-292">Example, **98A**.</span></span>          |
       |         <span data-ttu-id="aa0a3-293">**UNG7.3**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-293">**UNG7.3**</span></span>          |                         <span data-ttu-id="aa0a3-294">空白のままにできます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-294">You can leave this blank.</span></span>                         |
       |          <span data-ttu-id="aa0a3-295">**UNG8**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-295">**UNG8**</span></span>           |                         <span data-ttu-id="aa0a3-296">空白のままにできます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-296">You can leave this blank.</span></span>                         |


8. <span data-ttu-id="aa0a3-297">次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-297">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-298">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-298">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="aa0a3-299">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**UNG2.1**、 **UNG2.2**、 **UNG3.1**、および**UNG3.2**.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-299">To successfully create an agreement, both one-way agreement tabs must have values defined for **UNG2.1**, **UNG2.2**, **UNG3.1**, and **UNG3.2**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-300">受信確認の生成方法に関連するプロパティが構成されている、受信確認が、同じメッセージ トランザクションの一部であって、 **Contoso が Fabrikam-> **タブ。これは、必要なため、受信確認コンテキスト プロパティで指定した値の逆に、送信者と受信者の修飾子を設定、 **Contoso が Fabrikam-> **タブ。たとえば場合、送信者と受信者の識別子が 7654321 と 1234567 に設定されて、 **Fabrikam が Contoso を ->**  タブでは、送信者と受信者のコンテキスト プロパティは、受信確認で 1234567 と 7654321 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-300">Even though the acknowledgement is part of the same message transaction, the properties related to how the acknowledgement should be generated are configured in the **Contoso->Fabrikam** tab. This is required because the acknowledgement context properties for the sender and receiver qualifiers are set to the opposite of the values you specified in the **Contoso->Fabrikam** tab. For example, if sender and receiver identifiers are set to 7654321 and 1234567 in the **Fabrikam->Contoso** tab, the sender and receiver context properties will be set to 1234567 and 7654321 in the acknowledgement.</span></span> <span data-ttu-id="aa0a3-301">通常、もう一方の一方向アグリーメントに関するタブでも、送信者 ID と受信者 ID がそれぞれ 1234567 と 7654321 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-301">Typically, the other one-way agreement tab would also have the sender and receiver identifiers set to 1234567 and 7654321 respectively.</span></span> <span data-ttu-id="aa0a3-302">そのため、受信確認メッセージは、そのアグリーメントに従って解決され、プロパティの設定が取得されます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-302">Hence, the acknowledgement message would resolve to that agreement and the properties setting will be picked.</span></span> <span data-ttu-id="aa0a3-303">そのため、別の要素の区切り記号または CR LF を使用する受信確認がある場合に使用する受信確認がある場合でプロパティを指定、 **Contoso が Fabrikam]-> [** タブ。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-303">So, if you want to have the acknowledgement to use different element separators or if you want to have the acknowledgement to use CR LF, specify the properties in the **Contoso->Fabrikam** tab.</span></span>  
   >   
   >  <span data-ttu-id="aa0a3-304">概念的には、任意の一方向アグリーメント タブを持つ同じ送信者から受信確認のプロパティが取得され、受信者の修飾子としてが受信確認のコンテキスト プロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-304">Conceptually, the properties for the acknowledgement will be picked from any one-way agreement tab that has the same sender and receiver qualifiers as set in the acknowledgement’s context properties.</span></span> <span data-ttu-id="aa0a3-305">ただし、実際に使いやすいように、一般的には、インターチェンジの解決用に作成したアグリーメントのもう 1 つの一方向のアグリーメント タブでこの設定を行います。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-305">However, for ease of practical use, you would typically set this in the other one-way agreement tab of the agreement that you created to which the interchange would have resolved.</span></span>  

   1.  <span data-ttu-id="aa0a3-306">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**UNG2.1**、 **UNG2.2**、 **UNG3.1**、および**UNG3.2**) テスト メッセージのヘッダー フィールドの値に対応しています。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-306">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**UNG2.1**, **UNG2.2**, **UNG3.1**, and **UNG3.2**) that correspond to the values for those header fields in your test message.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="aa0a3-307">テスト メッセージとして、このトピックの前に示したサンプル メッセージを使用している場合は、設定**UNB2.1**に**1234567**、 **UNB2.2**に**ZZZ-相互定義**、 **UNB3.1**に**7654321**、および**UNB3.2**に**ZZZ-相互定義**します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-307">If you are using the sample message provided earlier in this topic as your test message, set **UNB2.1** to **1234567**, **UNB2.2** to **ZZZ – Mutually Defined**, **UNB3.1** to **7654321**, and **UNB3.2** to **ZZZ – Mutually Defined**.</span></span>  

9. <span data-ttu-id="aa0a3-308">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-308">Click **Apply**.</span></span>  

10. <span data-ttu-id="aa0a3-309">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-309">Click **OK**.</span></span> <span data-ttu-id="aa0a3-310">新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-310">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="aa0a3-311">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-311">The newly added agreement is enabled by default.</span></span>  

### <a name="testing-the-walkthrough"></a><span data-ttu-id="aa0a3-312">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="aa0a3-312">Testing the Walkthrough</span></span>  
 <span data-ttu-id="aa0a3-313">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-313">This section provides information on how to test the walkthrough.</span></span>  

##### <a name="to-test-the-walkthrough"></a><span data-ttu-id="aa0a3-314">チュートリアルをテストするには</span><span class="sxs-lookup"><span data-stu-id="aa0a3-314">To test the walkthrough</span></span>  

1. <span data-ttu-id="aa0a3-315">Windows エクスプローラーで、テスト EDI インターチェンジをローカル受信フォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-315">In Windows Explorer, drop the test EDI interchange into your local receive folder.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="aa0a3-316">このトピックの前半に示したサンプル メッセージをテスト メッセージとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-316">For a test message, you can use the sample message provided earlier in this topic.</span></span> <span data-ttu-id="aa0a3-317">メッセージをテキスト ファイルにコピーし、拡張子を .txt にしてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-317">Copy the message to a text file and save the file with a .txt extension.</span></span> <span data-ttu-id="aa0a3-318">このメッセージを使用する場合は、EFACT_D98A_APERAK.xsd スキーマを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-318">If you use this message, you must have deployed the EFACT_D98A_APERAK.xsd schema.</span></span> <span data-ttu-id="aa0a3-319">実行することによって、スキーマが使用可能な**MicrosoftEdiXSDTemplates.exe**ファイル (\XSD_Schema\EDI フォルダーにあります) を既定のフォルダーにスキーマを解凍します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-319">The schema is available by executing the **MicrosoftEdiXSDTemplates.exe** file (in the \XSD_Schema\EDI folder) to unzip the schemas into the default folder.</span></span> <span data-ttu-id="aa0a3-320">EFACT_D98A_APERAK.xsd スキーマは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A にあります。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-320">The EFACT_D98A_APERAK.xsd schema is then available under [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\EDIFACT\D98A.</span></span>  

2. <span data-ttu-id="aa0a3-321">インターチェンジ用の送信ポートに関連付けられたフォルダーを開き、そのフォルダーに EDI インターチェンジが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-321">Open the folder that you associated with the send port for interchanges, and verify that it contains the EDI interchange.</span></span>  

3. <span data-ttu-id="aa0a3-322">受信確認用の送信ポートに関連付けられたフォルダーを開き、そのフォルダーに技術確認と機能確認が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa0a3-322">Open the folder that you associated with the send port for the acknowledgements, and verify that it contains the technical and functional acknowledgements.</span></span>  

## <a name="see-also"></a><span data-ttu-id="aa0a3-323">参照</span><span class="sxs-lookup"><span data-stu-id="aa0a3-323">See Also</span></span>  
 [<span data-ttu-id="aa0a3-324">BizTalk Server EDI ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="aa0a3-324">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)
---
title: '(Azure) の手順 2: EDI アグリーメントを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a8003697-4955-45c0-ba0b-e7c293a050a2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc2db7361aef663c70c7227febfea5fc08dc699a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280074"
---
# <a name="step-2-for-azure-create-an-edi-agreement"></a><span data-ttu-id="ff02b-102">EDI アグリーメントを作成する (Azure) の手順 2。</span><span class="sxs-lookup"><span data-stu-id="ff02b-102">Step 2 (For Azure): Create an EDI Agreement</span></span>
<span data-ttu-id="ff02b-103">このトピックでは、[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] の一部として利用できる Azure BizTalk ポータルを使用してパートナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-103">In this topic, you will create partners using the Azure BizTalk portal available as part of the [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span> <span data-ttu-id="ff02b-104">また、2 つのパートナー (Northwind と Contoso) 間のアグリーメントも作成し、Contoso により Northwind に送信される X12 販売注文メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-104">You will also create an agreement between the two partners (Northwind and Contoso) to process the X12 sales order message sent by Contoso to Northwind.</span></span>  
  
### <a name="to-create-partners"></a><span data-ttu-id="ff02b-105">パートナーを作成するには</span><span class="sxs-lookup"><span data-stu-id="ff02b-105">To create partners</span></span>  
  
1.  <span data-ttu-id="ff02b-106">Microsoft アカウントを使用して、ポータルにログインに[http://go.microsoft.com/fwlink/p/?LinkId=235056](http://go.microsoft.com/fwlink/p/?LinkId=235056)です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-106">Using your Microsoft account, log into the portal at [http://go.microsoft.com/fwlink/p/?LinkId=235056](http://go.microsoft.com/fwlink/p/?LinkId=235056).</span></span>  
  
2.  <span data-ttu-id="ff02b-107">Northwind のパートナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-107">Create a partner for Northwind.</span></span> <span data-ttu-id="ff02b-108">手順に従う[パートナーとプロファイル](http://msdn.microsoft.com/library/windowsazure/hh689791)にパートナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-108">Follow the steps at [Partners and Profiles](http://msdn.microsoft.com/library/windowsazure/hh689791) to create a partner.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ff02b-109">このパートナーを管理対象のパートナーとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="ff02b-109">Mark this partner as the managed partner.</span></span>  
  
3.  <span data-ttu-id="ff02b-110">手順を繰り返して Contoso のパートナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-110">Repeat the steps to create a partner for Contoso.</span></span> <span data-ttu-id="ff02b-111">***そうしない***このパートナー管理対象のパートナーとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="ff02b-111">***Do not*** mark this partner as a managed partner.</span></span>  
  
### <a name="to-create-an-agreement"></a><span data-ttu-id="ff02b-112">アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="ff02b-112">To create an agreement</span></span>  
  
1.  <span data-ttu-id="ff02b-113">ポータルのホーム ページで、をクリックして**契約**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-113">In the portal home page, click **Agreements**.</span></span>  
  
2.  <span data-ttu-id="ff02b-114">**契約** ページで、をクリックして、 **X12**いない場合は既にそのタブをタブです。をクリックして**アグリーメントの作成**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-114">On the **Agreements** page, click the **X12** tab if you are not already on that tab. Then click **Create Agreement**.</span></span>  
  
3.  <span data-ttu-id="ff02b-115">**新しいアグリーメント** ページで、次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-115">In the **New Agreement** page, enter the following details:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="ff02b-116">**フィールド**</span><span class="sxs-lookup"><span data-stu-id="ff02b-116">**Field**</span></span>|<span data-ttu-id="ff02b-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="ff02b-117">**Description**</span></span>|  
    |<span data-ttu-id="ff02b-118">名前</span><span class="sxs-lookup"><span data-stu-id="ff02b-118">Name</span></span>|<span data-ttu-id="ff02b-119">アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-119">Enter a name for the agreement.</span></span> <span data-ttu-id="ff02b-120">このチュートリアルでは、名前を指定、として`DemoAgreement`です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-120">For this tutorial, specify the name as `DemoAgreement`.</span></span><br /><br /> <span data-ttu-id="ff02b-121">**注:** これは必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="ff02b-121">**Note:** This is a mandatory field.</span></span> <span data-ttu-id="ff02b-122">アグリーメントの名前は一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff02b-122">The name for the agreement must be unique.</span></span>|  
    |<span data-ttu-id="ff02b-123">Description</span><span class="sxs-lookup"><span data-stu-id="ff02b-123">Description</span></span>|<span data-ttu-id="ff02b-124">アグリーメントのメモまたは説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-124">Enter notes or a description for the agreement.</span></span>|  
    |<span data-ttu-id="ff02b-125">パートナー 1 プロファイル (管理対象)</span><span class="sxs-lookup"><span data-stu-id="ff02b-125">Partner 1 Profile (managed)</span></span>|<span data-ttu-id="ff02b-126">アグリーメントの管理対象のパートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-126">Select the managed partner for the agreement.</span></span> <span data-ttu-id="ff02b-127">管理対象のパートナーはサービス プロバイダーにより管理されるパートナーで、アグリーメントの展開時にはそのパートナーにパイプラインが展開されます。</span><span class="sxs-lookup"><span data-stu-id="ff02b-127">A managed partner is a partner managed by the service provider and the pipelines are deployed for that partner during agreement deployment.</span></span> <span data-ttu-id="ff02b-128">通常、サービス プロバイダーにより管理されるパートナーは管理対象のパートナーとして構成されますが、エンタープライズ パートナーは管理対象のパートナーとしてはマークされません。</span><span class="sxs-lookup"><span data-stu-id="ff02b-128">Typically partners managed by service provider are configured as a managed partner while the enterprise partners are not marked as managed partners.</span></span><br /><br /> <span data-ttu-id="ff02b-129">**注:** このチュートリアルでは、管理対象のパートナーは**Northwind**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-129">**Note:** For this tutorial, the managed partner is **Northwind**.</span></span><br /><br /> <span data-ttu-id="ff02b-130">**注:** プロファイル フィールドで、既定のプロファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff02b-130">**Note:** The default profile is displayed in the Profile field.</span></span> <span data-ttu-id="ff02b-131">パートナー用に構成された、該当するプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-131">Choose the desired profile which has been configured for the partner.</span></span>|  
    |<span data-ttu-id="ff02b-132">パートナー 2 プロファイル</span><span class="sxs-lookup"><span data-stu-id="ff02b-132">Partner 2 Profile</span></span>|<span data-ttu-id="ff02b-133">アグリーメントの (管理対象のパートナーではない) パートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-133">Select the partner for the agreement (who is not a managed partner).</span></span><br /><br /> <span data-ttu-id="ff02b-134">**注:** プロファイル フィールドで、既定のプロファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff02b-134">**Note:** The default profile is displayed in the Profile field.</span></span> <span data-ttu-id="ff02b-135">パートナー用に構成された、該当するプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-135">Choose the desired profile which has been configured for the partner.</span></span>|  
  
     <span data-ttu-id="ff02b-136">**Id**</span><span class="sxs-lookup"><span data-stu-id="ff02b-136">**Identities**</span></span>  
  
    |<span data-ttu-id="ff02b-137">**フィールド**</span><span class="sxs-lookup"><span data-stu-id="ff02b-137">**Field**</span></span>|<span data-ttu-id="ff02b-138">**Description**</span><span class="sxs-lookup"><span data-stu-id="ff02b-138">**Description**</span></span>|  
    |---------------|---------------------|  
    |<span data-ttu-id="ff02b-139">パートナー 1 ID 修飾子</span><span class="sxs-lookup"><span data-stu-id="ff02b-139">Partner 1 ID Qualifier</span></span>|<span data-ttu-id="ff02b-140">取引先に一意のビジネス ID を提供する認証修飾子を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-140">Select an authenticating qualifier that provides unique business identities to the trading partners.</span></span> <span data-ttu-id="ff02b-141">このチュートリアルでは、次のように選択します。 **ZZ-相互定義**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-141">For this tutorial, select **ZZ-Mutually Defined**.</span></span>|  
    |<span data-ttu-id="ff02b-142">値</span><span class="sxs-lookup"><span data-stu-id="ff02b-142">Value</span></span>|<span data-ttu-id="ff02b-143">入力`Northwind`です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-143">Enter `Northwind`.</span></span>|  
    |<span data-ttu-id="ff02b-144">パートナー 2 の ID 修飾子</span><span class="sxs-lookup"><span data-stu-id="ff02b-144">Partner 2 ID Qualifier</span></span>|<span data-ttu-id="ff02b-145">取引先に一意のビジネス ID を提供する認証修飾子を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-145">Select an authenticating qualifier that provides unique business identities to the trading partners.</span></span> <span data-ttu-id="ff02b-146">このチュートリアルでは、次のように選択します。 **ZZ-相互定義**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-146">For this tutorial, select **ZZ-Mutually Defined**.</span></span>|  
    |<span data-ttu-id="ff02b-147">値</span><span class="sxs-lookup"><span data-stu-id="ff02b-147">Value</span></span>|<span data-ttu-id="ff02b-148">入力`Contoso`です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-148">Enter `Contoso`.</span></span>|  
  
     <span data-ttu-id="ff02b-149">**追跡**</span><span class="sxs-lookup"><span data-stu-id="ff02b-149">**Tracking**</span></span>  
  
    |<span data-ttu-id="ff02b-150">**フィールド**</span><span class="sxs-lookup"><span data-stu-id="ff02b-150">**Field**</span></span>|<span data-ttu-id="ff02b-151">**Description**</span><span class="sxs-lookup"><span data-stu-id="ff02b-151">**Description**</span></span>|  
    |---------------|---------------------|  
    |<span data-ttu-id="ff02b-152">送信側メッセージのプロパティを追跡する</span><span class="sxs-lookup"><span data-stu-id="ff02b-152">Track Send side message properties</span></span>|<span data-ttu-id="ff02b-153">EDI メッセージがパートナーに送信される場合にメッセージのプロパティを格納するには、これをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ff02b-153">Check this to store the message properties when the EDI message is sent to the partner.</span></span> <span data-ttu-id="ff02b-154">クリックしてこのデータを照会して保存されると、**追跡**左側のウィンドウで、Azure BizTalk Portal からです。</span><span class="sxs-lookup"><span data-stu-id="ff02b-154">Once stored, you can query this data by clicking **Tracking** from the left pane on the Azure BizTalk Portal.</span></span><br /><br /> <span data-ttu-id="ff02b-155">チェックして、メッセージ本文を格納できますも有効にすると、**トラックの送信側メッセージ本文**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-155">When enabled, you can also store the message body by checking **Track Send side message body**.</span></span>|  
    |<span data-ttu-id="ff02b-156">受信側メッセージのプロパティを追跡する</span><span class="sxs-lookup"><span data-stu-id="ff02b-156">Track Receive side message properties</span></span>|<span data-ttu-id="ff02b-157">パートナーから EDI メッセージを受信する場合にメッセージのプロパティを格納するには、これをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ff02b-157">Check this to store the message properties when the EDI message is received from a partner.</span></span> <span data-ttu-id="ff02b-158">クリックしてこのデータを照会して保存されると、**追跡**左側のウィンドウで、Azure BizTalk Portal からです。</span><span class="sxs-lookup"><span data-stu-id="ff02b-158">Once stored, you can query this data by clicking **Tracking** from the left pane on the Azure BizTalk Portal.</span></span><br /><br /> <span data-ttu-id="ff02b-159">チェックして、メッセージ本文を格納できますも有効にすると、**トラックの受信側メッセージ本文**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-159">When enabled, you can also store the message body by checking **Track Receive side message body**.</span></span>|  
  
4.  <span data-ttu-id="ff02b-160">**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff02b-160">Click **Continue**.</span></span>  
  
     <span data-ttu-id="ff02b-161">クリックすると**続行**2 つの新しいタブが追加の 1 つの受信設定および他の送信設定用です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-161">Clicking **Continue** adds two new tabs, one for receive settings and the other for send settings.</span></span> <span data-ttu-id="ff02b-162">各タブは、2 つのパートナー間の一方向のアグリーメント用で、メッセージの受信用と送信用があります。</span><span class="sxs-lookup"><span data-stu-id="ff02b-162">Each tab is for a one-way agreement between the two partners, one for receiving messages and the other for sending messages.</span></span>  
  
5.  <span data-ttu-id="ff02b-163">受信の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-163">Specify the receive settings.</span></span>  
  
    1.  <span data-ttu-id="ff02b-164">**トランスポート** ページで、設定、**トランスポートの種類**を HTTP にします。</span><span class="sxs-lookup"><span data-stu-id="ff02b-164">On the **Transport** page, set the **Transport type** to HTTP.</span></span>  
  
         <span data-ttu-id="ff02b-165">**エンドポイント**フィールドは、X12 に送信する必要がある Contoso URL が表示販売注文メッセージです。</span><span class="sxs-lookup"><span data-stu-id="ff02b-165">The **Endpoint** field shows the URL to which Contoso must send the X12 sales order message.</span></span>  
  
    2.  <span data-ttu-id="ff02b-166">**プロトコル** ページで、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-166">On the **Protocol** page, specify the following values.</span></span>  
  
        1.  <span data-ttu-id="ff02b-167">必要である場合、ISA1、ISA2、ISA3、および ISA4 の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-167">If required, specify values for ISA1, ISA2, ISA3, and ISA4.</span></span>  
  
        2.  <span data-ttu-id="ff02b-168">**受信確認** **TA1 が必要**と**997 が必要です**を受信するための応答で技術確認と機能確認を生成する場合、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="ff02b-168">Under **Acknowledgements**, select **TA1 expected** and **997 expected** if you want to generate technical and functional acknowledgements in response for receiving the message.</span></span>  
  
        3.  <span data-ttu-id="ff02b-169">**スキーマ**をクリックして、**アップロード**ボタンをクリックし、アップロード、 **X12 840 スキーマ**(からダウンロードした[http://go.microsoft.com/fwlink/p/?LinkId = 235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)) および**SalesOrder**スキーマ (で作成した[EDI プロジェクト内のスキーマを作成する](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema))。</span><span class="sxs-lookup"><span data-stu-id="ff02b-169">Under **Schemas**, click the **Upload** button and upload the **X12 840 schema** (you downloaded from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)) and the **SalesOrder** schema (you created in [To create a schema within the EDI project](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema)).</span></span>  
  
             <span data-ttu-id="ff02b-170">次のプロパティを設定、**スキーマ**セクションです。</span><span class="sxs-lookup"><span data-stu-id="ff02b-170">Set the following properties under the **Schemas** section.</span></span>  
  
            |||  
            |-|-|  
            |<span data-ttu-id="ff02b-171">バージョン</span><span class="sxs-lookup"><span data-stu-id="ff02b-171">Version</span></span>|<span data-ttu-id="ff02b-172">00401</span><span class="sxs-lookup"><span data-stu-id="ff02b-172">00401</span></span>|  
            |<span data-ttu-id="ff02b-173">トランザクションの種類 (ST1)</span><span class="sxs-lookup"><span data-stu-id="ff02b-173">Transaction Type (ST1)</span></span>|<span data-ttu-id="ff02b-174">840</span><span class="sxs-lookup"><span data-stu-id="ff02b-174">840</span></span>|  
            |<span data-ttu-id="ff02b-175">スキーマ</span><span class="sxs-lookup"><span data-stu-id="ff02b-175">Schema</span></span>|<span data-ttu-id="ff02b-176">/X12_00401_840.xsd</span><span class="sxs-lookup"><span data-stu-id="ff02b-176">/X12_00401_840.xsd</span></span>|  
  
    3.  <span data-ttu-id="ff02b-177">**変換**で作成した変換のアップロード ページで、 [EDI プロジェクト内の変換を作成する](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm)です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-177">On the **Transform** page, upload the transform you created in [To create a transform within the EDI project](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm).</span></span>  
  
         <span data-ttu-id="ff02b-178">**このアグリーメントの一部として実行するマップを選択**、選択 **/X12_00401_840.xsd**の**スキーマ**と **/EDI840TOSALESORDER です。TRFM**の**変換ファイル名**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-178">Under **Choose the maps you want to execute as part of this agreement**, choose **/X12_00401_840.xsd** for **Schemas** and **/EDI840TOSALESORDER.TRFM** for **Transform file name**.</span></span>  
  
    4.  <span data-ttu-id="ff02b-179">**ルート**] ページで、[ **Service Bus キューへのルート**し、メッセージは送信キューの相対アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-179">On the **Route** page, select **Route to Service Bus Queue** and provide the relative address of the queue to which the message is sent.</span></span> <span data-ttu-id="ff02b-180">このチュートリアルでは、指定の相対アドレスとして`queueordersedi`完全な URL が実行されるよう`https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-180">For this tutorial, specify the relative address as `queueordersedi` so that the complete URL is `https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ff02b-181">このチュートリアルでは、エラー メッセージが、[メッセージ保留の設定] で指定したエンドポイントに送信されるシナリオについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="ff02b-181">This tutorial does not cover the scenario where a failed message is sent to the endpoint you specify in the Message Suspension Settings.</span></span> <span data-ttu-id="ff02b-182">ただし、アグリーメントの展開を成功させるには、この設定に値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff02b-182">However, for successful deployment of the agreement, you must provide a value for this setting.</span></span> <span data-ttu-id="ff02b-183">空ではない値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="ff02b-183">You can enter a non-empty value.</span></span>  
  
6.  <span data-ttu-id="ff02b-184">送信の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-184">Specify the send settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff02b-185">このチュートリアルで説明するシナリオの場合、アグリーメントに送信側の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ff02b-185">For the scenario described in this tutorial, you don’t need any send-side configuration for the agreement.</span></span> <span data-ttu-id="ff02b-186">ただし、送信の設定を指定しないと、設定がダミーの値であっても、アグリーメントを展開できません。</span><span class="sxs-lookup"><span data-stu-id="ff02b-186">However, an agreement cannot be deployed without specifying the send settings, even if they are dummy values.</span></span> <span data-ttu-id="ff02b-187">また、[、**送信の設定**] タブで、ダミーの値を指定する必要がない**受信 URI**、**変換**と**バッチ処理**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-187">Also, On the **Send Settings** tab, you don’t need to provide any dummy values for **Inbound URI**, **Transform**, and **Batching**.</span></span>  
  
    1.  <span data-ttu-id="ff02b-188">**プロトコル**] ページの [**スキーマ**をクリックして、**アップロード**ボタンをクリックし、X12 のスキーマをアップロード 840 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="ff02b-188">On the **Protocol** page, under **Schemas**, click the **Upload** button and upload the schema for the X12 840 message.</span></span>  
  
         <span data-ttu-id="ff02b-189">設定、**バージョン**に**00401**、**トランザクション タイプ**に**840**、および**スキーマ**に**X12_00401_840**です。</span><span class="sxs-lookup"><span data-stu-id="ff02b-189">Set the **Version** to **00401**, **Transaction Type** to **840**, and **Schema** to **X12_00401_840**.</span></span>  
  
    2.  <span data-ttu-id="ff02b-190">**トランスポート** ページで、パートナーへの応答メッセージまたは受信確認を送信する先のエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-190">On the **Transport** page, specify the endpoints where the response messages or acknowledgements will be sent to the partners.</span></span> <span data-ttu-id="ff02b-191">正常に処理されたメッセージだけでなく、処理中のエラーにより保留になったメッセージにも、エンドポイントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff02b-191">You must specify an endpoint each for the messages that are processed successfully as well as the messages that get suspended due to a failure in processing.</span></span>  
  
7.  <span data-ttu-id="ff02b-192">をクリックして**アグリーメントの展開**アグリーメントをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="ff02b-192">Click **Deploy Agreement** to deploy the agreement.</span></span> <span data-ttu-id="ff02b-193">表示された URL で、アグリーメントがデプロイされるようになりました、**トランスポート**のページ、**受信の設定**タブです。</span><span class="sxs-lookup"><span data-stu-id="ff02b-193">The agreement is now deployed at the URL that was displayed in the **Transport** page of the **Receive Settings** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff02b-194">参照</span><span class="sxs-lookup"><span data-stu-id="ff02b-194">See Also</span></span>  
 [<span data-ttu-id="ff02b-195">チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff02b-195">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)
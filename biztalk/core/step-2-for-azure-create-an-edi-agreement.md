---
title: 手順 2 (Azure 用):EDI アグリーメントを作成 |Microsoft Docs
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
ms.openlocfilehash: 38150af85186ec811383e52a455bd5591edbbb02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392760"
---
# <a name="step-2-for-azure-create-an-edi-agreement"></a><span data-ttu-id="db302-102">手順 2 (Azure 用):EDI アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="db302-102">Step 2 (For Azure): Create an EDI Agreement</span></span>
<span data-ttu-id="db302-103">このトピックでは、として使用できる Azure BizTalk ポータルを使用してパートナーを作成しますの一部、[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="db302-103">In this topic, you will create partners using the Azure BizTalk portal available as part of the [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span> <span data-ttu-id="db302-104">(Northwind と Contoso) が Contoso により Northwind に X12 販売注文メッセージの送信を処理する 2 つのパートナー間のアグリーメントも作成されます。</span><span class="sxs-lookup"><span data-stu-id="db302-104">You will also create an agreement between the two partners (Northwind and Contoso) to process the X12 sales order message sent by Contoso to Northwind.</span></span>  
  
### <a name="to-create-partners"></a><span data-ttu-id="db302-105">パートナーを作成するには</span><span class="sxs-lookup"><span data-stu-id="db302-105">To create partners</span></span>  
  
1.  <span data-ttu-id="db302-106">ポータルにログインして、Microsoft アカウントを使用して、 [ http://go.microsoft.com/fwlink/p/?LinkId=235056](http://go.microsoft.com/fwlink/p/?LinkId=235056)します。</span><span class="sxs-lookup"><span data-stu-id="db302-106">Using your Microsoft account, log into the portal at [http://go.microsoft.com/fwlink/p/?LinkId=235056](http://go.microsoft.com/fwlink/p/?LinkId=235056).</span></span>  
  
2.  <span data-ttu-id="db302-107">Northwind のパートナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="db302-107">Create a partner for Northwind.</span></span> <span data-ttu-id="db302-108">手順に従う[パートナーとプロファイル](http://msdn.microsoft.com/library/windowsazure/hh689791)パートナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="db302-108">Follow the steps at [Partners and Profiles](http://msdn.microsoft.com/library/windowsazure/hh689791) to create a partner.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="db302-109">このパートナー管理対象のパートナーとしてのマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="db302-109">Mark this partner as the managed partner.</span></span>  
  
3.  <span data-ttu-id="db302-110">Contoso のパートナーを作成する手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="db302-110">Repeat the steps to create a partner for Contoso.</span></span> <span data-ttu-id="db302-111">***しない***このパートナー管理対象のパートナーとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="db302-111">***Do not*** mark this partner as a managed partner.</span></span>  
  
### <a name="to-create-an-agreement"></a><span data-ttu-id="db302-112">アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="db302-112">To create an agreement</span></span>  
  
1.  <span data-ttu-id="db302-113">ポータルのホーム ページで次のようにクリックします。**契約**します。</span><span class="sxs-lookup"><span data-stu-id="db302-113">In the portal home page, click **Agreements**.</span></span>  
  
2.  <span data-ttu-id="db302-114">**契約** ページで、をクリックして、 **X12**  タブはないそのタブの場合。クリックして**アグリーメントの作成**です。</span><span class="sxs-lookup"><span data-stu-id="db302-114">On the **Agreements** page, click the **X12** tab if you are not already on that tab. Then click **Create Agreement**.</span></span>  
  
3.  <span data-ttu-id="db302-115">**新しいアグリーメント**ページで、次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="db302-115">In the **New Agreement** page, enter the following details:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="db302-116">**フィールド**</span><span class="sxs-lookup"><span data-stu-id="db302-116">**Field**</span></span>|<span data-ttu-id="db302-117">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="db302-117">**Description**</span></span>|  
    |<span data-ttu-id="db302-118">名前</span><span class="sxs-lookup"><span data-stu-id="db302-118">Name</span></span>|<span data-ttu-id="db302-119">アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="db302-119">Enter a name for the agreement.</span></span> <span data-ttu-id="db302-120">このチュートリアルと名前を指定`DemoAgreement`します。</span><span class="sxs-lookup"><span data-stu-id="db302-120">For this tutorial, specify the name as `DemoAgreement`.</span></span><br /><br /> <span data-ttu-id="db302-121">**注:** これは必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="db302-121">**Note:** This is a mandatory field.</span></span> <span data-ttu-id="db302-122">アグリーメントの名前は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="db302-122">The name for the agreement must be unique.</span></span>|  
    |<span data-ttu-id="db302-123">説明</span><span class="sxs-lookup"><span data-stu-id="db302-123">Description</span></span>|<span data-ttu-id="db302-124">メモまたはアグリーメントの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="db302-124">Enter notes or a description for the agreement.</span></span>|  
    |<span data-ttu-id="db302-125">パートナー 1 プロファイル (管理対象)</span><span class="sxs-lookup"><span data-stu-id="db302-125">Partner 1 Profile (managed)</span></span>|<span data-ttu-id="db302-126">契約の管理対象のパートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="db302-126">Select the managed partner for the agreement.</span></span> <span data-ttu-id="db302-127">管理対象のパートナーは、サービス プロバイダーによって管理されるパートナーとアグリーメントの展開中にそのパートナーに対してパイプラインが展開されます。</span><span class="sxs-lookup"><span data-stu-id="db302-127">A managed partner is a partner managed by the service provider and the pipelines are deployed for that partner during agreement deployment.</span></span> <span data-ttu-id="db302-128">通常、サービス プロバイダーによって管理されるパートナーは、エンタープライズ パートナーが管理対象のパートナーとしてマークされていないときに、管理対象のパートナーとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="db302-128">Typically partners managed by service provider are configured as a managed partner while the enterprise partners are not marked as managed partners.</span></span><br /><br /> <span data-ttu-id="db302-129">**注:** このチュートリアルでは、管理対象のパートナーは**Northwind**します。</span><span class="sxs-lookup"><span data-stu-id="db302-129">**Note:** For this tutorial, the managed partner is **Northwind**.</span></span><br /><br /> <span data-ttu-id="db302-130">**注:** 既定のプロファイルは、プロファイル フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db302-130">**Note:** The default profile is displayed in the Profile field.</span></span> <span data-ttu-id="db302-131">パートナーが構成されている目的のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="db302-131">Choose the desired profile which has been configured for the partner.</span></span>|  
    |<span data-ttu-id="db302-132">パートナー 2 プロファイル</span><span class="sxs-lookup"><span data-stu-id="db302-132">Partner 2 Profile</span></span>|<span data-ttu-id="db302-133">(ユーザーは、管理対象のパートナーではありません)、アグリーメントのパートナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="db302-133">Select the partner for the agreement (who is not a managed partner).</span></span><br /><br /> <span data-ttu-id="db302-134">**注:** 既定のプロファイルは、プロファイル フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="db302-134">**Note:** The default profile is displayed in the Profile field.</span></span> <span data-ttu-id="db302-135">パートナーが構成されている目的のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="db302-135">Choose the desired profile which has been configured for the partner.</span></span>|  
  
     <span data-ttu-id="db302-136">**Id**</span><span class="sxs-lookup"><span data-stu-id="db302-136">**Identities**</span></span>  
  
    |<span data-ttu-id="db302-137">**フィールド**</span><span class="sxs-lookup"><span data-stu-id="db302-137">**Field**</span></span>|<span data-ttu-id="db302-138">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="db302-138">**Description**</span></span>|  
    |---------------|---------------------|  
    |<span data-ttu-id="db302-139">パートナー 1 ID 修飾子</span><span class="sxs-lookup"><span data-stu-id="db302-139">Partner 1 ID Qualifier</span></span>|<span data-ttu-id="db302-140">取引先に一意のビジネス id を提供する認証修飾子を選択します。</span><span class="sxs-lookup"><span data-stu-id="db302-140">Select an authenticating qualifier that provides unique business identities to the trading partners.</span></span> <span data-ttu-id="db302-141">このチュートリアルでは、次のように選択します。 **ZZ-相互定義**します。</span><span class="sxs-lookup"><span data-stu-id="db302-141">For this tutorial, select **ZZ-Mutually Defined**.</span></span>|  
    |<span data-ttu-id="db302-142">値</span><span class="sxs-lookup"><span data-stu-id="db302-142">Value</span></span>|<span data-ttu-id="db302-143">入力`Northwind`します。</span><span class="sxs-lookup"><span data-stu-id="db302-143">Enter `Northwind`.</span></span>|  
    |<span data-ttu-id="db302-144">パートナー 2 ID 修飾子</span><span class="sxs-lookup"><span data-stu-id="db302-144">Partner 2 ID Qualifier</span></span>|<span data-ttu-id="db302-145">取引先に一意のビジネス id を提供する認証修飾子を選択します。</span><span class="sxs-lookup"><span data-stu-id="db302-145">Select an authenticating qualifier that provides unique business identities to the trading partners.</span></span> <span data-ttu-id="db302-146">このチュートリアルでは、次のように選択します。 **ZZ-相互定義**します。</span><span class="sxs-lookup"><span data-stu-id="db302-146">For this tutorial, select **ZZ-Mutually Defined**.</span></span>|  
    |<span data-ttu-id="db302-147">値</span><span class="sxs-lookup"><span data-stu-id="db302-147">Value</span></span>|<span data-ttu-id="db302-148">入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="db302-148">Enter `Contoso`.</span></span>|  
  
     <span data-ttu-id="db302-149">**追跡**</span><span class="sxs-lookup"><span data-stu-id="db302-149">**Tracking**</span></span>  
  
    |<span data-ttu-id="db302-150">**フィールド**</span><span class="sxs-lookup"><span data-stu-id="db302-150">**Field**</span></span>|<span data-ttu-id="db302-151">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="db302-151">**Description**</span></span>|  
    |---------------|---------------------|  
    |<span data-ttu-id="db302-152">送信側メッセージのプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="db302-152">Track Send side message properties</span></span>|<span data-ttu-id="db302-153">このパートナーに、EDI メッセージが送信されるメッセージのプロパティを格納するを確認します。</span><span class="sxs-lookup"><span data-stu-id="db302-153">Check this to store the message properties when the EDI message is sent to the partner.</span></span> <span data-ttu-id="db302-154">クリックしてこのデータを照会するには格納されたら、**追跡**Azure BizTalk ポータルの左側のウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="db302-154">Once stored, you can query this data by clicking **Tracking** from the left pane on the Azure BizTalk Portal.</span></span><br /><br /> <span data-ttu-id="db302-155">チェックして、メッセージ本文を格納できますも有効な場合、**トラックの送信側メッセージ本文**します。</span><span class="sxs-lookup"><span data-stu-id="db302-155">When enabled, you can also store the message body by checking **Track Send side message body**.</span></span>|  
    |<span data-ttu-id="db302-156">受信側メッセージのプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="db302-156">Track Receive side message properties</span></span>|<span data-ttu-id="db302-157">このパートナーから EDI メッセージを受信したときに、メッセージのプロパティを格納するを確認します。</span><span class="sxs-lookup"><span data-stu-id="db302-157">Check this to store the message properties when the EDI message is received from a partner.</span></span> <span data-ttu-id="db302-158">クリックしてこのデータを照会するには格納されたら、**追跡**Azure BizTalk ポータルの左側のウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="db302-158">Once stored, you can query this data by clicking **Tracking** from the left pane on the Azure BizTalk Portal.</span></span><br /><br /> <span data-ttu-id="db302-159">チェックして、メッセージ本文を格納できますも有効な場合、**トラックの受信側メッセージ本文**します。</span><span class="sxs-lookup"><span data-stu-id="db302-159">When enabled, you can also store the message body by checking **Track Receive side message body**.</span></span>|  
  
4.  <span data-ttu-id="db302-160">**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db302-160">Click **Continue**.</span></span>  
  
     <span data-ttu-id="db302-161">クリックすると**続行**2 つの新しいタブを追加します。 の 1 つの受信の設定とその他の送信設定。</span><span class="sxs-lookup"><span data-stu-id="db302-161">Clicking **Continue** adds two new tabs, one for receive settings and the other for send settings.</span></span> <span data-ttu-id="db302-162">各タブは、受信用のメッセージとメッセージを送信するため、その他の 2 つのパートナー間の一方向のアグリーメントです。</span><span class="sxs-lookup"><span data-stu-id="db302-162">Each tab is for a one-way agreement between the two partners, one for receiving messages and the other for sending messages.</span></span>  
  
5.  <span data-ttu-id="db302-163">受信設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="db302-163">Specify the receive settings.</span></span>  
  
    1.  <span data-ttu-id="db302-164">**トランスポート** ページで、設定、**トランスポートの種類**HTTP にします。</span><span class="sxs-lookup"><span data-stu-id="db302-164">On the **Transport** page, set the **Transport type** to HTTP.</span></span>  
  
         <span data-ttu-id="db302-165">**エンドポイント**フィールドには、Contoso が送信する必要があります、X12 URL が表示されます。 販売注文メッセージ。</span><span class="sxs-lookup"><span data-stu-id="db302-165">The **Endpoint** field shows the URL to which Contoso must send the X12 sales order message.</span></span>  
  
    2.  <span data-ttu-id="db302-166">**プロトコル** ページで、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="db302-166">On the **Protocol** page, specify the following values.</span></span>  
  
        1.  <span data-ttu-id="db302-167">必要に応じて、ISA1、ISA2、ISA3、および ISA4 の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="db302-167">If required, specify values for ISA1, ISA2, ISA3, and ISA4.</span></span>  
  
        2.  <span data-ttu-id="db302-168">**受信確認**を選択します**TA1 が必要**と**997 が必要です**受信するための応答として技術確認と機能確認を生成する場合、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="db302-168">Under **Acknowledgements**, select **TA1 expected** and **997 expected** if you want to generate technical and functional acknowledgements in response for receiving the message.</span></span>  
  
        3.  <span data-ttu-id="db302-169">**スキーマ**、クリックして、**アップロード**ボタンをクリックし、アップロード、 **X12 840 スキーマ**(からダウンロードした[ http://go.microsoft.com/fwlink/p/?LinkId=235057 ](http://go.microsoft.com/fwlink/p/?LinkId=235057)) と、 **SalesOrder**スキーマ (で作成した[EDI プロジェクト内のスキーマを作成する](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema))。</span><span class="sxs-lookup"><span data-stu-id="db302-169">Under **Schemas**, click the **Upload** button and upload the **X12 840 schema** (you downloaded from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)) and the **SalesOrder** schema (you created in [To create a schema within the EDI project](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema)).</span></span>  
  
             <span data-ttu-id="db302-170">次のプロパティを設定、**スキーマ**セクション。</span><span class="sxs-lookup"><span data-stu-id="db302-170">Set the following properties under the **Schemas** section.</span></span>  
  
            |||  
            |-|-|  
            |<span data-ttu-id="db302-171">バージョン</span><span class="sxs-lookup"><span data-stu-id="db302-171">Version</span></span>|<span data-ttu-id="db302-172">00401</span><span class="sxs-lookup"><span data-stu-id="db302-172">00401</span></span>|  
            |<span data-ttu-id="db302-173">トランザクションの種類 (ST1)</span><span class="sxs-lookup"><span data-stu-id="db302-173">Transaction Type (ST1)</span></span>|<span data-ttu-id="db302-174">840</span><span class="sxs-lookup"><span data-stu-id="db302-174">840</span></span>|  
            |<span data-ttu-id="db302-175">スキーマ</span><span class="sxs-lookup"><span data-stu-id="db302-175">Schema</span></span>|<span data-ttu-id="db302-176">/X12_00401_840.xsd</span><span class="sxs-lookup"><span data-stu-id="db302-176">/X12_00401_840.xsd</span></span>|  
  
    3.  <span data-ttu-id="db302-177">**変換**で作成した変換をアップロード ページで、 [EDI プロジェクト内の変換を作成する](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm)します。</span><span class="sxs-lookup"><span data-stu-id="db302-177">On the **Transform** page, upload the transform you created in [To create a transform within the EDI project](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm).</span></span>  
  
         <span data-ttu-id="db302-178">**このアグリーメントの一部として実行するマップを選択**、選択 **/X12_00401_840.xsd**の**スキーマ**と **/EDI840TOSALESORDER します。TRFM**の**変換ファイル名**します。</span><span class="sxs-lookup"><span data-stu-id="db302-178">Under **Choose the maps you want to execute as part of this agreement**, choose **/X12_00401_840.xsd** for **Schemas** and **/EDI840TOSALESORDER.TRFM** for **Transform file name**.</span></span>  
  
    4.  <span data-ttu-id="db302-179">**ルート**] ページで、[ **Service Bus キューへのルート**は、メッセージの送信先キューの相対アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="db302-179">On the **Route** page, select **Route to Service Bus Queue** and provide the relative address of the queue to which the message is sent.</span></span> <span data-ttu-id="db302-180">このチュートリアルでは、指定の相対アドレスとして`queueordersedi`完全な URL はように`https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`します。</span><span class="sxs-lookup"><span data-stu-id="db302-180">For this tutorial, specify the relative address as `queueordersedi` so that the complete URL is `https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="db302-181">このチュートリアルについては説明しませんメッセージ保留の設定に失敗したメッセージの送信先エンドポイントにするシナリオを指定します。</span><span class="sxs-lookup"><span data-stu-id="db302-181">This tutorial does not cover the scenario where a failed message is sent to the endpoint you specify in the Message Suspension Settings.</span></span> <span data-ttu-id="db302-182">ただし、アグリーメントの成功した展開は、この設定の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db302-182">However, for successful deployment of the agreement, you must provide a value for this setting.</span></span> <span data-ttu-id="db302-183">空でない値を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="db302-183">You can enter a non-empty value.</span></span>  
  
6.  <span data-ttu-id="db302-184">送信の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="db302-184">Specify the send settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db302-185">このチュートリアルで説明されている場合、送信側アグリーメントの構成が不要です。</span><span class="sxs-lookup"><span data-stu-id="db302-185">For the scenario described in this tutorial, you don’t need any send-side configuration for the agreement.</span></span> <span data-ttu-id="db302-186">ただし、アグリーメントはダミーの値にある場合でも、送信の設定を指定することがなく展開できません。</span><span class="sxs-lookup"><span data-stu-id="db302-186">However, an agreement cannot be deployed without specifying the send settings, even if they are dummy values.</span></span> <span data-ttu-id="db302-187">**送信の設定**ダミーの値を指定する必要はありません タブで、**受信 URI**、**変換**、および**バッチ処理**します。</span><span class="sxs-lookup"><span data-stu-id="db302-187">Also, On the **Send Settings** tab, you don’t need to provide any dummy values for **Inbound URI**, **Transform**, and **Batching**.</span></span>  
  
    1.  <span data-ttu-id="db302-188">**プロトコル**] ページ [**スキーマ**、クリックして、**アップロード**ボタンをクリックし、X12 のスキーマをアップロード 840 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="db302-188">On the **Protocol** page, under **Schemas**, click the **Upload** button and upload the schema for the X12 840 message.</span></span>  
  
         <span data-ttu-id="db302-189">設定、**バージョン**に**00401**、**トランザクション タイプ**に**840**、および**スキーマ**に**X12_00401_840**します。</span><span class="sxs-lookup"><span data-stu-id="db302-189">Set the **Version** to **00401**, **Transaction Type** to **840**, and **Schema** to **X12_00401_840**.</span></span>  
  
    2.  <span data-ttu-id="db302-190">**トランスポート** ページで、パートナーへの応答メッセージまたは受信確認を送信する先のエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="db302-190">On the **Transport** page, specify the endpoints where the response messages or acknowledgements will be sent to the partners.</span></span> <span data-ttu-id="db302-191">エンドポイントを正常に処理されるメッセージだけでなく、処理中のエラーにより保留になったメッセージを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db302-191">You must specify an endpoint each for the messages that are processed successfully as well as the messages that get suspended due to a failure in processing.</span></span>  
  
7.  <span data-ttu-id="db302-192">クリックして**アグリーメントの展開**アグリーメントをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="db302-192">Click **Deploy Agreement** to deploy the agreement.</span></span> <span data-ttu-id="db302-193">表示された URL で、アグリーメントが展開されているようになりました、**トランスポート**のページ、**受信の設定**タブ。</span><span class="sxs-lookup"><span data-stu-id="db302-193">The agreement is now deployed at the URL that was displayed in the **Transport** page of the **Receive Settings** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db302-194">参照</span><span class="sxs-lookup"><span data-stu-id="db302-194">See Also</span></span>  
 [<span data-ttu-id="db302-195">チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="db302-195">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)
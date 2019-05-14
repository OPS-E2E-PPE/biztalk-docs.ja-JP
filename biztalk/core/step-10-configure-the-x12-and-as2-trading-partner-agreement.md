---
title: 手順 10:X12 および AS2 取引先アグリーメントの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8fcdb3af-727a-4d20-9dcf-cf162e7d3398
caps.latest.revision: 46
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 582c3ebcbbfe5878d3cffbda187c3f8fcab2d46a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392789"
---
# <a name="step-10-configure-the-x12-and-as2-trading-partner-agreement"></a><span data-ttu-id="475f9-102">手順 10:X12 および AS2 取引先アグリーメントを構成します。</span><span class="sxs-lookup"><span data-stu-id="475f9-102">Step 10: Configure the X12 and AS2 Trading Partner Agreement</span></span>
<span data-ttu-id="475f9-103">![手順 10 の 11](../core/media/tut-step10-of-11.gif "Tut_Step10_of_11")</span><span class="sxs-lookup"><span data-stu-id="475f9-103">![Step 10 of 11](../core/media/tut-step10-of-11.gif "Tut_Step10_of_11")</span></span>  

 <span data-ttu-id="475f9-104">このステップでは、EDIINT/AS2 でエンコードされたメッセージを HTTP 経由で送信するように X12 および AS2 の取引先アグリーメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="475f9-104">In this step you set up X12 and AS2 trading partner agreements to transport an EDIINT/AS2-encoded message over HTTP.</span></span> <span data-ttu-id="475f9-105">この Fabrikam パーティは、EDI インターチェンジを Contoso に送信します。これにより、997 受信確認と非同期 MDN が Fabrikam に返されます。</span><span class="sxs-lookup"><span data-stu-id="475f9-105">This Fabrikam party sends the EDI interchange to Contoso, which returns the 997 acknowledgment and an asynchronous MDN to Fabrikam.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="475f9-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="475f9-106">Prerequisites</span></span>  
 <span data-ttu-id="475f9-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="475f9-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  

### <a name="to-create-an-as2-agreement"></a><span data-ttu-id="475f9-108">AS2 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="475f9-108">To create an AS2 agreement</span></span>  

1. <span data-ttu-id="475f9-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-109">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="475f9-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**パーティ**し、コンソール ツリーで、**パーティとビジネス プロファイル** ページで、右クリックして**Fabrikam_Profile**、 をポイント**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

3. <span data-ttu-id="475f9-111">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="475f9-111">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

4. <span data-ttu-id="475f9-112">**プロトコル**ドロップダウン リストで、 **AS2**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-112">From the **Protocol** drop-down list, select **AS2**.</span></span>  

5. <span data-ttu-id="475f9-113">**2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Contoso**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-113">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

6. <span data-ttu-id="475f9-114">**2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-114">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="475f9-115">2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは、一方向の AS2 アグリーメントの構成用です。</span><span class="sxs-lookup"><span data-stu-id="475f9-115">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  

7. <span data-ttu-id="475f9-116">**全般** タブで、**全般プロパティ**ページで、**共通のホスト設定**セクションで、**レポートをオン**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-116">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**.</span></span>  

8. <span data-ttu-id="475f9-117">次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。</span><span class="sxs-lookup"><span data-stu-id="475f9-117">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1.  <span data-ttu-id="475f9-118">**識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-118">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="475f9-119">**AS2-から**、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="475f9-119">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="475f9-120">**AS2-To**、入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="475f9-120">For **AS2- To**, enter `Contoso`.</span></span>  

   2.  <span data-ttu-id="475f9-121">**検証** ページで、、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="475f9-121">On the **Validation** page, select the **Use agreement settings for validation and MDN instead of message header** check box</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="475f9-122">このプロパティを設定すると、MDN を生成するときに受信 AS2 メッセージの AS2 ヘッダーではなくパーティのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="475f9-122">Setting this property ensures that the party properties will be used when generating the MDN, rather than the AS2 headers of the received AS2 message.</span></span>  

   3.  <span data-ttu-id="475f9-123">**受信確認 (Mdn)** ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="475f9-123">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  

       1.  <span data-ttu-id="475f9-124">選択、 **mdn を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="475f9-124">Select the **Request MDN** check box.</span></span>  

       2.  <span data-ttu-id="475f9-125">必ず、**署名付き MDN を要求**チェック ボックスをオフします。</span><span class="sxs-lookup"><span data-stu-id="475f9-125">Make sure the **Request Signed MDN** check box is cleared.</span></span>  

       3.  <span data-ttu-id="475f9-126">選択、**非同期 MDN を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="475f9-126">Select the **Request asynchronous MDN** check box.</span></span>  

       4.  <span data-ttu-id="475f9-127">**- Receipt-delivery-option (URL)** テキスト ボックスに、入力`http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="475f9-127">In the **Receipt-Delivery-Option (URL)** text box, enter `http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`.</span></span>  

9. <span data-ttu-id="475f9-128">次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。</span><span class="sxs-lookup"><span data-stu-id="475f9-128">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   1. <span data-ttu-id="475f9-129">**識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-129">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="475f9-130">**AS2-から**、入力`Contoso`します。</span><span class="sxs-lookup"><span data-stu-id="475f9-130">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="475f9-131">**AS2-To**、入力`Fabrikam`します。</span><span class="sxs-lookup"><span data-stu-id="475f9-131">For **AS2- To**, enter `Fabrikam`.</span></span>  

   2. <span data-ttu-id="475f9-132">**送信ポート**ページで、**インターチェンジの設定**セクションで、**送信ポート** ボックスの一覧の**名前**選択**Send_Async_997**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-132">On the **Send Ports** page under the **Interchange Settings** section, in the **Send Ports** list, for **Name** select **Send_Async_997**.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="475f9-133">入力される必要があります、Send_Async_997 送信ポート、**送信ポート**一覧ように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信 997 メッセージのパーティを解決することができます。</span><span class="sxs-lookup"><span data-stu-id="475f9-133">The Send_Async_997 send port needs to be entered into the **Send Ports** list so that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can resolve the party for the outgoing 997 message.</span></span> <span data-ttu-id="475f9-134">送信パイプラインは、送信ポートの名前をアグリーメント プロパティの送信ポートと照合します。</span><span class="sxs-lookup"><span data-stu-id="475f9-134">The send pipeline matches the name of the send port with the send port in the agreement properties.</span></span> <span data-ttu-id="475f9-135">これは、送信パイプラインがパーティの解決を試みる際に最初に照合する AS2-To プロパティがメッセージのコンテキストで昇格されないために必要になります。</span><span class="sxs-lookup"><span data-stu-id="475f9-135">This is necessary because in this case, the AS2-To property is not promoted in the context of the message, which is the first match that the send pipeline attempts to make to resolve the party.</span></span> <span data-ttu-id="475f9-136">詳細については、次を参照してください。[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="475f9-136">For more information, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  

10. <span data-ttu-id="475f9-137">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="475f9-137">Click **Apply**.</span></span>  

11. <span data-ttu-id="475f9-138">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="475f9-138">Click **OK**.</span></span> <span data-ttu-id="475f9-139">新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="475f9-139">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="475f9-140">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="475f9-140">The newly added agreement is enabled by default.</span></span>  

### <a name="to-create-an-x12-agreement"></a><span data-ttu-id="475f9-141">X12 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="475f9-141">To create an X12 agreement</span></span>  

1. <span data-ttu-id="475f9-142">右クリック**fabrikam_profile**、 をポイント**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-142">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="475f9-143">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="475f9-143">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  

3. <span data-ttu-id="475f9-144">**プロトコル**ドロップダウン リストで、 **X12**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-144">From the **Protocol** drop-down list, select **X12**.</span></span>  

4. <span data-ttu-id="475f9-145">**2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Contoso**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-145">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  

5. <span data-ttu-id="475f9-146">**2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-146">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  

    <span data-ttu-id="475f9-147">2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは一方向 X12 アグリーメントを構成するためのものです。</span><span class="sxs-lookup"><span data-stu-id="475f9-147">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way X12 agreement.</span></span>  

6. <span data-ttu-id="475f9-148">**全般** タブで、**全般プロパティ**ページで、**共通のホスト設定**セクションで、**レポートをオン**、し、選択**メッセージ ペイロードを格納するレポートの**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-148">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  

7. <span data-ttu-id="475f9-149">次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。</span><span class="sxs-lookup"><span data-stu-id="475f9-149">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  

   1. <span data-ttu-id="475f9-150">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応しています。</span><span class="sxs-lookup"><span data-stu-id="475f9-150">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span> <span data-ttu-id="475f9-151">このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**7654321**、 **ISA7**に**ZZ。**、および**ISA8**に**1234567**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-151">For this tutorial, set **ISA5** to **ZZ**, **ISA6** to **7654321**, **ISA7** to **ZZ**, and **ISA8** to **1234567**.</span></span>  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="475f9-152">では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="475f9-152">requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="475f9-153">値と一致します**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**をアグリーメントのプロパティと、インターチェンジ ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="475f9-153">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="475f9-154">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="475f9-154">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="475f9-155">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="475f9-155">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  

   2. <span data-ttu-id="475f9-156">**受信確認**ページで、**インターチェンジの設定**セクションで、 **997 が必要**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="475f9-156">On the **Acknowledgements** page under the **Interchange Settings** section, select the **997 Expected** check box.</span></span>  

   3. <span data-ttu-id="475f9-157">**検証**ページで、**インターチェンジの設定**セクションをご確認ください**重複している isa13 を確認**オプションが選択されていません。</span><span class="sxs-lookup"><span data-stu-id="475f9-157">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="475f9-158">オフにすると、**重複している isa13 を確認**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="475f9-158">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  

   4. <span data-ttu-id="475f9-159">**ローカル ホスト設定**ページで、**インターチェンジの設定**セクションの**受信者の設定**, clear**で送信パイプラインに確認をルーティング要求-応答の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-159">On the **Local Host Settings** page under the **Interchange Settings** section, under **Receiver’s Settings**, clear **Route ACK to send pipeline on request-response receive port**.</span></span>  

      > [!NOTE]
      >  <span data-ttu-id="475f9-160">このプロパティをオフにすると、双方向受信ポートに関連付けられた送信ポートではなく、別の送信ポート経由で 997 受信確認を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="475f9-160">Clearing this property enables you to send the 997 acknowledgment via a separate send port, rather than sending it over the send port associated with the two-way receive port.</span></span>  

8. <span data-ttu-id="475f9-161">次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。</span><span class="sxs-lookup"><span data-stu-id="475f9-161">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  

   1. <span data-ttu-id="475f9-162">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応しています。</span><span class="sxs-lookup"><span data-stu-id="475f9-162">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  <span data-ttu-id="475f9-163">このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**1234567**、 **ISA7**に**ZZ。**、および**ISA8**に**7654321**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-163">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **1234567**, **ISA7** to **ZZ**, and **ISA8** to **7654321**.</span></span>  

   2. <span data-ttu-id="475f9-164">**文字セットと区切り記号**ページで、**インターチェンジの設定**セクションの**サフィックス**を選択します**CR LF**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-164">On the **Charset and Separators** page under the **Interchange Settings** section, for **Suffix**, select **CR LF**.</span></span>  

   3. <span data-ttu-id="475f9-165">**エンベロープ**ページで、**トランザクション セットの設定**セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="475f9-165">On the **Envelopes** page under the **Transaction Set Settings** section, do the following:</span></span>  


      |       <span data-ttu-id="475f9-166">プロパティ</span><span class="sxs-lookup"><span data-stu-id="475f9-166">Use this</span></span>       |                                                                                                                                              <span data-ttu-id="475f9-167">目的</span><span class="sxs-lookup"><span data-stu-id="475f9-167">To do this</span></span>                                                                                                                                               |
      |----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     <span data-ttu-id="475f9-168">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="475f9-168">**Default**</span></span>      |              <span data-ttu-id="475f9-169">選択**既定**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-169">Select **Default**.</span></span> <span data-ttu-id="475f9-170">**注:** 既定の値としてこの行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**は使用されている場合であってもの値は、**トランザクションの種類**、**バージョン/リリース**と**ターゲットの名前空間**と一致するメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="475f9-170">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>              |
      | <span data-ttu-id="475f9-171">**トランザクションの種類**</span><span class="sxs-lookup"><span data-stu-id="475f9-171">**Transaction Type**</span></span> |                                                                                                          <span data-ttu-id="475f9-172">たとえば、テスト メッセージのメッセージの種類を選択**864 – テキスト メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-172">Select the message type of your test message, for example, **864 – Text Message**.</span></span>                                                                                                           |
      | <span data-ttu-id="475f9-173">**バージョン/リリース**</span><span class="sxs-lookup"><span data-stu-id="475f9-173">**Version/Release**</span></span>  |                                                                                                                                           <span data-ttu-id="475f9-174">入力**00401**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-174">Enter **00401**.</span></span>                                                                                                                                            |
      | <span data-ttu-id="475f9-175">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="475f9-175">**Target namespace**</span></span> |                                                                                                                    <span data-ttu-id="475f9-176">選択 **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>** します。</span><span class="sxs-lookup"><span data-stu-id="475f9-176">Select **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>**.</span></span>                                                                                                                    |
      |       <span data-ttu-id="475f9-177">**[GS1]**</span><span class="sxs-lookup"><span data-stu-id="475f9-177">**GS1**</span></span>        |                                                                                                <span data-ttu-id="475f9-178">テスト メッセージのメッセージの種類が選択されているなどを確認します。 **TX - テキスト メッセージ (864)** します。</span><span class="sxs-lookup"><span data-stu-id="475f9-178">Verify that the message type of the test message is selected, for example, **TX - Text Message (864)**.</span></span>                                                                                                |
      |       <span data-ttu-id="475f9-179">**[GS2]**</span><span class="sxs-lookup"><span data-stu-id="475f9-179">**GS2**</span></span>        |                                                                                                                                             <span data-ttu-id="475f9-180">入力**01**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-180">Enter **01**.</span></span>                                                                                                                                             |
      |       <span data-ttu-id="475f9-181">**[GS3]**</span><span class="sxs-lookup"><span data-stu-id="475f9-181">**GS3**</span></span>        |                                                                                                                                          <span data-ttu-id="475f9-182">入力**7654321**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-182">Enter **7654321**.</span></span>                                                                                                                                           |
      |       <span data-ttu-id="475f9-183">**GS4**</span><span class="sxs-lookup"><span data-stu-id="475f9-183">**GS4**</span></span>        | <span data-ttu-id="475f9-184">日付の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="475f9-184">Select the date format that you want.</span></span> <span data-ttu-id="475f9-185">選択**CCYYMMDD**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-185">Select **CCYYMMDD**.</span></span> <span data-ttu-id="475f9-186">**注:** ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="475f9-186">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="475f9-187">ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。</span><span class="sxs-lookup"><span data-stu-id="475f9-187">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span> |
      |       <span data-ttu-id="475f9-188">**GS5**</span><span class="sxs-lookup"><span data-stu-id="475f9-188">**GS5**</span></span>        |                                                                                                                      <span data-ttu-id="475f9-189">時刻の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="475f9-189">Select the time format that you want.</span></span> <span data-ttu-id="475f9-190">選択**HHMMSSdd**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-190">Select **HHMMSSdd**.</span></span>                                                                                                                       |
      |       <span data-ttu-id="475f9-191">**GS7**</span><span class="sxs-lookup"><span data-stu-id="475f9-191">**GS7**</span></span>        |                                                                                                                   <span data-ttu-id="475f9-192">選択**T - 運輸データ調整委員会 (Tdcc)** します。</span><span class="sxs-lookup"><span data-stu-id="475f9-192">Select **T - Transportation Data Coordinating Committee (TDCC)**.</span></span>                                                                                                                   |
      |       <span data-ttu-id="475f9-193">**GS8**</span><span class="sxs-lookup"><span data-stu-id="475f9-193">**GS8**</span></span>        |                                                                                                                      <span data-ttu-id="475f9-194">EDI のバージョンとして入力されたことを確認します。 **00401**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-194">Verify that the EDI version has been entered as **00401**.</span></span>                                                                                                                       |


9. <span data-ttu-id="475f9-195">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="475f9-195">Click **Apply**.</span></span>  

10. <span data-ttu-id="475f9-196">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="475f9-196">Click **OK**.</span></span> <span data-ttu-id="475f9-197">新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="475f9-197">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="475f9-198">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="475f9-198">The newly added agreement is enabled by default.</span></span>  

11. <span data-ttu-id="475f9-199">BizTalk サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="475f9-199">Restart the BizTalk service.</span></span> <span data-ttu-id="475f9-200">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[**プラットフォームの設定**、] をクリックして**ホスト インスタンス**、右クリックして**BizTalkServerApplication**順にクリックします**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="475f9-200">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="475f9-201">次の手順</span><span class="sxs-lookup"><span data-stu-id="475f9-201">Next Steps</span></span>  
 <span data-ttu-id="475f9-202">」の説明に従って、AS2 ソリューションをテストする[手順 11。AS2 ソリューションのテスト](../core/step-11-test-the-as2-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="475f9-202">You test the AS2 solution, as described in [Step 11: Test the AS2 Solution](../core/step-11-test-the-as2-solution.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="475f9-203">参照</span><span class="sxs-lookup"><span data-stu-id="475f9-203">See Also</span></span>  
 <span data-ttu-id="475f9-204">[AS2 のプロパティを構成します。](../core/configuring-as2-properties.md) </span><span class="sxs-lookup"><span data-stu-id="475f9-204">[Configuring AS2 Properties](../core/configuring-as2-properties.md) </span></span>  
 [<span data-ttu-id="475f9-205">EDI のプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="475f9-205">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)
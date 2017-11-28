---
title: "手順 10: X12 および AS2 取引先アグリーメントの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fcdb3af-727a-4d20-9dcf-cf162e7d3398
caps.latest.revision: "46"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd0ce0ef6fef056c52e06fc1843024cbcf683c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-10-configure-the-x12-and-as2-trading-partner-agreement"></a><span data-ttu-id="32eab-102">手順 10: X12 および AS2 取引先アグリーメントを構成します。</span><span class="sxs-lookup"><span data-stu-id="32eab-102">Step 10: Configure the X12 and AS2 Trading Partner Agreement</span></span>
<span data-ttu-id="32eab-103">![手順 11 の 10](../core/media/tut-step10-of-11.gif "Tut_Step10_of_11")</span><span class="sxs-lookup"><span data-stu-id="32eab-103">![Step 10 of 11](../core/media/tut-step10-of-11.gif "Tut_Step10_of_11")</span></span>  
  
 <span data-ttu-id="32eab-104">このステップでは、EDIINT/AS2 でエンコードされたメッセージを HTTP 経由で送信するように X12 および AS2 の取引先アグリーメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="32eab-104">In this step you set up X12 and AS2 trading partner agreements to transport an EDIINT/AS2-encoded message over HTTP.</span></span> <span data-ttu-id="32eab-105">この Fabrikam パーティは、EDI インターチェンジを Contoso に送信します。これにより、997 受信確認と非同期 MDN が Fabrikam に返されます。</span><span class="sxs-lookup"><span data-stu-id="32eab-105">This Fabrikam party sends the EDI interchange to Contoso, which returns the 997 acknowledgment and an asynchronous MDN to Fabrikam.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32eab-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="32eab-106">Prerequisites</span></span>  
 <span data-ttu-id="32eab-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32eab-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-an-as2-agreement"></a><span data-ttu-id="32eab-108">AS2 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="32eab-108">To create an AS2 agreement</span></span>  
  
1.  <span data-ttu-id="32eab-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-109">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="32eab-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**パーティ**し、コンソール ツリーで、[、**パーティとビジネス プロファイル**] ページを右クリックして**Fabrikam_Profile**、をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
3.  <span data-ttu-id="32eab-111">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="32eab-111">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
4.  <span data-ttu-id="32eab-112">**プロトコル**ドロップダウン リストで、 **AS2**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-112">From the **Protocol** drop-down list, select **AS2**.</span></span>  
  
5.  <span data-ttu-id="32eab-113">**2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、 **Contoso**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-113">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  
  
6.  <span data-ttu-id="32eab-114">**2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-114">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  
  
     <span data-ttu-id="32eab-115">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブは、一方向の AS2 アグリーメントの構成用です。</span><span class="sxs-lookup"><span data-stu-id="32eab-115">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way AS2 agreement.</span></span>  
  
7.  <span data-ttu-id="32eab-116">**全般** タブで、**全般プロパティ** ページの 、**共通のホスト設定**セクションで、**レポートをオンに**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-116">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**.</span></span>  
  
8.  <span data-ttu-id="32eab-117">次のタスクを実行、 **Fabrikam が Contoso ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="32eab-117">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    1.  <span data-ttu-id="32eab-118">**識別子** ページで、値を入力**AS2-から**と**AS2-に**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-118">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="32eab-119">**AS2-から**、入力`Fabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="32eab-119">For **AS2-From**, enter `Fabrikam`.</span></span> <span data-ttu-id="32eab-120">**AS2-To**、入力`Contoso`です。</span><span class="sxs-lookup"><span data-stu-id="32eab-120">For **AS2- To**, enter `Contoso`.</span></span>  
  
    2.  <span data-ttu-id="32eab-121">**検証** ページで、、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して** チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="32eab-121">On the **Validation** page, select the **Use agreement settings for validation and MDN instead of message header** check box</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="32eab-122">このプロパティを設定すると、MDN を生成するときに受信 AS2 メッセージの AS2 ヘッダーではなくパーティのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="32eab-122">Setting this property ensures that the party properties will be used when generating the MDN, rather than the AS2 headers of the received AS2 message.</span></span>  
  
    3.  <span data-ttu-id="32eab-123">**受信確認 (Mdn)**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="32eab-123">In the **Acknowledgements (MDNs)** page, do the following:</span></span>  
  
        1.  <span data-ttu-id="32eab-124">選択、 **mdn を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="32eab-124">Select the **Request MDN** check box.</span></span>  
  
        2.  <span data-ttu-id="32eab-125">確認してください、**署名付き mdn を要求してもする**チェック ボックスはオフです。</span><span class="sxs-lookup"><span data-stu-id="32eab-125">Make sure the **Request Signed MDN** check box is cleared.</span></span>  
  
        3.  <span data-ttu-id="32eab-126">選択、**非同期 MDN を要求する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="32eab-126">Select the **Request asynchronous MDN** check box.</span></span>  
  
        4.  <span data-ttu-id="32eab-127">**- Receipt-delivery-option (URL)**テキスト ボックスに、入力`http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="32eab-127">In the **Receipt-Delivery-Option (URL)** text box, enter `http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`.</span></span>  
  
9. <span data-ttu-id="32eab-128">次のタスクを実行、 **Contoso が Fabrikam ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="32eab-128">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="32eab-129">**識別子** ページで、値を入力**AS2-から**と**AS2-に**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-129">On the **Identifiers** page, enter values for **AS2-From** and **AS2-To**.</span></span> <span data-ttu-id="32eab-130">**AS2-から**、入力`Contoso`です。</span><span class="sxs-lookup"><span data-stu-id="32eab-130">For **AS2-From**, enter `Contoso`.</span></span> <span data-ttu-id="32eab-131">**AS2-To**、入力`Fabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="32eab-131">For **AS2- To**, enter `Fabrikam`.</span></span>  
  
    2.  <span data-ttu-id="32eab-132">**送信ポート**ページで、**インターチェンジの設定**セクションで、**送信ポート** ボックスの一覧の**名前**選択**Send_Async_997**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-132">On the **Send Ports** page under the **Interchange Settings** section, in the **Send Ports** list, for **Name** select **Send_Async_997**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="32eab-133">入力する必要があります、Send_Async_997 送信ポート、**送信ポート**リストように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信 997 メッセージのパーティを解決することができます。</span><span class="sxs-lookup"><span data-stu-id="32eab-133">The Send_Async_997 send port needs to be entered into the **Send Ports** list so that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can resolve the party for the outgoing 997 message.</span></span> <span data-ttu-id="32eab-134">送信パイプラインは、送信ポートの名前をアグリーメント プロパティの送信ポートと照合します。</span><span class="sxs-lookup"><span data-stu-id="32eab-134">The send pipeline matches the name of the send port with the send port in the agreement properties.</span></span> <span data-ttu-id="32eab-135">これは、送信パイプラインがパーティの解決を試みる際に最初に照合する AS2-To プロパティがメッセージのコンテキストで昇格されないために必要になります。</span><span class="sxs-lookup"><span data-stu-id="32eab-135">This is necessary because in this case, the AS2-To property is not promoted in the context of the message, which is the first match that the send pipeline attempts to make to resolve the party.</span></span> <span data-ttu-id="32eab-136">詳細については、次を参照してください。[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="32eab-136">For more information, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
10. <span data-ttu-id="32eab-137">**[適用]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32eab-137">Click **Apply**.</span></span>  
  
11. <span data-ttu-id="32eab-138">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32eab-138">Click **OK**.</span></span> <span data-ttu-id="32eab-139">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="32eab-139">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="32eab-140">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="32eab-140">The newly added agreement is enabled by default.</span></span>  
  
### <a name="to-create-an-x12-agreement"></a><span data-ttu-id="32eab-141">X12 アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="32eab-141">To create an X12 agreement</span></span>  
  
1.  <span data-ttu-id="32eab-142">右クリック**[fabrikam_profile]**、をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-142">Right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="32eab-143">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="32eab-143">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="32eab-144">**プロトコル**ドロップダウン リストで、 **X12**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-144">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
4.  <span data-ttu-id="32eab-145">**2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、 **Contoso**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-145">In the **Second Partner** section, from the **Name** drop-down list, select **Contoso**.</span></span>  
  
5.  <span data-ttu-id="32eab-146">**2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-146">In the **Second Partner** section, from the **Profile** drop-down list, select **Contoso_Profile**.</span></span>  
  
     <span data-ttu-id="32eab-147">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブは一方向 X12 アグリーメントを構成するためのものです。</span><span class="sxs-lookup"><span data-stu-id="32eab-147">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way X12 agreement.</span></span>  
  
6.  <span data-ttu-id="32eab-148">**全般** タブで、**全般プロパティ** ページの 、**共通のホスト設定**セクションで、**レポートをオンに**、し、選択**reporting 用メッセージ ペイロードを格納**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-148">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
7.  <span data-ttu-id="32eab-149">次のタスクを実行、 **Fabrikam が Contoso ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="32eab-149">Perform the following tasks on the **Fabrikam->Contoso** tab.</span></span>  
  
    1.  <span data-ttu-id="32eab-150">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="32eab-150">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span> <span data-ttu-id="32eab-151">このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**7654321**、 **ISA7**に**ZZ。**、および**ISA8**に**1234567**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-151">For this tutorial, set **ISA5** to **ZZ**, **ISA6** to **7654321**, **ISA7** to **ZZ**, and **ISA8** to **1234567**.</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="32eab-152"> では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32eab-152"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="32eab-153">値と照合**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**とアグリーメントのプロパティで、インターチェンジ ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="32eab-153">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="32eab-154">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="32eab-154">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="32eab-155">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="32eab-155">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
    2.  <span data-ttu-id="32eab-156">**受信確認**ページで、[、**インターチェンジの設定**] セクションで、select、 **997 が必要**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="32eab-156">On the **Acknowledgements** page under the **Interchange Settings** section, select the **997 Expected** check box.</span></span>  
  
    3.  <span data-ttu-id="32eab-157">**検証**ページで、、**インターチェンジの設定**セクションで、確認してください**重複している isa13 を確認**オプションがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="32eab-157">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="32eab-158">オフにすると、**重複している isa13 を確認して**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="32eab-158">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    4.  <span data-ttu-id="32eab-159">**ローカル ホストの設定**ページで、**インターチェンジの設定**セクションの **受信者の設定**, clear**で送信パイプラインに確認をルーティング要求-応答受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-159">On the **Local Host Settings** page under the **Interchange Settings** section, under **Receiver’s Settings**, clear **Route ACK to send pipeline on request-response receive port**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="32eab-160">このプロパティをオフにすると、双方向受信ポートに関連付けられた送信ポートではなく、別の送信ポート経由で 997 受信確認を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="32eab-160">Clearing this property enables you to send the 997 acknowledgment via a separate send port, rather than sending it over the send port associated with the two-way receive port.</span></span>  
  
8.  <span data-ttu-id="32eab-161">次のタスクを実行、 **Contoso が Fabrikam ->**タブです。</span><span class="sxs-lookup"><span data-stu-id="32eab-161">Perform the following tasks on the **Contoso->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="32eab-162">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="32eab-162">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  <span data-ttu-id="32eab-163">このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**1234567**、 **ISA7**に**ZZ。**、および**ISA8**に**7654321**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-163">For this walkthrough, set **ISA5** to **ZZ**, **ISA6** to **1234567**, **ISA7** to **ZZ**, and **ISA8** to **7654321**.</span></span>  
  
    2.  <span data-ttu-id="32eab-164">**文字セットと区切り記号**ページで、、**インターチェンジの設定** セクションの**サフィックス** **CR LF**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-164">On the **Charset and Separators** page under the **Interchange Settings** section, for **Suffix**, select **CR LF**.</span></span>  
  
    3.  <span data-ttu-id="32eab-165">**エンベロープ**ページで、**トランザクション セットの設定**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="32eab-165">On the **Envelopes** page under the **Transaction Set Settings** section, do the following:</span></span>  
  
        |<span data-ttu-id="32eab-166">プロパティ</span><span class="sxs-lookup"><span data-stu-id="32eab-166">Use this</span></span>|<span data-ttu-id="32eab-167">目的</span><span class="sxs-lookup"><span data-stu-id="32eab-167">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="32eab-168">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="32eab-168">**Default**</span></span>|<span data-ttu-id="32eab-169">選択**既定**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-169">Select **Default**.</span></span> <span data-ttu-id="32eab-170">**注:** 、既定の値は、この行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**が使用される場合でもの値は、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**の一致するものではありません、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="32eab-170">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="32eab-171">**トランザクションの種類**</span><span class="sxs-lookup"><span data-stu-id="32eab-171">**Transaction Type**</span></span>|<span data-ttu-id="32eab-172">たとえば、テスト メッセージのメッセージの種類を選択**864 – テキスト メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-172">Select the message type of your test message, for example, **864 – Text Message**.</span></span>|  
        |<span data-ttu-id="32eab-173">**バージョン/リリース**</span><span class="sxs-lookup"><span data-stu-id="32eab-173">**Version/Release**</span></span>|<span data-ttu-id="32eab-174">入力**00401**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-174">Enter **00401**.</span></span>|  
        |<span data-ttu-id="32eab-175">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="32eab-175">**Target namespace**</span></span>|<span data-ttu-id="32eab-176">選択**http://schemas.microsoft.com/BizTalk/EDI/X12/2006**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-176">Select **http://schemas.microsoft.com/BizTalk/EDI/X12/2006**.</span></span>|  
        |<span data-ttu-id="32eab-177">**GS1**</span><span class="sxs-lookup"><span data-stu-id="32eab-177">**GS1**</span></span>|<span data-ttu-id="32eab-178">テスト メッセージのメッセージの種類が選択されているなどを確認してください。 **TX - テキスト メッセージ (864)**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-178">Verify that the message type of the test message is selected, for example, **TX - Text Message (864)**.</span></span>|  
        |<span data-ttu-id="32eab-179">**[GS2]**</span><span class="sxs-lookup"><span data-stu-id="32eab-179">**GS2**</span></span>|<span data-ttu-id="32eab-180">入力**01**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-180">Enter **01**.</span></span>|  
        |<span data-ttu-id="32eab-181">**[GS3]**</span><span class="sxs-lookup"><span data-stu-id="32eab-181">**GS3**</span></span>|<span data-ttu-id="32eab-182">入力**7654321**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-182">Enter **7654321**.</span></span>|  
        |<span data-ttu-id="32eab-183">**GS4**</span><span class="sxs-lookup"><span data-stu-id="32eab-183">**GS4**</span></span>|<span data-ttu-id="32eab-184">日付の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="32eab-184">Select the date format that you want.</span></span> <span data-ttu-id="32eab-185">選択**CCYYMMDD**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-185">Select **CCYYMMDD**.</span></span> <span data-ttu-id="32eab-186">**注:**ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32eab-186">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="32eab-187">ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。</span><span class="sxs-lookup"><span data-stu-id="32eab-187">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="32eab-188">**GS5**</span><span class="sxs-lookup"><span data-stu-id="32eab-188">**GS5**</span></span>|<span data-ttu-id="32eab-189">時刻の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="32eab-189">Select the time format that you want.</span></span> <span data-ttu-id="32eab-190">選択**HHMMSSdd**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-190">Select **HHMMSSdd**.</span></span>|  
        |<span data-ttu-id="32eab-191">**GS7**</span><span class="sxs-lookup"><span data-stu-id="32eab-191">**GS7**</span></span>|<span data-ttu-id="32eab-192">選択**T - 運輸データ調整委員会 (TDCC)**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-192">Select **T - Transportation Data Coordinating Committee (TDCC)**.</span></span>|  
        |<span data-ttu-id="32eab-193">**GS8**</span><span class="sxs-lookup"><span data-stu-id="32eab-193">**GS8**</span></span>|<span data-ttu-id="32eab-194">EDI のバージョンとして入力されたことを確認してください。 **00401**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-194">Verify that the EDI version has been entered as **00401**.</span></span>|  
  
9. <span data-ttu-id="32eab-195">**[適用]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32eab-195">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="32eab-196">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32eab-196">Click **OK**.</span></span> <span data-ttu-id="32eab-197">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="32eab-197">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="32eab-198">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="32eab-198">The newly added agreement is enabled by default.</span></span>  
  
11. <span data-ttu-id="32eab-199">BizTalk サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="32eab-199">Restart the BizTalk service.</span></span> <span data-ttu-id="32eab-200">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの**プラットフォームの設定**をクリックして**ホスト インスタンス**を右クリックして**BizTalkServerApplication**をクリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="32eab-200">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="32eab-201">次の手順</span><span class="sxs-lookup"><span data-stu-id="32eab-201">Next Steps</span></span>  
 <span data-ttu-id="32eab-202">」の説明に従って、AS2 ソリューションをテストする[手順 11: AS2 ソリューションのテスト](../core/step-11-test-the-as2-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="32eab-202">You test the AS2 solution, as described in [Step 11: Test the AS2 Solution](../core/step-11-test-the-as2-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32eab-203">参照</span><span class="sxs-lookup"><span data-stu-id="32eab-203">See Also</span></span>  
 <span data-ttu-id="32eab-204">[AS2 のプロパティを構成します。](../core/configuring-as2-properties.md) </span><span class="sxs-lookup"><span data-stu-id="32eab-204">[Configuring AS2 Properties](../core/configuring-as2-properties.md) </span></span>  
 [<span data-ttu-id="32eab-205">EDI のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="32eab-205">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)
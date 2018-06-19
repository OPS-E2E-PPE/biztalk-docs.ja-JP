---
title: '手順 8: 当事者間の取引先アグリーメントの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f532f85-3f09-4b60-b7bb-817ee3c79899
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25e49bf5dcae7324fa3b68fe5080d094b4a2f603
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280018"
---
# <a name="step-8-configure-the-trading-partner-agreement-between-the-parties"></a><span data-ttu-id="16da3-102">手順 8: 当事者間の取引先アグリーメントを構成します。</span><span class="sxs-lookup"><span data-stu-id="16da3-102">Step 8: Configure the Trading Partner Agreement between the Parties</span></span>
<span data-ttu-id="16da3-103">![手順 9 の 8](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span><span class="sxs-lookup"><span data-stu-id="16da3-103">![Step 8 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")</span></span>  
  
 <span data-ttu-id="16da3-104">この手順で、X12 取引先アグリーメントの X12 を交換するためのパラメーターの定義を構成する OrderSystem と Fabrikam の 2 つの取引パートナー間のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="16da3-104">In this step, you configure an X12 trading partner agreement to define the parameters for exchanging X12 messages between the two trading partners, OrderSystem and Fabrikam.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="16da3-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="16da3-105">Prerequisites</span></span>  
 <span data-ttu-id="16da3-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16da3-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-an-agreement"></a><span data-ttu-id="16da3-107">アグリーメントを構成するには</span><span class="sxs-lookup"><span data-stu-id="16da3-107">To configure an agreement</span></span>  
  
1.  <span data-ttu-id="16da3-108">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-108">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="16da3-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**パーティ**し、コンソール ツリーで、[、**パーティとビジネス プロファイル**] ページを右クリックして**Fabrikam_Profile**、をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click **Fabrikam_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
3.  <span data-ttu-id="16da3-110">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="16da3-110">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
4.  <span data-ttu-id="16da3-111">**プロトコル**ドロップダウン リストで、 **X12**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-111">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
5.  <span data-ttu-id="16da3-112">**2 番目のパーティ** セクションから、**パーティ**ドロップダウン リストで、 **OrderSystem**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-112">In the **Second Party** section, from the **Party** drop-down list, select **OrderSystem**.</span></span>  
  
6.  <span data-ttu-id="16da3-113">**2 番目のパーティ** セクションから、**ビジネス**ドロップダウン リストで、 **OrderSystem_Profile**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-113">In the **Second Party** section, from the **Business** drop-down list, select **OrderSystem_Profile**.</span></span>  
  
     <span data-ttu-id="16da3-114">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブに 1 つの一方向のアグリーメントを構成するようになっており、一方向の各アグリーメントが 1 つの完全なメッセージ トランザクション (メッセージの送信と受信確認の送信を含む) を表します。</span><span class="sxs-lookup"><span data-stu-id="16da3-114">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  
  
7.  <span data-ttu-id="16da3-115">**全般** タブで、**全般プロパティ** ページの 、**共通のホスト設定**セクションで、**レポートをオンに**、し、選択**reporting 用メッセージ ペイロードを格納**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-115">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
8.  <span data-ttu-id="16da3-116">次のタスクを実行、 **Fabrikam OrderSystem]-> [** タブです。</span><span class="sxs-lookup"><span data-stu-id="16da3-116">Perform the following tasks on the **Fabrikam->OrderSystem** tab.</span></span>  
  
    1.  <span data-ttu-id="16da3-117">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="16da3-117">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        |<span data-ttu-id="16da3-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16da3-118">Use this</span></span>|<span data-ttu-id="16da3-119">目的</span><span class="sxs-lookup"><span data-stu-id="16da3-119">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="16da3-120">**送信者の修飾子 (ISA5)**</span><span class="sxs-lookup"><span data-stu-id="16da3-120">**Sender qualifier (ISA5)**</span></span>|<span data-ttu-id="16da3-121">選択**ZZ - 相互定義**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-121">Select **ZZ - Mutually Defined**.</span></span>|  
        |<span data-ttu-id="16da3-122">**送信者 id (ISA6)**</span><span class="sxs-lookup"><span data-stu-id="16da3-122">**Sender identifier (ISA6)**</span></span>|<span data-ttu-id="16da3-123">入力**THEM**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-123">Enter **THEM**.</span></span>|  
        |<span data-ttu-id="16da3-124">**受信者の修飾子 (ISA7)**</span><span class="sxs-lookup"><span data-stu-id="16da3-124">**Receiver qualifier (ISA7)**</span></span>|<span data-ttu-id="16da3-125">選択**ZZ - 相互定義**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-125">Select **ZZ - Mutually Defined**.</span></span>|  
        |<span data-ttu-id="16da3-126">**受信者 id (ISA8)**</span><span class="sxs-lookup"><span data-stu-id="16da3-126">**Receiver identifier (ISA8)**</span></span>|<span data-ttu-id="16da3-127">入力**米国**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-127">Enter **US**.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="16da3-128"> では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16da3-128"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="16da3-129">値と照合**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**とアグリーメントのプロパティで、インターチェンジ ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="16da3-129">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="16da3-130">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="16da3-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="16da3-131">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="16da3-131">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
    2.  <span data-ttu-id="16da3-132">**受信確認** ページの 、**インターチェンジの設定**セクションで、 **997 が必要**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-132">On the **Acknowledgements** page, under the **Interchange Settings** section, click **997 Expected**.</span></span> <span data-ttu-id="16da3-133">このチェック ボックスをオンにすることで、850 インターチェンジを受信したときに 997 受信確認を生成するという指示が受信パイプラインに対して出されます。</span><span class="sxs-lookup"><span data-stu-id="16da3-133">Selecting this check box prompts the receive pipeline to generate a 997 acknowledgment when it receives the 850 interchange..</span></span>  
  
    3.  <span data-ttu-id="16da3-134">**検証**ページで、、**インターチェンジの設定**セクションで、確認してください**インターチェンジ制御番号 (ISA13 の重複のチェック)** オプションがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="16da3-134">On the **Validation** page under the **Interchange Settings** section, make sure **Interchange Control Number (Check for duplicate ISA13)** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="16da3-135">オフにすると、**重複している isa13 を確認して**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="16da3-135">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    4.  <span data-ttu-id="16da3-136">**ローカル ホスト設定** ページの 、**インターチェンジの設定** セクションで、クリア**要求-応答で送信パイプラインに確認をルーティングの受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-136">On the **Local Host Settings** page, under the **Interchange Settings** section, clear **Route ACK to send pipeline on request-response receive port**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="16da3-137">オフにすると、**確認をルーティングする**プロパティは、このソリューションは、双方向に関連付けられている送信ポートを通じて同期受信確認の受信ポートのではなく、個別を使用して非同期受信確認の送信ポートを返すために必要です。</span><span class="sxs-lookup"><span data-stu-id="16da3-137">Clearing the **Route ACK** property is required because this solution returns an asynchronous acknowledgment via a separate send port, rather than a synchronous acknowledgment via the send port associated with a two-way receive port.</span></span>  
  
    5.  <span data-ttu-id="16da3-138">**ローカル ホスト設定**ページで、**トランザクション セットの設定**セクションで、受信インターチェンジを処理するために使用するスキーマの名前空間を選択します。</span><span class="sxs-lookup"><span data-stu-id="16da3-138">On the **Local Host Settings** page under the **Transaction Set Settings** section, select the namespace for the schema to be used to process the incoming interchange.</span></span>  
  
        |<span data-ttu-id="16da3-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16da3-139">Use this</span></span>|<span data-ttu-id="16da3-140">目的</span><span class="sxs-lookup"><span data-stu-id="16da3-140">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="16da3-141">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="16da3-141">**Default**</span></span>|<span data-ttu-id="16da3-142">列のチェック ボックスをオンにします</span><span class="sxs-lookup"><span data-stu-id="16da3-142">Select the checkbox in the column</span></span>|  
        |<span data-ttu-id="16da3-143">**ST1 の場合**</span><span class="sxs-lookup"><span data-stu-id="16da3-143">**For ST1**</span></span>|<span data-ttu-id="16da3-144">選択**850 - 注文**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-144">Select **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="16da3-145">**[GS2]**</span><span class="sxs-lookup"><span data-stu-id="16da3-145">**GS2**</span></span>|<span data-ttu-id="16da3-146">入力**THEM**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-146">Enter **THEM**.</span></span>|  
        |<span data-ttu-id="16da3-147">**Target Namespace**</span><span class="sxs-lookup"><span data-stu-id="16da3-147">**Target Namespace**</span></span>|<span data-ttu-id="16da3-148">選択**http://schemas.microsoft.com/BizTalk/EDI/X12/2006**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-148">Select **http://schemas.microsoft.com/BizTalk/EDI/X12/2006**.</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="16da3-149">プロパティを設定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、受信 850 インターチェンジの処理に使用するスキーマを決定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="16da3-149">Setting the properties enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to determine the schema to be used in processing the incoming 850 interchange.</span></span> <span data-ttu-id="16da3-150">グリッド内の行に入力された [GS02] と [ST01] の値がインターチェンジに設定されている場合は、同じ行にあるターゲットの名前空間により、使用するスキーマが決定されます。</span><span class="sxs-lookup"><span data-stu-id="16da3-150">If an interchange has the values of GS02 and ST01 that are entered on a line of the grid, then the target namespace for the same line will be used to determine the schema to be used.</span></span>  
  
9. <span data-ttu-id="16da3-151">次のタスクを実行、 **OrderSystem Fabrikam]-> [** タブです。</span><span class="sxs-lookup"><span data-stu-id="16da3-151">Perform the following tasks on the **OrderSystem->Fabrikam** tab.</span></span>  
  
    1.  <span data-ttu-id="16da3-152">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="16da3-152">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        |<span data-ttu-id="16da3-153">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16da3-153">Use this</span></span>|<span data-ttu-id="16da3-154">目的</span><span class="sxs-lookup"><span data-stu-id="16da3-154">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="16da3-155">**送信者の修飾子 (ISA5)**</span><span class="sxs-lookup"><span data-stu-id="16da3-155">**Sender qualifier (ISA5)**</span></span>|<span data-ttu-id="16da3-156">選択**ZZ - 相互定義**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-156">Select **ZZ - Mutually Defined**.</span></span>|  
        |<span data-ttu-id="16da3-157">**送信者 id (ISA6)**</span><span class="sxs-lookup"><span data-stu-id="16da3-157">**Sender identifier (ISA6)**</span></span>|<span data-ttu-id="16da3-158">入力**米国**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-158">Enter **US**.</span></span>|  
        |<span data-ttu-id="16da3-159">**受信者の修飾子 (ISA7)**</span><span class="sxs-lookup"><span data-stu-id="16da3-159">**Receiver qualifier (ISA7)**</span></span>|<span data-ttu-id="16da3-160">選択**ZZ - 相互定義**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-160">Select **ZZ - Mutually Defined**.</span></span>|  
        |<span data-ttu-id="16da3-161">**受信者 id (ISA8)**</span><span class="sxs-lookup"><span data-stu-id="16da3-161">**Receiver identifier (ISA8)**</span></span>|<span data-ttu-id="16da3-162">入力**THEM**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-162">Enter **THEM**.</span></span>|  
  
    2.  <span data-ttu-id="16da3-163">**文字セットと区切り記号**] ページの [、**インターチェンジの設定**セクションで、 **CR LF**の**サフィックス**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="16da3-163">On the **Charset and Separators** page, under the **Interchange Settings** section, select **CR LF** for the **Suffix** property.</span></span>  
  
    3.  <span data-ttu-id="16da3-164">**送信ポート**ページで、**インターチェンジの設定**セクションには、Fabrikam に返信する受信確認を送信する送信ポートを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="16da3-164">On the **Send Ports** page under the **Interchange Settings** section, associate the send port that will be sending the acknowledgement back to Fabrikam.</span></span> <span data-ttu-id="16da3-165">**送信ポート**グリッド 、**名前**列は、空のセルをクリックし、ドロップダウン リストから、送信ポートを選択します (**toTHEM_997**)、997 を送信するための作成受信確認を Fabrikam にされました。</span><span class="sxs-lookup"><span data-stu-id="16da3-165">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port (**toTHEM_997**) created for sending the 997 acknowledgement to Fabrikam.</span></span>  
  
    4.  <span data-ttu-id="16da3-166">**エンベロープ**ページで、**トランザクション セットの設定**セクションで、グリッドの最初の行のすべての列の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="16da3-166">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  
  
        |<span data-ttu-id="16da3-167">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16da3-167">Use this</span></span>|<span data-ttu-id="16da3-168">目的</span><span class="sxs-lookup"><span data-stu-id="16da3-168">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="16da3-169">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="16da3-169">**Default**</span></span>|<span data-ttu-id="16da3-170">チェック ボックスをオン、**既定**列です。</span><span class="sxs-lookup"><span data-stu-id="16da3-170">Select the checkbox in the **Default** column.</span></span> <span data-ttu-id="16da3-171">**注:** 、既定の値は、この行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**が使用される場合でもの値は、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**の一致するものではありません、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="16da3-171">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="16da3-172">**トランザクションの種類**</span><span class="sxs-lookup"><span data-stu-id="16da3-172">**Transaction Type**</span></span>|<span data-ttu-id="16da3-173">テスト メッセージのメッセージの種類を選択して**850 - 注文**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-173">Select the message type of your test message, **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="16da3-174">**バージョン/リリース**</span><span class="sxs-lookup"><span data-stu-id="16da3-174">**Version/Release**</span></span>|<span data-ttu-id="16da3-175">EDI のバージョンを入力**00401**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-175">Enter the EDI version, **00401**.</span></span>|  
        |<span data-ttu-id="16da3-176">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="16da3-176">**Target namespace**</span></span>|<span data-ttu-id="16da3-177">選択**http://schemas.microsoft.com/Edi/X12**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-177">Select **http://schemas.microsoft.com/Edi/X12**.</span></span>|  
        |<span data-ttu-id="16da3-178">**GS1**</span><span class="sxs-lookup"><span data-stu-id="16da3-178">**GS1**</span></span>|<span data-ttu-id="16da3-179">いることを確認**PO - 注文書 (850)** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="16da3-179">Verify that **PO - Purchase Order (850)** is selected.</span></span>|  
        |<span data-ttu-id="16da3-180">**[GS2]**</span><span class="sxs-lookup"><span data-stu-id="16da3-180">**GS2**</span></span>|<span data-ttu-id="16da3-181">入力**1234567**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-181">Enter **1234567**.</span></span><br /><br /> <span data-ttu-id="16da3-182">**送信者アプリケーション id。**</span><span class="sxs-lookup"><span data-stu-id="16da3-182">**Sender Application ID.**</span></span>|  
        |<span data-ttu-id="16da3-183">**[GS3]**</span><span class="sxs-lookup"><span data-stu-id="16da3-183">**GS3**</span></span>|<span data-ttu-id="16da3-184">入力**0000000**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-184">Enter **0000000**.</span></span><br /><br /> <span data-ttu-id="16da3-185">**受信者アプリケーション id。**</span><span class="sxs-lookup"><span data-stu-id="16da3-185">**Receiver Application ID.**</span></span>|  
        |<span data-ttu-id="16da3-186">**GS4**</span><span class="sxs-lookup"><span data-stu-id="16da3-186">**GS4**</span></span>|<span data-ttu-id="16da3-187">選択**CCYYMMDD**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-187">Select **CCYYMMDD**.</span></span> <span data-ttu-id="16da3-188">**注:** ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16da3-188">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="16da3-189">ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。</span><span class="sxs-lookup"><span data-stu-id="16da3-189">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="16da3-190">**GS5**</span><span class="sxs-lookup"><span data-stu-id="16da3-190">**GS5**</span></span>|<span data-ttu-id="16da3-191">選択**HHMM**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-191">Select **HHMM**.</span></span>|  
        |<span data-ttu-id="16da3-192">**GS7**</span><span class="sxs-lookup"><span data-stu-id="16da3-192">**GS7**</span></span>|<span data-ttu-id="16da3-193">選択**X の間に認可 Standards Committee X12**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-193">Select **X - Accredited Standards Committee X12**.</span></span>|  
        |<span data-ttu-id="16da3-194">**GS8**</span><span class="sxs-lookup"><span data-stu-id="16da3-194">**GS8**</span></span>|<span data-ttu-id="16da3-195">いることを確認**00401**が入力されました。</span><span class="sxs-lookup"><span data-stu-id="16da3-195">Verify that **00401** has been entered.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="16da3-196">GS01、GS02、GS03、GS04、GS05、GS07、および入力した値に基づいて、送信する受信確認の GS08 の値が設定されます**トランザクション タイプ**、**バージョン/リリース**、および**ターゲット名前空間**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-196"> will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="16da3-197">送信パイプラインは、トランザクション セットの種類、X12 バージョン、およびターゲットの名前空間と、メッセージ ヘッダー内の対応する値との照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="16da3-197">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="16da3-198">成功すると、その値が使用 GS に関連付けられている、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**値。</span><span class="sxs-lookup"><span data-stu-id="16da3-198">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  
  
10. <span data-ttu-id="16da3-199">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16da3-199">Click **Apply**.</span></span>  
  
11. <span data-ttu-id="16da3-200">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16da3-200">Click **OK**.</span></span> <span data-ttu-id="16da3-201">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="16da3-201">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="16da3-202">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="16da3-202">The newly added agreement is enabled by default.</span></span>  
  
12. <span data-ttu-id="16da3-203">BizTalk サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="16da3-203">Restart the BizTalk Service.</span></span> <span data-ttu-id="16da3-204">BizTalk Server 管理コンソールで **プラットフォームの設定**をクリックして**ホスト インスタンス**を右クリックして**BizTalkServerApplication**をクリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="16da3-204">In the BizTalk Server Administration Console, under **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="16da3-205">EDI 状態レポートをアクティブ化または非アクティブ化した後は、変更を有効にするために、BizTalk サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16da3-205">The BizTalk Service needs to be restarted after EDI status reporting has been activated or deactivated for the change to take effect.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="16da3-206">次の手順</span><span class="sxs-lookup"><span data-stu-id="16da3-206">Next Steps</span></span>  
 <span data-ttu-id="16da3-207">EDI ソリューションのテスト」の説明に従って[手順 9: EDI ソリューションのテスト](../core/step-9-test-the-edi-solution.md)</span><span class="sxs-lookup"><span data-stu-id="16da3-207">Test the EDI solution as described in [Step 9: Test the EDI Solution](../core/step-9-test-the-edi-solution.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16da3-208">参照</span><span class="sxs-lookup"><span data-stu-id="16da3-208">See Also</span></span>  
 [<span data-ttu-id="16da3-209">エンコード アグリーメントのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="16da3-209">Configuring Encoding Agreement Properties</span></span>](../core/configuring-encoding-agreement-properties.md)
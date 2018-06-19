---
title: (EDIFACT) をバッチ処理の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f711ff4b-702b-419b-9c17-dce60ea437a0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 116c196d4688e4e7d21c8951c32838539cf10aa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234666"
---
# <a name="configuring-batching-edifact"></a><span data-ttu-id="f6125-102">バッチ処理の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="f6125-102">Configuring Batching (EDIFACT)</span></span>
<span data-ttu-id="f6125-103">バッチは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が EDI バッチを生成してパーティに送信する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f6125-103">Batches define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates and sends an EDI batches to the party.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f6125-104">オフにした場合でも、このページですべてのプロパティが無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="f6125-104">All properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span> <span data-ttu-id="f6125-105">**新しいバッチ**ボタンがこのページで無効になります。</span><span class="sxs-lookup"><span data-stu-id="f6125-105">The **New Batch** button is disabled on this page.</span></span>  
>   
>  <span data-ttu-id="f6125-106">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="f6125-106">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="f6125-107">たとえば、2 つのパーティのパーティ A とパーティ B を作成する場合、パーティ A 用に、チェック ボックスをオフ、**新しいバッチ**にボタンが無効になっている、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="f6125-107">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the **New Batch** button is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f6125-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="f6125-108">Prerequisites</span></span>  
 <span data-ttu-id="f6125-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6125-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-batching-settings"></a><span data-ttu-id="f6125-110">バッチ処理設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="f6125-110">To configure batching settings</span></span>  
  
1.  <span data-ttu-id="f6125-111">EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。</span><span class="sxs-lookup"><span data-stu-id="f6125-111">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="f6125-112">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-112">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f6125-113">一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**バッチ処理構成**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-113">On a one-way agreement tab, under **Interchange Settings** section, click **Batching Configuration**.</span></span>  
  
3.  <span data-ttu-id="f6125-114">**バッチ構成**ページをクリックして**新しいバッチ**新しいバッチ構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="f6125-114">From the **Batch Configuration** page click **New Batch** to create a new batch configuration.</span></span> <span data-ttu-id="f6125-115">A **Batch1**  タブを追加します。</span><span class="sxs-lookup"><span data-stu-id="f6125-115">A **Batch1** tab is added.</span></span>  
  
4.  <span data-ttu-id="f6125-116">**識別** タブのセクションでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6125-116">In the **Identification** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="f6125-117">入力、**バッチ**名。</span><span class="sxs-lookup"><span data-stu-id="f6125-117">Enter the **Batch** name.</span></span> <span data-ttu-id="f6125-118">この値は、このバッチ構成のタブ ID として使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6125-118">This value is used as the tab identifier for this batch configuration.</span></span>  
  
    2.  <span data-ttu-id="f6125-119">このバッチ構成の説明を入力**バッチ説明**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-119">Enter a description of this batch configuration in **Batch description**.</span></span>  
  
    3.  <span data-ttu-id="f6125-120">**バッチ ID**は、バッチの設定を適用した後に、一意のバッチ ID を表示する読み取り専用のテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="f6125-120">**Batch ID** is a read-only text box that displays a unique batch ID after you apply the settings for the batch.</span></span>  
  
    4.  <span data-ttu-id="f6125-121">**オーケストレーション インスタンス ID**バッチが関連付けられているバッチ処理オーケストレーション インスタンス ID を表示する読み取り専用のテキスト ボックスは、します。</span><span class="sxs-lookup"><span data-stu-id="f6125-121">**Orchestration instance ID** is a read-only text box that displays the batching orchestration instance ID that the batch is associated with.</span></span> <span data-ttu-id="f6125-122">オーケストレーション インスタンス ID は、バッチの開始後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6125-122">An orchestration instance ID is displayed after a batch is started.</span></span>  
  
5.  <span data-ttu-id="f6125-123">**フィルター**  タブのセクションでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6125-123">In the **Filter** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="f6125-124">をクリックして**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-124">Click **Filter**.</span></span>  
  
    2.  <span data-ttu-id="f6125-125">**バッチ フィルター**  ダイアログ ボックスで、バッチ処理オーケストレーションのサブスクリプション フィルターを作成するには、プロパティ、演算子、値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-125">In the **Batch Filter** dialog box, enter the property, operator and values to build the subscription filter for the batching orchestration.</span></span> <span data-ttu-id="f6125-126">これらのフィルター句によって、ルーティング オーケストレーションがバッチ処理のためにメッセージ ボックスにルーティングするトランザクション セットが決まります。</span><span class="sxs-lookup"><span data-stu-id="f6125-126">These filter clauses determine which transaction sets the routing orchestration will route to the MessageBox for batching.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f6125-127">グループへのすべてのメッセージをバッチ処理するように指定するには、バッチ フィルター内のパーティのプロパティをパーティ名に設定します。</span><span class="sxs-lookup"><span data-stu-id="f6125-127">To specify that all messages to a group will be batched, set the party property in the batch filter to the party name.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f6125-128">バッチ処理プロセスの詳細については、次を参照してください。[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)です。</span><span class="sxs-lookup"><span data-stu-id="f6125-128">For more information about the batching process, see [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
    3.  <span data-ttu-id="f6125-129">行を削除する行を選択し、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-129">To delete a row, select the row and click **Delete**.</span></span>  
  
    4.  <span data-ttu-id="f6125-130">上または下に行を移動するクリックして、**上へ移動**または**下へ移動**ボタン。</span><span class="sxs-lookup"><span data-stu-id="f6125-130">To move a row up or down, click the **Move Up** or **Move Down** buttons.</span></span>  
  
6.  <span data-ttu-id="f6125-131">**リリース** タブのセクションでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6125-131">In the **Release** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="f6125-132">選択**スケジュール**を作成して、あらかじめ決められたスケジュールに従ってバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="f6125-132">Select **Schedule** to create and send a batch according to a predetermined schedule.</span></span> <span data-ttu-id="f6125-133">スケジュールを定義する をクリックして**スケジューラ**次のように進みます。</span><span class="sxs-lookup"><span data-stu-id="f6125-133">To define the schedule, click **Scheduler** and then proceed as follows:</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f6125-134">バッチ スケジュールは、特別なイベントの影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6125-134">A batch schedule may be affected by special events.</span></span> <span data-ttu-id="f6125-135">一例として、夏時間の開始が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="f6125-135">An example is the onset of daylight savings time.</span></span> <span data-ttu-id="f6125-136">バッチ スケジュールが時間単位で設定されており、夏時間の開始からバッチの予定時刻までの時間が 1 時間に満たない場合、時計を 1 時間進めてリセットすると、そのバッチの作成と送信は行われなくなります。</span><span class="sxs-lookup"><span data-stu-id="f6125-136">If a batch were scheduled on an hourly basis less than an hour after the onset of daylight savings time, the batch would not be created and sent after clocks were reset by incrementing the hour.</span></span> <span data-ttu-id="f6125-137">特別なイベントをクリックして、バッチがスキップされる結果を補うことができます、**開始**のボタンでは、**バッチ**バッチ処理オーケストレーションを手動で開始するページ。</span><span class="sxs-lookup"><span data-stu-id="f6125-137">You can compensate for special events that result in a skipped batch by clicking the **Start** button on the **Batches** page to start the batching orchestration manually.</span></span> <span data-ttu-id="f6125-138">重複するバッチの停止が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f6125-138">You may also have to stop a duplicated batch.</span></span>  
  
        -   <span data-ttu-id="f6125-139">1 時間ごとにバッチを送信する **毎時**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-139">To send a batch on an hourly basis, select **Hourly**.</span></span> <span data-ttu-id="f6125-140">ドロップダウン リストから**最初のリリース**バッチの最初のリリースを作成する日付を選択して、時間を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-140">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="f6125-141">**次のリリースすべて**、期間がであるかどうか、ドロップダウン リストから選択**時間**または**分**、を時間または分の数を入力各バッチを区切ります。</span><span class="sxs-lookup"><span data-stu-id="f6125-141">For **Subsequent release every**, select from the drop-down list whether the period is in **Hours** or **Minutes**, and then enter the number of hours or minutes that will separate each batch.</span></span>  
  
        -   <span data-ttu-id="f6125-142">日常的にバッチを送信する **毎日**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-142">To send a batch on a daily basis, select **Daily**.</span></span> <span data-ttu-id="f6125-143">ドロップダウン リストから**最初のリリース**バッチの最初のリリースを作成する日付を選択して、時間を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-143">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="f6125-144">**次のリリースすべて**、各バッチを区切る日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-144">For **Subsequent release every**, enter the number of days that will separate each batch.</span></span>  
  
        -   <span data-ttu-id="f6125-145">週単位でバッチを送信する **毎週**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-145">To send a batch on a weekly basis, select **Weekly**.</span></span> <span data-ttu-id="f6125-146">ドロップダウン リストから**最初のリリース**バッチの最初のリリースを作成する日付を選択して、時間を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-146">From the drop-down list for **First release at**, select a date for the first release of the batch, and then enter the time.</span></span> <span data-ttu-id="f6125-147">**次のリリースすべて**、後続の各リリースの週の最初のリリースの週までの週の数を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-147">For **Subsequent release every**, enter the number of weeks between the week of the first release and the week of each subsequent release.</span></span> <span data-ttu-id="f6125-148">続いて、バッチをリリースする曜日を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6125-148">Then select the days of the week that the batch will be released on.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="f6125-149">最初のリリースがその日に行わされ、設定、**最初のリリース**フィールドには、その曜日がダイアログ ボックスで選択されていない場合でもです。</span><span class="sxs-lookup"><span data-stu-id="f6125-149">The first release will be made at the date and set in the **First release at** field, even if that day of the week was not selected in the dialog box.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="f6125-150">ダイアログ ボックスで 1 つ以上の曜日を選択した場合、リリースは、最初のリリース後の第 1 週目の選択したいずれかの曜日に行われます。</span><span class="sxs-lookup"><span data-stu-id="f6125-150">If you selected one or more days of the week in the dialog box, a release will be made on any selected day of that first week that comes after the first release.</span></span> <span data-ttu-id="f6125-151">たとえば、選択した曜日が月曜日と金曜日で、最初のリリースが水曜日に行われた場合は、その第 1 週の金曜日にリリースが行われます。</span><span class="sxs-lookup"><span data-stu-id="f6125-151">For example, if Monday and Friday have been selected, and the first release was on a Wednesday, a release will be made on Friday of the first week.</span></span> <span data-ttu-id="f6125-152">今後のリリースが発生 *n* 週間後は、最初の週と *n* で値によって決定されます、**次のリリースすべて**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="f6125-152">Subsequent releases will occur *n* weeks after the first week, with *n* determined by the value in the **Subsequent release every** field.</span></span> <span data-ttu-id="f6125-153">リリースは、ダイアログ ボックスで選択した各曜日に発生します。</span><span class="sxs-lookup"><span data-stu-id="f6125-153">Release will occur on each day of the week selected in the dialog box.</span></span>  
  
        -   <span data-ttu-id="f6125-154">選択**空のバッチ通知を送信**メッセージが受信されていない場合、バッチ処理オーケストレーションによって送信されるバッチがスケジュールされている場合は、空のバッチ通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="f6125-154">Select **Send empty batch signal** to send an empty batch signal if no messages have been received by the batching orchestration when the batch is scheduled to be sent.</span></span>  
  
    2.  <span data-ttu-id="f6125-155">選択**セットのトランザクションの最大数**を作成し、特定のトランザクション セットまたはメッセージの数がバッチ処理用のメッセージ ボックスにルーティングされたときにバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="f6125-155">Select **Maximum number of transaction sets in** to create and send a batch whenever a certain number of transaction sets or messages has been routed to the MessageBox for batching.</span></span> <span data-ttu-id="f6125-156">トランザクションをカウントするメッセージの一部がセットの選択 (か**グループ**または**インターチェンジ**)、バッチ処理するグループまたはインターチェンジ内にあるトランザクション セットの最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-156">Select the part of the message to count the transaction sets in (either **Group** or **Interchange**), and then enter the maximum number of transaction sets to be in the batched group or interchange.</span></span>  
  
         <span data-ttu-id="f6125-157">たとえば、1 つのバッチに 2 つのインターチェンジのバッチをする場合が選択**インターチェンジ**ドロップダウン リストから入力と`2`テキスト ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="f6125-157">For example, if you want to batch two interchanges into one batch select **Interchange** from the drop-down and enter `2` in the text box.</span></span>  
  
    3.  <span data-ttu-id="f6125-158">選択**インターチェンジ内の文字の最大数**を作成し、特定の文字数がバッチ処理に使用できる場合は、バッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="f6125-158">Select **Maximum number of characters in an interchange** to create and send a batch when a specific number of characters are available for batch processing.</span></span> <span data-ttu-id="f6125-159">バッチ処理するグループまたはインターチェンジの最大文字数を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-159">Enter the maximum number of characters in the batched group or interchange.</span></span>  
  
         <span data-ttu-id="f6125-160">バッチ処理オーケストレーションでは、バッチ処理要素内の文字数 (からエンベロープ内の数を除いたもの) が最大数を超えるまで、バッチ処理要素を蓄積します。</span><span class="sxs-lookup"><span data-stu-id="f6125-160">The batching orchestration will accumulate batching elements until the character count in those elements (minus the count in the envelope) exceeds the maximum count.</span></span> <span data-ttu-id="f6125-161">その後、最後の要素 (文字数が最大数を超える原因になった要素) を除くすべての要素をバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="f6125-161">It will then batch all but the last element (which caused the count to exceed the maximum count).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f6125-162">最大文字数として、有効なバッチを生成するのに十分な文字数を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-162">For the maximum number of characters, enter a number large enough that you will generate meaningful batches.</span></span> <span data-ttu-id="f6125-163">この数は、少なくとも、バッチ ヘッダー内の合計文字数およびメッセージ内の最大文字数よりも大きい数にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6125-163">That number should at least be greater than the total number of characters in the batch headers and the maximum number of characters in a message.</span></span> <span data-ttu-id="f6125-164">入力した値が小さすぎると、結果として空のバッチが生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f6125-164">A number that is too small could result in empty batches.</span></span>  
  
    4.  <span data-ttu-id="f6125-165">選択**外部リリースのトリガ**を作成し、BizTalk Server 外部のアプリケーションによって外部トリガーが実行されると、バッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="f6125-165">Select **External release trigger** to create and then send a batch when an external trigger is executed by an application external to BizTalk Server.</span></span> <span data-ttu-id="f6125-166">このメカニズムを設定する方法の詳細については、次を参照してください。[外部バッチ リリース メカニズムを実装する](../core/implementing-an-external-batch-release-mechanism.md)です。</span><span class="sxs-lookup"><span data-stu-id="f6125-166">For more information about how to set up this mechanism, see [Implementing an External Batch Release Mechanism](../core/implementing-an-external-batch-release-mechanism.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f6125-167">**オーバーライド**ボタンと**アクティベーションの範囲**コントロールは有効なまま場合、**外部リリース**トリガー プロパティが選択されています。</span><span class="sxs-lookup"><span data-stu-id="f6125-167">The **Override** button and **Activation range** controls remain valid if the **External release** trigger property has been selected.</span></span>  
  
7.  <span data-ttu-id="f6125-168">**アクティベーション** タブのセクションでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6125-168">In the **Activation** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="f6125-169">選択**今すぐ開始**オーケストレーションがすぐにメッセージをバッチ処理を開始して、バッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="f6125-169">Select **Start Immediately** to have the batching orchestration begin batching messages immediately.</span></span>  
  
         <span data-ttu-id="f6125-170">バッチ処理オーケストレーションを開始するには、特定の日付をクリア、 **今すぐ開始**ボックスし日付を選択し、バッチ処理オーケストレーションをアクティブ化する時間します。</span><span class="sxs-lookup"><span data-stu-id="f6125-170">To start the batching orchestration on a specific date, clear the **Start Immediately** box and select a date and time to activate the batching orchestration.</span></span>  
  
8.  <span data-ttu-id="f6125-171">**終了** タブのセクションでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6125-171">In the **Termination** section of the tab perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="f6125-172">保持**終了日が**非アクティブ化、バッチ処理オーケストレーションの終了日を指定しない場合に選択しません。</span><span class="sxs-lookup"><span data-stu-id="f6125-172">Keep **No end date** selected if you do not want to specify an end date for the batching orchestration to be deactivated.</span></span>  
  
    2.  <span data-ttu-id="f6125-173">選択 **(出現数) の後に終了**バッチ数を生成した後、バッチ処理オーケストレーションを非アクティブにすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6125-173">Select **End after (occurrences)** to specify that the batching orchestration will be deactivated after a certain number of batches have been generated.</span></span> <span data-ttu-id="f6125-174">テキスト ボックスに、目的の回数を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6125-174">Enter the number desired in the text box.</span></span>  
  
    3.  <span data-ttu-id="f6125-175">選択**によって終了**をバッチ処理オーケストレーションが非アクティブ化する終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6125-175">Select **End by** to specify an end date that the batching orchestration will be deactivated.</span></span> <span data-ttu-id="f6125-176">この時間以後はバッチ処理のメッセージは収集されません。</span><span class="sxs-lookup"><span data-stu-id="f6125-176">Messages will no longer be collected for batching as of this time.</span></span> <span data-ttu-id="f6125-177">カレンダーから終了日を選択するか、テキスト ボックスの日付または時刻を直接変更します。</span><span class="sxs-lookup"><span data-stu-id="f6125-177">Select an end date from the calendar or change the date or time directly in the text box.</span></span>  
  
9. <span data-ttu-id="f6125-178">をクリックして**適用**前の手順で指定したバッチ設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f6125-178">Click **Apply** to apply the batch settings you provided in the previous steps.</span></span> <span data-ttu-id="f6125-179">クリックした後**適用**、バッチ ID が作成されに表示される、**バッチ ID**内のテキスト フィールド、**識別**セクションです。</span><span class="sxs-lookup"><span data-stu-id="f6125-179">After you click **Apply**, a batch ID is created and is displayed in the **Batch ID** text field in the **Identification** section.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6125-180">メッセージ**バッチ処理がアクティブ化されていない**下に表示されます、**開始**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6125-180">A message **Batching is not activated** will be displayed under the **Start** button.</span></span>  
  
10. <span data-ttu-id="f6125-181">をクリックして**開始**をバッチ処理オーケストレーションを手動でアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="f6125-181">Click **Start** to activate a batching orchestration manually.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6125-182">バッチ処理オーケストレーションがすぐにアクティブ化をクリックするとかどうかを確認する、**開始**ボタンを SQL アダプタの BatchControlMessageReccvLoc 受信場所のポーリング間隔を更新します。</span><span class="sxs-lookup"><span data-stu-id="f6125-182">To make sure that the batching orchestration will be promptly activated when you click the **Start** button, update the polling interval for the SQL adapter in the BatchControlMessageReccvLoc receive location.</span></span> <span data-ttu-id="f6125-183">詳細については、次を参照してください。[チュートリアル (X12): バッチ EDI インターチェンジの送信](../core/walkthrough-x12-sending-batched-edi-interchanges.md)です。</span><span class="sxs-lookup"><span data-stu-id="f6125-183">For more information, see [Walkthrough (X12): Sending Batched EDI Interchanges](../core/walkthrough-x12-sending-batched-edi-interchanges.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6125-184">クリックした後**開始**をクリックして**更新**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-184">After you click **Start**, click **Refresh**.</span></span> <span data-ttu-id="f6125-185">バッチとオーケストレーション インスタンスを関連付けるのにしばらく時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f6125-185">It can take a while to associate the batch with the orchestration instance.</span></span> <span data-ttu-id="f6125-186">クリックすると**更新**バッチは、オーケストレーションに関連付けられて、前に、メッセージが表示**バッチ処理がアクティブ化されて、バッチ処理オーケストレーション インスタンスがまだいない**です。</span><span class="sxs-lookup"><span data-stu-id="f6125-186">If you click **Refresh** before the batch is associated with the orchestration, you see the message **Batching is activated, Batching orchestration not instantiated yet**.</span></span> <span data-ttu-id="f6125-187">をクリックして**更新**に関連付けられているオーケストレーションのインスタンス ID を表示するには、もう一度、**オーケストレーション インスタンス ID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="f6125-187">Click **Refresh** again to see the associated orchestration’s instance ID in the **Orchestration instance ID** text box.</span></span> <span data-ttu-id="f6125-188">メッセージ**バッチ処理がアクティブ化**下に表示されます、**開始**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6125-188">The message **Batching is activated** is displayed under the **Start** button.</span></span>  
  
11. <span data-ttu-id="f6125-189">をクリックして**オーバーライド**のため、バッチを送信バッチ処理オーケストレーションが強制的に、リリース条件が満たされているかどうかを示すです。</span><span class="sxs-lookup"><span data-stu-id="f6125-189">Click **Override** to forces the batching orchestration to send a batch, whether or not the release criteria have been met.</span></span> <span data-ttu-id="f6125-190">このオプションを使用すると、既存のバッチ条件が上書きされます。結果として、既存の要素を使用してバッチが作成され、直ちに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f6125-190">Using this option overrides the existing batch criteria, with the result that a batch is created using existing elements and then sent immediately.</span></span> <span data-ttu-id="f6125-191">この後、バッチ処理のオーケストレーションは、確立された設定に基づいてバッチ処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="f6125-191">After this, the batching orchestration resumes batch processing according to the established settings.</span></span>  
  
12. <span data-ttu-id="f6125-192">をクリックして**停止**バッチを送信せずにアクティブなバッチ処理オーケストレーションを終了してから、バッチ処理オーケストレーションを手動で非アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="f6125-192">Click **Stop** to terminate an active batching orchestration without sending a batch and deactivate the batching orchestration manually.</span></span>  
  
13. <span data-ttu-id="f6125-193">をクリックして**更新**バッチ処理オーケストレーションの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="f6125-193">Click **Refresh** to refresh the status of the batching orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6125-194">上部にあるドロップダウン リストを使用して**バッチ構成**ページを選択して表示されるバッチ構成タブをフィルター処理を**すべて**(すべてのバッチのタブを参照してください) を**アクティブ**(アクティブなバッチのタブを参照してください) をまたは**Inactive** (を非アクティブなバッチのタブを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f6125-194">You can use the drop-down list at the top of **the Batch Configuration** page to filter the batch configuration tabs displayed by selecting **All** (to see tabs for all batches), **Active** (to see tabs for active batches), or **Inactive** (to see tabs for inactive batches).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6125-195">オーケストレーションがバッチを処理している間に構成設定を変更すると、新しい設定はそのバッチに適用されません。</span><span class="sxs-lookup"><span data-stu-id="f6125-195">If you change the configuration settings while the orchestration is processing a batch, the new settings will not be applied to that batch.</span></span> <span data-ttu-id="f6125-196">これにより、送信パイプラインで検証エラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6125-196">This can result in validation errors in the send pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6125-197">開発サーバーでバッチ処理のオーケストレーション パーティを迅速にアクティブ化するには、そのサーバー上のバッチ処理 SQL アダプターの受信場所 (BatchControlMessageRecvLoc) のポーリング間隔を短くします。</span><span class="sxs-lookup"><span data-stu-id="f6125-197">To speed up activation of the batching orchestration party on a development server, you can decrease the polling interval for the batching SQL adapter receive location (BatchControlMessageRecvLoc) on that server.</span></span> <span data-ttu-id="f6125-198">開発サーバーのポーリング間隔を 30 秒に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6125-198">We recommend you set the polling interval for a development server to 30 seconds.</span></span>  
  
14. <span data-ttu-id="f6125-199">をクリックして**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f6125-199">Click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6125-200">参照</span><span class="sxs-lookup"><span data-stu-id="f6125-200">See Also</span></span>  
 [<span data-ttu-id="f6125-201">インターチェンジの設定の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="f6125-201">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)
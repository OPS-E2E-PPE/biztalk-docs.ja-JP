---
title: 全般設定 (AS2) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8592c52e-5156-418c-9c49-7478f73c372e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23ff62f90f14238f7834312ab909a137d49bcbab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234626"
---
# <a name="configuring-general-settings-as2"></a><span data-ttu-id="4c07b-102">全般的な設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="4c07b-102">Configuring General Settings (AS2)</span></span>
<span data-ttu-id="4c07b-103">全般的な設定の一部としてアグリーメント名、アグリーメントで使用するプロトコル (AS2)、およびアグリーメント対象のパーティとプロファイルを指定し、アグリーメントにより処理されるすべてのメッセージに対してレポート機能を有効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-103">As part of the general settings, you specify agreement name, the protocol it will use (AS2), the parties and profiles that the agreement is between, and whether to have reporting enabled for all messages processed through the agreement.</span></span> <span data-ttu-id="4c07b-104">また、アグリーメントの中でパーティの連絡先情報を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-104">You can also specify the party contact information as part of the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4c07b-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="4c07b-105">Prerequisites</span></span>  
 <span data-ttu-id="4c07b-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c07b-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-general-agreement-settings"></a><span data-ttu-id="4c07b-107">アグリーメントの全般設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="4c07b-107">To configure general agreement settings</span></span>  
  
1.  <span data-ttu-id="4c07b-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**パーティ**し、コンソール ツリーで、、**パーティとビジネス プロファイル**] ページで、アグリーメントの一部にする必要があるビジネス プロファイルを右クリックします。作成し、[**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="4c07b-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click **Parties** in the console tree, and in the **Parties and Business Profiles** page, right-click a business profile that must be part of the agreement that you are creating, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="4c07b-109">次の表は、さまざまなプロパティと値をプロパティに指定する、**全般プロパティ**ページ。</span><span class="sxs-lookup"><span data-stu-id="4c07b-109">The following tables list the different properties and the values to be specified for the properties in the **General Properties** page.</span></span>  
  
    1.  <span data-ttu-id="4c07b-110">**アグリーメントのパラメーター**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-110">In the **Agreement Parameters** section, do the following:</span></span>  
  
        |<span data-ttu-id="4c07b-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c07b-111">Use this</span></span>|<span data-ttu-id="4c07b-112">目的</span><span class="sxs-lookup"><span data-stu-id="4c07b-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4c07b-113">**名前**</span><span class="sxs-lookup"><span data-stu-id="4c07b-113">**Name**</span></span>|<span data-ttu-id="4c07b-114">このアグリーメントの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-114">Specify a name for the agreement</span></span>|  
        |<span data-ttu-id="4c07b-115">**ID**</span><span class="sxs-lookup"><span data-stu-id="4c07b-115">**ID**</span></span>|<span data-ttu-id="4c07b-116">アグリーメントの一意な ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-116">Lists unique identification for the agreement.</span></span> <span data-ttu-id="4c07b-117">このテキスト ボックスは編集できませんしをクリックした後、アグリーメント ID が表示されます**適用**の最初の時刻と設定が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-117">This text box is not editable and will display the agreement ID after you click **Apply** for the first time and settings are accepted.</span></span>|  
        |<span data-ttu-id="4c07b-118">**[状態]**</span><span class="sxs-lookup"><span data-stu-id="4c07b-118">**Status**</span></span>|<span data-ttu-id="4c07b-119">アグリーメントの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-119">Specifies the status of the agreement.</span></span> <span data-ttu-id="4c07b-120">既定では、アグリーメントの作成、 **Active**状態です。</span><span class="sxs-lookup"><span data-stu-id="4c07b-120">By default, an agreement is created in an **Active** state.</span></span> <span data-ttu-id="4c07b-121">場合は、作成した最初の select があるときに無効にするアグリーメント**無効になっている**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-121">If you want the agreement to be disabled when it is first created, select **Disabled** from the drop-down list.</span></span>|  
        |<span data-ttu-id="4c07b-122">**[プロトコル]**</span><span class="sxs-lookup"><span data-stu-id="4c07b-122">**Protocol**</span></span>|<span data-ttu-id="4c07b-123">アグリーメントのプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-123">Specifies the protocol for the agreement.</span></span> <span data-ttu-id="4c07b-124">AS2 トランスポート プロトコルでは、選択**AS2**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-124">For an AS2 transport protocol, select **AS2** from the drop-down list.</span></span>|  
  
    2.  <span data-ttu-id="4c07b-125">**最初のパートナーと**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-125">In the **First Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="4c07b-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c07b-126">Use this</span></span>|<span data-ttu-id="4c07b-127">目的</span><span class="sxs-lookup"><span data-stu-id="4c07b-127">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4c07b-128">**名前**</span><span class="sxs-lookup"><span data-stu-id="4c07b-128">**Name**</span></span>|<span data-ttu-id="4c07b-129">このアグリーメントの作成に使用するビジネス プロファイルが属するパートナーの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-129">Displays the partner name that has the business profile for which you are creating the agreement.</span></span> <span data-ttu-id="4c07b-130">このテキスト ボックスは編集できません。</span><span class="sxs-lookup"><span data-stu-id="4c07b-130">This text box is not editable.</span></span>|  
        |<span data-ttu-id="4c07b-131">**プロファイル**</span><span class="sxs-lookup"><span data-stu-id="4c07b-131">**Profile**</span></span>|<span data-ttu-id="4c07b-132">このアグリーメントの作成に使用するプロファイルの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-132">Displays the name of the profile for which you are creating the agreement.</span></span> <span data-ttu-id="4c07b-133">このテキスト ボックスは編集できません。</span><span class="sxs-lookup"><span data-stu-id="4c07b-133">This text box is not editable.</span></span>|  
        |<span data-ttu-id="4c07b-134">**プロトコル セット**</span><span class="sxs-lookup"><span data-stu-id="4c07b-134">**Protocol Set**</span></span>|<span data-ttu-id="4c07b-135">ビジネス プロファイルの一部として作成した AS2 プロトコル セットは、ドロップダウン リストから選択できます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-135">If you created an AS2 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="4c07b-136">ビジネス プロファイルの一部として作成しなかった AS2 プロトコル セットは、空白のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-136">If you did not create an AS2 protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
    3.  <span data-ttu-id="4c07b-137">**2 番目のパートナー**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-137">In the **Second Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="4c07b-138">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c07b-138">Use this</span></span>|<span data-ttu-id="4c07b-139">目的</span><span class="sxs-lookup"><span data-stu-id="4c07b-139">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4c07b-140">**名前**</span><span class="sxs-lookup"><span data-stu-id="4c07b-140">**Name**</span></span>|<span data-ttu-id="4c07b-141">ドロップダウン リストから、アグリーメントの作成に使用するビジネス プロファイルが属するパーティを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-141">From the drop-down select a party that has the business profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="4c07b-142">**プロファイル**</span><span class="sxs-lookup"><span data-stu-id="4c07b-142">**Profile**</span></span>|<span data-ttu-id="4c07b-143">ドロップダウン リストから、アグリーメントの作成に使用するプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-143">From the drop-down select a profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="4c07b-144">**プロトコル セット**</span><span class="sxs-lookup"><span data-stu-id="4c07b-144">**Protocol Set**</span></span>|<span data-ttu-id="4c07b-145">ビジネス プロファイルの一部として作成した AS2 プロトコル セットは、ドロップダウン リストから選択できます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-145">If you created an AS2 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="4c07b-146">ビジネス プロファイルの一部として作成しなかった AS2 プロトコル セットは、空白のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-146">If you did not create an AS2 protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
        > [!TIP]
        >  <span data-ttu-id="4c07b-147">キーを押して`CTRL`は、アグリーメントの一部にする、いずれかのビジネス プロファイルを右クリックし、 をポイントするビジネス プロファイルを選択して**新規**、順にクリック**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="4c07b-147">Press `CTRL`, select the business profiles that will be part of the agreement, right-click either business profile, point to **New**, and then click **Agreement**.</span></span> <span data-ttu-id="4c07b-148">値は、パートナー名と、両方のパートナーのビジネス プロファイルで自動的に設定されますが、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4c07b-148">The values for partner name and business profiles for both the partners will be automatically populated in the **Agreement Properties** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4c07b-149">2 つのタブが横に追加された別のプロファイルを選択するとすぐに、**全般**タブです。各タブは 2 つのパーティ間の一方向の AS2 アグリーメントを表します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-149">As soon as you select the other profile, two tabs are added next to the **General** tab. Each tab represents a one-way AS2 agreement between the two parties.</span></span> <span data-ttu-id="4c07b-150">このタブを使用して、インターチェンジやトランザクション セット関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-150">You use the tabs to specify interchange and transaction set related settings in the tabs.</span></span>  
  
    4.  <span data-ttu-id="4c07b-151">選択、**を有効にするアグリーメント**チェック ボックスをアグリーメントを有効にし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-151">Select the **Enable Agreement** check box to enable the agreement and do the following:</span></span>  
  
        |<span data-ttu-id="4c07b-152">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c07b-152">Use this</span></span>|<span data-ttu-id="4c07b-153">目的</span><span class="sxs-lookup"><span data-stu-id="4c07b-153">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4c07b-154">**From**</span><span class="sxs-lookup"><span data-stu-id="4c07b-154">**From**</span></span>|<span data-ttu-id="4c07b-155">アグリーメントが有効となる日時を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-155">Select the date and time from which the agreement will be valid.</span></span>|  
        |<span data-ttu-id="4c07b-156">**終了日がないです。**</span><span class="sxs-lookup"><span data-stu-id="4c07b-156">**No End Date**</span></span>|<span data-ttu-id="4c07b-157">アグリーメントの有効期限を設定しない場合はこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-157">Select this option if you do not want to set an end date when the agreement is disabled.</span></span>|  
        |<span data-ttu-id="4c07b-158">**終了日します。**</span><span class="sxs-lookup"><span data-stu-id="4c07b-158">**End By**</span></span>|<span data-ttu-id="4c07b-159">アグリーメントが有効期限となる日時を指定するにはこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-159">Select this option and specify the date and time until which the agreement will be valid.</span></span>|  
  
    5.  <span data-ttu-id="4c07b-160">**共通のホスト設定**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-160">In the **Common Host Settings** section, do the following:</span></span>  
  
        |<span data-ttu-id="4c07b-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4c07b-161">Use this</span></span>|<span data-ttu-id="4c07b-162">目的</span><span class="sxs-lookup"><span data-stu-id="4c07b-162">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4c07b-163">**レポートで有効にします。**</span><span class="sxs-lookup"><span data-stu-id="4c07b-163">**Turn ON reporting**</span></span>|<span data-ttu-id="4c07b-164">すべての AS2 メッセージ (受信および送信) で状態エントリを表示する、 **AS2 メッセージおよび関連する MDN 状態**のタブ、**グループの概要**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-164">to display status entries for all AS2 messages (incoming and outgoing) in the **AS2 Message and Correlated MDN Status** tab of the **Group Overview** pane in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="4c07b-165">このオプションがオフの場合、状況を示すエントリは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4c07b-165">If cleared, no status entries will be displayed</span></span>|  
  
3.  <span data-ttu-id="4c07b-166">**全般** タブで、**連絡先情報** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-166">In the **General** tab, on the **Contact Information** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="4c07b-167">**連絡先 1**  タブを使用するアグリーメントを作成するパーティのプロファイルの連絡先情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-167">In the **Contact1** tab, enter the contact information for the party’s profile with which you are creating an agreement.</span></span> <span data-ttu-id="4c07b-168">このデータは参考用であり、BizTalk ランタイムでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="4c07b-168">This data is for information purposes only; it will not be used by the BizTalk Runtime.</span></span>  
  
    2.  <span data-ttu-id="4c07b-169">連絡先の別のタブを追加する をクリックして、**新しい連絡先**タブです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-169">To add another tab for contact, click the **New Contact** tab.</span></span>  
  
    3.  <span data-ttu-id="4c07b-170">連絡先 タブを削除しても**削除**タブ ページの右上隅にあるからです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-170">To delete a contact tab, click **Delete** from the top right corner of the tab page.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4c07b-171">削除することはできません、**連絡先 1**タブです。削除できるのは、追加したタブだけです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-171">You cannot delete the **Contact1** tab. You can only delete the new tabs that you add.</span></span>  
  
4.  <span data-ttu-id="4c07b-172">**全般** タブで、**追加プロパティ** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-172">In the **General** tab, on the **Additional Properties** page, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c07b-173">このページで指定する情報は、BizTalk Server による処理には使用されません。このデータは参考用です。</span><span class="sxs-lookup"><span data-stu-id="4c07b-173">The information you specify on this page is not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>  
  
    1.  <span data-ttu-id="4c07b-174">**追加プロパティ**グリッドで、パーティまたはアグリーメントに関連する情報を追加する名前と値のペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-174">In the **Additional Properties** grid, enter name-value pairs for any information that you want to add related to the party or agreement.</span></span>  <span data-ttu-id="4c07b-175">パーティに関する任意の情報を格納する、名前と値の組み合わせを入力します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-175">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="4c07b-176">名前と値の組み合わせは、必要な数だけ追加できます。</span><span class="sxs-lookup"><span data-stu-id="4c07b-176">You can add as many name-value pairs as you want.</span></span>  
  
         <span data-ttu-id="4c07b-177">名前と値のペアを削除、行を選択し、をクリックする**削除**右上隅からです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-177">To delete a name-value pair, select the row and click **Delete** from the top-right corner.</span></span>  
  
    2.  <span data-ttu-id="4c07b-178">**テキスト 1**、**テキスト 2**、および**アグリーメント**テキスト ボックスでは、パーティとのアグリーメントに関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-178">In the **Text 1**, **Text 2**, and **Agreement** text boxes, enter information about the agreement with a party.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="4c07b-179">クリックすると **[ok]** または**適用**すべての値を提供することは、このページに一覧表示後に、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4c07b-179">If you click **OK** or **Apply** after providing all the values listed in this page, you will get an error.</span></span> <span data-ttu-id="4c07b-180">その理由は、アグリーメントの作成に必要な値がまだ入力されていないからです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-180">That is because the mandatory values to create an agreement are not yet provided.</span></span> <span data-ttu-id="4c07b-181">これらは、AS2-から AS2 に-の値を**識別子**各一方向アグリーメント タブのページです。</span><span class="sxs-lookup"><span data-stu-id="4c07b-181">These are AS2-From to AS2-To values on the **Identifiers** page of each one-way agreement tab.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4c07b-182">次の手順</span><span class="sxs-lookup"><span data-stu-id="4c07b-182">Next Steps</span></span>  
 <span data-ttu-id="4c07b-183">アグリーメントの識別子設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c07b-183">You must now configure the identifier settings for the agreement.</span></span> <span data-ttu-id="4c07b-184">手順を参照してください[識別子の構成 (AS2)](../core/configuring-identifiers-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c07b-184">For instructions see [Configuring Identifiers (AS2)](../core/configuring-identifiers-as2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c07b-185">参照</span><span class="sxs-lookup"><span data-stu-id="4c07b-185">See Also</span></span>  
 [<span data-ttu-id="4c07b-186">AS2 アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="4c07b-186">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)
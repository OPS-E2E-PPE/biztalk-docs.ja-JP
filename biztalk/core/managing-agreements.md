---
title: 契約の管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.agreement
ms.assetid: e9c6cdd1-8c17-4b1e-a556-2b287593bb9d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 012a4a5032bd9f9e9a66b855d41a83b5dc5736d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265562"
---
# <a name="managing-agreements"></a><span data-ttu-id="0ded5-102">契約の管理</span><span class="sxs-lookup"><span data-stu-id="0ded5-102">Managing Agreements</span></span>
<span data-ttu-id="0ded5-103">取引先アグリーメント (TPA) は、特定の B2B プロトコルでメッセージをやり取りする際に 2 つの取引パートナー間で交わされる決定的で拘束力があるアグリーメントと定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-103">A Trading Partner Agreement (TPA) is defined as a definitive and binding agreement between two trading partners for transacting messages over a specific B2B Protocol.</span></span> <span data-ttu-id="0ded5-104">参照してください[取引先アグリーメント](../core/trading-partner-agreement.md)です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-104">See [Trading Partner Agreement](../core/trading-partner-agreement.md).</span></span> 

<span data-ttu-id="0ded5-105">このトピックでは、作成、表示、編集、有効にするに、無効化、または契約を削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-105">This topics shows you how to create, view, edit, enable, disable, or delete an agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0ded5-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="0ded5-106">Prerequisites</span></span>  
 <span data-ttu-id="0ded5-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ded5-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="create-an-agreement"></a><span data-ttu-id="0ded5-108">アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-108">Create an agreement</span></span>  
  
1.  <span data-ttu-id="0ded5-109">開いている**BizTalk Server 管理コンソール**BizTalk グループを展開し、選択、**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-109">Open **BizTalk Server Administration**, expand the BizTalk group, and select **Parties**.</span></span> 
2. <span data-ttu-id="0ded5-110">**パーティとビジネス プロファイル**] ページで、選択、作成する場合は、アグリーメントの一部であるビジネス プロファイルを右クリックして**新規**、し、[**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-110">In the **Parties and Business Profiles** page, right-click a business profile that is part of the agreement you are creating, select **New**, and then select **Agreement**.</span></span>  
  
3.  <span data-ttu-id="0ded5-111">**全般プロパティ**:</span><span class="sxs-lookup"><span data-stu-id="0ded5-111">In the **General Properties**:</span></span> 
  
    1.  <span data-ttu-id="0ded5-112">**アグリーメントのパラメーター**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-112">In the **Agreement Parameters** section, do the following:</span></span>  
  
        |<span data-ttu-id="0ded5-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0ded5-113">Use this</span></span>|<span data-ttu-id="0ded5-114">目的</span><span class="sxs-lookup"><span data-stu-id="0ded5-114">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0ded5-115">**名前**</span><span class="sxs-lookup"><span data-stu-id="0ded5-115">**Name**</span></span>|<span data-ttu-id="0ded5-116">アグリーメントの名前を入力してください。</span><span class="sxs-lookup"><span data-stu-id="0ded5-116">Enter a name for the agreement</span></span>|  
        |<span data-ttu-id="0ded5-117">**ID**</span><span class="sxs-lookup"><span data-stu-id="0ded5-117">**ID**</span></span>|<span data-ttu-id="0ded5-118">アグリーメントの一意な ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-118">Lists unique identification for the agreement.</span></span> <span data-ttu-id="0ded5-119">このテキスト ボックスは読み取り専用と、選択した後、アグリーメントの ID を表示**適用**最初の時刻、および設定が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-119">This text box is read-only, and display the agreement ID after you select **Apply** for the first time, and the settings are accepted.</span></span>|  
        |<span data-ttu-id="0ded5-120">**[状態]**</span><span class="sxs-lookup"><span data-stu-id="0ded5-120">**Status**</span></span>|<span data-ttu-id="0ded5-121">アグリーメントの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-121">Specifies the status of the agreement.</span></span> <span data-ttu-id="0ded5-122">既定では、アグリーメントの作成、 **Active**状態です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-122">By default, an agreement is created in an **Active** state.</span></span> <span data-ttu-id="0ded5-123">場合は、作成した最初の select があるときに無効にするアグリーメント**無効になっている**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-123">If you want the agreement to be disabled when it is first created, select **Disabled** from the drop-down list.</span></span>|  
        |<span data-ttu-id="0ded5-124">**[プロトコル]**</span><span class="sxs-lookup"><span data-stu-id="0ded5-124">**Protocol**</span></span>|<span data-ttu-id="0ded5-125">アグリーメントのプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-125">Specifies the protocol for the agreement.</span></span><br /><br /> <span data-ttu-id="0ded5-126">X12 エンコード プロトコルの次のように選択します。 **X12**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-126">-   For an X12 encoding protocol, select **X12** from the drop-down list.</span></span> <span data-ttu-id="0ded5-127">参照してください[X12 に固有のアグリーメント プロパティの構成](../core/configuring-x12-specific-agreement-properties.md)</span><span class="sxs-lookup"><span data-stu-id="0ded5-127">See [Configuring X12-Specific Agreement Properties](../core/configuring-x12-specific-agreement-properties.md)</span></span><br /><span data-ttu-id="0ded5-128">EDIFACT エンコーディング プロトコルの場合、次のように選択します。 **EDIFACT**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-128">-   For an EDIFACT encoding protocol, select **EDIFACT** from the drop-down list.</span></span>  <span data-ttu-id="0ded5-129">参照してください[EDIFACT に固有のアグリーメントのプロパティを構成する](../core/configuring-edifact-specific-agreement-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-129">See [Configuring EDIFACT-Specific Agreement Properties](../core/configuring-edifact-specific-agreement-properties.md).</span></span><br /><span data-ttu-id="0ded5-130">AS2 エンコード プロトコルの場合、次のように選択します。 **AS2**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-130">-   For an AS2 encoding protocol, select **AS2** from the drop-down list.</span></span> <span data-ttu-id="0ded5-131">参照してください[AS2 アグリーメントのプロパティを構成する](../core/configuring-as2-agreement-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-131">See [Configuring AS2 Agreement Properties](../core/configuring-as2-agreement-properties.md).</span></span> <br/><br/><span data-ttu-id="0ded5-132">**注**</span><span class="sxs-lookup"><span data-stu-id="0ded5-132">**Note**</span></span><br/>  <span data-ttu-id="0ded5-133">アグリーメントのプロパティは、一方向のアグリーメント タブにあります。</span><span class="sxs-lookup"><span data-stu-id="0ded5-133">The agreement properties are provided in the one-way agreement tabs.</span></span> <span data-ttu-id="0ded5-134">一方向のアグリーメント タブは、アグリーメントを作成する 2 つ目のプロファイルを選択した後で表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-134">The one-way agreement tabs appear after you have selected the second profile with which the agreement will be created.</span></span> <span data-ttu-id="0ded5-135">2 つ目のパートナーは次の手順で選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-135">You select the second partner in the following steps.</span></span>|  
  
    2.  <span data-ttu-id="0ded5-136">**最初のパートナーと**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-136">In the **First Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="0ded5-137">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0ded5-137">Use this</span></span>|<span data-ttu-id="0ded5-138">目的</span><span class="sxs-lookup"><span data-stu-id="0ded5-138">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0ded5-139">**名前**</span><span class="sxs-lookup"><span data-stu-id="0ded5-139">**Name**</span></span>|<span data-ttu-id="0ded5-140">このアグリーメントの作成に使用するビジネス プロファイルが属するパートナーの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-140">Displays the partner name that has the business profile for which you are creating the agreement.</span></span> <span data-ttu-id="0ded5-141">このテキスト ボックスとは、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-141">This text box is read-only.</span></span>|  
        |<span data-ttu-id="0ded5-142">**プロファイル**</span><span class="sxs-lookup"><span data-stu-id="0ded5-142">**Profile**</span></span>|<span data-ttu-id="0ded5-143">このアグリーメントの作成に使用するプロファイルの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-143">Displays the name of the profile for which you are creating the agreement.</span></span> <span data-ttu-id="0ded5-144">このテキスト ボックスとは、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-144">This text box is read-only.</span></span>|  
        |<span data-ttu-id="0ded5-145">**プロトコル セット**</span><span class="sxs-lookup"><span data-stu-id="0ded5-145">**Protocol Set**</span></span>|<span data-ttu-id="0ded5-146">ビジネス プロファイルの一部として X12 プロトコル セットを作成した場合は、ドロップダウン リストからそのセットを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-146">If you created an X12 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="0ded5-147">ビジネス プロファイルの一部として X12 プロトコル セットを作成していない場合は、空白のまま残しておきます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-147">If you did not create an X12 protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
    3.  <span data-ttu-id="0ded5-148">**2 番目のパートナー**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-148">In the **Second Partner** section, do the following:</span></span>  
  
        |<span data-ttu-id="0ded5-149">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0ded5-149">Use this</span></span>|<span data-ttu-id="0ded5-150">目的</span><span class="sxs-lookup"><span data-stu-id="0ded5-150">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0ded5-151">**名前**</span><span class="sxs-lookup"><span data-stu-id="0ded5-151">**Name**</span></span>|<span data-ttu-id="0ded5-152">ドロップダウン リストから、アグリーメントの作成に使用するビジネス プロファイルが属するパーティを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-152">From the drop-down select a party that has the business profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="0ded5-153">**プロファイル**</span><span class="sxs-lookup"><span data-stu-id="0ded5-153">**Profile**</span></span>|<span data-ttu-id="0ded5-154">ドロップダウン リストから、アグリーメントの作成に使用するプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-154">From the drop-down select a profile with which you want to create an agreement.</span></span>|  
        |<span data-ttu-id="0ded5-155">**プロトコル セット**</span><span class="sxs-lookup"><span data-stu-id="0ded5-155">**Protocol Set**</span></span>|<span data-ttu-id="0ded5-156">ビジネス プロファイルの一部として X12 プロトコル セットを作成した場合は、ドロップダウン リストからそのセットを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-156">If you created an X12 protocol set as part of the business profile, you can select that from the drop-down list.</span></span> <span data-ttu-id="0ded5-157">ビジネス プロファイルの一部として X12 プロトコル セットを作成していない場合は、空白のまま残しておきます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-157">If you did not create an X12 protocol set as part of the business profile, you can leave this empty.</span></span>|  
  
        > [!TIP]
        >  <span data-ttu-id="0ded5-158">キーを押して`CTRL`は、アグリーメントの一部にする、いずれかのビジネス プロファイルを右クリックし、選択するビジネス プロファイルを選択して**新規**、し、**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-158">Press `CTRL`, select the business profiles that will be part of the agreement, right-click either business profile, select **New**, and then select **Agreement**.</span></span> <span data-ttu-id="0ded5-159">値は、パートナー名と、両方のパートナーのビジネス プロファイルが自動的に挿入されます、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0ded5-159">The values for partner name and business profiles for both the partners are automatically populated in the **Agreement Properties** dialog box.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0ded5-160">2 つのタブが横に追加された別のプロファイルを選択するとすぐに、**全般**タブです。各タブは、2 つのパーティ間の一方向のアグリーメントを表します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-160">As soon as you select the other profile, two tabs are added next to the **General** tab. Each tab represents a one-way agreement between the two parties.</span></span> <span data-ttu-id="0ded5-161">タブを使用して、アグリーメントのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-161">You use the tabs to enter the agreement properties.</span></span>  
  
    4.  <span data-ttu-id="0ded5-162">選択、**を有効にするアグリーメント**チェック ボックスをアグリーメントを有効にし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-162">Select the **Enable Agreement** check box to enable the agreement, and do the following:</span></span>  
  
        |<span data-ttu-id="0ded5-163">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0ded5-163">Use this</span></span>|<span data-ttu-id="0ded5-164">目的</span><span class="sxs-lookup"><span data-stu-id="0ded5-164">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0ded5-165">**From**</span><span class="sxs-lookup"><span data-stu-id="0ded5-165">**From**</span></span>|<span data-ttu-id="0ded5-166">元のアグリーメントが有効では日時を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-166">Select the date and time from which the agreement is valid.</span></span>|  
        |<span data-ttu-id="0ded5-167">**終了日がないです。**</span><span class="sxs-lookup"><span data-stu-id="0ded5-167">**No End Date**</span></span>|<span data-ttu-id="0ded5-168">アグリーメントの有効期限を設定しない場合はこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-168">Select this option if you do not want to set an end date when the agreement is disabled.</span></span>|  
        |<span data-ttu-id="0ded5-169">**終了日します。**</span><span class="sxs-lookup"><span data-stu-id="0ded5-169">**End By**</span></span>|<span data-ttu-id="0ded5-170">日付と、アグリーメントが有効になるまでの時刻を入力するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-170">Select this option to enter the date and time until the agreement is valid.</span></span>|  
  
    5.  <span data-ttu-id="0ded5-171">**共通のホスト設定**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-171">In the **Common Host Settings** section, do the following:</span></span>  
  
        |<span data-ttu-id="0ded5-172">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0ded5-172">Use this</span></span>|<span data-ttu-id="0ded5-173">目的</span><span class="sxs-lookup"><span data-stu-id="0ded5-173">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0ded5-174">**エラーをイベント ログに記録**</span><span class="sxs-lookup"><span data-stu-id="0ded5-174">**Log errors to event log**</span></span>|<span data-ttu-id="0ded5-175">オンにすると、EDI エンジン (EDI パイプライン、バッチ処理オーケストレーション、ルーティング オーケストレーションなど) で生成されるすべてのエラーが、コンテキスト情報と共に、Windows イベント ビューアーに記録されます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-175">Select this option if you want to log any errors generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span><br/><br/><span data-ttu-id="0ded5-176">**注**: AS2 アグリーメントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="0ded5-176">**Note**:  Does not apply to AS2 agreements.</span></span>|  
        |<span data-ttu-id="0ded5-177">**警告イベント ログを記録します。**</span><span class="sxs-lookup"><span data-stu-id="0ded5-177">**Log warnings to event log**</span></span>|<span data-ttu-id="0ded5-178">オンにすると、EDI エンジン (EDI パイプライン、バッチ処理オーケストレーション、ルーティング オーケストレーションなど) で生成されるすべての警告が、コンテキスト情報と共に、Windows イベント ビューアーに記録されます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-178">Select this option if you want to log any warnings generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span> <br/><br/><span data-ttu-id="0ded5-179">**注**: AS2 アグリーメントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="0ded5-179">**Note**:  Does not apply to AS2 agreements.</span></span>|  
        |<span data-ttu-id="0ded5-180">**レポートで有効にします。**</span><span class="sxs-lookup"><span data-stu-id="0ded5-180">**Turn ON reporting**</span></span>|<span data-ttu-id="0ded5-181">すべての EDI メッセージ (受信および送信) の状態エントリを表示するには、このオプションを選択で、 **EDI インターチェンジと関連する ACK の状態**のタブ、**グループの概要** ページで、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-181">Select this option to display status entries for all EDI messages (incoming and outgoing) on the **EDI Interchange and Correlated ACK Status** tab of the **Group Overview** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="0ded5-182">オフの場合、状態エントリは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0ded5-182">If unchecked, no status entries are displayed.</span></span>|  
        |<span data-ttu-id="0ded5-183">**レポート作成用のメッセージ ペイロードを格納**</span><span class="sxs-lookup"><span data-stu-id="0ded5-183">**Store message payload for reporting**</span></span>|<span data-ttu-id="0ded5-184">選択した場合は**レポートをオンに**追跡 (BizTalkDTADb) データベースの EDI テーブルにトランザクションを保存するには、このオプションの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-184">If you selected **Turn ON reporting**, select this option to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span> <br/><br/><span data-ttu-id="0ded5-185">**注**: AS2 アグリーメントには適用されません。</span><span class="sxs-lookup"><span data-stu-id="0ded5-185">**Note**:  Does not apply to AS2 agreements.</span></span>|  
  
4.  <span data-ttu-id="0ded5-186">**全般** タブで、**連絡先情報** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-186">In the **General** tab, on the **Contact Information** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="0ded5-187">**連絡先 1**  タブを使用するアグリーメントを作成するパーティのプロファイルの連絡先情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-187">In the **Contact1** tab, enter the contact information for the party’s profile with which you are creating an agreement.</span></span> <span data-ttu-id="0ded5-188">このデータは情報目的でのみです。BizTalk ランタイムでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="0ded5-188">This data is for information purposes only; it is not used by the BizTalk Runtime.</span></span>  
  
    2.  <span data-ttu-id="0ded5-189">連絡先の別のタブを追加するには、選択、**新しい連絡先**タブです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-189">To add another tab for contact, select the **New Contact** tab.</span></span>  
  
    3.  <span data-ttu-id="0ded5-190">連絡先 タブを削除する選択**削除**タブ ページの右上隅にあるからです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-190">To delete a contact tab, select **Delete** from the top right corner of the tab page.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0ded5-191">削除することはできません、**連絡先 1**タブです。削除できるのは、追加したタブだけです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-191">You cannot delete the **Contact1** tab. You can only delete the new tabs that you add.</span></span>  
  
5.  <span data-ttu-id="0ded5-192">**全般** タブで、**追加プロパティ** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-192">In the **General** tab, on the **Additional Properties** page, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ded5-193">このページで入力した情報がない処理に使用される、BizTalk Server によって任意です。このデータは情報提供のみを目的です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-193">The information you enter on this page is not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>  
  
    1.  <span data-ttu-id="0ded5-194">**追加プロパティ**グリッドで、パーティまたはアグリーメントに関連する情報を追加する名前と値のペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-194">In the **Additional Properties** grid, enter name-value pairs for any information that you want to add related to the party or agreement.</span></span>  <span data-ttu-id="0ded5-195">パーティに関する任意の情報を格納する、名前と値の組み合わせを入力します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-195">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="0ded5-196">名前と値の組み合わせは、必要な数だけ追加できます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-196">You can add as many name-value pairs as you want.</span></span>  
  
         <span data-ttu-id="0ded5-197">名前と値のペアを削除し、行を選択して、選択**削除**右上隅からです。</span><span class="sxs-lookup"><span data-stu-id="0ded5-197">To delete a name-value pair, select the row, and select **Delete** from the top-right corner.</span></span>  
  
    2.  <span data-ttu-id="0ded5-198">**テキスト 1**、**テキスト 2**、および**アグリーメント**テキスト ボックスでは、パーティとのアグリーメントに関する情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-198">In the **Text 1**, **Text 2**, and **Agreement** text boxes, enter information about the agreement with a party.</span></span>  
  
    3.  <span data-ttu-id="0ded5-199">選択**適用**、プロパティを受け入れるかを選択する**OK**構成設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-199">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="0ded5-200">どちらの操作では、設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-200">Either action validates the settings.</span></span>  

## <a name="view-or-change-an-agreement"></a><span data-ttu-id="0ded5-201">表示またはアグリーメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-201">View or change an agreement</span></span>  
  
1.  <span data-ttu-id="0ded5-202">**BizTalk Server 管理コンソール****パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-202">In **BizTalk Server Administration**, select **Parties**.</span></span> 

2. <span data-ttu-id="0ded5-203">**パーティとビジネス プロファイル** ページで、表示または編集する契約を結んでいる 2 つのビジネス プロファイルのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-203">In the **Parties and Business Profiles** page, select any of the two business profile that have the agreement that you want to view or edit.</span></span>  
  
3.  <span data-ttu-id="0ded5-204">**契約**セクションには、アグリーメントを右クリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-204">In the **Agreements** section, right-click the agreement, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="0ded5-205">**アグリーメントのプロパティ**、表示またはアグリーメントを編集します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-205">In the **Agreement Properties**, view or edit the agreement.</span></span> <span data-ttu-id="0ded5-206">さまざまなタブおよび内のページで入力できる値について、**アグリーメントのプロパティ** ダイアログ ボックスで、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ded5-206">For the values that can be entered on the different tabs and pages in the **Agreement Properties** dialog box, see the following:</span></span>  
  
    |<span data-ttu-id="0ded5-207">こちらは</span><span class="sxs-lookup"><span data-stu-id="0ded5-207">For this</span></span>|<span data-ttu-id="0ded5-208">これを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ded5-208">See this</span></span>|  
    |--------------|--------------|  
    |<span data-ttu-id="0ded5-209">X12 アグリーメント</span><span class="sxs-lookup"><span data-stu-id="0ded5-209">For X12 agreement</span></span>|[<span data-ttu-id="0ded5-210">X12 固有のアグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="0ded5-210">Configuring X12-Specific Agreement Properties</span></span>](../core/configuring-x12-specific-agreement-properties.md)|  
    |<span data-ttu-id="0ded5-211">EDIFACT アグリーメント</span><span class="sxs-lookup"><span data-stu-id="0ded5-211">For EDIFACT agreement</span></span>|[<span data-ttu-id="0ded5-212">EDIFACT 固有のアグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="0ded5-212">Configuring EDIFACT-Specific Agreement Properties</span></span>](../core/configuring-edifact-specific-agreement-properties.md)|  
    |<span data-ttu-id="0ded5-213">AS2 アグリーメント</span><span class="sxs-lookup"><span data-stu-id="0ded5-213">For AS2 agreement</span></span>|[<span data-ttu-id="0ded5-214">AS2 アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="0ded5-214">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)|  
  
5.  <span data-ttu-id="0ded5-215">選択**適用**、プロパティを受け入れるかを選択する**OK**構成設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-215">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="0ded5-216">どちらの操作では、設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-216">Either action validates the settings.</span></span> 

## <a name="enable-or-disable-an-agreement"></a><span data-ttu-id="0ded5-217">アグリーメントを無効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="0ded5-217">Enable or disable an agreement</span></span>  
  
1.  <span data-ttu-id="0ded5-218">**BizTalk Server 管理コンソール****パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-218">In **BizTalk Server Administration**, select **Parties**.</span></span> 

2. <span data-ttu-id="0ded5-219">**パーティとビジネス プロファイル** ページで、編集する契約を結んでいる 2 つのビジネス プロファイルのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-219">In the **Parties and Business Profiles** page, select any of the two business profile that have the agreement that you want to edit.</span></span>  
  
3.  <span data-ttu-id="0ded5-220">**契約**セクションには、アグリーメントを右クリックし、**を有効にする**または**を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-220">In the **Agreements** section, right-click the agreement, and then select **Enable** or **Disable**.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="0ded5-221">アグリーメントの初回作成時は、既定で常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="0ded5-221">When an agreement is first created, it is always enabled by default.</span></span> <span data-ttu-id="0ded5-222">**を有効にする**オプションは、アグリーメントが無効な場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-222">The **Enable** option is available only when the agreement is disabled.</span></span> <span data-ttu-id="0ded5-223">**を無効にする**オプションは、アグリーメントが有効な場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ded5-223">The **Disable** option is available only when the agreement is enabled.</span></span>  

## <a name="delete-an-agreement"></a><span data-ttu-id="0ded5-224">アグリーメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-224">Delete an agreement</span></span>  
1.  <span data-ttu-id="0ded5-225">**BizTalk Server 管理コンソール****パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-225">In **BizTalk Server Administration**, select **Parties**.</span></span> 
  
2.  <span data-ttu-id="0ded5-226">**パーティとビジネス プロファイル** ページで、削除する契約を結んでいる 2 つのビジネス プロファイルのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-226">In the **Parties and Business Profiles** page, select any of the two business profile that have the agreement that you want to delete.</span></span>  
  
3.  <span data-ttu-id="0ded5-227">**契約**セクションで、削除、およびを選択するアグリーメントを右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="0ded5-227">In the **Agreements** section, right-click the agreement that you want to delete, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="0ded5-228">**アグリーメント削除の確認**ダイアログ ボックスで、**はい**した契約を削除します。</span><span class="sxs-lookup"><span data-stu-id="0ded5-228">In the **Confirm delete agreement** dialog box, select **Yes** to delete the agreement.</span></span>  

      
## <a name="see-also"></a><span data-ttu-id="0ded5-229">参照</span><span class="sxs-lookup"><span data-stu-id="0ded5-229">See Also</span></span>  
 [<span data-ttu-id="0ded5-230">EDI および AS2 ソリューションの管理</span><span class="sxs-lookup"><span data-stu-id="0ded5-230">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)
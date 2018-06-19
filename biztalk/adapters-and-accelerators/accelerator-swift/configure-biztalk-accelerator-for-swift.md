---
title: BizTalk Accelerator を SWIFT の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e34b0b2d-f563-468b-b6b9-536f0df96f52
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaa9812243ef7d5ff4bb8b902ac7aee48e54ab99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210858"
---
# <a name="configure-biztalk-accelerator-for-swift"></a><span data-ttu-id="b052d-102">SWIFT の BizTalk アクセラレータを構成します。</span><span class="sxs-lookup"><span data-stu-id="b052d-102">Configure BizTalk Accelerator for SWIFT</span></span>

<span data-ttu-id="b052d-103">構成、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b052d-103">Configure the [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> 

<span data-ttu-id="b052d-104">インストールするときに[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]構成を自動的に実行できるようにする チェック ボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="b052d-104">When you install [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)], there is a checkbox that lets you run the configuration automatically.</span></span> <span data-ttu-id="b052d-105">または、BizTalk Accelerator 用 SWIFT (A4SWIFT) の構成では、アプリの一覧を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="b052d-105">Or, you can open the BizTalk Accelerator for SWIFT (A4SWIFT) Configuration listed in your apps.</span></span>

<span data-ttu-id="b052d-106">このトピックは、構成する方法を示します、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アクセラレータ、構成とも、後の構成手順の一覧をインポートまたはエクスポートの方法です。</span><span class="sxs-lookup"><span data-stu-id="b052d-106">This topic shows you how to configure the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] accelerator, how to export or import a configuration, and also lists the post-configuration steps.</span></span>

## <a name="configure-a4swift"></a><span data-ttu-id="b052d-107">A4SWIFT を構成します。</span><span class="sxs-lookup"><span data-stu-id="b052d-107">Configure A4SWIFT</span></span>

1. <span data-ttu-id="b052d-108">SWIFT (A4SWIFT) の構成を BizTalk Accelerator を開きます。</span><span class="sxs-lookup"><span data-stu-id="b052d-108">Open the BizTalk Accelerator for SWIFT (A4SWIFT) Configuration.</span></span>
2. <span data-ttu-id="b052d-109">選択**MCRR**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-109">Select **MCRR**.</span></span> <span data-ttu-id="b052d-110">MCRR をインストールした場合にのみ使用できますが、 **Message Repair and New Submission**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="b052d-110">MCRR is available only if you installed the **Message Repair and New Submission** components.</span></span>
3. <span data-ttu-id="b052d-111">確認を求められたら**を新しいデータベース グループを作成する**:</span><span class="sxs-lookup"><span data-stu-id="b052d-111">When asked **Do you want to create a new database group**:</span></span>

  * <span data-ttu-id="b052d-112">示すように新しいグループを作成するには、このオプションを選択、**グループ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="b052d-112">Select this option to create the new groups shown in the **Group** pane.</span></span> 
  * <span data-ttu-id="b052d-113">データベースの既存のグループを参加させるのには、このオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b052d-113">To join an existing database group, uncheck this option.</span></span>

3. <span data-ttu-id="b052d-114">インストールした場合**Message Repair and New Submission の Web コンポーネント**選択してから、 **WebService**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-114">If you installed **Web Components for Message Repair and New Submission**, then select **WebService**.</span></span>
4. <span data-ttu-id="b052d-115">A4SWIFT Web サービスをホストする web サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="b052d-115">Select the web site to host the A4SWIFT Web service.</span></span> <span data-ttu-id="b052d-116">既定では、既定の Web サイトが選択されます。</span><span class="sxs-lookup"><span data-stu-id="b052d-116">By default, the Default Web Site is selected.</span></span>
5. <span data-ttu-id="b052d-117">選択**構成を適用**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-117">Select **Apply Configuration**.</span></span>
6. <span data-ttu-id="b052d-118">**概要**構成設定を確認し、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-118">In **Summary**, verify the configuration settings, and then click **Configure**.</span></span> 

    > [!TIP] 
    > <span data-ttu-id="b052d-119">必要であれば、構成設定を XML ファイルとして保存できます。</span><span class="sxs-lookup"><span data-stu-id="b052d-119">You can save the configuration settings as an XML file, if desired.</span></span>

7. <span data-ttu-id="b052d-120">選択**完了**構成が完了するとします。</span><span class="sxs-lookup"><span data-stu-id="b052d-120">Select **Finish** when the configuration completes.</span></span>

## <a name="export-or-import-a-configuration"></a><span data-ttu-id="b052d-121">エクスポートまたはインポートする構成</span><span class="sxs-lookup"><span data-stu-id="b052d-121">Export or import a configuration</span></span>
<span data-ttu-id="b052d-122">A4SWIFT の構成設定は、XML ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b052d-122">You can export the configuration settings of A4SWIFT to an XML file.</span></span> <span data-ttu-id="b052d-123">これらの設定は、別の A4SWIFT インストールを構成し、インポートできます。</span><span class="sxs-lookup"><span data-stu-id="b052d-123">These settings can then be imported to configure another A4SWIFT installation.</span></span> 

### <a name="export-the-configuration"></a><span data-ttu-id="b052d-124">構成をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b052d-124">Export the configuration</span></span>

1. <span data-ttu-id="b052d-125">SWIFT の構成には、Microsoft BizTalk Accelerator を開き、選択**構成のエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-125">Open the Microsoft BizTalk Accelerator for SWIFT Configuration, and select **Export Configuration**.</span></span>
2. <span data-ttu-id="b052d-126">**名前を付けて保存**、構成ファイルを保存するには、構成ファイルの名前を入力するフォルダーを参照し、**保存**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-126">In **Save As**, browse to the folder where you want to save the configuration file, enter a name for the configuration file, and then **Save**.</span></span>
3. <span data-ttu-id="b052d-127">正常にエクスポートされると、選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-127">When exported successfully, select **OK**.</span></span>

### <a name="import-a-configuration"></a><span data-ttu-id="b052d-128">構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="b052d-128">Import a configuration</span></span>
1. <span data-ttu-id="b052d-129">SWIFT の構成には、Microsoft BizTalk Accelerator を開き、選択**構成のインポート**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-129">Open the Microsoft BizTalk Accelerator for SWIFT Configuration, and select **Import Configuration**.</span></span>
2. <span data-ttu-id="b052d-130">構成ファイルを格納するフォルダーを参照、ファイルを選択し、**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-130">Browse to the folder that contains the configuration file, select the file, and then select **Import**.</span></span>

## <a name="post-configuration-steps"></a><span data-ttu-id="b052d-131">インストール後の構成手順</span><span class="sxs-lookup"><span data-stu-id="b052d-131">Post-configuration steps</span></span>

### <a name="add-users-to-the-a4swift-users-group"></a><span data-ttu-id="b052d-132">A4SWIFT の Users グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b052d-132">Add users to the A4SWIFT Users group</span></span>

<span data-ttu-id="b052d-133">構成した後、 [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]、BizTalkServerApplication ホスト インスタンスを実行するアカウントを追加、 **A4SWIFT ユーザー**グループ (*いない*、 **A4SWIFT 管理者**グループ)。</span><span class="sxs-lookup"><span data-stu-id="b052d-133">After you configure the [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)], add the account that runs the BizTalkServerApplication host instance to the **A4SWIFT Users** group (*not* the **A4SWIFT Administrators** group).</span></span> 

<span data-ttu-id="b052d-134">**手順**:</span><span class="sxs-lookup"><span data-stu-id="b052d-134">**Steps**:</span></span>

1. <span data-ttu-id="b052d-135">開いている**Services**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-135">Open **Services**.</span></span> <span data-ttu-id="b052d-136">使用可能なサービスも**サーバー マネージャー**、し**ツール**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-136">Services is also available in **Server Manager**, and then **Tools**.</span></span> 
2. <span data-ttu-id="b052d-137">一覧で、検索**BizTalk Service BizTalk Group: BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-137">In the list, find **BizTalk Service BizTalk Group: BizTalkServerApplication**.</span></span> 
3. <span data-ttu-id="b052d-138">そのプロパティを開くには、二重選択します。</span><span class="sxs-lookup"><span data-stu-id="b052d-138">Double-select to open its properties.</span></span>
4. <span data-ttu-id="b052d-139">**ログオン** タブで、ユーザー アカウントは、として表示されている**このアカウント**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-139">In the **Log On** tab, note the user account listed as **This account**.</span></span>
5. <span data-ttu-id="b052d-140">開いている**ローカル ユーザーとグループ**(コンピューターの管理) し、検索、 **A4SWIFT ユーザー**グループ。</span><span class="sxs-lookup"><span data-stu-id="b052d-140">Open **Local Users and Groups** (in Computer Management), and then find the **A4SWIFT Users** group.</span></span> <span data-ttu-id="b052d-141">このグループにユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="b052d-141">Add the user account to this group.</span></span>

> [!TIP] 
> <span data-ttu-id="b052d-142">ホスト インスタンス アカウントには、このグループのメンバーシップ Message Repair ランタイム コンポーネントのホストの BizTalk Server データベースにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b052d-142">The host instance account needs this group membership for the host Message Repair runtime component to access the BizTalk Server database.</span></span>

### <a name="check-the-identity-of-the-application-pool"></a><span data-ttu-id="b052d-143">アプリケーション プールの id を確認します。</span><span class="sxs-lookup"><span data-stu-id="b052d-143">Check the identity of the application pool</span></span>
<span data-ttu-id="b052d-144">A4SWIFT_MRSR web サービスは、IIS のアプリケーションでホストされます。</span><span class="sxs-lookup"><span data-stu-id="b052d-144">The A4SWIFT_MRSR web service is hosted in an application in IIS.</span></span> <span data-ttu-id="b052d-145">アプリケーション プール id*できません*ネットワーク サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b052d-145">The application pool identity *cannot* be Network Service.</span></span> <span data-ttu-id="b052d-146">メンバーであるローカルまたはドメイン アカウントにアプリケーション プールの id を変更、 **A4SWIFT ユーザー**グループ。</span><span class="sxs-lookup"><span data-stu-id="b052d-146">Change the identity of the application pool to a local or domain account that is a member of the **A4SWIFT Users** group.</span></span>

<span data-ttu-id="b052d-147">**手順**:</span><span class="sxs-lookup"><span data-stu-id="b052d-147">**Steps**:</span></span>

1. <span data-ttu-id="b052d-148">開いている**インターネット インフォメーション サービス マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-148">Open **Internet Information Services Manager**.</span></span> <span data-ttu-id="b052d-149">IIS マネージャーはでも利用できます**サーバー マネージャー**、し**ツール**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-149">The IIS Manager is also available in **Server Manager**, and then **Tools**.</span></span> 
2. <span data-ttu-id="b052d-150">展開して、**既定の Web サイト**、A4SWIFT_MRSR web サービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b052d-150">Expand the **Default Web Site**, and select the A4SWIFT_MRSR web service.</span></span> 
3. <span data-ttu-id="b052d-151">選択**基本設定**です。</span><span class="sxs-lookup"><span data-stu-id="b052d-151">Select **Basic Settings**.</span></span> <span data-ttu-id="b052d-152">アプリケーション プールの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b052d-152">The name of the application pool is listed.</span></span>
4. <span data-ttu-id="b052d-153">左のペインで選択**アプリケーション プール**、アプリケーション プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b052d-153">In the left pane, select **Application Pools**, and then select your application pool.</span></span>
5. <span data-ttu-id="b052d-154">選択**詳細設定**、し、変更、 **Identity**必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="b052d-154">Select **Advanced Settings**, and change the **Identity** if needed.</span></span>
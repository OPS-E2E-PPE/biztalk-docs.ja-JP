---
title: "適用し、追跡プロファイルを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, testing
- tracking profiles, deleting
- testing, tracking profiles
ms.assetid: 77cef14b-c390-4da7-a383-b3abe414a168
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 955b2ccddb215b79fd7cdc7d51ed6f5160c297fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a><span data-ttu-id="f782e-102">追跡プロファイルを適用および削除する方法</span><span class="sxs-lookup"><span data-stu-id="f782e-102">How to Apply and Remove a Tracking Profile</span></span>
<span data-ttu-id="f782e-103">追跡プロファイルを作成または変更したら、そのプロファイルをテスト データベースに適用し、結合テストを行って結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="f782e-103">Once you have created or modified the tracking profile, the next step is to apply it to a test database and verify the result through integration testing.</span></span> <span data-ttu-id="f782e-104">追跡プロファイルは、追跡プロファイル エディター (TPE) から直接適用するか、またはコマンド ラインを使用して適用することができます。</span><span class="sxs-lookup"><span data-stu-id="f782e-104">You can apply the tracking profile from within Tracking Profile Editor (TPE) itself or by using the command line.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f782e-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="f782e-105">Prerequisites</span></span>  
 <span data-ttu-id="f782e-106">ハード ドライブに保存されている、作成済みの追跡プロファイル。</span><span class="sxs-lookup"><span data-stu-id="f782e-106">A previously created tracking profile that you saved to your hard drive.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a><span data-ttu-id="f782e-107">TPE から追跡プロファイルを適用するには</span><span class="sxs-lookup"><span data-stu-id="f782e-107">To apply the tracking profile from within the TPE</span></span>  
  
1.  <span data-ttu-id="f782e-108">をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**追跡プロファイル エディター**です。</span><span class="sxs-lookup"><span data-stu-id="f782e-108">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f782e-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f782e-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="f782e-110">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="f782e-110">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="f782e-111">**ファイル** メニューのをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="f782e-111">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="f782e-112">適用する .btt ファイルが保存されているハード ドライブの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="f782e-112">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="f782e-113">をクリックして**開く**ファイルを読み込むことです。</span><span class="sxs-lookup"><span data-stu-id="f782e-113">Click **Open** to load it.</span></span>  
  
3.  <span data-ttu-id="f782e-114">**ツール** メニューのをクリックして**追跡プロファイルの適用**から設定した管理データベースに .btt ファイルを適用する、**管理データベースの設定**にメニュー項目が、**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="f782e-114">On the **Tools** menu, click **Apply Tracking Profile** to apply the .btt file to a management database that you have set from the **Set Management Database** menu item on the **Tools** menu.</span></span> <span data-ttu-id="f782e-115">結合テストを行って結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="f782e-115">Verify the result through integration testing.</span></span>  
  
4.  <span data-ttu-id="f782e-116">追跡プロファイルのテストが正常に完了し、追跡プロファイルを展開できるようになったことを、プロファイルの展開を担当する責任者に通知します。</span><span class="sxs-lookup"><span data-stu-id="f782e-116">Notify the person in your organization responsible for deployment that the tracking profile tests correctly and is ready for deployment.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a><span data-ttu-id="f782e-117">コマンド ラインから追跡プロファイルを適用するには</span><span class="sxs-lookup"><span data-stu-id="f782e-117">To apply the tracking profile from the command line</span></span>  
  
-   <span data-ttu-id="f782e-118">コマンド プロンプトから、次のコマンドを使用して bttdeploy.exe ツールを実行します (このツールは \Tracking フォルダーにあります)。</span><span class="sxs-lookup"><span data-stu-id="f782e-118">From the command prompt, run the bttdeploy.exe tool located in the \Tracking folder as follows:</span></span>  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="f782e-119">このツールを使用するには、BizTalk 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="f782e-119">You must have BizTalk Administrator privileges to use this tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f782e-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f782e-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="f782e-121">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="f782e-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f782e-122">展開時には、bttdeploy ツールにより、追跡プロファイルに含まれているアセンブリのバージョンが確認され、展開されているアセンブリのバージョンと照合されます。</span><span class="sxs-lookup"><span data-stu-id="f782e-122">During the deployment, bttdeploy verifies the assembly version contained in the tracking profiles and matches it to the version of the deployed assembly.</span></span> <span data-ttu-id="f782e-123">追跡プロファイルに含まれているアセンブリが展開されていない場合、bttdeploy ツールはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="f782e-123">Bttdeploy will fail if the assembly is not currently deployed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f782e-124">コマンド ラインから追跡プロファイルを適用する場合、bttdeploy ツールでは、構成ウィザードの実行時に指定した BizTalk 管理データベースに追跡プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="f782e-124">When applying a tracking profile from the command line, bttdeploy applies the profile to the BizTalk Management database that you indicated when you ran the configuration wizard.</span></span> <span data-ttu-id="f782e-125">追跡プロファイル エディターのオプション [管理データベースの設定] で別のデータベースを指定した場合は、その設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f782e-125">If you specify a different database setting in the Tracking Profile Editor Option "Set Management Database," then that setting is used.</span></span> <span data-ttu-id="f782e-126">bttdeploy ツールのコマンド ライン オプションとして管理サーバーと管理データベースを指定した場合、コマンド ライン オプションが他の設定に優先されます。</span><span class="sxs-lookup"><span data-stu-id="f782e-126">If you specify a management server and database as part of the command line option to bttdeploy, then the command line option overrides everything else.</span></span> <span data-ttu-id="f782e-127">Bttdeploy ツールの使用の詳細については、次を参照してください。[追跡プロファイルの展開ユーティリティ](../core/tracking-profile-deployment-utility.md)です。</span><span class="sxs-lookup"><span data-stu-id="f782e-127">For more information about using bttdeploy, see [Tracking Profile Deployment Utility](../core/tracking-profile-deployment-utility.md).</span></span>  
  
### <a name="to-remove-a-tracking-profile"></a><span data-ttu-id="f782e-128">追跡プロファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="f782e-128">To remove a tracking profile</span></span>  
  
1.  <span data-ttu-id="f782e-129">をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**追跡プロファイル エディター**です。</span><span class="sxs-lookup"><span data-stu-id="f782e-129">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f782e-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f782e-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="f782e-131">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="f782e-131">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="f782e-132">**ファイル** メニューのをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="f782e-132">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="f782e-133">適用する .btt ファイルが保存されているハード ドライブの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="f782e-133">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="f782e-134">をクリックして**開く**ファイルを読み込むことです。</span><span class="sxs-lookup"><span data-stu-id="f782e-134">Click **Open** to load it.</span></span>  
  
3.  <span data-ttu-id="f782e-135">**ツール** メニューのをクリックして**追跡プロファイルの削除**BizTalk 管理データベースから .btt ファイルに基づいて追跡プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="f782e-135">On the **Tools** menu, click **Remove Tracking Profile** to remove the tracking profile based on the .btt file from the BizTalk Management database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f782e-136">参照</span><span class="sxs-lookup"><span data-stu-id="f782e-136">See Also</span></span>  
 [<span data-ttu-id="f782e-137">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f782e-137">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)
---
title: 適用し、追跡プロファイルを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, testing
- tracking profiles, deleting
- testing, tracking profiles
ms.assetid: 77cef14b-c390-4da7-a383-b3abe414a168
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc3b321647a5861a4b4b3d24251f1ecf013ee09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985027"
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a><span data-ttu-id="eafb0-102">追跡プロファイルを適用および削除する方法</span><span class="sxs-lookup"><span data-stu-id="eafb0-102">How to Apply and Remove a Tracking Profile</span></span>
<span data-ttu-id="eafb0-103">追跡プロファイルを作成または変更したら、そのプロファイルをテスト データベースに適用し、結合テストを行って結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-103">Once you have created or modified the tracking profile, the next step is to apply it to a test database and verify the result through integration testing.</span></span> <span data-ttu-id="eafb0-104">追跡プロファイルは、追跡プロファイル エディター (TPE) から直接適用するか、またはコマンド ラインを使用して適用することができます。</span><span class="sxs-lookup"><span data-stu-id="eafb0-104">You can apply the tracking profile from within Tracking Profile Editor (TPE) itself or by using the command line.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eafb0-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="eafb0-105">Prerequisites</span></span>  
 <span data-ttu-id="eafb0-106">ハード ドライブに保存されている、作成済みの追跡プロファイル。</span><span class="sxs-lookup"><span data-stu-id="eafb0-106">A previously created tracking profile that you saved to your hard drive.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a><span data-ttu-id="eafb0-107">TPE から追跡プロファイルを適用するには</span><span class="sxs-lookup"><span data-stu-id="eafb0-107">To apply the tracking profile from within the TPE</span></span>  
  
1. <span data-ttu-id="eafb0-108">クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**追跡プロファイル エディター**します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-108">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="eafb0-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="eafb0-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="eafb0-110">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-110">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="eafb0-111">**ファイル** メニューのをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-111">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="eafb0-112">適用する .btt ファイルが保存されているハード ドライブの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-112">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="eafb0-113">クリックして**オープン**を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="eafb0-113">Click **Open** to load it.</span></span>  
  
3. <span data-ttu-id="eafb0-114">**ツール** メニューのをクリックして**追跡プロファイルの適用**から設定されている管理データベースに .btt ファイルを適用する、**管理データベースの設定**にメニュー項目が、**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="eafb0-114">On the **Tools** menu, click **Apply Tracking Profile** to apply the .btt file to a management database that you have set from the **Set Management Database** menu item on the **Tools** menu.</span></span> <span data-ttu-id="eafb0-115">結合テストを行って結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-115">Verify the result through integration testing.</span></span>  
  
4. <span data-ttu-id="eafb0-116">追跡プロファイルのテストが正常に完了し、追跡プロファイルを展開できるようになったことを、プロファイルの展開を担当する責任者に通知します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-116">Notify the person in your organization responsible for deployment that the tracking profile tests correctly and is ready for deployment.</span></span>  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a><span data-ttu-id="eafb0-117">コマンド ラインから追跡プロファイルを適用するには</span><span class="sxs-lookup"><span data-stu-id="eafb0-117">To apply the tracking profile from the command line</span></span>  
  
-   <span data-ttu-id="eafb0-118">コマンド プロンプトから、次のコマンドを使用して bttdeploy.exe ツールを実行します (このツールは \Tracking フォルダーにあります)。</span><span class="sxs-lookup"><span data-stu-id="eafb0-118">From the command prompt, run the bttdeploy.exe tool located in the \Tracking folder as follows:</span></span>  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="eafb0-119">このツールを使用するには、BizTalk 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="eafb0-119">You must have BizTalk Administrator privileges to use this tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eafb0-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="eafb0-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="eafb0-121">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eafb0-122">展開時には、bttdeploy ツールにより、追跡プロファイルに含まれているアセンブリのバージョンが確認され、展開されているアセンブリのバージョンと照合されます。</span><span class="sxs-lookup"><span data-stu-id="eafb0-122">During the deployment, bttdeploy verifies the assembly version contained in the tracking profiles and matches it to the version of the deployed assembly.</span></span> <span data-ttu-id="eafb0-123">追跡プロファイルに含まれているアセンブリが展開されていない場合、bttdeploy ツールはエラーになります。</span><span class="sxs-lookup"><span data-stu-id="eafb0-123">Bttdeploy will fail if the assembly is not currently deployed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eafb0-124">コマンド ラインから追跡プロファイルを適用する場合、bttdeploy ツールでは、構成ウィザードの実行時に指定した BizTalk 管理データベースに追跡プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-124">When applying a tracking profile from the command line, bttdeploy applies the profile to the BizTalk Management database that you indicated when you ran the configuration wizard.</span></span> <span data-ttu-id="eafb0-125">追跡プロファイル エディターのオプション [管理データベースの設定] で別のデータベースを指定した場合は、その設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="eafb0-125">If you specify a different database setting in the Tracking Profile Editor Option "Set Management Database," then that setting is used.</span></span> <span data-ttu-id="eafb0-126">bttdeploy ツールのコマンド ライン オプションとして管理サーバーと管理データベースを指定した場合、コマンド ライン オプションが他の設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="eafb0-126">If you specify a management server and database as part of the command line option to bttdeploy, then the command line option overrides everything else.</span></span> <span data-ttu-id="eafb0-127">Bttdeploy ツールの使用に関する詳細については、[追跡プロファイルの展開ユーティリティ](../core/tracking-profile-deployment-utility.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eafb0-127">For more information about using bttdeploy, see [Tracking Profile Deployment Utility](../core/tracking-profile-deployment-utility.md).</span></span>  
  
### <a name="to-remove-a-tracking-profile"></a><span data-ttu-id="eafb0-128">追跡プロファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="eafb0-128">To remove a tracking profile</span></span>  
  
1. <span data-ttu-id="eafb0-129">クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**追跡プロファイル エディター**します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-129">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="eafb0-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="eafb0-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="eafb0-131">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-131">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="eafb0-132">**ファイル** メニューのをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-132">On the **File** menu, click **Open**.</span></span> <span data-ttu-id="eafb0-133">適用する .btt ファイルが保存されているハード ドライブの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-133">Navigate to the correct .btt file on your hard drive.</span></span> <span data-ttu-id="eafb0-134">クリックして**オープン**を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="eafb0-134">Click **Open** to load it.</span></span>  
  
3. <span data-ttu-id="eafb0-135">**ツール** メニューのをクリックして**追跡プロファイルの削除**BizTalk 管理データベースから .btt ファイルに基づいて追跡プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="eafb0-135">On the **Tools** menu, click **Remove Tracking Profile** to remove the tracking profile based on the .btt file from the BizTalk Management database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafb0-136">参照</span><span class="sxs-lookup"><span data-stu-id="eafb0-136">See Also</span></span>  
 [<span data-ttu-id="eafb0-137">追跡プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="eafb0-137">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)
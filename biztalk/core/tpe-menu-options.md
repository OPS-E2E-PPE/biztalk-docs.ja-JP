---
title: "TPE のメニュー オプション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, menu options
- activities [BAM], importing
- activities [BAM], definitions
ms.assetid: 5179fcb5-6dab-481d-ad89-3868c8b07383
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e04d2dfcd6d7f34b0a60a450b64e217b02390a6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="tpe-menu-options"></a><span data-ttu-id="7806e-102">TPE のメニュー オプション</span><span class="sxs-lookup"><span data-stu-id="7806e-102">TPE Menu Options</span></span>
<span data-ttu-id="7806e-103">このトピックでは、追跡プロファイル エディター (TPE) のメニュー オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7806e-103">This topic describes the menu options of the Tracking Profile Editor (TPE).</span></span> <span data-ttu-id="7806e-104">メイン メニューには [ファイル]、[ツール]、および [ヘルプ] があります。</span><span class="sxs-lookup"><span data-stu-id="7806e-104">The main menus include File, Tools, and Help.</span></span>  
  
 <span data-ttu-id="7806e-105">メッセージングの傍受に固有の追加機能は、アクティビティ ビュー (アプリケーションの左ペイン) に表示される項目のショートカット メニュー上に公開されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-105">Additional functionality specific to messaging interception is exposed on the context menu of items displayed in the Activity View in the left pane of the application.</span></span>  
  
## <a name="file-menu"></a><span data-ttu-id="7806e-106">[ファイル] メニュー</span><span class="sxs-lookup"><span data-stu-id="7806e-106">File Menu</span></span>  
 <span data-ttu-id="7806e-107">[ファイル] メニューには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7806e-107">The File menu contains the following options:</span></span>  
  
-   <span data-ttu-id="7806e-108">**新しい**– 新しい追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7806e-108">**New** – Creates a new tracking profile.</span></span> <span data-ttu-id="7806e-109">このオプションは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7806e-109">This option is always available.</span></span>  
  
-   <span data-ttu-id="7806e-110">**開いている**– 既存の追跡プロファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-110">**Open** – Opens an existing tracking profile.</span></span> <span data-ttu-id="7806e-111">このオプションは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7806e-111">This option is always available.</span></span>  
  
-   <span data-ttu-id="7806e-112">**保存**– 現在編集中の追跡プロファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7806e-112">**Save** – Saves the tracking profile currently being edited.</span></span> <span data-ttu-id="7806e-113">追跡プロファイルが編集中でない場合、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7806e-113">If no tracking profile is being edited, this option is not available.</span></span>  
  
-   <span data-ttu-id="7806e-114">**名前を付けて保存**– 指定した名前に、現在編集中の追跡プロファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7806e-114">**Save As** – Saves the tracking profile currently being edited to a name you specify.</span></span> <span data-ttu-id="7806e-115">追跡プロファイルが編集中でない場合、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7806e-115">If no tracking profile is being edited, this option is not available.</span></span>  
  
-   <span data-ttu-id="7806e-116">**BAM アクティビティ定義のインポート**– が適用されているアクティビティ定義をインポートします。</span><span class="sxs-lookup"><span data-stu-id="7806e-116">**Import BAM Activity Definition** – Imports an activity definition that has been applied.</span></span> <span data-ttu-id="7806e-117">このメニュー項目には、左側のフレームにあるウォーターマークのリンクと同じ機能があります。つまり、この機能は、[ファイル] メニューからでも、左側のフレームからでも実行できるということです (ウォーターマークは機能の使用可否を示すヒントです)。</span><span class="sxs-lookup"><span data-stu-id="7806e-117">This menu item has the same functionality as the watermark link in the left frame, meaning the user can start this action from either place (the watermark being a kind of usability hint).</span></span> <span data-ttu-id="7806e-118">このオプションは、BizTalk 管理データベースおよび BAM プライマリ インポート データベースに接続されているときは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7806e-118">This option is always available when there is a connection to the BizTalk Management database and BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="7806e-119">**終了**– TPE を終了します。</span><span class="sxs-lookup"><span data-stu-id="7806e-119">**Exit** – Exits the TPE.</span></span> <span data-ttu-id="7806e-120">編集中に終了しようとすると、Windows の標準機能によって、[保存] または [名前を付けて保存] が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-120">Exiting during an active edit invokes a Save or Save As per Windows standards.</span></span> <span data-ttu-id="7806e-121">このオプションは常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7806e-121">This option is always available.</span></span>  
  
### <a name="new-profile"></a><span data-ttu-id="7806e-122">[新しいプロファイル]</span><span class="sxs-lookup"><span data-stu-id="7806e-122">New Profile</span></span>  
 <span data-ttu-id="7806e-123">**新しいプロファイル**メニュー オプションは空白を表示する追跡プロファイルのソース ファイルで空の BTT ファイルに対してコンテンツなし (追跡プロファイル ファイル)。</span><span class="sxs-lookup"><span data-stu-id="7806e-123">The **New Profile** menu option opens a blank tracking profile source file with no contents against an empty BTT file (a tracking profile file).</span></span> <span data-ttu-id="7806e-124">新しいプロファイルの既定の名前は、TrackingProfile1 (2、3 など) です。</span><span class="sxs-lookup"><span data-stu-id="7806e-124">The default name of the new profile is TrackingProfile1 (…2, 3, etc.).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7806e-125">初期設定では、BizTalk の管理データベースは、BizTalk グループの既定の BizTalk 管理データベースに設定されています。</span><span class="sxs-lookup"><span data-stu-id="7806e-125">By default, the BizTalk Management database is set to the default BizTalk Management database of the BizTalk group.</span></span> <span data-ttu-id="7806e-126">管理データベースを変更するには、使用、**設定 Mgmt DB**  オプションを選択、**ツール**です。</span><span class="sxs-lookup"><span data-stu-id="7806e-126">To change the management database, use the **Set Mgmt DB** option on the **Tools**.</span></span> <span data-ttu-id="7806e-127">BizTalk 管理データベースの設定は、セッションが異なっても維持されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-127">The BizTalk Management database setting is retained between sessions.</span></span>  
  
### <a name="open"></a><span data-ttu-id="7806e-128">開く</span><span class="sxs-lookup"><span data-stu-id="7806e-128">Open</span></span>  
 <span data-ttu-id="7806e-129">**開く**メニュー オプションでは、ユーザーを検索して作業に使用する 1 つのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7806e-129">The **Open** menu option allows the user to locate and select a single profile with which to work.</span></span> <span data-ttu-id="7806e-130">プロファイルは、プロファイルの表示や検証を行うために作成されたアセンブリの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="7806e-130">Profiles are dependent on the assemblies they were created against being available in order to render and validate the profile.</span></span>  
  
 <span data-ttu-id="7806e-131">明示的に呼び出すオプションがあるか、元の展開済みのアセンブリが使用できなくプロファイルが関連付けられているアセンブリを変更する必要があります、**設定 Mgmt DB**をこのリンクを更新する操作。</span><span class="sxs-lookup"><span data-stu-id="7806e-131">If the original deployed assembly is no longer available or you need to change the assembly with which the profile is associated, you have the option of explicitly invoking the **Set Mgmt DB** action to refresh this link.</span></span> <span data-ttu-id="7806e-132">プロファイルを編集して適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7806e-132">You can also edit the profile and apply it.</span></span>  
  
### <a name="save"></a><span data-ttu-id="7806e-133">保存</span><span class="sxs-lookup"><span data-stu-id="7806e-133">Save</span></span>  
 <span data-ttu-id="7806e-134">**保存**オプションは、現在編集中の追跡プロファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7806e-134">The **Save** option saves the tracking profile currently being edited.</span></span> <span data-ttu-id="7806e-135">初めて新しい追跡プロファイルが呼び出されますで保存を選択、**名前を付けて保存**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="7806e-135">The first time Save is selected on new a tracking profile the option invokes the **Save As** dialog.</span></span>  
  
### <a name="save-as"></a><span data-ttu-id="7806e-136">[名前を付けて保存]</span><span class="sxs-lookup"><span data-stu-id="7806e-136">Save As</span></span>  
 <span data-ttu-id="7806e-137">**名前を付けて保存**オプションでは、フォルダーと追跡プロファイルの名前を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="7806e-137">The **Save As** option allows you to specify the folder and the name for the tracking profile.</span></span> <span data-ttu-id="7806e-138">追跡プロファイルのファイルが持つ既定の拡張子は .btt です。</span><span class="sxs-lookup"><span data-stu-id="7806e-138">The default extension for the tracking profile file is .btt.</span></span>  
  
### <a name="import-bam-activity-definition"></a><span data-ttu-id="7806e-139">[BAM アクティビティ定義のインポート]</span><span class="sxs-lookup"><span data-stu-id="7806e-139">Import BAM Activity Definition</span></span>  
 <span data-ttu-id="7806e-140">**BAM アクティビティ定義のインポート**オプションは、BAM プライマリ インポート データベースで見つかった BAM アクティビティ定義の一覧が設定されている BAM アクティビティ定義のインポート ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="7806e-140">The **Import BAM Activity Definition** option opens the Import BAM Activity Definition dialog box which is populated with a list of BAM activity definitions found in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="7806e-141">クリックしてこの機能が呼び出されますも**ここをクリックして、BAM アクティビティ定義のリンクをインポートする**追跡プロファイルの新しいアクティビティ ビューにします。</span><span class="sxs-lookup"><span data-stu-id="7806e-141">This feature is also invoked by clicking **Click here to import a BAM Activity Definition link** in the Activity View of a new tracking profile.</span></span>  
  
 <span data-ttu-id="7806e-142">**Existing Profile チェック ボックスを取得します。**</span><span class="sxs-lookup"><span data-stu-id="7806e-142">**Retrieve Existing Profile Check box**</span></span>  
  
 <span data-ttu-id="7806e-143">このチェック ボックスをオンにすると、既存の追跡プロファイルのアクティビティ定義のマッピングを抽出して取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="7806e-143">This check box allows you to extract and include existing tracking profile mappings for the activity definition.</span></span>  <span data-ttu-id="7806e-144">既定では、チェック ボックスが選択されていません。</span><span class="sxs-lookup"><span data-stu-id="7806e-144">The check box is not selected by default.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7806e-145">BAM アクティビティ定義がその定義の設定と共にインポートされるとき、既存のマッピングは、現在選択されている BizTalk 管理データベースのアセンブリ、オーケストレーション、スキーマ、およびポートに対して検証されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-145">When BAM activity definitions are imported with their tracking settings, existing mappings are validated against the assemblies, orchestrations, schemas, and ports in the currently selected BizTalk Management database.</span></span> <span data-ttu-id="7806e-146">マッピングがデータベースに対して無効である場合、無効なマッピングの横にエラー アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-146">If the mappings are invalid with respect to the database, an error icon appears next to the invalid mapping.</span></span> <span data-ttu-id="7806e-147">このようなインスタンスは、アセンブリの展開が解除される前に展開された追跡プロファイルであるか、BAM プライマリ インポート データベースが複数のグループおよび複数の BizTalk 管理データベースによって共有されている追跡プロファイルの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7806e-147">Instances where this could occur are a tracking profile that was deployed before an assembly was undeployed, or where the BAM Primary Import database is being shared by multiple groups and multiple BizTalk Management databases.</span></span> <span data-ttu-id="7806e-148">後者の場合、エラー アイコンは、追跡プロファイルが 1 つのグループから展開されて別のグループからインポートされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-148">In the latter case, the error icons appear if the tracking profile was deployed from one group and imported from another group.</span></span>  
  
### <a name="exit"></a><span data-ttu-id="7806e-149">終了する</span><span class="sxs-lookup"><span data-stu-id="7806e-149">Exit</span></span>  
 <span data-ttu-id="7806e-150">**終了**TPE を閉じます。</span><span class="sxs-lookup"><span data-stu-id="7806e-150">The **Exit** Option closes the TPE.</span></span> <span data-ttu-id="7806e-151">追跡プロファイルに変更が加えられている場合、追跡プロファイル エディターを閉じると、プロファイルの保存を確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-151">If there has been a modification to the tracking profile you are prompted to save the profile when the Tracking Profile Editor closes.</span></span>  
  
## <a name="tools-menu"></a><span data-ttu-id="7806e-152">[ツール] メニュー</span><span class="sxs-lookup"><span data-stu-id="7806e-152">Tools Menu</span></span>  
 <span data-ttu-id="7806e-153">[ツール] メニューには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7806e-153">The Tools menu contains the following options:</span></span>  
  
-   <span data-ttu-id="7806e-154">**追跡プロファイルの適用**– プロファイルを BAM プライマリ インポート データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="7806e-154">**Apply Tracking Profile** – Stores the profile in the BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="7806e-155">**追跡プロファイルの削除**– 追跡を削除、BAM プライマリ インポート データベースからのマッピングをプロファイルします。</span><span class="sxs-lookup"><span data-stu-id="7806e-155">**Remove Tracking Profile** – Removes the tracking profile mappings from the BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="7806e-156">**管理データベースの設定**– TPE での操作対象の管理データベースを設定します。</span><span class="sxs-lookup"><span data-stu-id="7806e-156">**Set Management Database** – Sets the management database that the TPE is working against.</span></span>  
  
-   <span data-ttu-id="7806e-157">**オプション**: TPE オプションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="7806e-157">**Options** – Allows you to set TPE options.</span></span>  
  
### <a name="apply-tracking-profile"></a><span data-ttu-id="7806e-158">[追跡プロファイルの適用]</span><span class="sxs-lookup"><span data-stu-id="7806e-158">Apply Tracking Profile</span></span>  
 <span data-ttu-id="7806e-159">**追跡プロファイルの適用**メニュー オプションが指定したアセンブリにも対応するオーケストレーションやポートへのマッピング、追跡プロファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7806e-159">The **Apply Tracking Profile** menu option stores the tracking profile mapping to the specified assembly as well as to the corresponding orchestrations and ports.</span></span> <span data-ttu-id="7806e-160">追跡プロファイルで参照されるすべてのアイテムは、指定した BizTalk 管理データベースで使用可能になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7806e-160">All the artifacts that are referred to in the tracking profile should be available in a specified BizTalk Management database.</span></span> <span data-ttu-id="7806e-161">関連するサービスのすべての新しいインスタンスでは、開始時に新しい追跡プロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-161">All new instances of the relevant services use the new tracking profile when starting.</span></span>  
  
 <span data-ttu-id="7806e-162">同時に複数のアセンブリに対して操作を行えます。</span><span class="sxs-lookup"><span data-stu-id="7806e-162">You can work against multiple assemblies at the same time.</span></span> <span data-ttu-id="7806e-163">複数のアセンブリの同時操作は行わない場合でも、1 つの任意の BAM アクティビティ定義に関連する 1 つの編集セッションで、複数のアセンブリにアクセスすることは可能です。</span><span class="sxs-lookup"><span data-stu-id="7806e-163">You do not work with the assemblies concurrently, but multiple assemblies can be accessed in a single editing session relative to any single BAM activity definition.</span></span>  <span data-ttu-id="7806e-164">つまり、BAM アクティビティ定義をインポートして、追跡対象の項目を描画する 3 つのアセンブリを選択する場合、TPE で作成されるプロファイルは、追跡プロファイルで使用されるオーケストレーションおよびポートに関連付けられた、複数のプロファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-164">In other words, if you import a BAM activity definition and then select three assemblies from which to draw tracked items, the profile that TPE creates is applied to multiple profiles that are associated with the orchestrations and ports that are used in the tracking profile.</span></span> <span data-ttu-id="7806e-165">追跡プロファイルには、指定した任意の BAM アクティビティ定義に関連付けられた、すべてのアセンブリに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7806e-165">The tracking profile always contains information about all assemblies associated with any given BAM activity definition.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7806e-166">BizTalk Server では、各 BAM アクティビティは追跡プロファイルを 1 つに対して展開のみを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="7806e-166">In BizTalk Server, each BAM activity can only have one tracking profile deployed against it.</span></span> <span data-ttu-id="7806e-167">つまり、あるオーケストレーションにマップされたアクティビティを含むプロファイルを展開してから、別のオーケストレーションにマップされた同じアクティビティを含む別のプロファイルを展開すると、最初に展開されたプロファイルが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="7806e-167">In other words, if you deploy a profile that has an activity mapped to an orchestration and later deploy a different profile that has the same activity mapped to a different orchestration, the first profile deployed is over written.</span></span>  
  
### <a name="remove-tracking-profile"></a><span data-ttu-id="7806e-168">[追跡プロファイルの削除]</span><span class="sxs-lookup"><span data-stu-id="7806e-168">Remove Tracking Profile</span></span>  
 <span data-ttu-id="7806e-169">**追跡プロファイルの削除**メニュー オプションは、読み込まれたアクティビティ定義とその対応するオーケストレーションとポートの追跡プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="7806e-169">The **Remove Tracking Profile** menu option removes the tracking profile for the loaded activity definition and its corresponding orchestrations and ports.</span></span> <span data-ttu-id="7806e-170">このアクションを完了する前に、確認のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-170">You are prompted for confirmation before this action is completed.</span></span>  
  
### <a name="set-management-database"></a><span data-ttu-id="7806e-171">管理データベースの設定</span><span class="sxs-lookup"><span data-stu-id="7806e-171">Set Management Database</span></span>  
 <span data-ttu-id="7806e-172">**管理データベースの設定**メニュー オプションは、マッピングからソースを選択することができますとなり、bam アクティビティ定義が見つかりましたが、BizTalk 管理データベースを指定します。</span><span class="sxs-lookup"><span data-stu-id="7806e-172">The **Set Management Database** menu option specifies the BizTalk Management database from which mapping sources can be chosen, and through which BAM activity definitions are found.</span></span> <span data-ttu-id="7806e-173">追跡プロファイルの初期設定では、構成時に指定した既定の BizTalk 管理データベースが設定されています。</span><span class="sxs-lookup"><span data-stu-id="7806e-173">By default, the tracking profile is set to the default BizTalk Management database specified during configuration.</span></span>  
  
 <span data-ttu-id="7806e-174">SQL 接続文字列は、2 つの方法のいずれかで指定できます。</span><span class="sxs-lookup"><span data-stu-id="7806e-174">SQL connection strings can be specified in one of two manners:</span></span>  
  
-   <span data-ttu-id="7806e-175">サーバー名のみを指定します。TPE は既定のポートに接続されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-175">You can specify just the server name, and the TPE will connect to the default port.</span></span>  
  
-   <span data-ttu-id="7806e-176">サーバー名とポートの組み合わせ、つまり、サーバー名とポート番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7806e-176">You can specify a server name and port pair, ServerName,port number.</span></span> <span data-ttu-id="7806e-177">TPE は、指定されたポートを使用する、SQL Server が実行されているコンピューターに接続されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-177">The TPE will connect to the computer running SQL Server that is using the specified port.</span></span>  
  
## <a name="help-menu"></a><span data-ttu-id="7806e-178">[ヘルプ] メニュー</span><span class="sxs-lookup"><span data-stu-id="7806e-178">Help Menu</span></span>  
 <span data-ttu-id="7806e-179">[ヘルプ] メニューには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7806e-179">The Help menu contains the following options:</span></span>  
  
-   <span data-ttu-id="7806e-180">**BizTalk Server ヘルプ**– BizTalk Server ヘルプ ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7806e-180">**BizTalk Server Help** – Opens the BizTalk Server Help file.</span></span>  
  
-   <span data-ttu-id="7806e-181">**追跡プロファイル エディター ヘルプ**– BizTalk Server のヘルプ ファイルの TPE に関するセクションを開きます。</span><span class="sxs-lookup"><span data-stu-id="7806e-181">**Tracking Profile Editor Help** – Opens the TPE section in the BizTalk Server Help file.</span></span>  
  
-   <span data-ttu-id="7806e-182">**BizTalk Server オンライン**-BizTalk Server のオンライン ヘルプを開きます。</span><span class="sxs-lookup"><span data-stu-id="7806e-182">**BizTalk Server Online** - Opens BizTalk Server Online Help.</span></span>  
  
-   <span data-ttu-id="7806e-183">**追跡プロファイル エディターについて**– 標準のバージョン情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7806e-183">**About Tracking Profile Editor** – Displays the standard About information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7806e-184">参照</span><span class="sxs-lookup"><span data-stu-id="7806e-184">See Also</span></span>  
 <span data-ttu-id="7806e-185">[TPE のコンポーネント](../core/components-of-the-tpe.md) </span><span class="sxs-lookup"><span data-stu-id="7806e-185">[Components of the TPE](../core/components-of-the-tpe.md) </span></span>  
 [<span data-ttu-id="7806e-186">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="7806e-186">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)
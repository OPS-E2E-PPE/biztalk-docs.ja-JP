---
title: 管理コマンドの表示 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f25ee3-9bb3-4682-a9ff-cac8c25f58c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ced7a9ac58fa0375e3eaefa49832e6c23ba1a73
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975176"
---
# <a name="view-management-commands"></a><span data-ttu-id="c87e5-102">ビュー管理コマンド</span><span class="sxs-lookup"><span data-stu-id="c87e5-102">View Management Commands</span></span>
<span data-ttu-id="c87e5-103">BAM 管理ユーティリティのビュー管理コマンドを使用すると、展開済みのビューを操作できます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-103">The BAM Management utility view management commands allow you to work with deployed views.</span></span>  
  
-   <span data-ttu-id="c87e5-104">get ビュー: すべての展開されたビューを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c87e5-104">get-views: Lists all the deployed views.</span></span>  
  
-   <span data-ttu-id="c87e5-105">削除ビュー: 展開されたビューを削除します。</span><span class="sxs-lookup"><span data-stu-id="c87e5-105">remove-view: Removes a deployed view.</span></span>  
  
-   <span data-ttu-id="c87e5-106">get rtawindow: ビューの期間を取得します。</span><span class="sxs-lookup"><span data-stu-id="c87e5-106">get-rtawindow: Gets the duration on a view.</span></span>  
  
-   <span data-ttu-id="c87e5-107">セット rtawindow: ビューの期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="c87e5-107">set-rtawindow: Sets the duration on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c87e5-108">含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="c87e5-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="c87e5-109">Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="c87e5-110">このスイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c87e5-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c87e5-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-views-command"></a><span data-ttu-id="c87e5-112">get-views コマンド</span><span class="sxs-lookup"><span data-stu-id="c87e5-112">get-views Command</span></span>  
 <span data-ttu-id="c87e5-113">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c87e5-113">**Usage**</span></span>  
  
 <span data-ttu-id="c87e5-114">**bm.exe get ビュー [-アクティビティ:\<アクティビティ名\>] [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="c87e5-114">**bm.exe get-views [ -Activity:\<activity name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c87e5-115">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c87e5-115">**Parameters**</span></span>  
  
|<span data-ttu-id="c87e5-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c87e5-116">Parameter</span></span>|<span data-ttu-id="c87e5-117">Description</span><span class="sxs-lookup"><span data-stu-id="c87e5-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c87e5-118">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="c87e5-118">Activity:\<activity name\></span></span>|<span data-ttu-id="c87e5-119">ビューを一覧表示するアクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="c87e5-119">The name of the activity from which to list the views.</span></span>|  
|<span data-ttu-id="c87e5-120">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c87e5-120">Server:\<server\></span></span>|<span data-ttu-id="c87e5-121">省略可能: ビューの一覧を取得するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c87e5-121">Optional: The name of the server from which to get the list of views.</span></span> <span data-ttu-id="c87e5-122">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c87e5-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c87e5-123">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c87e5-124">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c87e5-124">Database:\<database\></span></span>|<span data-ttu-id="c87e5-125">省略可能: ビューの一覧の取得元のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c87e5-125">Optional: The name of the database from which to get the list of views.</span></span> <span data-ttu-id="c87e5-126">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c87e5-127">コマンドを実行するコンピューターに展開されているビューを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c87e5-127">Lists the views deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="c87e5-128">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c87e5-128">**Examples**</span></span>  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a><span data-ttu-id="c87e5-129">remove-view コマンド</span><span class="sxs-lookup"><span data-stu-id="c87e5-129">remove-view Command</span></span>  
 <span data-ttu-id="c87e5-130">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c87e5-130">**Usage**</span></span>  
  
 <span data-ttu-id="c87e5-131">**bm.exe 削除ビューの名前:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="c87e5-131">**bm.exe remove-view -Name:\<view name\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c87e5-132">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c87e5-132">**Parameters**</span></span>  
  
|<span data-ttu-id="c87e5-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c87e5-133">Parameter</span></span>|<span data-ttu-id="c87e5-134">Description</span><span class="sxs-lookup"><span data-stu-id="c87e5-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c87e5-135">[名前]:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="c87e5-135">Name:\<view name\></span></span>|<span data-ttu-id="c87e5-136">削除するビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="c87e5-136">The name of the view to remove.</span></span>|  
|<span data-ttu-id="c87e5-137">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c87e5-137">Server:\<server\></span></span>|<span data-ttu-id="c87e5-138">省略可能: ビューを削除するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c87e5-138">Optional: The name of the server from which to remove the view.</span></span> <span data-ttu-id="c87e5-139">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c87e5-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c87e5-140">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c87e5-141">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c87e5-141">Database:\<database\></span></span>|<span data-ttu-id="c87e5-142">省略可能: ビューを削除するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c87e5-142">Optional: The name of the database from which to remove the view.</span></span> <span data-ttu-id="c87e5-143">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c87e5-144">指定されたビューを BAM プライマリ インポート データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="c87e5-144">Removes the specified view from the BAM Primary Import database.</span></span> <span data-ttu-id="c87e5-145">そのビューに依存する警告が存在する場合、これらの警告も同時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-145">If the view has dependent alerts, they are removed at the same time.</span></span>  
  
 <span data-ttu-id="c87e5-146">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c87e5-146">**Examples**</span></span>  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a><span data-ttu-id="c87e5-147">get-rtawindow コマンド</span><span class="sxs-lookup"><span data-stu-id="c87e5-147">get-rtawindow Command</span></span>  
 <span data-ttu-id="c87e5-148">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c87e5-148">**Usage**</span></span>  
  
 <span data-ttu-id="c87e5-149">**bm.exe get rtawindow-ビュー:\<ビュー名\>-アクティビティ:\<アクティビティ名\>Rta:\<RTA 名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="c87e5-149">**bm.exe get-rtawindow -View:\<view name\> -Activity:\<activity name\> -Rta:\<RTA name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c87e5-150">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c87e5-150">**Parameters**</span></span>  
  
|<span data-ttu-id="c87e5-151">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c87e5-151">Parameter</span></span>|<span data-ttu-id="c87e5-152">Description</span><span class="sxs-lookup"><span data-stu-id="c87e5-152">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c87e5-153">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="c87e5-153">View:\<view name\></span></span>|<span data-ttu-id="c87e5-154">ビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="c87e5-154">The view name.</span></span>|  
|<span data-ttu-id="c87e5-155">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="c87e5-155">Activity:\<activity name\></span></span>|<span data-ttu-id="c87e5-156">アクティビティ名。</span><span class="sxs-lookup"><span data-stu-id="c87e5-156">The activity name.</span></span>|  
|<span data-ttu-id="c87e5-157">Rta:\<RTA 名\></span><span class="sxs-lookup"><span data-stu-id="c87e5-157">Rta:\<RTA name\></span></span>|<span data-ttu-id="c87e5-158">リアルタイム集計の名前です。</span><span class="sxs-lookup"><span data-stu-id="c87e5-158">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="c87e5-159">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c87e5-159">Server:\<server\></span></span>|<span data-ttu-id="c87e5-160">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c87e5-160">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="c87e5-161">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c87e5-161">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c87e5-162">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-162">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c87e5-163">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c87e5-163">Database:\<database\></span></span>|<span data-ttu-id="c87e5-164">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c87e5-164">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="c87e5-165">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-165">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c87e5-166">指定されたリアルタイム集計の期間を表示します。</span><span class="sxs-lookup"><span data-stu-id="c87e5-166">Displays the duration of the specified real-time aggregation.</span></span> <span data-ttu-id="c87e5-167">このコマンドにより、期間の長さと、その期間の基準となる単位が返されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-167">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="c87e5-168">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c87e5-168">**Examples**</span></span>  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a><span data-ttu-id="c87e5-169">set-rtawindow コマンド</span><span class="sxs-lookup"><span data-stu-id="c87e5-169">set-rtawindow Command</span></span>  
 <span data-ttu-id="c87e5-170">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c87e5-170">**Usage**</span></span>  
  
 <span data-ttu-id="c87e5-171">**bm.exe セット rtawindow-ビュー:\<ビュー名\>-アクティビティ:\<アクティビティ名\>-名前:\<RTA 名\>- TimeLength:\<整数\>-TimeUnit:Day &#124;です。1 時間 &#124;です。分 [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="c87e5-171">**bm.exe set-rtawindow -View:\<view name\> -Activity:\<activity name\> -Name:\<RTA name\> -TimeLength:\<integer number\>-TimeUnit:Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c87e5-172">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c87e5-172">**Parameters**</span></span>  
  
|<span data-ttu-id="c87e5-173">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c87e5-173">Parameter</span></span>|<span data-ttu-id="c87e5-174">Description</span><span class="sxs-lookup"><span data-stu-id="c87e5-174">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c87e5-175">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="c87e5-175">View:\<view name\></span></span>|<span data-ttu-id="c87e5-176">ビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="c87e5-176">The view name.</span></span>|  
|<span data-ttu-id="c87e5-177">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="c87e5-177">Activity:\<activity name\></span></span>|<span data-ttu-id="c87e5-178">アクティビティ名。</span><span class="sxs-lookup"><span data-stu-id="c87e5-178">The activity name.</span></span>|  
|<span data-ttu-id="c87e5-179">[名前]:\<RTA 名\></span><span class="sxs-lookup"><span data-stu-id="c87e5-179">Name:\<RTA name\></span></span>|<span data-ttu-id="c87e5-180">リアルタイム集計の名前です。</span><span class="sxs-lookup"><span data-stu-id="c87e5-180">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="c87e5-181">TimeLength:\<整数\></span><span class="sxs-lookup"><span data-stu-id="c87e5-181">TimeLength:\<integer number\></span></span>|<span data-ttu-id="c87e5-182">リアルタイム集計の期間です。</span><span class="sxs-lookup"><span data-stu-id="c87e5-182">The duration for the real-time aggregation.</span></span>|  
|<span data-ttu-id="c87e5-183">TimeUnit:Month &#124; 日付 &#124;です。1 時間 &#124;です。1 分</span><span class="sxs-lookup"><span data-stu-id="c87e5-183">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="c87e5-184">期間の単位です。</span><span class="sxs-lookup"><span data-stu-id="c87e5-184">The unit measure for the window duration.</span></span>|  
|<span data-ttu-id="c87e5-185">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c87e5-185">Server:\<server\></span></span>|<span data-ttu-id="c87e5-186">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c87e5-186">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="c87e5-187">サーバーは、bm.exe を実行しているコンピューターと同じドメインにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c87e5-187">The server must be in the same domain as the machine from which you are running bm.exe.</span></span> <span data-ttu-id="c87e5-188">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-188">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c87e5-189">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c87e5-189">Database:\<database\></span></span>|<span data-ttu-id="c87e5-190">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c87e5-190">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="c87e5-191">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c87e5-191">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c87e5-192">指定されたリアルタイム集計の期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="c87e5-192">Sets the duration for the specified real-time aggregation.</span></span>  
  
 <span data-ttu-id="c87e5-193">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c87e5-193">**Examples**</span></span>  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a><span data-ttu-id="c87e5-194">参照</span><span class="sxs-lookup"><span data-stu-id="c87e5-194">See Also</span></span>  
 [<span data-ttu-id="c87e5-195">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="c87e5-195">BAM Management Utility</span></span>](../core/bam-management-utility.md)
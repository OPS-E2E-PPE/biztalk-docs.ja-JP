---
title: 管理コマンドの表示 |Microsoft Docs
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
ms.openlocfilehash: fbd91cf632b655fe3c2cb535f2ee4db3c889688d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243250"
---
# <a name="view-management-commands"></a><span data-ttu-id="cf026-102">ビュー管理コマンド</span><span class="sxs-lookup"><span data-stu-id="cf026-102">View Management Commands</span></span>
<span data-ttu-id="cf026-103">BAM 管理ユーティリティのビュー管理コマンドを使用すると、展開されているビューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf026-103">The BAM Management utility view management commands allow you to work with deployed views.</span></span>  
  
-   <span data-ttu-id="cf026-104">get ビュー:展開されているすべてのビューを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cf026-104">get-views: Lists all the deployed views.</span></span>  
  
-   <span data-ttu-id="cf026-105">削除ビュー:ビューが展開を削除します。</span><span class="sxs-lookup"><span data-stu-id="cf026-105">remove-view: Removes a deployed view.</span></span>  
  
-   <span data-ttu-id="cf026-106">get-rtawindow プロパティ:ビューの期間を取得します。</span><span class="sxs-lookup"><span data-stu-id="cf026-106">get-rtawindow: Gets the duration on a view.</span></span>  
  
-   <span data-ttu-id="cf026-107">セット-rtawindow プロパティ:ビューの期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="cf026-107">set-rtawindow: Sets the duration on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf026-108">含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="cf026-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="cf026-109">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="cf026-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="cf026-110">スイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf026-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf026-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf026-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-views-command"></a><span data-ttu-id="cf026-112">get-views コマンド</span><span class="sxs-lookup"><span data-stu-id="cf026-112">get-views Command</span></span>  
 <span data-ttu-id="cf026-113">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="cf026-113">**Usage**</span></span>  
  
 <span data-ttu-id="cf026-114">**bm.exe の get ビュー [-アクティビティ:\<アクティビティ名\>] [-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="cf026-114">**bm.exe get-views [ -Activity:\<activity name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="cf026-115">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="cf026-115">**Parameters**</span></span>  
  
|<span data-ttu-id="cf026-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf026-116">Parameter</span></span>|<span data-ttu-id="cf026-117">説明</span><span class="sxs-lookup"><span data-stu-id="cf026-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf026-118">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="cf026-118">Activity:\<activity name\></span></span>|<span data-ttu-id="cf026-119">ビューを一覧表示するアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-119">The name of the activity from which to list the views.</span></span>|  
|<span data-ttu-id="cf026-120">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="cf026-120">Server:\<server\></span></span>|<span data-ttu-id="cf026-121">省略可能:ビューの一覧の取得元のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-121">Optional: The name of the server from which to get the list of views.</span></span> <span data-ttu-id="cf026-122">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf026-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="cf026-123">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="cf026-124">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="cf026-124">Database:\<database\></span></span>|<span data-ttu-id="cf026-125">省略可能:ビューの一覧の取得元のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-125">Optional: The name of the database from which to get the list of views.</span></span> <span data-ttu-id="cf026-126">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="cf026-127">コマンドを実行するコンピューターに展開されたビューを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cf026-127">Lists the views deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="cf026-128">**使用例**</span><span class="sxs-lookup"><span data-stu-id="cf026-128">**Examples**</span></span>  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a><span data-ttu-id="cf026-129">remove-view コマンド</span><span class="sxs-lookup"><span data-stu-id="cf026-129">remove-view Command</span></span>  
 <span data-ttu-id="cf026-130">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="cf026-130">**Usage**</span></span>  
  
 <span data-ttu-id="cf026-131">**bm.exe remove-view -Name:\<view name\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="cf026-131">**bm.exe remove-view -Name:\<view name\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="cf026-132">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="cf026-132">**Parameters**</span></span>  
  
|<span data-ttu-id="cf026-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf026-133">Parameter</span></span>|<span data-ttu-id="cf026-134">説明</span><span class="sxs-lookup"><span data-stu-id="cf026-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf026-135">名前:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="cf026-135">Name:\<view name\></span></span>|<span data-ttu-id="cf026-136">削除するビューの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-136">The name of the view to remove.</span></span>|  
|<span data-ttu-id="cf026-137">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="cf026-137">Server:\<server\></span></span>|<span data-ttu-id="cf026-138">省略可能:元のビューを削除するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-138">Optional: The name of the server from which to remove the view.</span></span> <span data-ttu-id="cf026-139">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf026-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="cf026-140">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="cf026-141">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="cf026-141">Database:\<database\></span></span>|<span data-ttu-id="cf026-142">省略可能:元のビューを削除するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-142">Optional: The name of the database from which to remove the view.</span></span> <span data-ttu-id="cf026-143">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="cf026-144">BAM プライマリ インポート データベースから、指定されたビューを削除します。</span><span class="sxs-lookup"><span data-stu-id="cf026-144">Removes the specified view from the BAM Primary Import database.</span></span> <span data-ttu-id="cf026-145">ビューに依存するアラートがある場合は、同時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-145">If the view has dependent alerts, they are removed at the same time.</span></span>  
  
 <span data-ttu-id="cf026-146">**使用例**</span><span class="sxs-lookup"><span data-stu-id="cf026-146">**Examples**</span></span>  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a><span data-ttu-id="cf026-147">get-rtawindow コマンド</span><span class="sxs-lookup"><span data-stu-id="cf026-147">get-rtawindow Command</span></span>  
 <span data-ttu-id="cf026-148">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="cf026-148">**Usage**</span></span>  
  
 <span data-ttu-id="cf026-149">**bm.exe の get rtawindow プロパティの表示:\<ビュー名\>-アクティビティ:\<アクティビティ名\>Rta:\<RTA 名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="cf026-149">**bm.exe get-rtawindow -View:\<view name\> -Activity:\<activity name\> -Rta:\<RTA name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="cf026-150">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="cf026-150">**Parameters**</span></span>  
  
|<span data-ttu-id="cf026-151">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf026-151">Parameter</span></span>|<span data-ttu-id="cf026-152">説明</span><span class="sxs-lookup"><span data-stu-id="cf026-152">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf026-153">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="cf026-153">View:\<view name\></span></span>|<span data-ttu-id="cf026-154">ビューの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-154">The view name.</span></span>|  
|<span data-ttu-id="cf026-155">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="cf026-155">Activity:\<activity name\></span></span>|<span data-ttu-id="cf026-156">アクティビティ名。</span><span class="sxs-lookup"><span data-stu-id="cf026-156">The activity name.</span></span>|  
|<span data-ttu-id="cf026-157">Rta:\<RTA 名\></span><span class="sxs-lookup"><span data-stu-id="cf026-157">Rta:\<RTA name\></span></span>|<span data-ttu-id="cf026-158">リアルタイム集計の名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-158">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="cf026-159">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="cf026-159">Server:\<server\></span></span>|<span data-ttu-id="cf026-160">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-160">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="cf026-161">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf026-161">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="cf026-162">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-162">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="cf026-163">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="cf026-163">Database:\<database\></span></span>|<span data-ttu-id="cf026-164">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-164">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="cf026-165">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-165">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="cf026-166">指定されたリアルタイム集計の期間を表示します。</span><span class="sxs-lookup"><span data-stu-id="cf026-166">Displays the duration of the specified real-time aggregation.</span></span> <span data-ttu-id="cf026-167">コマンドは、期間と期間の測定単位の長さを返します。</span><span class="sxs-lookup"><span data-stu-id="cf026-167">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="cf026-168">**使用例**</span><span class="sxs-lookup"><span data-stu-id="cf026-168">**Examples**</span></span>  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a><span data-ttu-id="cf026-169">set-rtawindow コマンド</span><span class="sxs-lookup"><span data-stu-id="cf026-169">set-rtawindow Command</span></span>  
 <span data-ttu-id="cf026-170">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="cf026-170">**Usage**</span></span>  
  
 <span data-ttu-id="cf026-171">**bm.exe セット-rtawindow プロパティのビュー:\<ビュー名\>-アクティビティ:\<アクティビティ名\>-名前:\<RTA 名\>- TimeLength:\<整数\>-TimeUnit: Day&#124;時間&#124;分 [-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="cf026-171">**bm.exe set-rtawindow -View:\<view name\> -Activity:\<activity name\> -Name:\<RTA name\> -TimeLength:\<integer number\>-TimeUnit:Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="cf026-172">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="cf026-172">**Parameters**</span></span>  
  
|<span data-ttu-id="cf026-173">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf026-173">Parameter</span></span>|<span data-ttu-id="cf026-174">説明</span><span class="sxs-lookup"><span data-stu-id="cf026-174">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf026-175">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="cf026-175">View:\<view name\></span></span>|<span data-ttu-id="cf026-176">ビューの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-176">The view name.</span></span>|  
|<span data-ttu-id="cf026-177">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="cf026-177">Activity:\<activity name\></span></span>|<span data-ttu-id="cf026-178">アクティビティ名。</span><span class="sxs-lookup"><span data-stu-id="cf026-178">The activity name.</span></span>|  
|<span data-ttu-id="cf026-179">名前:\<RTA 名\></span><span class="sxs-lookup"><span data-stu-id="cf026-179">Name:\<RTA name\></span></span>|<span data-ttu-id="cf026-180">リアルタイム集計の名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-180">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="cf026-181">TimeLength:\<整数\></span><span class="sxs-lookup"><span data-stu-id="cf026-181">TimeLength:\<integer number\></span></span>|<span data-ttu-id="cf026-182">リアルタイム集計の期間です。</span><span class="sxs-lookup"><span data-stu-id="cf026-182">The duration for the real-time aggregation.</span></span>|  
|<span data-ttu-id="cf026-183">TimeUnit:Month&#124;日&#124;時間&#124;分</span><span class="sxs-lookup"><span data-stu-id="cf026-183">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="cf026-184">期間の単位。</span><span class="sxs-lookup"><span data-stu-id="cf026-184">The unit measure for the window duration.</span></span>|  
|<span data-ttu-id="cf026-185">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="cf026-185">Server:\<server\></span></span>|<span data-ttu-id="cf026-186">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-186">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="cf026-187">Bm.exe の実行元となるマシンと同じドメインで、サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="cf026-187">The server must be in the same domain as the machine from which you are running bm.exe.</span></span> <span data-ttu-id="cf026-188">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-188">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="cf026-189">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="cf026-189">Database:\<database\></span></span>|<span data-ttu-id="cf026-190">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="cf026-190">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="cf026-191">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf026-191">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="cf026-192">指定されたリアルタイム集計の期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="cf026-192">Sets the duration for the specified real-time aggregation.</span></span>  
  
 <span data-ttu-id="cf026-193">**使用例**</span><span class="sxs-lookup"><span data-stu-id="cf026-193">**Examples**</span></span>  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf026-194">参照</span><span class="sxs-lookup"><span data-stu-id="cf026-194">See Also</span></span>  
 [<span data-ttu-id="cf026-195">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="cf026-195">BAM Management Utility</span></span>](../core/bam-management-utility.md)
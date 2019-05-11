---
title: アクティビティ管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dc32b005d0a6492fbdce87a1149c23c5a13442e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361674"
---
# <a name="activity-management-commands"></a><span data-ttu-id="15ffd-102">アクティビティ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-102">Activity Management Commands</span></span>
<span data-ttu-id="15ffd-103">BAM 管理ユーティリティのアクティビティ管理コマンドを使用すると、展開済みのアクティビティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-103">The BAM Management utility activity management commands allow you to work with deployed activities.</span></span>  
  
-   <span data-ttu-id="15ffd-104">get アクティビティ:展開済みアクティビティの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-104">get-activities: Gets a list of deployed activities.</span></span>  
  
-   <span data-ttu-id="15ffd-105">削除アクティビティ:アクティビティを削除します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-105">remove-activity: Removes an activity.</span></span>  
  
-   <span data-ttu-id="15ffd-106">get activitywindow:アクティビティの期間を取得します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-106">get-activitywindow: Gets the duration for an activity.</span></span>  
  
-   <span data-ttu-id="15ffd-107">セット activitywindow:アクティビティのアクティビティ期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-107">set-activitywindow: Sets the activity duration for an activity.</span></span>  
  
-   <span data-ttu-id="15ffd-108">get インデックス:インデックスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-108">get-index: Gets the list of indexes.</span></span>  
  
-   <span data-ttu-id="15ffd-109">インデックスの作成:新しいインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-109">create-index: Creates a new index.</span></span>  
  
-   <span data-ttu-id="15ffd-110">-インデックスを削除します。インデックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-110">delete-index: Deletes an index.</span></span>  
  
-   <span data-ttu-id="15ffd-111">get アーカイブ:アーカイブ済みアクティビティの動作を取得します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-111">get-archive: Gets the behavior of archived activity.</span></span>  
  
-   <span data-ttu-id="15ffd-112">セット-アーカイブ:アーカイブ済みアクティビティの動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-112">set-archive: Sets the behavior of archived activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15ffd-113">含めることによって任意の BAM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="15ffd-113">You can enable tracing on any BAM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="15ffd-114">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-114">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="15ffd-115">スイッチは、通常の BAM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-115">The switch can be used in conjunction with any normal BAM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15ffd-116">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-activities-command"></a><span data-ttu-id="15ffd-117">get-activities コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-117">get-activities Command</span></span>  
 <span data-ttu-id="15ffd-118">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-118">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-119">**bm.exe の取得活動 [-ビュー:\<ビュー名\>] [-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-119">**bm.exe get-activities [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="15ffd-120">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-120">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-121">Parameter</span></span>|<span data-ttu-id="15ffd-122">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-123">名前:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-123">Name:\<activity name\></span></span>|<span data-ttu-id="15ffd-124">削除するアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-124">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="15ffd-125">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-125">Server:\<server\></span></span>|<span data-ttu-id="15ffd-126">省略可能:アクティビティの一覧の取得元のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-126">Optional: The name of the server from which to get the list of activities.</span></span> <span data-ttu-id="15ffd-127">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-127">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-128">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-128">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-129">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-129">Database:\<database\></span></span>|<span data-ttu-id="15ffd-130">省略可能:アクティビティの一覧の取得元のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-130">Optional: The name of the database from which to get the list of activities.</span></span> <span data-ttu-id="15ffd-131">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-131">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-132">コマンドを実行するコンピューターに展開されているアクティビティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-132">Lists the activities deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="15ffd-133">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-133">**Examples**</span></span>  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a><span data-ttu-id="15ffd-134">remove-activity コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-134">remove-activity Command</span></span>  
 <span data-ttu-id="15ffd-135">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-135">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-136">**bm.exe remove-activity -Name:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-136">**bm.exe remove-activity -Name:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="15ffd-137">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-137">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-138">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-138">Parameter</span></span>|<span data-ttu-id="15ffd-139">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-139">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-140">名前:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-140">Name:\<activity name\></span></span>|<span data-ttu-id="15ffd-141">削除するアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-141">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="15ffd-142">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-142">Server:\<server\></span></span>|<span data-ttu-id="15ffd-143">省略可能:元のアクティビティを削除するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-143">Optional: The name of the server from which to remove the activity.</span></span> <span data-ttu-id="15ffd-144">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-144">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-145">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-145">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-146">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-146">Database:\<database\></span></span>|<span data-ttu-id="15ffd-147">省略可能:元のアクティビティを削除するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-147">Optional: The name of the database from which to remove the activity.</span></span> <span data-ttu-id="15ffd-148">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-148">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-149">指定したアクティビティを BAM プライマリ インポート データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-149">Removes the specified activity from the BAM Primary Import database.</span></span> <span data-ttu-id="15ffd-150">アクティビティに依存するビューがある場合は、コマンドが失敗し、エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-150">If the activity has dependent views, the command will fail and report an error.</span></span> <span data-ttu-id="15ffd-151">Remove-view コマンドを使用して、依存するすべてのビューを削除し、remove-activity コマンドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-151">Use the remove-view command to remove all the dependent views and execute the remove-activity command again.</span></span>  
  
 <span data-ttu-id="15ffd-152">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-152">**Examples**</span></span>  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a><span data-ttu-id="15ffd-153">get-activitywindow コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-153">get-activitywindow Command</span></span>  
 <span data-ttu-id="15ffd-154">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-154">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-155">**bm.exe の get activitywindow-アクティビティ:\<アクティビティ名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-155">**bm.exe get-activitywindow -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="15ffd-156">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-156">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-157">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-157">Parameter</span></span>|<span data-ttu-id="15ffd-158">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-158">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-159">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-159">Activity:\<activity name\></span></span>|<span data-ttu-id="15ffd-160">.Activity の名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-160">The name of the .activity.</span></span>|  
|<span data-ttu-id="15ffd-161">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-161">Server:\<server\></span></span>|<span data-ttu-id="15ffd-162">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-162">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="15ffd-163">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-163">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-164">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-164">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-165">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-165">Database:\<database\></span></span>|<span data-ttu-id="15ffd-166">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-166">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="15ffd-167">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-167">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-168">指定されたアクティビティの期間を表示します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-168">Displays the duration for the specified activity.</span></span> <span data-ttu-id="15ffd-169">コマンドは、期間と期間の測定単位の長さを返します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-169">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="15ffd-170">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-170">**Examples**</span></span>  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a><span data-ttu-id="15ffd-171">set-activitywindow コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-171">set-activitywindow Command</span></span>  
 <span data-ttu-id="15ffd-172">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-172">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-173">**bm.exe のセット activitywindow-アクティビティ:\<アクティビティ名\>- TimeLength:\<整数\>- TimeUnit: 月&#124;日&#124;時間&#124;分 [-サーバー:\<server\> ][-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-173">**bm.exe set-activitywindow -Activity:\<activity name\> -TimeLength:\<integer number\> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="15ffd-174">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-174">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-175">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-175">Parameter</span></span>|<span data-ttu-id="15ffd-176">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-176">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-177">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-177">Activity:\<activity name\></span></span>|<span data-ttu-id="15ffd-178">アクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-178">The name of the activity.</span></span>|  
|<span data-ttu-id="15ffd-179">TimeLength:\<整数\></span><span class="sxs-lookup"><span data-stu-id="15ffd-179">TimeLength:\<integer number\></span></span>|<span data-ttu-id="15ffd-180">アクティビティの期間です。</span><span class="sxs-lookup"><span data-stu-id="15ffd-180">The duration for the activity.</span></span>|  
|<span data-ttu-id="15ffd-181">TimeUnit:Month&#124;日&#124;時間&#124;分</span><span class="sxs-lookup"><span data-stu-id="15ffd-181">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="15ffd-182">期間の単位。</span><span class="sxs-lookup"><span data-stu-id="15ffd-182">The unit measure for the duration.</span></span>|  
|<span data-ttu-id="15ffd-183">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-183">Server:\<server\></span></span>|<span data-ttu-id="15ffd-184">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-184">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="15ffd-185">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-186">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-186">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-187">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-187">Database:\<database\></span></span>|<span data-ttu-id="15ffd-188">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-188">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="15ffd-189">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-189">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-190">指定したアクティビティの期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-190">Sets the duration for the specified activity.</span></span>  
  
 <span data-ttu-id="15ffd-191">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-191">**Examples**</span></span>  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a><span data-ttu-id="15ffd-192">get-index コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-192">get-index Command</span></span>  
 <span data-ttu-id="15ffd-193">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-193">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-194">**bm.exe の get インデックス-アクティビティ:\<アクティビティ名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-194">**bm.exe get-index -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="15ffd-195">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-195">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-196">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-196">Parameter</span></span>|<span data-ttu-id="15ffd-197">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-197">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-198">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-198">Activity:\<activity name\></span></span>|<span data-ttu-id="15ffd-199">アクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-199">The name of the activity.</span></span>|  
|<span data-ttu-id="15ffd-200">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-200">Server:\<server\></span></span>|<span data-ttu-id="15ffd-201">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-201">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="15ffd-202">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-202">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-203">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-203">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-204">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-204">Database:\<database\></span></span>|<span data-ttu-id="15ffd-205">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-205">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="15ffd-206">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-206">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-207">指定したアクティビティ用に作成されたすべてのインデックスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-207">Lists all the indexes that have been created for the specified activity.</span></span>  
  
 <span data-ttu-id="15ffd-208">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-208">**Examples**</span></span>  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a><span data-ttu-id="15ffd-209">create index コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-209">create-index Command</span></span>  
 <span data-ttu-id="15ffd-210">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-210">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-211">**bm.exe インデックスの作成-indexname:\<インデックス名\>-アクティビティ:\<アクティビティ名\>-チェックポイント:\<チェックポイント 1\>[、\<チェックポイント 2\>...][-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-211">**bm.exe create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="15ffd-212">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-212">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-213">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-213">Parameter</span></span>|<span data-ttu-id="15ffd-214">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-214">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-215">IndexName:\<インデックス名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-215">IndexName:\<index name\></span></span>|<span data-ttu-id="15ffd-216">新しいインデックスの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-216">The name of the new index.</span></span>|  
|<span data-ttu-id="15ffd-217">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-217">Activity:\<activity name\></span></span>|<span data-ttu-id="15ffd-218">インデックスを作成するアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-218">The name of the activity for which the index is created.</span></span>|  
|<span data-ttu-id="15ffd-219">チェックポイント:\<チェックポイント 1\>[、\<チェックポイント 2\>...]</span><span class="sxs-lookup"><span data-stu-id="15ffd-219">Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...]</span></span>|<span data-ttu-id="15ffd-220">インデックスのチェックポイントのコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="15ffd-220">A comma-delimited list of checkpoints for the index.</span></span>|  
|<span data-ttu-id="15ffd-221">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-221">Server:\<server\></span></span>|<span data-ttu-id="15ffd-222">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-222">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="15ffd-223">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-223">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-224">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-224">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-225">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-225">Database:\<database\></span></span>|<span data-ttu-id="15ffd-226">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-226">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="15ffd-227">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-227">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-228">指定したチェックポイントを使用して、指定したアクティビティのインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-228">Creates an index for the specified activity using the specified checkpoints.</span></span>  
  
 <span data-ttu-id="15ffd-229">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-229">**Examples**</span></span>  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a><span data-ttu-id="15ffd-230">delete-index コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-230">delete-index Command</span></span>  
 <span data-ttu-id="15ffd-231">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-231">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-232">**bm.exe インデックスを削除-indexname:\<インデックス名\>-アクティビティ:\<アクティビティ名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-232">**bm.exe delete-index -IndexName:\<index name\> -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="15ffd-233">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-233">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-234">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-234">Parameter</span></span>|<span data-ttu-id="15ffd-235">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-235">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-236">IndexName:\<インデックス名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-236">IndexName:\<index name\></span></span>|<span data-ttu-id="15ffd-237">削除するインデックスの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-237">The name of the index to delete.</span></span>|  
|<span data-ttu-id="15ffd-238">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-238">Activity:\<activity name\></span></span>|<span data-ttu-id="15ffd-239">インデックスが削除されるアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-239">The name of the activity for which the index is deleted.</span></span>|  
|<span data-ttu-id="15ffd-240">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-240">Server:\<server\></span></span>|<span data-ttu-id="15ffd-241">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-241">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="15ffd-242">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-242">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-243">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-243">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-244">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-244">Database:\<database\></span></span>|<span data-ttu-id="15ffd-245">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-245">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="15ffd-246">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-246">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-247">指定したアクティビティから、指定した名前の指定したインデックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-247">Deletes the specified index with the given name from the specified activity.</span></span>  
  
 <span data-ttu-id="15ffd-248">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-248">**Examples**</span></span>  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="15ffd-249">set-archive コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-249">set-archive Command</span></span>  
 <span data-ttu-id="15ffd-250">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-250">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-251">**bm.exe get-archive -Activity:\<activity\> [-Server:\<server\>] [-Database:\<database\>]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-251">**bm.exe get-archive -Activity:\<activity\> [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="15ffd-252">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-252">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-253">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-253">Parameter</span></span>|<span data-ttu-id="15ffd-254">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-254">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-255">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-255">Activity:\<activity name\></span></span>|<span data-ttu-id="15ffd-256">動作を表示するアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-256">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="15ffd-257">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-257">Server:\<server\></span></span>|<span data-ttu-id="15ffd-258">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-258">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="15ffd-259">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-259">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-260">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-260">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-261">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-261">Database:\<database\></span></span>|<span data-ttu-id="15ffd-262">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-262">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="15ffd-263">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-263">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-264">アーカイブのパッケージは orpurge アクティビティ データをアーカイブするかどうかは、指定されたアクティビティのアーカイブ パッケージの動作を取得します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-264">Gets the behavior of the archiving package for the specified activity, whether the archiving package will archive orpurge activity data.</span></span>  
  
 <span data-ttu-id="15ffd-265">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-265">**Examples**</span></span>  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="15ffd-266">set-archive コマンド</span><span class="sxs-lookup"><span data-stu-id="15ffd-266">set-archive Command</span></span>  
 <span data-ttu-id="15ffd-267">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="15ffd-267">**Usage**</span></span>  
  
 <span data-ttu-id="15ffd-268">**bm.exe set-archive -Activity:\<activity\> -ShouldArchive:True [-Server:\<server\>] [-Database:\<database\>]**</span><span class="sxs-lookup"><span data-stu-id="15ffd-268">**bm.exe set-archive -Activity:\<activity\> -ShouldArchive:True [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="15ffd-269">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="15ffd-269">**Parameters**</span></span>  
  
|<span data-ttu-id="15ffd-270">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15ffd-270">Parameter</span></span>|<span data-ttu-id="15ffd-271">説明</span><span class="sxs-lookup"><span data-stu-id="15ffd-271">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15ffd-272">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="15ffd-272">Activity:\<activity name\></span></span>|<span data-ttu-id="15ffd-273">動作を表示するアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-273">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="15ffd-274">ShouldArchive:True</span><span class="sxs-lookup"><span data-stu-id="15ffd-274">ShouldArchive: True</span></span>|<span data-ttu-id="15ffd-275">True に設定すると、アクティビティに移動されますアーカイブ DB します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-275">If set to True, the activity is moved to Archive DB.</span></span> <span data-ttu-id="15ffd-276">場合は、アクティビティを False に設定は消去されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-276">If set to False, the activity is purged.</span></span>|  
|<span data-ttu-id="15ffd-277">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="15ffd-277">Server:\<server\></span></span>|<span data-ttu-id="15ffd-278">省略可能:アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-278">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="15ffd-279">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="15ffd-279">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="15ffd-280">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-280">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="15ffd-281">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="15ffd-281">Database:\<database\></span></span>|<span data-ttu-id="15ffd-282">省略可能:アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15ffd-282">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="15ffd-283">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-283">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="15ffd-284">アクティビティ データがアーカイブ DB に移動されるように指定されたアクティビティのアーカイブ パッケージの動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-284">Sets the behavior of the archiving package for the activity specified so that activity data is moved into the Archive DB.</span></span> <span data-ttu-id="15ffd-285">既定では、この動作は、展開されている新しいアクティビティに対して設定されます。</span><span class="sxs-lookup"><span data-stu-id="15ffd-285">By default, this behavior is set for new activities that are deployed.</span></span>  
  
 <span data-ttu-id="15ffd-286">**使用例**</span><span class="sxs-lookup"><span data-stu-id="15ffd-286">**Examples**</span></span>  
  
 <span data-ttu-id="15ffd-287">BAM アクティビティ データを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-287">To purge the BAM activity data, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 <span data-ttu-id="15ffd-288">BAM アクティビティ データを BAMArchive データベースに移動するには次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="15ffd-288">To move the BAM activity data to the BAMArchive database, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a><span data-ttu-id="15ffd-289">参照</span><span class="sxs-lookup"><span data-stu-id="15ffd-289">See Also</span></span>  
 [<span data-ttu-id="15ffd-290">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="15ffd-290">BAM Management Utility</span></span>](../core/bam-management-utility.md)
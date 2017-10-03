---
title: "BAM 定義 (監視モデル) コマンドの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 847dd40bc7d0e8fe9ec225ad8af45d06c92d7b63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a><span data-ttu-id="f5c0f-102">BAM 定義 (監視モデル) の展開コマンド</span><span class="sxs-lookup"><span data-stu-id="f5c0f-102">Deployment of BAM Definition (Observation Model) Commands</span></span>
<span data-ttu-id="f5c0f-103">BAM 管理ユーティリティの展開コマンドを使用すると、定義を適用、変更、および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-103">The BAM management utility deployment commands allow you to apply, modify, and remove definitions.</span></span>  
  
-   <span data-ttu-id="f5c0f-104">展開すべて: BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-104">deploy-all: Deploys a BAM definition.</span></span>  
  
-   <span data-ttu-id="f5c0f-105">すべての更新: BAM 定義を更新します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-105">update-all: Updates a BAM definition.</span></span>  
  
-   <span data-ttu-id="f5c0f-106">すべてを削除します。 BAM 定義を削除します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-106">remove-all: Removes a BAM definition.</span></span>  
  
-   <span data-ttu-id="f5c0f-107">更新 livedataworkbook: ライブ データ ブック内のデータベース接続情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-107">update-livedataworkbook: Updates the database connection information in a live data workbook.</span></span>  
  
-   <span data-ttu-id="f5c0f-108">regenerate livedataworkbook: サーバーでライブ データ ブックを再生成します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-108">regenerate-livedataworkbook: Regenerates the live data workbook on the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5c0f-109">含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で & #124 オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-109">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="f5c0f-110">Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-110">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="f5c0f-111">このスイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-111">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5c0f-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-all-command"></a><span data-ttu-id="f5c0f-113">deploy-all コマンド</span><span class="sxs-lookup"><span data-stu-id="f5c0f-113">deploy-all Command</span></span>  
 <span data-ttu-id="f5c0f-114">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-114">**Usage**</span></span>  
  
 <span data-ttu-id="f5c0f-115">**bm.exe 展開すべて-definitionfile:\<def ファイル > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-115">**bm.exe deploy-all -DefinitionFile:\<def file>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f5c0f-116">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-116">**Parameters**</span></span>  
  
|<span data-ttu-id="f5c0f-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5c0f-117">Parameter</span></span>|<span data-ttu-id="f5c0f-118">Description</span><span class="sxs-lookup"><span data-stu-id="f5c0f-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5c0f-119">DefinitionFile:\<def ファイル ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-119">DefinitionFile:\<def file></span></span>|<span data-ttu-id="f5c0f-120">展開する定義が格納されたファイルのパスおよび名前です。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-120">The path and name of the file containing the definitions to deploy.</span></span>|  
|<span data-ttu-id="f5c0f-121">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-121">Server:\<server></span></span>|<span data-ttu-id="f5c0f-122">省略可能: 定義を展開するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-122">Optional: The name of the server to which to deploy the definitions.</span></span> <span data-ttu-id="f5c0f-123">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f5c0f-124">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f5c0f-125">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-125">Database:\<database></span></span>|<span data-ttu-id="f5c0f-126">省略可能: 定義を配置するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-126">Optional: The name of the database to which to deploy the definitions.</span></span> <span data-ttu-id="f5c0f-127">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f5c0f-128">指定された BAM 定義 XML ファイルのすべてのアイテムを、指定されたサーバーおよびデータベースに展開します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-128">Deploys all artifacts from the specified BAM definition XML file to the specified server and database.</span></span> <span data-ttu-id="f5c0f-129">BAM 定義 XML が含まれたテキスト ファイルか、BAM Excel ブックのいずれかのファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-129">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="f5c0f-130">定義ファイルに、既存のアイテムを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-130">The definition file must include only new artifacts.</span></span> <span data-ttu-id="f5c0f-131">既に展開済みのアイテムが格納されていた場合、展開は失敗し、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-131">If the file contains artifacts that have already been deployed, the deployment will fail and report an error.</span></span>  
  
 <span data-ttu-id="f5c0f-132">**BAM 定義の展開に関する考慮事項**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-132">**Considerations for deploying BAM definitions**</span></span>  
  
 <span data-ttu-id="f5c0f-133">警告サブスクリプションを展開する場合は、サブスクライバーのユーザー ID を domain\user 形式で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-133">When deploying alert subscriptions, user IDs of the subscribers must be specified in a domain\user format.</span></span>  
  
 <span data-ttu-id="f5c0f-134">コンピューターに分散トランザクション コーディネーター (DTC) サービスが実行されている必要があります、**展開すべて**コマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-134">The distributed transaction coordinator (DTC) service must be running on the computer on which the **deploy-all** command is issued.</span></span>  
  
 <span data-ttu-id="f5c0f-135">BAM 管理ユーティリティで定義を展開するとき、RTA (リアルタイム集計) ビューでサポートされるディメンション レベルは 14 レベルまでです。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-135">When deploying a definition the BAM Management utility only supports 14 dimension levels in Real-Time Aggregation (RTA) view.</span></span> <span data-ttu-id="f5c0f-136">それ以上のレベルを展開すると、"配置に失敗しました" というエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-136">Deploying additional levels returns a Deployment failed error.</span></span>  
  
 <span data-ttu-id="f5c0f-137">言語設定がそれぞれ異なる複数のビューを定義し、単一言語のサーバーに対してソリューションを展開した場合、これらのビューは展開されません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-137">If you define multiple views that use different language settings and deploy your solution to a server that uses a single language, the views will be undeployable.</span></span> <span data-ttu-id="f5c0f-138">このシナリオがサポートされるのは、BAM 定義に、OLAP を必要とするスケジュール済みの集計が含まれない場合だけです。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-138">This scenario is supported only in a case where you don't have scheduled aggregations that require OLAP as part of the BAM definition.</span></span>  
  
 <span data-ttu-id="f5c0f-139">BAM 管理ユーティリティでは、BAM 警告が有効な場合、展開できるアクティビティ ビューが 49 個に制限されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-139">The BAM management utility limits you to 49 deployed activity views when BAM Alerts are enabled.</span></span> <span data-ttu-id="f5c0f-140">アクティビティ ビューの数は、各ビューに関連付けられた親アクティビティ数の総和として計算されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-140">The number of activity views is calculated as the Summation 1..N of View(n) multiplied by the number of parent activities.</span></span>  <span data-ttu-id="f5c0f-141">たとえば、2 つのアクティビティに基づくビューを 1 つ展開した場合、アクティビティ ビューは 2 つです。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-141">For example, if you deploy a view that is based on two activities, you get two activity views.</span></span>  <span data-ttu-id="f5c0f-142">また、一方は 2 つのアクティビティに、もう一方は単一のアクティビティに基づく 2 つのビューを展開した場合、アクティビティ ビューの数は 3 つということになります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-142">If you deploy two views, one of which spans two activities and the other based on a single activity, you have 3 activity views.</span></span>  
  
 <span data-ttu-id="f5c0f-143">BAM 管理ユーティリティでは、同じ RTA およびキューブ名の組み合わせに対して複数の PivotTable レポートを定義し、それを BAM 定義に割り当てて展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-143">The BAM Management utility blocks deployment of BAM definitions which have multiple PivotTable reports which are defined on the same RTA and cube name combination.</span></span> <span data-ttu-id="f5c0f-144">Bm.exe によって展開作業が強制終了され、次のようなエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-144">Bm.exe will terminate the deployment and return the following error:</span></span>  
  
 <span data-ttu-id="f5c0f-145">ビューを展開しています...エラー: BAM 展開に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-145">Deploying View... ERROR: The BAM deployment failed.</span></span>  
  
 <span data-ttu-id="f5c0f-146">特定の RTA とキューブに対して定義できる PivotTable ビューは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-146">Only one PivotTable view can be defined on a given RTA and cube.</span></span>  
  
 <span data-ttu-id="f5c0f-147">次に示した名前は予約されています。使用すると定義の展開時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-147">The following list of names are reserved and will cause the definition deployment to fail:</span></span>  
  
-   <span data-ttu-id="f5c0f-148">RecordID</span><span class="sxs-lookup"><span data-stu-id="f5c0f-148">RecordID</span></span>  
  
-   <span data-ttu-id="f5c0f-149">ActivityID</span><span class="sxs-lookup"><span data-stu-id="f5c0f-149">ActivityID</span></span>  
  
-   <span data-ttu-id="f5c0f-150">可視</span><span class="sxs-lookup"><span data-stu-id="f5c0f-150">IsVisible</span></span>  
  
-   <span data-ttu-id="f5c0f-151">IsComplete</span><span class="sxs-lookup"><span data-stu-id="f5c0f-151">IsComplete</span></span>  
  
-   <span data-ttu-id="f5c0f-152">LastModified</span><span class="sxs-lookup"><span data-stu-id="f5c0f-152">LastModified</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5c0f-153">展開中に bm.exe でエラーが発生した場合、展開は強制終了され、ビューやアクティビティに対する変更はロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-153">If bm.exe encounters an error during the deployment, the deployment is terminated and changes to the views and activities are rolled back.</span></span> <span data-ttu-id="f5c0f-154">ただし、OLAP はトランザクション配置に対応していないため、OLAP キューブに対する変更はロールバックされません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-154">Changes to OLAP cubes are not rolled back since OLAP does not support transactional deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5c0f-155">BAM 定義を作成するコンピューターと、その展開先のコンピューターは、ロケール設定が一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-155">BAM definitions created on a computer using one locale setting cannot be deployed to a computer configured with a different locale setting.</span></span> <span data-ttu-id="f5c0f-156">たとえば、ロケール設定が EN のコンピューターで、英語版の Microsoft Excel を使って作成された BAM 定義を、ロケール設定が JA (日本語) のコンピューターに展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-156">For example, a BAM definition generated using an English language version of Microsoft Excel on a computer configured with a EN locale setting cannot be deployed on a computer configured for Japanese using a JA locale setting.</span></span>  
  
 <span data-ttu-id="f5c0f-157">**使用例**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-157">**Examples**</span></span>  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a><span data-ttu-id="f5c0f-158">update-all コマンド</span><span class="sxs-lookup"><span data-stu-id="f5c0f-158">update-all Command</span></span>  
 <span data-ttu-id="f5c0f-159">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-159">**Usage**</span></span>  
  
 <span data-ttu-id="f5c0f-160">**すべての bm.exe 更新-definitionfile:\<def ファイル > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-160">**bm.exe update-all -DefinitionFile:\<def file>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f5c0f-161">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-161">**Parameters**</span></span>  
  
|<span data-ttu-id="f5c0f-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5c0f-162">Parameter</span></span>|<span data-ttu-id="f5c0f-163">Description</span><span class="sxs-lookup"><span data-stu-id="f5c0f-163">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5c0f-164">DefinitionFile:\<def ファイル ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-164">DefinitionFile:\<def file></span></span>|<span data-ttu-id="f5c0f-165">更新に使用する定義が格納されたファイルのパスおよび名前です。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-165">The path and name of the file containing the definitions from which to perform the update.</span></span>|  
|<span data-ttu-id="f5c0f-166">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-166">Server:\<server></span></span>|<span data-ttu-id="f5c0f-167">省略可能: 定義の更新を展開するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-167">Optional: The name of the server to which to deploy the definition updates.</span></span> <span data-ttu-id="f5c0f-168">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-168">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f5c0f-169">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-169">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f5c0f-170">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-170">Database:\<database></span></span>|<span data-ttu-id="f5c0f-171">省略可能: 定義の更新を展開するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-171">Optional: The name of the database to which to deploy the definition updates.</span></span> <span data-ttu-id="f5c0f-172">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-172">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f5c0f-173">BAM 定義 XML に基づいて特定のアイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-173">Updates certain artifacts from the BAM definition XML.</span></span> <span data-ttu-id="f5c0f-174">BAM 定義 XML が含まれたテキスト ファイルか、BAM Excel ブックのいずれかのファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-174">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="f5c0f-175">更新時、現在の定義ファイルに記述されていないアイテムは削除されません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-175">The update does not delete artifacts that are not described in the current definition file.</span></span> <span data-ttu-id="f5c0f-176">アクティビティに新しいチェックポイントを追加することはできますが、展開済みのアクティビティからチェックポイントを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-176">It can add new checkpoints to activities, but cannot drop checkpoints from deployed activities.</span></span> <span data-ttu-id="f5c0f-177">更新中にチェックポイントの名前を変更したり、チェックポイントのプロパティを変更したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-177">The update can neither rename checkpoints nor change checkpoint properties.</span></span>  
  
 <span data-ttu-id="f5c0f-178">アクティビティを展開した後は、アクティビティに対して実行できる操作が制限されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-178">Once an activity has been deployed, the actions you can take on an activity become restricted.</span></span> <span data-ttu-id="f5c0f-179">特に、アクティビティから項目を削除するには、管理者に依頼して BAM のアクティビティとビュー セット全体を展開解除し、再展開してもらう必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-179">Specifically, you cannot delete items from an activity unless you are prepared to have your administrator undeploy the entire BAM activity and view sets and then redeploy them.</span></span> <span data-ttu-id="f5c0f-180">このとき、管理者がデータのバックアップと復元を行わないと、データが失われたり、表示できなくなったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-180">This can cause an interruption of visibility and loss of data unless the administrator does a backup and restore of the data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5c0f-181">このコマンドを使って、既存のビューに新しいアクティビティを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-181">You cannot use this command to add new activities to an existing view.</span></span> <span data-ttu-id="f5c0f-182">ビューをアクティビティに追加するには、新しいアクティビティを含んだビューを新規作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-182">To add a view to an activity you must create a new view that includes the new activity.</span></span> <span data-ttu-id="f5c0f-183">古いビューはその後で展開解除できますが、その場合、OLAP のデータ履歴は失われます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-183">You can then undeploy the old view, but be aware that you will then lose your OLAP data history.</span></span>  
  
 <span data-ttu-id="f5c0f-184">**使用例**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-184">**Examples**</span></span>  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a><span data-ttu-id="f5c0f-185">remove-all コマンド</span><span class="sxs-lookup"><span data-stu-id="f5c0f-185">remove-all Command</span></span>  
 <span data-ttu-id="f5c0f-186">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-186">**Usage**</span></span>  
  
 <span data-ttu-id="f5c0f-187">**すべての bm.exe 削除 DefinitionFile:\<def ファイル > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-187">**bm.exe remove-all DefinitionFile:\<def file> [ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f5c0f-188">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-188">**Parameters**</span></span>  
  
|<span data-ttu-id="f5c0f-189">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5c0f-189">Parameter</span></span>|<span data-ttu-id="f5c0f-190">Description</span><span class="sxs-lookup"><span data-stu-id="f5c0f-190">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5c0f-191">DefinitionFile:\<def ファイル ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-191">DefinitionFile:\<def file></span></span>|<span data-ttu-id="f5c0f-192">削除する定義が格納されたファイルのパスおよび名前です。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-192">The path and name of the file containing the definitions to remove.</span></span>|  
|<span data-ttu-id="f5c0f-193">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-193">Server:\<server></span></span>|<span data-ttu-id="f5c0f-194">省略可能: 定義の削除元となるサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-194">Optional: The name of the server from which the definitions will be removed.</span></span> <span data-ttu-id="f5c0f-195">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-195">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f5c0f-196">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-196">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f5c0f-197">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-197">Database:\<database></span></span>|<span data-ttu-id="f5c0f-198">省略可能: 定義の削除元となるデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-198">Optional: The name of the database from which the definitions will be removed.</span></span> <span data-ttu-id="f5c0f-199">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-199">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f5c0f-200">BAM 定義 XML ファイルに指定されている、すべてのアイテムを削除します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-200">Removes all artifacts specified in the BAM definition XML file.</span></span> <span data-ttu-id="f5c0f-201">BAM 定義 XML が含まれたテキスト ファイルか、BAM Excel ブックのいずれかのファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-201">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="f5c0f-202">各アイテムの定義は、元の (展開時の) 定義と完全に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-202">The definition for each artifact must exactly match the original definition that was used for deployment.</span></span>  
  
 <span data-ttu-id="f5c0f-203">**使用例**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-203">**Examples**</span></span>  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a><span data-ttu-id="f5c0f-204">update-livedataworkbook コマンド</span><span class="sxs-lookup"><span data-stu-id="f5c0f-204">update-livedataworkbook Command</span></span>  
 <span data-ttu-id="f5c0f-205">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-205">**Usage**</span></span>  
  
 <span data-ttu-id="f5c0f-206">**bm.exe 更新 livedataworkbook-名前:\<livedata ブックのファイル名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-206">**bm.exe update-livedataworkbook -Name:\<livedata workbook file name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f5c0f-207">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-207">**Parameters**</span></span>  
  
|<span data-ttu-id="f5c0f-208">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5c0f-208">Parameter</span></span>|<span data-ttu-id="f5c0f-209">Description</span><span class="sxs-lookup"><span data-stu-id="f5c0f-209">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5c0f-210">[名前]:\<livedata ブック ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-210">Name:\<livedata workbook></span></span>|<span data-ttu-id="f5c0f-211">更新する既存のライブ ブックの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-211">The name of the existing live workbook to update.</span></span>|  
|<span data-ttu-id="f5c0f-212">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-212">Server:\<server></span></span>|<span data-ttu-id="f5c0f-213">省略可能: ブックが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-213">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="f5c0f-214">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-214">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f5c0f-215">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-215">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f5c0f-216">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-216">Database:\<database></span></span>|<span data-ttu-id="f5c0f-217">省略可能: ブックが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-217">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="f5c0f-218">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-218">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f5c0f-219">指定された BAM ライブ データ ブックを対象に、BAM プライマリ インポート データベースの接続情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-219">Updates the BAM Primary Import database connection information in the specified BAM live data workbook.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5c0f-220">新しい接続文字列を構成するときには TDDS サービスを再起動して、変更がサービスから確実に認識されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-220">When configuring new connection string, you must restart the TDDS service to ensure that the service recognizes the change.</span></span> <span data-ttu-id="f5c0f-221">TDDS サービスの詳細については、次を参照してください。 [BAM イベント バス サービス Stored Procedures](../core/bam-event-bus-service-stored-procedures.md)です。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-221">For more information on the TDDS service, see [BAM Event Bus Service Stored Procedures](../core/bam-event-bus-service-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="f5c0f-222">**使用例**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-222">**Examples**</span></span>  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a><span data-ttu-id="f5c0f-223">regenerate-livedataworkbook コマンド</span><span class="sxs-lookup"><span data-stu-id="f5c0f-223">regenerate-livedataworkbook Command</span></span>  
 <span data-ttu-id="f5c0f-224">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-224">**Usage**</span></span>  
  
 <span data-ttu-id="f5c0f-225">**bm.exe を再生成 livedataworkbook WorkbookName:\<livedata ブックのファイル名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-225">**bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f5c0f-226">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f5c0f-226">**Parameters**</span></span>  
  
|<span data-ttu-id="f5c0f-227">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5c0f-227">Parameter</span></span>|<span data-ttu-id="f5c0f-228">Description</span><span class="sxs-lookup"><span data-stu-id="f5c0f-228">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5c0f-229">WorkbookName:\<livedata ブックのファイル名 ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-229">WorkbookName:\<livedata workbook file name></span></span>|<span data-ttu-id="f5c0f-230">更新するブックの名前です。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-230">The name of the workbook to update.</span></span>|  
|<span data-ttu-id="f5c0f-231">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-231">Server:\<server></span></span>|<span data-ttu-id="f5c0f-232">省略可能: ブックが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-232">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="f5c0f-233">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-233">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f5c0f-234">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-234">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f5c0f-235">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f5c0f-235">Database:\<database></span></span>|<span data-ttu-id="f5c0f-236">省略可能: ブックが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-236">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="f5c0f-237">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-237">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f5c0f-238">BAM ライブ データ ブックを生成します。ただし、ブックは展開されません。</span><span class="sxs-lookup"><span data-stu-id="f5c0f-238">Generates a BAM live data workbook but does not deploy the workbook.</span></span>  
  
 <span data-ttu-id="f5c0f-239">使用例</span><span class="sxs-lookup"><span data-stu-id="f5c0f-239">Examples</span></span>  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5c0f-240">参照</span><span class="sxs-lookup"><span data-stu-id="f5c0f-240">See Also</span></span>  
 [<span data-ttu-id="f5c0f-241">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="f5c0f-241">BAM Management Utility</span></span>](../core/bam-management-utility.md)
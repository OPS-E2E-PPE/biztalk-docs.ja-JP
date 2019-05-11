---
title: BAM 定義 (監視モデル) コマンドの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506b563136fec86fdde9aebab31ad9bb4435736b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351740"
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a><span data-ttu-id="c3bdc-102">BAM 定義 (監視モデル) コマンドの配置</span><span class="sxs-lookup"><span data-stu-id="c3bdc-102">Deployment of BAM Definition (Observation Model) Commands</span></span>
<span data-ttu-id="c3bdc-103">BAM 管理ユーティリティの展開コマンドを使用すると、適用、変更、および定義を削除できます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-103">The BAM management utility deployment commands allow you to apply, modify, and remove definitions.</span></span>  
  
-   <span data-ttu-id="c3bdc-104">すべてを展開します。BAM 定義をデプロイします。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-104">deploy-all: Deploys a BAM definition.</span></span>  
  
-   <span data-ttu-id="c3bdc-105">すべての更新プログラム。BAM 定義を更新します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-105">update-all: Updates a BAM definition.</span></span>  
  
-   <span data-ttu-id="c3bdc-106">すべて削除します。BAM 定義を削除します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-106">remove-all: Removes a BAM definition.</span></span>  
  
-   <span data-ttu-id="c3bdc-107">更新プログラム-livedataworkbook:ライブ データ ブック内のデータベース接続情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-107">update-livedataworkbook: Updates the database connection information in a live data workbook.</span></span>  
  
-   <span data-ttu-id="c3bdc-108">再生成 livedataworkbook:サーバーでライブ データ ブックを再生成します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-108">regenerate-livedataworkbook: Regenerates the live data workbook on the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3bdc-109">含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-109">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="c3bdc-110">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-110">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="c3bdc-111">スイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-111">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3bdc-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-all-command"></a><span data-ttu-id="c3bdc-113">deploy-all コマンド</span><span class="sxs-lookup"><span data-stu-id="c3bdc-113">deploy-all Command</span></span>  
 <span data-ttu-id="c3bdc-114">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-114">**Usage**</span></span>  
  
 <span data-ttu-id="c3bdc-115">**bm.exe deploy-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-115">**bm.exe deploy-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c3bdc-116">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-116">**Parameters**</span></span>  
  
|<span data-ttu-id="c3bdc-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3bdc-117">Parameter</span></span>|<span data-ttu-id="c3bdc-118">説明</span><span class="sxs-lookup"><span data-stu-id="c3bdc-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3bdc-119">DefinitionFile:\<def ファイル\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-119">DefinitionFile:\<def file\></span></span>|<span data-ttu-id="c3bdc-120">パスとデプロイには、定義を含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-120">The path and name of the file containing the definitions to deploy.</span></span>|  
|<span data-ttu-id="c3bdc-121">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-121">Server:\<server\></span></span>|<span data-ttu-id="c3bdc-122">省略可能:定義を展開する先のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-122">Optional: The name of the server to which to deploy the definitions.</span></span> <span data-ttu-id="c3bdc-123">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c3bdc-124">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c3bdc-125">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-125">Database:\<database\></span></span>|<span data-ttu-id="c3bdc-126">省略可能:定義を配置するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-126">Optional: The name of the database to which to deploy the definitions.</span></span> <span data-ttu-id="c3bdc-127">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c3bdc-128">指定した BAM 定義 XML ファイルから、指定されたサーバーとデータベースへのすべての成果物をデプロイします。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-128">Deploys all artifacts from the specified BAM definition XML file to the specified server and database.</span></span> <span data-ttu-id="c3bdc-129">ファイルは、BAM 定義 XML または BAM Excel ブックを含むテキスト ファイルであることができます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-129">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="c3bdc-130">定義ファイルには、新しい成果物のみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-130">The definition file must include only new artifacts.</span></span> <span data-ttu-id="c3bdc-131">ファイルに既にデプロイされている成果物が含まれている場合、デプロイは失敗し、エラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-131">If the file contains artifacts that have already been deployed, the deployment will fail and report an error.</span></span>  
  
 <span data-ttu-id="c3bdc-132">**BAM 定義の展開に関する考慮事項**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-132">**Considerations for deploying BAM definitions**</span></span>  
  
 <span data-ttu-id="c3bdc-133">警告のサブスクリプションを展開する場合は、domain \user 形式で、サブスクライバーのユーザー Id を指定してください。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-133">When deploying alert subscriptions, user IDs of the subscribers must be specified in a domain\user format.</span></span>  
  
 <span data-ttu-id="c3bdc-134">コンピューターに、分散トランザクション コーディネーター (DTC) サービスを実行する必要があります、**展開すべて**コマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-134">The distributed transaction coordinator (DTC) service must be running on the computer on which the **deploy-all** command is issued.</span></span>  
  
 <span data-ttu-id="c3bdc-135">定義を展開するときに、BAM 管理ユーティリティにより、ディメンション レベルは 14 がリアルタイム集計 (RTA) ビューでのみサポートします。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-135">When deploying a definition the BAM Management utility only supports 14 dimension levels in Real-Time Aggregation (RTA) view.</span></span> <span data-ttu-id="c3bdc-136">追加レベルを展開するには、配置に失敗しましたエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-136">Deploying additional levels returns a Deployment failed error.</span></span>  
  
 <span data-ttu-id="c3bdc-137">別の言語設定を使用し、1 つの言語を使用するサーバーに、ソリューションを配置する複数のビューを定義する場合、ビューは展開されません。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-137">If you define multiple views that use different language settings and deploy your solution to a server that uses a single language, the views will be undeployable.</span></span> <span data-ttu-id="c3bdc-138">このシナリオは、BAM 定義の一部として OLAP を必要とするスケジュール済みの集計の必要がないケースでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-138">This scenario is supported only in a case where you don't have scheduled aggregations that require OLAP as part of the BAM definition.</span></span>  
  
 <span data-ttu-id="c3bdc-139">BAM 管理ユーティリティは、49 展開されたアクティビティ ビューに BAM 警告を有効にするように制限されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-139">The BAM management utility limits you to 49 deployed activity views when BAM Alerts are enabled.</span></span> <span data-ttu-id="c3bdc-140">アクティビティ ビューの数は合計として計算されますの総和は親アクティビティの数を掛けた値します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-140">The number of activity views is calculated as the Summation 1..N of View(n) multiplied by the number of parent activities.</span></span>  <span data-ttu-id="c3bdc-141">たとえば、2 つのアクティビティに基づいているビューを展開する場合に、2 つのアクティビティ ビューを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-141">For example, if you deploy a view that is based on two activities, you get two activity views.</span></span>  <span data-ttu-id="c3bdc-142">うちの 1 つは、2 つのアクティビティおよびその他の 1 つのアクティビティに基づくにまたがる、2 つのビューを展開する場合は、3 つのアクティビティ ビューが。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-142">If you deploy two views, one of which spans two activities and the other based on a single activity, you have 3 activity views.</span></span>  
  
 <span data-ttu-id="c3bdc-143">複数のピボット テーブルが BAM 定義の BAM 管理ユーティリティのブロックの展開では、同じ RTA およびキューブ名の組み合わせで定義されているを報告します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-143">The BAM Management utility blocks deployment of BAM definitions which have multiple PivotTable reports which are defined on the same RTA and cube name combination.</span></span> <span data-ttu-id="c3bdc-144">Bm.exe が配置を終了し、次のエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-144">Bm.exe will terminate the deployment and return the following error:</span></span>  
  
 <span data-ttu-id="c3bdc-145">ビューを展開しています.ERROR:BAM の展開に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-145">Deploying View... ERROR: The BAM deployment failed.</span></span>  
  
 <span data-ttu-id="c3bdc-146">1 つのピボット テーブル ビューは、特定の RTA とキューブを定義できます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-146">Only one PivotTable view can be defined on a given RTA and cube.</span></span>  
  
 <span data-ttu-id="c3bdc-147">名の次の一覧は、予約されていますし、定義の展開に失敗すると。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-147">The following list of names are reserved and will cause the definition deployment to fail:</span></span>  
  
-   <span data-ttu-id="c3bdc-148">RecordID</span><span class="sxs-lookup"><span data-stu-id="c3bdc-148">RecordID</span></span>  
  
-   <span data-ttu-id="c3bdc-149">ActivityID</span><span class="sxs-lookup"><span data-stu-id="c3bdc-149">ActivityID</span></span>  
  
-   <span data-ttu-id="c3bdc-150">可視</span><span class="sxs-lookup"><span data-stu-id="c3bdc-150">IsVisible</span></span>  
  
-   <span data-ttu-id="c3bdc-151">完了</span><span class="sxs-lookup"><span data-stu-id="c3bdc-151">IsComplete</span></span>  
  
-   <span data-ttu-id="c3bdc-152">LastModified</span><span class="sxs-lookup"><span data-stu-id="c3bdc-152">LastModified</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3bdc-153">Bm.exe には、展開中にエラーが発生するは、展開が終了し、ビューとアクティビティへの変更はロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-153">If bm.exe encounters an error during the deployment, the deployment is terminated and changes to the views and activities are rolled back.</span></span> <span data-ttu-id="c3bdc-154">OLAP はトランザクション配置をサポートするいないとしているために、OLAP キューブへの変更はロールバックされません。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-154">Changes to OLAP cubes are not rolled back since OLAP does not support transactional deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3bdc-155">1 つのロケール設定を使用してコンピューター上に作成された BAM 定義は、別のロケール設定で構成されているコンピューターに展開できません。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-155">BAM definitions created on a computer using one locale setting cannot be deployed to a computer configured with a different locale setting.</span></span> <span data-ttu-id="c3bdc-156">たとえば、EN のロケール設定で構成されているコンピューターに Microsoft Excel の英語バージョンを使用して生成された BAM 定義は、日本語、日本のロケール設定を使用して構成されているコンピューターに展開できません。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-156">For example, a BAM definition generated using an English language version of Microsoft Excel on a computer configured with a EN locale setting cannot be deployed on a computer configured for Japanese using a JA locale setting.</span></span>  
  
 <span data-ttu-id="c3bdc-157">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-157">**Examples**</span></span>  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a><span data-ttu-id="c3bdc-158">update-all コマンド</span><span class="sxs-lookup"><span data-stu-id="c3bdc-158">update-all Command</span></span>  
 <span data-ttu-id="c3bdc-159">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-159">**Usage**</span></span>  
  
 <span data-ttu-id="c3bdc-160">**bm.exe update-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-160">**bm.exe update-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c3bdc-161">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-161">**Parameters**</span></span>  
  
|<span data-ttu-id="c3bdc-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3bdc-162">Parameter</span></span>|<span data-ttu-id="c3bdc-163">説明</span><span class="sxs-lookup"><span data-stu-id="c3bdc-163">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3bdc-164">DefinitionFile:\<def ファイル\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-164">DefinitionFile:\<def file\></span></span>|<span data-ttu-id="c3bdc-165">パスと、更新プログラムを実行する定義が格納されたファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-165">The path and name of the file containing the definitions from which to perform the update.</span></span>|  
|<span data-ttu-id="c3bdc-166">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-166">Server:\<server\></span></span>|<span data-ttu-id="c3bdc-167">省略可能:定義の更新を展開するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-167">Optional: The name of the server to which to deploy the definition updates.</span></span> <span data-ttu-id="c3bdc-168">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-168">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c3bdc-169">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-169">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c3bdc-170">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-170">Database:\<database\></span></span>|<span data-ttu-id="c3bdc-171">省略可能:定義の更新を展開するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-171">Optional: The name of the database to which to deploy the definition updates.</span></span> <span data-ttu-id="c3bdc-172">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-172">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c3bdc-173">BAM 定義 XML に基づいて特定のアイテムを更新します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-173">Updates certain artifacts from the BAM definition XML.</span></span> <span data-ttu-id="c3bdc-174">ファイルは、BAM 定義 XML または BAM Excel ブックを含むテキスト ファイルであることができます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-174">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="c3bdc-175">更新プログラムでは、現在の定義ファイルに記述されていないアイテムは削除されません。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-175">The update does not delete artifacts that are not described in the current definition file.</span></span> <span data-ttu-id="c3bdc-176">活動に新しいチェックポイントを追加することができますが、展開済みのアクティビティからチェックポイントを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-176">It can add new checkpoints to activities, but cannot drop checkpoints from deployed activities.</span></span> <span data-ttu-id="c3bdc-177">更新プログラムはチェックポイントの名前も、チェックポイントのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-177">The update can neither rename checkpoints nor change checkpoint properties.</span></span>  
  
 <span data-ttu-id="c3bdc-178">アクティビティを展開した後は、アクティビティに対して実行できる操作が制限されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-178">Once an activity has been deployed, the actions you can take on an activity become restricted.</span></span> <span data-ttu-id="c3bdc-179">特に、アクティビティから項目を削除するには、管理者に依頼して BAM のアクティビティとビュー セット全体を展開解除し、再展開してもらう必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-179">Specifically, you cannot delete items from an activity unless you are prepared to have your administrator undeploy the entire BAM activity and view sets and then redeploy them.</span></span> <span data-ttu-id="c3bdc-180">このとき、管理者がデータのバックアップと復元を行わないと、データが失われたり、表示できなくなったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-180">This can cause an interruption of visibility and loss of data unless the administrator does a backup and restore of the data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3bdc-181">このコマンドを使用して、既存のビューに新しいアクティビティを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-181">You cannot use this command to add new activities to an existing view.</span></span> <span data-ttu-id="c3bdc-182">アクティビティにビューを追加するには、新しいアクティビティを含む新しいビューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-182">To add a view to an activity you must create a new view that includes the new activity.</span></span> <span data-ttu-id="c3bdc-183">できますが、元のビューを展開解除し、OLAP データの履歴が失われることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-183">You can then undeploy the old view, but be aware that you will then lose your OLAP data history.</span></span>  
  
 <span data-ttu-id="c3bdc-184">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-184">**Examples**</span></span>  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a><span data-ttu-id="c3bdc-185">remove-all コマンド</span><span class="sxs-lookup"><span data-stu-id="c3bdc-185">remove-all Command</span></span>  
 <span data-ttu-id="c3bdc-186">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-186">**Usage**</span></span>  
  
 <span data-ttu-id="c3bdc-187">**bm.exe remove-all DefinitionFile:\<def file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-187">**bm.exe remove-all DefinitionFile:\<def file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c3bdc-188">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-188">**Parameters**</span></span>  
  
|<span data-ttu-id="c3bdc-189">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3bdc-189">Parameter</span></span>|<span data-ttu-id="c3bdc-190">説明</span><span class="sxs-lookup"><span data-stu-id="c3bdc-190">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3bdc-191">DefinitionFile:\<def ファイル\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-191">DefinitionFile:\<def file\></span></span>|<span data-ttu-id="c3bdc-192">パスと、削除する定義を含むファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-192">The path and name of the file containing the definitions to remove.</span></span>|  
|<span data-ttu-id="c3bdc-193">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-193">Server:\<server\></span></span>|<span data-ttu-id="c3bdc-194">省略可能:定義の削除元となるサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-194">Optional: The name of the server from which the definitions will be removed.</span></span> <span data-ttu-id="c3bdc-195">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-195">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c3bdc-196">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-196">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c3bdc-197">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-197">Database:\<database\></span></span>|<span data-ttu-id="c3bdc-198">省略可能:定義の削除元となるデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-198">Optional: The name of the database from which the definitions will be removed.</span></span> <span data-ttu-id="c3bdc-199">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-199">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c3bdc-200">BAM 定義 XML ファイルで指定されたすべての成果物を削除します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-200">Removes all artifacts specified in the BAM definition XML file.</span></span> <span data-ttu-id="c3bdc-201">ファイルは、BAM 定義 XML または BAM Excel ブックを含むテキスト ファイルであることができます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-201">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="c3bdc-202">各成果物の定義では、展開に使用された元の定義を正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-202">The definition for each artifact must exactly match the original definition that was used for deployment.</span></span>  
  
 <span data-ttu-id="c3bdc-203">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-203">**Examples**</span></span>  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a><span data-ttu-id="c3bdc-204">update-livedataworkbook コマンド</span><span class="sxs-lookup"><span data-stu-id="c3bdc-204">update-livedataworkbook Command</span></span>  
 <span data-ttu-id="c3bdc-205">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-205">**Usage**</span></span>  
  
 <span data-ttu-id="c3bdc-206">**bm.exe update-livedataworkbook -Name:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-206">**bm.exe update-livedataworkbook -Name:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c3bdc-207">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-207">**Parameters**</span></span>  
  
|<span data-ttu-id="c3bdc-208">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3bdc-208">Parameter</span></span>|<span data-ttu-id="c3bdc-209">説明</span><span class="sxs-lookup"><span data-stu-id="c3bdc-209">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3bdc-210">名前:\<livedata ブック\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-210">Name:\<livedata workbook\></span></span>|<span data-ttu-id="c3bdc-211">更新する既存のライブ ブックの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-211">The name of the existing live workbook to update.</span></span>|  
|<span data-ttu-id="c3bdc-212">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-212">Server:\<server\></span></span>|<span data-ttu-id="c3bdc-213">省略可能:ブックが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-213">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="c3bdc-214">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-214">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c3bdc-215">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-215">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c3bdc-216">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-216">Database:\<database\></span></span>|<span data-ttu-id="c3bdc-217">省略可能:ブックが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-217">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="c3bdc-218">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-218">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c3bdc-219">指定された BAM ライブ データ ブックで BAM プライマリ インポート データベースの接続情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-219">Updates the BAM Primary Import database connection information in the specified BAM live data workbook.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3bdc-220">新しい接続文字列を構成するときに、サービスが、変更を認識していることを確認する TDDS サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-220">When configuring new connection string, you must restart the TDDS service to ensure that the service recognizes the change.</span></span> <span data-ttu-id="c3bdc-221">TDDS サービスの詳細については、次を参照してください。 [BAM イベント バス サービス ストアド プロシージャ](../core/bam-event-bus-service-stored-procedures.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-221">For more information on the TDDS service, see [BAM Event Bus Service Stored Procedures](../core/bam-event-bus-service-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="c3bdc-222">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-222">**Examples**</span></span>  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a><span data-ttu-id="c3bdc-223">regenerate-livedataworkbook コマンド</span><span class="sxs-lookup"><span data-stu-id="c3bdc-223">regenerate-livedataworkbook Command</span></span>  
 <span data-ttu-id="c3bdc-224">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-224">**Usage**</span></span>  
  
 <span data-ttu-id="c3bdc-225">**bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-225">**bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c3bdc-226">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c3bdc-226">**Parameters**</span></span>  
  
|<span data-ttu-id="c3bdc-227">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3bdc-227">Parameter</span></span>|<span data-ttu-id="c3bdc-228">説明</span><span class="sxs-lookup"><span data-stu-id="c3bdc-228">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3bdc-229">WorkbookName:\<livedata ブック ファイル名\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-229">WorkbookName:\<livedata workbook file name\></span></span>|<span data-ttu-id="c3bdc-230">更新するブックの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-230">The name of the workbook to update.</span></span>|  
|<span data-ttu-id="c3bdc-231">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-231">Server:\<server\></span></span>|<span data-ttu-id="c3bdc-232">省略可能:ブックが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-232">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="c3bdc-233">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-233">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c3bdc-234">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-234">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c3bdc-235">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c3bdc-235">Database:\<database\></span></span>|<span data-ttu-id="c3bdc-236">省略可能:ブックが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-236">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="c3bdc-237">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-237">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c3bdc-238">BAM ライブ データ ブックを生成しますが、ブックを配置しません。</span><span class="sxs-lookup"><span data-stu-id="c3bdc-238">Generates a BAM live data workbook but does not deploy the workbook.</span></span>  
  
 <span data-ttu-id="c3bdc-239">使用例</span><span class="sxs-lookup"><span data-stu-id="c3bdc-239">Examples</span></span>  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3bdc-240">参照</span><span class="sxs-lookup"><span data-stu-id="c3bdc-240">See Also</span></span>  
 [<span data-ttu-id="c3bdc-241">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="c3bdc-241">BAM Management Utility</span></span>](../core/bam-management-utility.md)
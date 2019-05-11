---
title: インターセプター管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2be6460-1f81-4bc3-a831-34ff24d65d34
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbce63f7c5616396dd208460323f6aac98adff99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331721"
---
# <a name="interceptor-management-commands"></a><span data-ttu-id="25bc6-102">インターセプター管理コマンド</span><span class="sxs-lookup"><span data-stu-id="25bc6-102">Interceptor Management Commands</span></span>
<span data-ttu-id="25bc6-103">新しい BAM インターセプター機能をサポートするために、BAM 管理ユーティリティに 4 つの新しいコマンドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="25bc6-103">To support the new BAM interceptor functionality, four new commands have been added to the BAM Management utility.</span></span>  
  
 <span data-ttu-id="25bc6-104">これらのコマンドは、展開、取得、およびインターセプターの削除をサポートします。</span><span class="sxs-lookup"><span data-stu-id="25bc6-104">These commands support the deployment, retrieval, and removal of interceptors.</span></span> <span data-ttu-id="25bc6-105">コマンドは、構成されているインターセプターを一覧にも提供されます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-105">A command is also provided to list the configured interceptors.</span></span>  
  
-   <span data-ttu-id="25bc6-106">インターセプターの展開:インターセプター構成をデプロイします。</span><span class="sxs-lookup"><span data-stu-id="25bc6-106">deploy-interceptor: Deploys an interceptor configuration.</span></span>  
  
-   <span data-ttu-id="25bc6-107">get interceptorlist:インターセプトが展開されているアクティビティの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-107">get-interceptorlist: Gets a list of activities on which interception is deployed.</span></span>  
  
-   <span data-ttu-id="25bc6-108">get インターセプター:インターセプター構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-108">get-interceptor: Gets the interceptor configuration.</span></span>  
  
-   <span data-ttu-id="25bc6-109">削除インターセプター:インターセプター構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-109">remove-interceptor: Removes an interceptor configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25bc6-110">含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="25bc6-110">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="25bc6-111">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-111">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="25bc6-112">スイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-112">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25bc6-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="25bc6-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-interceptor-command"></a><span data-ttu-id="25bc6-114">deploy-interceptor コマンド</span><span class="sxs-lookup"><span data-stu-id="25bc6-114">deploy-interceptor Command</span></span>  
 <span data-ttu-id="25bc6-115">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="25bc6-115">**Usage**</span></span>  
  
 <span data-ttu-id="25bc6-116">**bm.exe deploy-interceptor -FileName:\<Configuration XML Filename\> [-Force:True ] [-Server:\<server\>] [-Database:\<database\>]**</span><span class="sxs-lookup"><span data-stu-id="25bc6-116">**bm.exe deploy-interceptor -FileName:\<Configuration XML Filename\> [-Force:True ] [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="25bc6-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="25bc6-117">**Parameters**</span></span>  
  
|<span data-ttu-id="25bc6-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25bc6-118">Parameter</span></span>|<span data-ttu-id="25bc6-119">説明</span><span class="sxs-lookup"><span data-stu-id="25bc6-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25bc6-120">ファイル名:\<構成 XML ファイル名\></span><span class="sxs-lookup"><span data-stu-id="25bc6-120">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="25bc6-121">インターセプター構成を含む XML ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-121">The name of the XML file containing the interceptor configuration.</span></span>|  
|<span data-ttu-id="25bc6-122">Force: True</span><span class="sxs-lookup"><span data-stu-id="25bc6-122">Force:True</span></span>|<span data-ttu-id="25bc6-123">省略可能:イベント ソース名の競合が検出されたときに、インターセプター構成を展開します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-123">Optional: Forces deployment of the interceptor configuration when event source name collisions are detected.</span></span>|  
|<span data-ttu-id="25bc6-124">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="25bc6-124">Server:\<server\></span></span>|<span data-ttu-id="25bc6-125">省略可能:インターセプターを展開先サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-125">Optional: The name of the server on which to deploy the interceptor.</span></span> <span data-ttu-id="25bc6-126">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="25bc6-126">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="25bc6-127">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="25bc6-127">Database:\<database\></span></span>|<span data-ttu-id="25bc6-128">省略可能:インターセプターを構成する BAM プライマリ インポート データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-128">Optional: The name of the BAM Primary Import database on which to configure the interceptor.</span></span>|  
  
 <span data-ttu-id="25bc6-129">このコマンドは、指定したサーバーおよびデータベースにインターセプター構成をデプロイします。</span><span class="sxs-lookup"><span data-stu-id="25bc6-129">This command deploys the interceptor configuration to the specified server and database.</span></span> <span data-ttu-id="25bc6-130">デプロイ時に、BAM 管理ユーティリティは、次の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-130">During deployment, the BAM Management utility performs the following validations:</span></span>  
  
- <span data-ttu-id="25bc6-131">XSD 検証:インターセプター構成は、共通のインターセプター構成スキーマに対して検証されます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-131">XSD validation: The interceptor configuration is validated against the common interceptor configuration schema.</span></span>  
  
- <span data-ttu-id="25bc6-132">アクティビティが存在する検証 (は、プライマリ インポート データベースに展開) のチェックポイントが有効であると (存在し、一致するデータ型である)。</span><span class="sxs-lookup"><span data-stu-id="25bc6-132">Validation that the activity exists (is deployed in the Primary Import database) and that checkpoints are valid (exist and have a matching data type).</span></span>  
  
  <span data-ttu-id="25bc6-133">イベント ソース名の競合が検出されると、競合を説明する警告がスローされます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-133">If a collision is detected in the event source name, a warning is thrown describing the collision.</span></span> <span data-ttu-id="25bc6-134">競合がある場合、配置が失敗しない限り、 **– Force:true**パラメーター フラグが使用されます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-134">In the case of a collision, the deployment will fail unless the **–Force:True** parameter flag is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25bc6-135">**– Force:true**パラメーターは可能性のある同じ名前のイベント ソースを参照するインターセプター構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-135">The **–Force:True** parameter potentially removes interceptor configurations that reference event sources with the same name.</span></span> <span data-ttu-id="25bc6-136">使用する必要があります、 **get インターセプター**コマンドを使用する前に既存のインターセプター構成のバックアップを作成、 **– Force:true**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="25bc6-136">You should use the **get-interceptor** command to create a backup of existing interceptor configurations before using the **–Force:True** parameter.</span></span>  
  
 <span data-ttu-id="25bc6-137">**使用例**</span><span class="sxs-lookup"><span data-stu-id="25bc6-137">**Examples**</span></span>  
  
```  
bm.exe deploy-interceptor  -FileName:myInceptor.xml  
bm.exe deploy-interceptor  -FileName:myInceptor.xml -Force:True  
```  
  
## <a name="get-interceptorlist-command"></a><span data-ttu-id="25bc6-138">get-interceptorlist コマンド</span><span class="sxs-lookup"><span data-stu-id="25bc6-138">get-interceptorlist Command</span></span>  
 <span data-ttu-id="25bc6-139">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="25bc6-139">**Usage**</span></span>  
  
 <span data-ttu-id="25bc6-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-Database:\<database\>]**</span><span class="sxs-lookup"><span data-stu-id="25bc6-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="25bc6-141">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="25bc6-141">**Parameters**</span></span>  
  
|<span data-ttu-id="25bc6-142">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25bc6-142">Parameter</span></span>|<span data-ttu-id="25bc6-143">説明</span><span class="sxs-lookup"><span data-stu-id="25bc6-143">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25bc6-144">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="25bc6-144">Server:\<server\></span></span>|<span data-ttu-id="25bc6-145">省略可能:展開されたインターセプターの一覧を返す元のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-145">Optional: The name of the server from which to return a list of deployed interceptors.</span></span> <span data-ttu-id="25bc6-146">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="25bc6-146">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="25bc6-147">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="25bc6-147">Database:\<database\></span></span>|<span data-ttu-id="25bc6-148">省略可能:展開されたインターセプターの取得元となる BAM プライマリ インポート データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-148">Optional: The name of the BAM Primary Import database from which to retrieve the deployed interceptors.</span></span>|  
  
 <span data-ttu-id="25bc6-149">このコマンドは、アクティビティおよびインターセプションが有効になっている、関連付けられたイベント ソースの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-149">This command returns a list of the activities, and their associated event sources, for which interception is enabled.</span></span>  
  
 <span data-ttu-id="25bc6-150">**例**</span><span class="sxs-lookup"><span data-stu-id="25bc6-150">**Example**</span></span>  
  
```  
bm.exe get-interceptorlist   
```  
  
## <a name="get-interceptor-command"></a><span data-ttu-id="25bc6-151">get-interceptor コマンド</span><span class="sxs-lookup"><span data-stu-id="25bc6-151">get-interceptor Command</span></span>  
 <span data-ttu-id="25bc6-152">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="25bc6-152">**Usage**</span></span>  
  
 <span data-ttu-id="25bc6-153">**bm.exe の get インターセプター [-サーバー:\<server\>] [-データベース:\<データベース\>]-filename:\<構成 XML ファイル名\>[-アクティビティ。\<アクティビティ名\>] [-EventSource:\<イベント ソース名\>]**</span><span class="sxs-lookup"><span data-stu-id="25bc6-153">**bm.exe get-interceptor [-Server:\<server\>] [-Database:\<database\>] -FileName: \<Configuration XML Filename\> [ -Activity: \<Activity Name\>] [-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="25bc6-154">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="25bc6-154">**Parameters**</span></span>  
  
|<span data-ttu-id="25bc6-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25bc6-155">Parameter</span></span>|<span data-ttu-id="25bc6-156">説明</span><span class="sxs-lookup"><span data-stu-id="25bc6-156">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25bc6-157">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="25bc6-157">Server:\<server\></span></span>|<span data-ttu-id="25bc6-158">省略可能:展開されたインターセプターの取得元となるサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-158">Optional: The name of the server from which to retrieve the deployed interceptor.</span></span> <span data-ttu-id="25bc6-159">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="25bc6-159">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="25bc6-160">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="25bc6-160">Database:\<database\></span></span>|<span data-ttu-id="25bc6-161">省略可能:展開されたインターセプターの取得元となる BAM プライマリ インポート データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-161">Optional: The name of the BAM Primary Import database from which to retrieve deployed interceptor.</span></span>|  
|<span data-ttu-id="25bc6-162">ファイル名:\<構成 XML ファイル名\></span><span class="sxs-lookup"><span data-stu-id="25bc6-162">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="25bc6-163">インターセプター構成を記述する XML ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-163">The name of the XML file to which to write the interceptor configuration.</span></span>|  
|<span data-ttu-id="25bc6-164">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="25bc6-164">Activity:\<Activity Name\></span></span>|<span data-ttu-id="25bc6-165">省略可能:構成されたインターセプターを返す対象のアクティビティを指定します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-165">Optional: Specifies the activity for which to return the configured interceptor.</span></span> <span data-ttu-id="25bc6-166">組み合わせて使用できる、 **EventSource**パラメーターを返す構成をさらに詳しく指定できます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-166">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="25bc6-167">EventSource:\<イベント ソース名\></span><span class="sxs-lookup"><span data-stu-id="25bc6-167">EventSource:\<Event Source Name\></span></span>|<span data-ttu-id="25bc6-168">省略可能:構成されたインターセプターを返す対象のイベント ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-168">Optional: Specifies the event source for which to return the configured interceptor.</span></span> <span data-ttu-id="25bc6-169">組み合わせて使用できる、**アクティビティ**パラメーターを返す構成をさらに詳しく指定できます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-169">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="25bc6-170">アクティビティ名、またはイベント ソース名が指定されていない場合は、すべてのイベント ソースとアクティビティに対するインターセプター構成を含む有効な構成ファイルが返されます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-170">If no activity name or event source name is provided, the command returns a valid configuration file containing the interceptor configurations for all event sources and activities.</span></span>  
  
 <span data-ttu-id="25bc6-171">場合のみ、アクティビティ名を指定すると、コマンドはそのアクティビティのすべてのイベント ソースの構成ファイル、有効なインターセプターを返します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-171">If only an activity name is provided, the command returns a valid interceptor configuration file for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="25bc6-172">のみ、イベント ソースの名前を指定すると、コマンドは、ファイルを返します有効なインターセプター構成したイベント ソースのすべてのアクティビティ間で。</span><span class="sxs-lookup"><span data-stu-id="25bc6-172">If only an event source name is provided, the command returns a valid interceptor configuration file for that event source across all activities.</span></span>  
  
 <span data-ttu-id="25bc6-173">アクティビティ名とイベント ソース名の両方を指定しない場合、コマンドを返します有効なインターセプターそのアクティビティには、そのイベント ソースの構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="25bc6-173">If both an activity name and an event source name are provided, then the command returns a valid interceptor configuration file for that event source for that activity.</span></span>  
  
 <span data-ttu-id="25bc6-174">**使用例**</span><span class="sxs-lookup"><span data-stu-id="25bc6-174">**Examples**</span></span>  
  
```  
bm.exe get-interceptor   
bm.exe get-interceptor  -Activity:ShippingPO  
```  
  
## <a name="remove-interceptor-command"></a><span data-ttu-id="25bc6-175">remove-interceptor コマンド</span><span class="sxs-lookup"><span data-stu-id="25bc6-175">remove-interceptor Command</span></span>  
 <span data-ttu-id="25bc6-176">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="25bc6-176">**Usage**</span></span>  
  
 <span data-ttu-id="25bc6-177">**bm.exe の削除インターセプター [-サーバー:\<server\>] [-データベース:\<データベース\>] [-アクティビティ。\<アクティビティ名\>] [-EventSource:\<イベント ソース名\>]**</span><span class="sxs-lookup"><span data-stu-id="25bc6-177">**bm.exe remove-interceptor [-Server:\<server\>] [-Database:\<database\>] [ -Activity: \<Activity Name\>][-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="25bc6-178">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="25bc6-178">**Parameters**</span></span>  
  
|<span data-ttu-id="25bc6-179">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25bc6-179">Parameter</span></span>|<span data-ttu-id="25bc6-180">説明</span><span class="sxs-lookup"><span data-stu-id="25bc6-180">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25bc6-181">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="25bc6-181">Server:\<server\></span></span>|<span data-ttu-id="25bc6-182">省略可能:インターセプターが構成されているサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-182">Optional: The name of the server on which the interceptor is configured.</span></span> <span data-ttu-id="25bc6-183">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="25bc6-183">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="25bc6-184">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="25bc6-184">Database:\<database\></span></span>|<span data-ttu-id="25bc6-185">省略可能:インターセプターが構成されているデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="25bc6-185">Optional: The name of the database on which the interceptor is configured.</span></span>|  
|<span data-ttu-id="25bc6-186">アクティビティ:\<アクティビティ名\></span><span class="sxs-lookup"><span data-stu-id="25bc6-186">Activity: \<Activity Name\></span></span>|<span data-ttu-id="25bc6-187">省略可能:指定のインターセプターを削除するアクティビティを指定します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-187">Optional: Specifies the activity for which to remove the specified interceptor.</span></span> <span data-ttu-id="25bc6-188">組み合わせて使用できる、 **EventSource**パラメーターを返す構成をさらに詳しく指定できます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-188">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="25bc6-189">EventSource:\<イベント ソース名\></span><span class="sxs-lookup"><span data-stu-id="25bc6-189">EventSource: \<Event Source Name\></span></span>|<span data-ttu-id="25bc6-190">省略可能:指定のインターセプターを削除するイベント ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="25bc6-190">Optional: Specifies the event source for which to remove the specified interceptor.</span></span> <span data-ttu-id="25bc6-191">組み合わせて使用できる、**アクティビティ**パラメーターを返す構成をさらに詳しく指定できます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-191">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="25bc6-192">場合のみ、アクティビティ名を指定すると、そのアクティビティのすべてのイベント ソースのインターセプターが削除されます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-192">If only an activity name is provided, the command removes the interceptor for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="25bc6-193">場合のみ、イベント ソースの名前を指定すると、すべてのアクティビティのイベント ソース部分のみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="25bc6-193">If only an event source name is provided, the command removes only that event source portion for all activities.</span></span>  
  
 <span data-ttu-id="25bc6-194">**例**</span><span class="sxs-lookup"><span data-stu-id="25bc6-194">**Example**</span></span>  
  
```  
bm.exe remove-interceptor   
```  
  
## <a name="see-also"></a><span data-ttu-id="25bc6-195">参照</span><span class="sxs-lookup"><span data-stu-id="25bc6-195">See Also</span></span>  
 [<span data-ttu-id="25bc6-196">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="25bc6-196">BAM Management Utility</span></span>](../core/bam-management-utility.md)
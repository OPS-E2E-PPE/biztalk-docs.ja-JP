---
title: アラートの管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 651bc1d0df943df022cf597bb7292cb3143ad327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359302"
---
# <a name="alert-management-commands"></a><span data-ttu-id="89d87-102">警告管理コマンド</span><span class="sxs-lookup"><span data-stu-id="89d87-102">Alert Management Commands</span></span>
<span data-ttu-id="89d87-103">BAM 管理ユーティリティの警告管理コマンドを使用すると、展開済みの警告を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89d87-103">The BAM management utility alert management commands allow you to work with deployed alerts.</span></span>  
  
-   <span data-ttu-id="89d87-104">get アラート:展開済みの警告の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="89d87-104">get-alerts: Get a list of deployed alerts.</span></span>  
  
-   <span data-ttu-id="89d87-105">削除通知:警告を削除します。</span><span class="sxs-lookup"><span data-stu-id="89d87-105">remove-alerts: Removes an alert.</span></span>  
  
-   <span data-ttu-id="89d87-106">有効にするアラート:ビューの警告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="89d87-106">enable-alerts: Enables alerts on a view.</span></span>  
  
-   <span data-ttu-id="89d87-107">無効にするアラート:ビューの警告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="89d87-107">disable-alerts: Disables alerts on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89d87-108">含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="89d87-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="89d87-109">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="89d87-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="89d87-110">スイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="89d87-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89d87-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="89d87-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-alerts-command"></a><span data-ttu-id="89d87-112">get-alerts コマンド</span><span class="sxs-lookup"><span data-stu-id="89d87-112">get-alerts Command</span></span>  
 <span data-ttu-id="89d87-113">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="89d87-113">**Usage**</span></span>  
  
 <span data-ttu-id="89d87-114">**bm.exe の get アラート [-ビュー:\<ビュー名\>] [-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="89d87-114">**bm.exe get-alerts [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="89d87-115">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="89d87-115">**Parameters**</span></span>  
  
|<span data-ttu-id="89d87-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="89d87-116">Parameter</span></span>|<span data-ttu-id="89d87-117">説明</span><span class="sxs-lookup"><span data-stu-id="89d87-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89d87-118">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="89d87-118">View:\<view name\></span></span>|<span data-ttu-id="89d87-119">アラートの一覧の取得元のビューの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-119">The name of the view from which to get the list of alerts.</span></span>|  
|<span data-ttu-id="89d87-120">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="89d87-120">Server:\<server\></span></span>|<span data-ttu-id="89d87-121">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-121">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="89d87-122">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="89d87-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="89d87-123">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d87-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="89d87-124">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="89d87-124">Database:\<database\></span></span>|<span data-ttu-id="89d87-125">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-125">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="89d87-126">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d87-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="89d87-127">コマンドを実行するコンピューターで定義された警告を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="89d87-127">Lists the alerts defined on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="89d87-128">**使用例**</span><span class="sxs-lookup"><span data-stu-id="89d87-128">**Examples**</span></span>  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a><span data-ttu-id="89d87-129">remove-alerts コマンド</span><span class="sxs-lookup"><span data-stu-id="89d87-129">remove-alerts Command</span></span>  
 <span data-ttu-id="89d87-130">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="89d87-130">**Usage**</span></span>  
  
 <span data-ttu-id="89d87-131">**bm.exe 削除-アラートの表示:\<ビュー名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="89d87-131">**bm.exe remove-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="89d87-132">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="89d87-132">**Parameters**</span></span>  
  
|<span data-ttu-id="89d87-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="89d87-133">Parameter</span></span>|<span data-ttu-id="89d87-134">説明</span><span class="sxs-lookup"><span data-stu-id="89d87-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89d87-135">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="89d87-135">View:\<view name\></span></span>|<span data-ttu-id="89d87-136">アラートを削除するビューの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-136">The name of the view from which to remove alerts.</span></span>|  
|<span data-ttu-id="89d87-137">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="89d87-137">Server:\<server\></span></span>|<span data-ttu-id="89d87-138">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-138">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="89d87-139">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="89d87-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="89d87-140">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d87-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="89d87-141">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="89d87-141">Database:\<database\></span></span>|<span data-ttu-id="89d87-142">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-142">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="89d87-143">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d87-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="89d87-144">すべての警告を指定されたビューを削除します。</span><span class="sxs-lookup"><span data-stu-id="89d87-144">Removes all alerts on the specified view.</span></span>  
  
 <span data-ttu-id="89d87-145">**使用例**</span><span class="sxs-lookup"><span data-stu-id="89d87-145">**Examples**</span></span>  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a><span data-ttu-id="89d87-146">enable-alerts コマンド</span><span class="sxs-lookup"><span data-stu-id="89d87-146">enable-alerts Command</span></span>  
 <span data-ttu-id="89d87-147">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="89d87-147">**Usage**</span></span>  
  
 <span data-ttu-id="89d87-148">**bm.exe の有効にするアラートの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="89d87-148">**bm.exe enable-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="89d87-149">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="89d87-149">**Parameters**</span></span>  
  
|<span data-ttu-id="89d87-150">パラメーター</span><span class="sxs-lookup"><span data-stu-id="89d87-150">Parameter</span></span>|<span data-ttu-id="89d87-151">説明</span><span class="sxs-lookup"><span data-stu-id="89d87-151">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89d87-152">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="89d87-152">View:\<view name\></span></span>|<span data-ttu-id="89d87-153">アラートを有効にするビューの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-153">The name of the view on which to enable alerts.</span></span>|  
|<span data-ttu-id="89d87-154">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="89d87-154">Server:\<server\></span></span>|<span data-ttu-id="89d87-155">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-155">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="89d87-156">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="89d87-156">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="89d87-157">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d87-157">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="89d87-158">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="89d87-158">Database:\<database\></span></span>|<span data-ttu-id="89d87-159">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-159">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="89d87-160">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d87-160">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="89d87-161">指定されたビューの警告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="89d87-161">Enables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="89d87-162">**使用例**</span><span class="sxs-lookup"><span data-stu-id="89d87-162">**Examples**</span></span>  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a><span data-ttu-id="89d87-163">disable-alerts コマンド</span><span class="sxs-lookup"><span data-stu-id="89d87-163">disable-alerts Command</span></span>  
 <span data-ttu-id="89d87-164">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="89d87-164">**Usage**</span></span>  
  
 <span data-ttu-id="89d87-165">**bm.exe の無効にするアラートの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="89d87-165">**bm.exe disable-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="89d87-166">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="89d87-166">**Parameters**</span></span>  
  
|<span data-ttu-id="89d87-167">パラメーター</span><span class="sxs-lookup"><span data-stu-id="89d87-167">Parameter</span></span>|<span data-ttu-id="89d87-168">説明</span><span class="sxs-lookup"><span data-stu-id="89d87-168">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89d87-169">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="89d87-169">View:\<view name\></span></span>|<span data-ttu-id="89d87-170">アラートを無効にするビューの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-170">The name of the view on which to disable alerts.</span></span>|  
|<span data-ttu-id="89d87-171">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="89d87-171">Server:\<server\></span></span>|<span data-ttu-id="89d87-172">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-172">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="89d87-173">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="89d87-173">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="89d87-174">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d87-174">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="89d87-175">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="89d87-175">Database:\<database\></span></span>|<span data-ttu-id="89d87-176">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="89d87-176">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="89d87-177">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89d87-177">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="89d87-178">指定されたビューの警告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="89d87-178">Disables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="89d87-179">**使用例**</span><span class="sxs-lookup"><span data-stu-id="89d87-179">**Examples**</span></span>  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="89d87-180">参照</span><span class="sxs-lookup"><span data-stu-id="89d87-180">See Also</span></span>  
 [<span data-ttu-id="89d87-181">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="89d87-181">BAM Management Utility</span></span>](../core/bam-management-utility.md)
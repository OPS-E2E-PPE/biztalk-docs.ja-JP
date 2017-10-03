---
title: "アラートの管理コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b73129d884fea81bdb64609de5e95570275a344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="alert-management-commands"></a><span data-ttu-id="f9bdf-102">警告管理コマンド</span><span class="sxs-lookup"><span data-stu-id="f9bdf-102">Alert Management Commands</span></span>
<span data-ttu-id="f9bdf-103">BAM 管理ユーティリティの警告管理コマンドを使用すると、展開済みの警告を操作することができます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-103">The BAM management utility alert management commands allow you to work with deployed alerts.</span></span>  
  
-   <span data-ttu-id="f9bdf-104">get アラート: 展開済みの警告の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-104">get-alerts: Get a list of deployed alerts.</span></span>  
  
-   <span data-ttu-id="f9bdf-105">削除するアラート: 警告を削除します。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-105">remove-alerts: Removes an alert.</span></span>  
  
-   <span data-ttu-id="f9bdf-106">有効にするアラート: 警告ビューを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-106">enable-alerts: Enables alerts on a view.</span></span>  
  
-   <span data-ttu-id="f9bdf-107">無効にするアラート: ビューの警告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-107">disable-alerts: Disables alerts on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9bdf-108">含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で & #124 オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="f9bdf-109">Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="f9bdf-110">このスイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9bdf-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-alerts-command"></a><span data-ttu-id="f9bdf-112">get-alerts コマンド</span><span class="sxs-lookup"><span data-stu-id="f9bdf-112">get-alerts Command</span></span>  
 <span data-ttu-id="f9bdf-113">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-113">**Usage**</span></span>  
  
 <span data-ttu-id="f9bdf-114">**bm.exe get アラート [-ビュー:\<ビュー名 >] [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-114">**bm.exe get-alerts [ -View:\<view name> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f9bdf-115">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-115">**Parameters**</span></span>  
  
|<span data-ttu-id="f9bdf-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9bdf-116">Parameter</span></span>|<span data-ttu-id="f9bdf-117">Description</span><span class="sxs-lookup"><span data-stu-id="f9bdf-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9bdf-118">ビュー:\<ビュー名 ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-118">View:\<view name></span></span>|<span data-ttu-id="f9bdf-119">警告の一覧を取得するビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-119">The name of the view from which to get the list of alerts.</span></span>|  
|<span data-ttu-id="f9bdf-120">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-120">Server:\<server></span></span>|<span data-ttu-id="f9bdf-121">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-121">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="f9bdf-122">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f9bdf-123">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f9bdf-124">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-124">Database:\<database></span></span>|<span data-ttu-id="f9bdf-125">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-125">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="f9bdf-126">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f9bdf-127">コマンドを実行するコンピューターで定義されている警告を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-127">Lists the alerts defined on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="f9bdf-128">**使用例**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-128">**Examples**</span></span>  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a><span data-ttu-id="f9bdf-129">remove-alerts コマンド</span><span class="sxs-lookup"><span data-stu-id="f9bdf-129">remove-alerts Command</span></span>  
 <span data-ttu-id="f9bdf-130">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-130">**Usage**</span></span>  
  
 <span data-ttu-id="f9bdf-131">**bm.exe 削除アラートの表示:\<ビュー名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-131">**bm.exe remove-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f9bdf-132">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-132">**Parameters**</span></span>  
  
|<span data-ttu-id="f9bdf-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9bdf-133">Parameter</span></span>|<span data-ttu-id="f9bdf-134">Description</span><span class="sxs-lookup"><span data-stu-id="f9bdf-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9bdf-135">ビュー:\<ビュー名 ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-135">View:\<view name></span></span>|<span data-ttu-id="f9bdf-136">警告を削除するビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-136">The name of the view from which to remove alerts.</span></span>|  
|<span data-ttu-id="f9bdf-137">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-137">Server:\<server></span></span>|<span data-ttu-id="f9bdf-138">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-138">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="f9bdf-139">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f9bdf-140">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f9bdf-141">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-141">Database:\<database></span></span>|<span data-ttu-id="f9bdf-142">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-142">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="f9bdf-143">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f9bdf-144">指定されたビューから、すべての警告を削除します。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-144">Removes all alerts on the specified view.</span></span>  
  
 <span data-ttu-id="f9bdf-145">**使用例**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-145">**Examples**</span></span>  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a><span data-ttu-id="f9bdf-146">enable-alerts コマンド</span><span class="sxs-lookup"><span data-stu-id="f9bdf-146">enable-alerts Command</span></span>  
 <span data-ttu-id="f9bdf-147">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-147">**Usage**</span></span>  
  
 <span data-ttu-id="f9bdf-148">**bm.exe 有効にするアラートの表示:\<ビュー名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-148">**bm.exe enable-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f9bdf-149">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-149">**Parameters**</span></span>  
  
|<span data-ttu-id="f9bdf-150">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9bdf-150">Parameter</span></span>|<span data-ttu-id="f9bdf-151">Description</span><span class="sxs-lookup"><span data-stu-id="f9bdf-151">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9bdf-152">ビュー:\<ビュー名 ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-152">View:\<view name></span></span>|<span data-ttu-id="f9bdf-153">警告を有効にするビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-153">The name of the view on which to enable alerts.</span></span>|  
|<span data-ttu-id="f9bdf-154">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-154">Server:\<server></span></span>|<span data-ttu-id="f9bdf-155">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-155">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="f9bdf-156">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-156">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f9bdf-157">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-157">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f9bdf-158">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-158">Database:\<database></span></span>|<span data-ttu-id="f9bdf-159">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-159">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="f9bdf-160">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-160">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f9bdf-161">指定されたビューの警告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-161">Enables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="f9bdf-162">**使用例**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-162">**Examples**</span></span>  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a><span data-ttu-id="f9bdf-163">disable-alerts コマンド</span><span class="sxs-lookup"><span data-stu-id="f9bdf-163">disable-alerts Command</span></span>  
 <span data-ttu-id="f9bdf-164">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-164">**Usage**</span></span>  
  
 <span data-ttu-id="f9bdf-165">**bm.exe 無効にするアラートの表示:\<ビュー名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-165">**bm.exe disable-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="f9bdf-166">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-166">**Parameters**</span></span>  
  
|<span data-ttu-id="f9bdf-167">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9bdf-167">Parameter</span></span>|<span data-ttu-id="f9bdf-168">Description</span><span class="sxs-lookup"><span data-stu-id="f9bdf-168">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9bdf-169">ビュー:\<ビュー名 ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-169">View:\<view name></span></span>|<span data-ttu-id="f9bdf-170">警告を無効にするビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-170">The name of the view on which to disable alerts.</span></span>|  
|<span data-ttu-id="f9bdf-171">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-171">Server:\<server></span></span>|<span data-ttu-id="f9bdf-172">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-172">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="f9bdf-173">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-173">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f9bdf-174">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-174">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f9bdf-175">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="f9bdf-175">Database:\<database></span></span>|<span data-ttu-id="f9bdf-176">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-176">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="f9bdf-177">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-177">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f9bdf-178">指定されたビューの警告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f9bdf-178">Disables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="f9bdf-179">**使用例**</span><span class="sxs-lookup"><span data-stu-id="f9bdf-179">**Examples**</span></span>  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9bdf-180">参照</span><span class="sxs-lookup"><span data-stu-id="f9bdf-180">See Also</span></span>  
 [<span data-ttu-id="f9bdf-181">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="f9bdf-181">BAM Management Utility</span></span>](../core/bam-management-utility.md)
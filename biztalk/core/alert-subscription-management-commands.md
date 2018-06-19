---
title: アラートのサブスクリプション管理コマンド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cd6ad27-6217-466a-b616-4b26fb31b0af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02234637e38bb59e71c0f435ee24feef39e09e91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966656"
---
# <a name="alert-subscription-management-commands"></a><span data-ttu-id="b0429-102">警告サブスクリプション管理コマンド</span><span class="sxs-lookup"><span data-stu-id="b0429-102">Alert Subscription Management Commands</span></span>
<span data-ttu-id="b0429-103">BAM 管理ユーティリティのサブスクリプション管理コマンドを使用すると、警告サブスクリプションを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="b0429-103">The BAM management utility subscription management commands allow you to work with alert subscriptions.</span></span>  
  
-   <span data-ttu-id="b0429-104">get サブスクリプション: サブスクライバーは、アラートの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b0429-104">get-subscription: Gets a list of subscribers to an alert.</span></span>  
  
-   <span data-ttu-id="b0429-105">サブスクリプションの追加: アラートにサブスクライバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0429-105">add-subscription: Adds a subscriber to an alert.</span></span>  
  
-   <span data-ttu-id="b0429-106">削除するサブスクリプション: サブスクライバーを警告から削除します。</span><span class="sxs-lookup"><span data-stu-id="b0429-106">remove-subscription: Removes a subscriber from an alert.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0429-107">含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="b0429-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="b0429-108">Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b0429-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="b0429-109">このスイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0429-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0429-110">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0429-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-subscription-command"></a><span data-ttu-id="b0429-111">get-subscription コマンド</span><span class="sxs-lookup"><span data-stu-id="b0429-111">get-subscription Command</span></span>  
 <span data-ttu-id="b0429-112">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="b0429-112">**Usage**</span></span>  
  
 <span data-ttu-id="b0429-113">**bm.exe get サブスクリプション-ビュー:\<ビュー名\>-警告:\<警告名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="b0429-113">**bm.exe get-subscriptions -View:\<view name\> -Alert:\<alert name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="b0429-114">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b0429-114">**Parameters**</span></span>  
  
|<span data-ttu-id="b0429-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0429-115">Parameter</span></span>|<span data-ttu-id="b0429-116">Description</span><span class="sxs-lookup"><span data-stu-id="b0429-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0429-117">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="b0429-117">View:\<view name\></span></span>|<span data-ttu-id="b0429-118">指定できますが、アラート ビューの名前。</span><span class="sxs-lookup"><span data-stu-id="b0429-118">The name of the view on which the alert is to be specified.</span></span>|  
|<span data-ttu-id="b0429-119">警告:\<アラート名\></span><span class="sxs-lookup"><span data-stu-id="b0429-119">Alert:\<alert name\></span></span>|<span data-ttu-id="b0429-120">サブスクリプションを取得する警告の名前です。</span><span class="sxs-lookup"><span data-stu-id="b0429-120">The name of the alert from which to get the subscription.</span></span>|  
|<span data-ttu-id="b0429-121">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="b0429-121">Server:\<server\></span></span>|<span data-ttu-id="b0429-122">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="b0429-122">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="b0429-123">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0429-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="b0429-124">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0429-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="b0429-125">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="b0429-125">Database:\<database\></span></span>|<span data-ttu-id="b0429-126">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="b0429-126">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="b0429-127">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0429-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="b0429-128">指定した警告のすべてのサブスクライバーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b0429-128">Lists all the subscribers to the specified alert.</span></span>  
  
 <span data-ttu-id="b0429-129">**使用例**</span><span class="sxs-lookup"><span data-stu-id="b0429-129">**Examples**</span></span>  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a><span data-ttu-id="b0429-130">add-subscription コマンド</span><span class="sxs-lookup"><span data-stu-id="b0429-130">add-subscription Command</span></span>  
 <span data-ttu-id="b0429-131">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="b0429-131">**Usage**</span></span>  
  
 <span data-ttu-id="b0429-132">**bm.exe - サブスクリプションの追加-ビュー:\<ビュー名\>-警告:\<警告名\>-accountname:\<アカウント名\>-型: [ファイル (&) #124 です。Email] [-電子メール:\<電子メール アドレス\>] [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="b0429-132">**bm.exe add-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\> -Type: [ File &#124; Email ][ -Email:\<e-mail address\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="b0429-133">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b0429-133">**Parameters**</span></span>  
  
|<span data-ttu-id="b0429-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0429-134">Parameter</span></span>|<span data-ttu-id="b0429-135">Description</span><span class="sxs-lookup"><span data-stu-id="b0429-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0429-136">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="b0429-136">View:\<view name\></span></span>|<span data-ttu-id="b0429-137">警告が指定されたビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="b0429-137">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="b0429-138">警告:\<アラート名\></span><span class="sxs-lookup"><span data-stu-id="b0429-138">Alert:\<alert name\></span></span>|<span data-ttu-id="b0429-139">サブスクライブする警告の名前です。</span><span class="sxs-lookup"><span data-stu-id="b0429-139">The name of the alert to which to subscribe.</span></span>|  
|<span data-ttu-id="b0429-140">AccountName:\<アカウント名\></span><span class="sxs-lookup"><span data-stu-id="b0429-140">AccountName:\<account name\></span></span>|<span data-ttu-id="b0429-141">警告をサブスクライブするアカウント (domain\user 形式) です。</span><span class="sxs-lookup"><span data-stu-id="b0429-141">The account, in domain\user format, to subscribe to the alert.</span></span>|  
|<span data-ttu-id="b0429-142">型: [ファイル (&) #124 です。電子メール]</span><span class="sxs-lookup"><span data-stu-id="b0429-142">Type: [ File &#124; Email ]</span></span>|<span data-ttu-id="b0429-143">警告の配信方法です。</span><span class="sxs-lookup"><span data-stu-id="b0429-143">The delivery type of the alert.</span></span> <span data-ttu-id="b0429-144">配信方法として電子メールを指定した場合は、Email パラメーターも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0429-144">If you specify a delivery type of e-mail, you must include the e-mail parameter on the command line.</span></span>|  
|<span data-ttu-id="b0429-145">電子メール:\<電子メール アドレス\></span><span class="sxs-lookup"><span data-stu-id="b0429-145">Email:\<e-mail address\></span></span>|<span data-ttu-id="b0429-146">省略可能: アラートの通知を配信する電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="b0429-146">Optional: The email address to which the alert notification will be delivered.</span></span>|  
|<span data-ttu-id="b0429-147">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="b0429-147">Server:\<server\></span></span>|<span data-ttu-id="b0429-148">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="b0429-148">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="b0429-149">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0429-149">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="b0429-150">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0429-150">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="b0429-151">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="b0429-151">Database:\<database\></span></span>|<span data-ttu-id="b0429-152">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="b0429-152">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="b0429-153">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0429-153">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="b0429-154">指定したアカウントに対し、特定の警告に対するサブスクリプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="b0429-154">Adds a subscription for the specified account to the specified alert.</span></span>  
  
 <span data-ttu-id="b0429-155">**使用例**</span><span class="sxs-lookup"><span data-stu-id="b0429-155">**Examples**</span></span>  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a><span data-ttu-id="b0429-156">remove-subscription コマンド</span><span class="sxs-lookup"><span data-stu-id="b0429-156">remove-subscription Command</span></span>  
 <span data-ttu-id="b0429-157">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="b0429-157">**Usage**</span></span>  
  
 <span data-ttu-id="b0429-158">**bm.exe 削除-サブスクリプション-ビュー:\<ビュー名\>-警告:\<警告名\>-accountname:\<アカウント名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="b0429-158">**bm.exe remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="b0429-159">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="b0429-159">**Parameters**</span></span>  
  
|<span data-ttu-id="b0429-160">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0429-160">Parameter</span></span>|<span data-ttu-id="b0429-161">Description</span><span class="sxs-lookup"><span data-stu-id="b0429-161">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0429-162">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="b0429-162">View:\<view name\></span></span>|<span data-ttu-id="b0429-163">警告が指定されたビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="b0429-163">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="b0429-164">警告:\<アラート名\></span><span class="sxs-lookup"><span data-stu-id="b0429-164">Alert:\<alert name\></span></span>|<span data-ttu-id="b0429-165">警告の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0429-165">The name of the alert.</span></span>|  
|<span data-ttu-id="b0429-166">AccountName:\<アカウント名\></span><span class="sxs-lookup"><span data-stu-id="b0429-166">AccountName:\<account name\></span></span>|<span data-ttu-id="b0429-167">警告から削除するアカウント (domain\user 形式) です。</span><span class="sxs-lookup"><span data-stu-id="b0429-167">The account, in domain\user format, to remove from the alert.</span></span>|  
|<span data-ttu-id="b0429-168">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="b0429-168">Server:\<server\></span></span>|<span data-ttu-id="b0429-169">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="b0429-169">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="b0429-170">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0429-170">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="b0429-171">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0429-171">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="b0429-172">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="b0429-172">Database:\<database\></span></span>|<span data-ttu-id="b0429-173">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="b0429-173">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="b0429-174">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0429-174">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="b0429-175">特定の警告から、指定したアカウントのサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="b0429-175">Removes the subscription of the specified account from the specified alert.</span></span> <span data-ttu-id="b0429-176">指定されたアカウントのすべてのサブスクリプションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b0429-176">All subscriptions for the specified account are removed.</span></span>  
  
 <span data-ttu-id="b0429-177">**使用例**</span><span class="sxs-lookup"><span data-stu-id="b0429-177">**Examples**</span></span>  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0429-178">参照</span><span class="sxs-lookup"><span data-stu-id="b0429-178">See Also</span></span>  
 [<span data-ttu-id="b0429-179">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="b0429-179">BAM Management Utility</span></span>](../core/bam-management-utility.md)
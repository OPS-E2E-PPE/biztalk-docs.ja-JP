---
title: 警告サブスクリプション管理コマンド |Microsoft Docs
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
ms.openlocfilehash: e0ffcfea22ac63f3a8f4eb22aaeeae3513705ab2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359274"
---
# <a name="alert-subscription-management-commands"></a><span data-ttu-id="04472-102">警告サブスクリプション管理コマンド</span><span class="sxs-lookup"><span data-stu-id="04472-102">Alert Subscription Management Commands</span></span>
<span data-ttu-id="04472-103">BAM 管理ユーティリティのサブスクリプション管理コマンドを使用すると、警告のサブスクリプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="04472-103">The BAM management utility subscription management commands allow you to work with alert subscriptions.</span></span>  
  
-   <span data-ttu-id="04472-104">get サブスクリプション:警告のサブスクライバーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="04472-104">get-subscription: Gets a list of subscribers to an alert.</span></span>  
  
-   <span data-ttu-id="04472-105">追加のサブスクリプション:アラートには、サブスクライバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="04472-105">add-subscription: Adds a subscriber to an alert.</span></span>  
  
-   <span data-ttu-id="04472-106">サブスクリプションの削除:アラートから、サブスクライバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="04472-106">remove-subscription: Removes a subscriber from an alert.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04472-107">含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="04472-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="04472-108">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="04472-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="04472-109">スイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="04472-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04472-110">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="04472-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-subscription-command"></a><span data-ttu-id="04472-111">get-subscription コマンド</span><span class="sxs-lookup"><span data-stu-id="04472-111">get-subscription Command</span></span>  
 <span data-ttu-id="04472-112">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="04472-112">**Usage**</span></span>  
  
 <span data-ttu-id="04472-113">**bm.exe の get サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="04472-113">**bm.exe get-subscriptions -View:\<view name\> -Alert:\<alert name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="04472-114">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="04472-114">**Parameters**</span></span>  
  
|<span data-ttu-id="04472-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04472-115">Parameter</span></span>|<span data-ttu-id="04472-116">説明</span><span class="sxs-lookup"><span data-stu-id="04472-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04472-117">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="04472-117">View:\<view name\></span></span>|<span data-ttu-id="04472-118">指定する、アラートがビューの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-118">The name of the view on which the alert is to be specified.</span></span>|  
|<span data-ttu-id="04472-119">アラート:\<アラート名\></span><span class="sxs-lookup"><span data-stu-id="04472-119">Alert:\<alert name\></span></span>|<span data-ttu-id="04472-120">サブスクリプションの取得元となるアラートの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-120">The name of the alert from which to get the subscription.</span></span>|  
|<span data-ttu-id="04472-121">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="04472-121">Server:\<server\></span></span>|<span data-ttu-id="04472-122">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-122">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="04472-123">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="04472-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="04472-124">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04472-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="04472-125">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="04472-125">Database:\<database\></span></span>|<span data-ttu-id="04472-126">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-126">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="04472-127">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04472-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="04472-128">指定した警告へのすべてのサブスクライバーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="04472-128">Lists all the subscribers to the specified alert.</span></span>  
  
 <span data-ttu-id="04472-129">**使用例**</span><span class="sxs-lookup"><span data-stu-id="04472-129">**Examples**</span></span>  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a><span data-ttu-id="04472-130">サブスクリプションの追加コマンド</span><span class="sxs-lookup"><span data-stu-id="04472-130">add-subscription Command</span></span>  
 <span data-ttu-id="04472-131">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="04472-131">**Usage**</span></span>  
  
 <span data-ttu-id="04472-132">**bm.exe の追加-サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>-accountname:\<アカウント名\>-型: [ファイル&#124;電子メール] [-電子メール:\<電子メールアドレス\>] [-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="04472-132">**bm.exe add-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\> -Type: [ File &#124; Email ][ -Email:\<e-mail address\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="04472-133">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="04472-133">**Parameters**</span></span>  
  
|<span data-ttu-id="04472-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04472-134">Parameter</span></span>|<span data-ttu-id="04472-135">説明</span><span class="sxs-lookup"><span data-stu-id="04472-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04472-136">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="04472-136">View:\<view name\></span></span>|<span data-ttu-id="04472-137">アラートが指定されているビューの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-137">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="04472-138">アラート:\<アラート名\></span><span class="sxs-lookup"><span data-stu-id="04472-138">Alert:\<alert name\></span></span>|<span data-ttu-id="04472-139">サブスクライブするアラートの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-139">The name of the alert to which to subscribe.</span></span>|  
|<span data-ttu-id="04472-140">AccountName:\<アカウント名\></span><span class="sxs-lookup"><span data-stu-id="04472-140">AccountName:\<account name\></span></span>|<span data-ttu-id="04472-141">Domain \user 形式で警告をサブスクライブするアカウントです。</span><span class="sxs-lookup"><span data-stu-id="04472-141">The account, in domain\user format, to subscribe to the alert.</span></span>|  
|<span data-ttu-id="04472-142">種類: [ファイル&#124;メール]</span><span class="sxs-lookup"><span data-stu-id="04472-142">Type: [ File &#124; Email ]</span></span>|<span data-ttu-id="04472-143">警告の配信の種類。</span><span class="sxs-lookup"><span data-stu-id="04472-143">The delivery type of the alert.</span></span> <span data-ttu-id="04472-144">電子メールの配信の種類を指定する場合は、コマンドラインで電子メールのパラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="04472-144">If you specify a delivery type of e-mail, you must include the e-mail parameter on the command line.</span></span>|  
|<span data-ttu-id="04472-145">電子メール:\<電子メール アドレス\></span><span class="sxs-lookup"><span data-stu-id="04472-145">Email:\<e-mail address\></span></span>|<span data-ttu-id="04472-146">省略可能:アラート通知の配信先の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="04472-146">Optional: The email address to which the alert notification will be delivered.</span></span>|  
|<span data-ttu-id="04472-147">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="04472-147">Server:\<server\></span></span>|<span data-ttu-id="04472-148">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-148">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="04472-149">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="04472-149">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="04472-150">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04472-150">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="04472-151">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="04472-151">Database:\<database\></span></span>|<span data-ttu-id="04472-152">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-152">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="04472-153">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04472-153">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="04472-154">指定した警告には、指定されたアカウントのサブスクリプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="04472-154">Adds a subscription for the specified account to the specified alert.</span></span>  
  
 <span data-ttu-id="04472-155">**使用例**</span><span class="sxs-lookup"><span data-stu-id="04472-155">**Examples**</span></span>  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a><span data-ttu-id="04472-156">remove-subscription コマンド</span><span class="sxs-lookup"><span data-stu-id="04472-156">remove-subscription Command</span></span>  
 <span data-ttu-id="04472-157">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="04472-157">**Usage**</span></span>  
  
 <span data-ttu-id="04472-158">**bm.exe の削除-サブスクリプション-ビュー:\<ビュー名\>-警告:\<アラート名\>-accountname:\<アカウント名\>[-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="04472-158">**bm.exe remove-subscription -View:\<view name\> -Alert:\<alert name\> -AccountName:\<account name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="04472-159">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="04472-159">**Parameters**</span></span>  
  
|<span data-ttu-id="04472-160">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04472-160">Parameter</span></span>|<span data-ttu-id="04472-161">説明</span><span class="sxs-lookup"><span data-stu-id="04472-161">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04472-162">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="04472-162">View:\<view name\></span></span>|<span data-ttu-id="04472-163">アラートが指定されているビューの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-163">The name of the view on which the alert is specified.</span></span>|  
|<span data-ttu-id="04472-164">アラート:\<アラート名\></span><span class="sxs-lookup"><span data-stu-id="04472-164">Alert:\<alert name\></span></span>|<span data-ttu-id="04472-165">警告の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="04472-165">The name of the alert.</span></span>|  
|<span data-ttu-id="04472-166">AccountName:\<アカウント名\></span><span class="sxs-lookup"><span data-stu-id="04472-166">AccountName:\<account name\></span></span>|<span data-ttu-id="04472-167">Domain \user 形式で、警告から削除するアカウントです。</span><span class="sxs-lookup"><span data-stu-id="04472-167">The account, in domain\user format, to remove from the alert.</span></span>|  
|<span data-ttu-id="04472-168">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="04472-168">Server:\<server\></span></span>|<span data-ttu-id="04472-169">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-169">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="04472-170">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="04472-170">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="04472-171">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04472-171">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="04472-172">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="04472-172">Database:\<database\></span></span>|<span data-ttu-id="04472-173">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="04472-173">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="04472-174">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="04472-174">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="04472-175">指定された警告から、指定されたアカウントのサブスクリプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="04472-175">Removes the subscription of the specified account from the specified alert.</span></span> <span data-ttu-id="04472-176">指定されたアカウントのすべてのサブスクリプションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="04472-176">All subscriptions for the specified account are removed.</span></span>  
  
 <span data-ttu-id="04472-177">**使用例**</span><span class="sxs-lookup"><span data-stu-id="04472-177">**Examples**</span></span>  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="04472-178">参照</span><span class="sxs-lookup"><span data-stu-id="04472-178">See Also</span></span>  
 [<span data-ttu-id="04472-179">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="04472-179">BAM Management Utility</span></span>](../core/bam-management-utility.md)
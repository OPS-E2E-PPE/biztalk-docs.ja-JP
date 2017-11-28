---
title: "ファイル アダプターに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aaf448c-0035-4648-910b-ae2f15106342
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2690803346efc5931a88acd70be9d24af107156f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-file-adapter"></a><span data-ttu-id="dc2e5-102">ファイル アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="dc2e5-102">Known Issues with the File Adapter</span></span>
<span data-ttu-id="dc2e5-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="dc2e5-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="dc2e5-104">Known Issues</span></span>  
  
#### <a name="a-file-receive-location-is-disabled"></a><span data-ttu-id="dc2e5-105">ファイルの受信場所が無効になる</span><span class="sxs-lookup"><span data-stu-id="dc2e5-105">A File Receive Location is Disabled</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="dc2e5-106">問題</span><span class="sxs-lookup"><span data-stu-id="dc2e5-106">Problem</span></span>  
 <span data-ttu-id="dc2e5-107">ファイルの受信場所が無効になります。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-107">A File receive location becomes disabled.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="dc2e5-108">原因</span><span class="sxs-lookup"><span data-stu-id="dc2e5-108">Cause</span></span>  
 <span data-ttu-id="dc2e5-109">次のいずれかが発生すると、ファイル受信アダプターは受信場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-109">The File receive adapter disables the receive location if any of the following occur:</span></span>  
  
-   <span data-ttu-id="dc2e5-110">指定されたパスが存在しないために、ファイル受信アダプターがファイル システム上またはネットワーク共有上の受信場所にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-110">The File receive adapter cannot access the receive location on the file system or network share because the specified path does not exist.</span></span> <span data-ttu-id="dc2e5-111">ネットワーク共有の場合、ファイル受信アダプターはすべての再試行が終了した後で、受信場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-111">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="dc2e5-112">関連付けられているホスト インスタンスで使用されるアカウントに、ファイル システム上またはネットワーク共有上の受信場所への読み取り/書き込みアクセス許可がないために、ファイル受信アダプターはその受信場所にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-112">The File receive adapter cannot access the receive location on the file system or network share because the account used by the associated host instance does not have read-write permission for that location.</span></span> <span data-ttu-id="dc2e5-113">ネットワーク共有の場合、ファイル受信アダプターはすべての再試行が終了した後で、受信場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-113">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="dc2e5-114">256 文字を超える名前のファイルが受信場所に存在します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-114">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="dc2e5-115">解決策</span><span class="sxs-lookup"><span data-stu-id="dc2e5-115">Resolution</span></span>  
  
-   <span data-ttu-id="dc2e5-116">指定されたパスまたは共有が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-116">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="dc2e5-117">として使用するアカウントを確認してください、**ログオン:**アカウントが、ファイル受信ハンドラーのホスト インスタンス用に読み取りし、書き込みのアクセス許可を指定した受信場所。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-117">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="dc2e5-118">ファイル受信アダプターが監視するフォルダーに書き込まれたファイルの名前が 256 文字を超えていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-118">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="files-are-not-being-read-from-the-specified-receive-location"></a><span data-ttu-id="dc2e5-119">ファイルの読み取りが、指定した受信場所から行われていない</span><span class="sxs-lookup"><span data-stu-id="dc2e5-119">Files Are Not Being Read from the Specified Receive Location</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="dc2e5-120">問題</span><span class="sxs-lookup"><span data-stu-id="dc2e5-120">Problem</span></span>  
 <span data-ttu-id="dc2e5-121">ファイル受信アダプターが、指定した受信場所からファイルを読み取りません。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-121">The File receive adapter does not read a file from the specified receive location.</span></span> <span data-ttu-id="dc2e5-122">ファイル受信アダプターでこのようなファイルが受信された場合、イベント ログにエラーが記録され、そのファイルは受信場所に残されます。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-122">When the File receive adapter encounters such a file, it logs an error in the event log and leaves the file in the receive location.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="dc2e5-123">原因</span><span class="sxs-lookup"><span data-stu-id="dc2e5-123">Cause</span></span>  
 <span data-ttu-id="dc2e5-124">次のいずれかの条件に該当すると、ファイル受信アダプターは受信場所からファイルを読み取りません。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-124">The File receive adapter does not read a file from the receive location if any of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="dc2e5-125">ファイルが読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-125">The file is read-only.</span></span>  
  
-   <span data-ttu-id="dc2e5-126">ファイルにシステム属性があります。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-126">The file has a system attribute.</span></span>  
  
-   <span data-ttu-id="dc2e5-127">ファイル受信アダプターに、ファイルの読み取りと書き込みのアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-127">The File receive adapter does not have permissions to read and write to the file.</span></span>  
  
-   <span data-ttu-id="dc2e5-128">256 文字を超える名前のファイルが受信場所に存在します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-128">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="dc2e5-129">解決策</span><span class="sxs-lookup"><span data-stu-id="dc2e5-129">Resolution</span></span>  
  
-   <span data-ttu-id="dc2e5-130">指定した受信場所のファイルが "読み取り専用" として設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-130">Ensure that the files in the specified receive location are not marked as "read only".</span></span>  
  
-   <span data-ttu-id="dc2e5-131">指定した受信場所のファイルにシステム属性が付いていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-131">Ensure that the files in the specified receive location are not marked with a system attribute.</span></span>  
  
-   <span data-ttu-id="dc2e5-132">として使用するアカウントを確認してください、**ログオン:**アカウントが、ファイル受信ハンドラーのホスト インスタンス用に読み取りし、書き込みのアクセス許可を指定した受信場所。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-132">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="dc2e5-133">ファイル受信アダプターが監視するフォルダーに書き込まれたファイルの名前が 256 文字を超えていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-133">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="messages-are-not-being-sent-by-the-file-send-adapter"></a><span data-ttu-id="dc2e5-134">ファイル送信アダプターでメッセージが送信されない</span><span class="sxs-lookup"><span data-stu-id="dc2e5-134">Messages Are Not Being Sent by the File Send Adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="dc2e5-135">問題</span><span class="sxs-lookup"><span data-stu-id="dc2e5-135">Problem</span></span>  
 <span data-ttu-id="dc2e5-136">ファイル送信アダプターが、指定したディレクトリまたはファイル共有にメッセージを送信できません。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-136">The File send adapter fails to send a message to the specified directory or file share.</span></span>  
  
 <span data-ttu-id="dc2e5-137">メッセージが指定したディレクトリやファイル共有に書き込まれない場合、BizTalk Server コンピューターのイベント ログにエラーが書き込まれ、イベントが次の順序で発生します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-137">If a message fails to be written to the specified directory or file share, an error is written to the Event log of the BizTalk server computer and the following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="dc2e5-138">ファイル送信アダプターは、書き込み操作を再試行します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-138">The File send adapter will retry the write operation.</span></span>  
  
2.  <span data-ttu-id="dc2e5-139">ファイル アダプターは、バックアップ トランスポート (構成されている場合) を使用してファイルの送信を試みます。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-139">The File adapter will attempt to deliver the file using the backup transport (if configured).</span></span>  
  
3.  <span data-ttu-id="dc2e5-140">メッセージが保留キューに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-140">The message will be written to the suspended queue.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="dc2e5-141">原因</span><span class="sxs-lookup"><span data-stu-id="dc2e5-141">Cause</span></span>  
  
-   <span data-ttu-id="dc2e5-142">指定されたパスが存在しないために、ファイル送信アダプターがファイル システム上またはネットワーク共有上のファイルの送信元ディレクトリにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-142">The File send adapter cannot access the directory that files are sent from on the file system or network share because the specified path does not exist.</span></span>  
  
-   <span data-ttu-id="dc2e5-143">関連付けられたホスト インスタンスに、ファイル システム上またはネットワーク共有上の送信先またはその送信先にあるファイルへの書き込みアクセス許可がないために、ファイル送信アダプターはその送信先にあるファイルへ書き込むことができません。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-143">The File send adapter cannot write to a file in the destination location on the file system or network share because the associated host instance does not have write permissions for that file or for that location.</span></span>  
  
-   <span data-ttu-id="dc2e5-144">ファイル送信アダプターは、読み取り専用またはでマークされたために指定されたファイルを書き込むことはできません、**システム**ファイル属性。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-144">The File send adapter cannot write to the file specified because it is read-only or is marked with the **system** file attribute.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="dc2e5-145">解決策</span><span class="sxs-lookup"><span data-stu-id="dc2e5-145">Resolution</span></span>  
  
-   <span data-ttu-id="dc2e5-146">指定されたパスまたは共有が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-146">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="dc2e5-147">として使用するアカウントを確認してください、**ログオン:**ファイル送信ハンドラーのホスト インスタンスのアカウントに読み取りし、書き込み権限を指定したディレクトリまたはファイル共有です。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-147">Ensure that the account used as the **Logon:** account for the File send handler host instance has read and write permissions to the specified directory or file share.</span></span>  
  
-   <span data-ttu-id="dc2e5-148">指定したディレクトリまたはファイル共有内の既存のファイルに、システム属性が付いていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-148">Ensure that existing files in the specified directory or file share are not marked with the system attribute.</span></span>  
  
#### <a name="sending-a-file-using-the-file-adapter-is-very-slow"></a><span data-ttu-id="dc2e5-149">ファイル アダプターを使用したファイル送信が著しく遅い</span><span class="sxs-lookup"><span data-stu-id="dc2e5-149">Sending a file using the File adapter is very slow</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="dc2e5-150">問題</span><span class="sxs-lookup"><span data-stu-id="dc2e5-150">Problem</span></span>  
 <span data-ttu-id="dc2e5-151">ファイル送信アダプターのパフォーマンスが低速の場合に、**書き込み時のキャッシュを許可**プロパティに設定されている**False**です。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-151">Performance of the File send adapter is slower when the **Allow cache on write** property is set to **False**.</span></span> <span data-ttu-id="dc2e5-152">**書き込み時のキャッシュを許可**プロパティに設定されている**False**既定です。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-152">The **Allow cache on write** property is set to **False** by default.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="dc2e5-153">原因</span><span class="sxs-lookup"><span data-stu-id="dc2e5-153">Cause</span></span>  
 <span data-ttu-id="dc2e5-154">設定、**書き込み時のキャッシュを許可**プロパティを**False**ようにこの設定には、オペレーティング システムでのファイルのメモリ内キャッシュの使用が許可されていません。 パフォーマンスが低下することができます。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-154">Setting the **Allow cache on write** property to **False** can reduce performance as this setting disallows the use of in-memory caching of files by the operating system.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="dc2e5-155">解決策</span><span class="sxs-lookup"><span data-stu-id="dc2e5-155">Resolution</span></span>  
 <span data-ttu-id="dc2e5-156">アダプターの変更を送信するファイルのパフォーマンスを向上させる、**書き込み時のキャッシュを許可**プロパティを**True** (チェック ボックスをオン) です。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-156">To increase performance of the File send adapter change the **Allow cache on write** property to **True** (check the box).</span></span> <span data-ttu-id="dc2e5-157">詳細については、**書き込み時のキャッシュを許可**プロパティを参照してください[File 送信ポートを構成する方法](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9)です。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-157">For more information about the **Allow cache on write** property, see [How to Configure a File Send Port](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc2e5-158">設定、**書き込み時のキャッシュを許可**プロパティを**True**オペレーティング システムで障害が発生した場合にデータ損失の可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-158">Setting the **Allow cache on write** property to **True** increases the possibility of data loss in the event that the operating system experiences a failure.</span></span> <span data-ttu-id="dc2e5-159">このシナリオでは、メモリ内ファイル キャッシュに保存されているデータがすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-159">In this scenario, any data that is stored in the in-memory file cache will be lost.</span></span>  
  
#### <a name="zero-byte-files-received-by-the-file-adapter-are-deleted"></a><span data-ttu-id="dc2e5-160">ファイル アダプターによって受信された 0 バイトのファイルが削除される</span><span class="sxs-lookup"><span data-stu-id="dc2e5-160">Zero byte files received by the File adapter are deleted</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="dc2e5-161">問題</span><span class="sxs-lookup"><span data-stu-id="dc2e5-161">Problem</span></span>  
 <span data-ttu-id="dc2e5-162">ファイル受信アダプターで空 (0 バイト) のファイルが取得されると、そのファイルが削除され、次のような警告が BizTalk Server のアプリケーション ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-162">If an empty (zero byte) file is picked up by the File receive adapter, the file is deleted and a warning similar to the following is written to the application log of the BizTalk server:</span></span>  
  
```  
Event Type:Warning  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:7182  
Date:8/30/2006  
Time:1:32:32 PM  
User:N/A  
Computer:BIZTALKSERVER  
Description:  
The FILE receive adapter deleted the empty file "C:\filesource\emptyfile.xml.BTS-WIP" without performing any processing.  
```  
  
##### <a name="cause"></a><span data-ttu-id="dc2e5-163">原因</span><span class="sxs-lookup"><span data-stu-id="dc2e5-163">Cause</span></span>  
 <span data-ttu-id="dc2e5-164">ファイル受信アダプターは、仕様により 0 バイトのファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-164">The File receive adapter deletes zero byte files by design.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="dc2e5-165">解決策</span><span class="sxs-lookup"><span data-stu-id="dc2e5-165">Resolution</span></span>  
 <span data-ttu-id="dc2e5-166">アクションは不要です。この動作は仕様によるものです。</span><span class="sxs-lookup"><span data-stu-id="dc2e5-166">No action is required, this behavior is by design.</span></span>
---
title: ファイル アダプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aaf448c-0035-4648-910b-ae2f15106342
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef5da0b47efc357da7b3e85f3ceb48f93f3845b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380778"
---
# <a name="known-issues-with-the-file-adapter"></a><span data-ttu-id="9a8e2-102">ファイル アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="9a8e2-102">Known Issues with the File Adapter</span></span>
<span data-ttu-id="9a8e2-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="9a8e2-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="9a8e2-104">Known Issues</span></span>  
  
#### <a name="a-file-receive-location-is-disabled"></a><span data-ttu-id="9a8e2-105">ファイルの受信場所が無効になっています</span><span class="sxs-lookup"><span data-stu-id="9a8e2-105">A File Receive Location is Disabled</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9a8e2-106">問題</span><span class="sxs-lookup"><span data-stu-id="9a8e2-106">Problem</span></span>  
 <span data-ttu-id="9a8e2-107">File 受信場所を無効になります。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-107">A File receive location becomes disabled.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="9a8e2-108">原因</span><span class="sxs-lookup"><span data-stu-id="9a8e2-108">Cause</span></span>  
 <span data-ttu-id="9a8e2-109">ファイル受信アダプターでは、次のいずれかが発生した場合、受信場所が無効にします。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-109">The File receive adapter disables the receive location if any of the following occur:</span></span>  
  
-   <span data-ttu-id="9a8e2-110">ネットワーク共有の指定されたパスが存在しないため、または、ファイル受信アダプターがファイル システム上の受信場所をアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-110">The File receive adapter cannot access the receive location on the file system or network share because the specified path does not exist.</span></span> <span data-ttu-id="9a8e2-111">ネットワーク共有の場合、ファイル受信アダプターでは、すべての再試行が終了している後に、受信場所が無効にします。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-111">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="9a8e2-112">ファイル受信アダプターがファイル システム上の受信場所にアクセスできない、またはネットワーク共有に関連付けられたホスト インスタンスによって使用されるアカウントにその場所に対する読み取り/書き込みのアクセス許可があるないためです。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-112">The File receive adapter cannot access the receive location on the file system or network share because the account used by the associated host instance does not have read-write permission for that location.</span></span> <span data-ttu-id="9a8e2-113">ネットワーク共有の場合、ファイル受信アダプターでは、すべての再試行が終了している後に、受信場所が無効にします。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-113">For a network share, the File receive adapter disables the receive location after all retry attempts have been exhausted.</span></span>  
  
-   <span data-ttu-id="9a8e2-114">受信場所では、256 文字より長い名前のファイルが検出されました。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-114">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9a8e2-115">解決策</span><span class="sxs-lookup"><span data-stu-id="9a8e2-115">Resolution</span></span>  
  
-   <span data-ttu-id="9a8e2-116">指定されたパスまたは共有が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-116">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="9a8e2-117">アカウントとして使用することを確認、**ログオン:** アカウントが、ファイル受信ハンドラーのホスト インスタンス用に読み取りし、書き込みのアクセス許可を指定した受信場所。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-117">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="9a8e2-118">ファイルの監視対象フォルダに書き込まれるファイル受信アダプターであることを確認します。 256 文字を超えるとファイル名がありません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-118">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="files-are-not-being-read-from-the-specified-receive-location"></a><span data-ttu-id="9a8e2-119">ファイルがないから読み取られる、指定した受信場所</span><span class="sxs-lookup"><span data-stu-id="9a8e2-119">Files Are Not Being Read from the Specified Receive Location</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9a8e2-120">問題</span><span class="sxs-lookup"><span data-stu-id="9a8e2-120">Problem</span></span>  
 <span data-ttu-id="9a8e2-121">ファイル受信アダプターは読み取ることができません、指定したファイルの受信場所。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-121">The File receive adapter does not read a file from the specified receive location.</span></span> <span data-ttu-id="9a8e2-122">ファイル受信アダプターには、このようなファイルが検出されると、イベント ログにエラーが記録し、ファイル受信場所のままになります。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-122">When the File receive adapter encounters such a file, it logs an error in the event log and leaves the file in the receive location.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="9a8e2-123">原因</span><span class="sxs-lookup"><span data-stu-id="9a8e2-123">Cause</span></span>  
 <span data-ttu-id="9a8e2-124">ファイル受信アダプターは、次の条件のいずれかに該当する場合も、受信場所からファイルを読み取れません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-124">The File receive adapter does not read a file from the receive location if any of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="9a8e2-125">ファイルが読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-125">The file is read-only.</span></span>  
  
-   <span data-ttu-id="9a8e2-126">ファイルには、システム属性があります。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-126">The file has a system attribute.</span></span>  
  
-   <span data-ttu-id="9a8e2-127">ファイル受信アダプターには、ファイルの読み書きのアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-127">The File receive adapter does not have permissions to read and write to the file.</span></span>  
  
-   <span data-ttu-id="9a8e2-128">受信場所では、256 文字より長い名前のファイルが検出されました。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-128">Files with names longer than 256 characters are encountered in the receive location.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9a8e2-129">解決策</span><span class="sxs-lookup"><span data-stu-id="9a8e2-129">Resolution</span></span>  
  
-   <span data-ttu-id="9a8e2-130">受信場所の指定したファイルを確認します「読み取り専用」としてマークされていません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-130">Ensure that the files in the specified receive location are not marked as "read only".</span></span>  
  
-   <span data-ttu-id="9a8e2-131">確認の受信場所の指定したファイル システム属性でマークされていません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-131">Ensure that the files in the specified receive location are not marked with a system attribute.</span></span>  
  
-   <span data-ttu-id="9a8e2-132">アカウントとして使用することを確認、**ログオン:** アカウントが、ファイル受信ハンドラーのホスト インスタンス用に読み取りし、書き込みのアクセス許可を指定した受信場所。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-132">Ensure that the account used as the **Logon:** account for the File receive handler host instance has read and write permissions to the specified receive location.</span></span>  
  
-   <span data-ttu-id="9a8e2-133">ファイルの監視対象フォルダに書き込まれるファイル受信アダプターであることを確認します。 256 文字を超えるとファイル名がありません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-133">Ensure that files written to the folder monitored by the File receive adapter do not have file names exceeding 256 characters.</span></span>  
  
#### <a name="messages-are-not-being-sent-by-the-file-send-adapter"></a><span data-ttu-id="9a8e2-134">メッセージは、ファイル送信アダプターによって送信されていません</span><span class="sxs-lookup"><span data-stu-id="9a8e2-134">Messages Are Not Being Sent by the File Send Adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9a8e2-135">問題</span><span class="sxs-lookup"><span data-stu-id="9a8e2-135">Problem</span></span>  
 <span data-ttu-id="9a8e2-136">ファイル送信アダプターは、指定されたディレクトリまたはファイル共有にメッセージを送信に失敗します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-136">The File send adapter fails to send a message to the specified directory or file share.</span></span>  
  
 <span data-ttu-id="9a8e2-137">指定されたディレクトリまたはファイル共有に書き込まれるメッセージが失敗した場合は、エラーは、BizTalk server コンピューターのイベント ログに書き込まれます、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-137">If a message fails to be written to the specified directory or file share, an error is written to the Event log of the BizTalk server computer and the following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="9a8e2-138">ファイル送信アダプターでは、書き込み操作を再試行します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-138">The File send adapter will retry the write operation.</span></span>  
  
2.  <span data-ttu-id="9a8e2-139">ファイル アダプターは (構成されている) 場合は、バックアップ トランスポートを使用してファイルを配信しようとします。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-139">The File adapter will attempt to deliver the file using the backup transport (if configured).</span></span>  
  
3.  <span data-ttu-id="9a8e2-140">メッセージは保留キューに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-140">The message will be written to the suspended queue.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="9a8e2-141">原因</span><span class="sxs-lookup"><span data-stu-id="9a8e2-141">Cause</span></span>  
  
-   <span data-ttu-id="9a8e2-142">ファイル送信アダプターは、ファイルから送信されるファイル システムまたはネットワーク共有に指定されたパスが存在しないため、ディレクトリにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-142">The File send adapter cannot access the directory that files are sent from on the file system or network share because the specified path does not exist.</span></span>  
  
-   <span data-ttu-id="9a8e2-143">ファイル送信アダプターは、関連付けられているホスト インスタンスにそのファイルまたはその場所への書き込みアクセス許可があるないために、ファイル システムまたはネットワーク共有に先の場所にファイルに書き込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-143">The File send adapter cannot write to a file in the destination location on the file system or network share because the associated host instance does not have write permissions for that file or for that location.</span></span>  
  
-   <span data-ttu-id="9a8e2-144">ファイル送信アダプターが読み取り専用かでマークされたために指定されたファイルに書き込むことはできません、**システム**ファイル属性。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-144">The File send adapter cannot write to the file specified because it is read-only or is marked with the **system** file attribute.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9a8e2-145">解決策</span><span class="sxs-lookup"><span data-stu-id="9a8e2-145">Resolution</span></span>  
  
-   <span data-ttu-id="9a8e2-146">指定されたパスまたは共有が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-146">Ensure that the specified path or share exists.</span></span>  
  
-   <span data-ttu-id="9a8e2-147">アカウントとして使用することを確認、**ログオン:** ファイル送信ハンドラーのホスト インスタンスのアカウントに読み取り、指定されたディレクトリまたはファイル共有に対する書き込みアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-147">Ensure that the account used as the **Logon:** account for the File send handler host instance has read and write permissions to the specified directory or file share.</span></span>  
  
-   <span data-ttu-id="9a8e2-148">指定されたディレクトリまたはファイル共有で既存のファイルがシステム属性でマークされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-148">Ensure that existing files in the specified directory or file share are not marked with the system attribute.</span></span>  
  
#### <a name="sending-a-file-using-the-file-adapter-is-very-slow"></a><span data-ttu-id="9a8e2-149">ファイル アダプターを使用してファイルを送信することが非常に遅い</span><span class="sxs-lookup"><span data-stu-id="9a8e2-149">Sending a file using the File adapter is very slow</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9a8e2-150">問題</span><span class="sxs-lookup"><span data-stu-id="9a8e2-150">Problem</span></span>  
 <span data-ttu-id="9a8e2-151">ファイル送信アダプターのパフォーマンスが遅い場合に、**への書き込みキャッシュを許可する**プロパティに設定されて**False**します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-151">Performance of the File send adapter is slower when the **Allow cache on write** property is set to **False**.</span></span> <span data-ttu-id="9a8e2-152">**への書き込みキャッシュを許可する**プロパティに設定されて**False**既定。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-152">The **Allow cache on write** property is set to **False** by default.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="9a8e2-153">原因</span><span class="sxs-lookup"><span data-stu-id="9a8e2-153">Cause</span></span>  
 <span data-ttu-id="9a8e2-154">設定、**への書き込みキャッシュを許可する**プロパティを**False**オペレーティング システムでのファイルのメモリ内キャッシュの使用が許可されないパフォーマンスが低下することができます。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-154">Setting the **Allow cache on write** property to **False** can reduce performance as this setting disallows the use of in-memory caching of files by the operating system.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9a8e2-155">解決策</span><span class="sxs-lookup"><span data-stu-id="9a8e2-155">Resolution</span></span>  
 <span data-ttu-id="9a8e2-156">アダプターの変更を送信するファイルのパフォーマンスを高めるために、**への書き込みキャッシュを許可する**プロパティを**True** (チェック ボックスをオン)。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-156">To increase performance of the File send adapter change the **Allow cache on write** property to **True** (check the box).</span></span> <span data-ttu-id="9a8e2-157">詳細については、**への書き込みキャッシュを許可する**プロパティを参照してください[File 送信ポートを構成する方法](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9)します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-157">For more information about the **Allow cache on write** property, see [How to Configure a File Send Port](http://msdn.microsoft.com/library/d801c5b7-da0a-4228-af0c-c2d450c251a9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a8e2-158">設定、**への書き込みキャッシュを許可する**プロパティを**True**オペレーティング システムでエラーが発生するデータ損失の可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-158">Setting the **Allow cache on write** property to **True** increases the possibility of data loss in the event that the operating system experiences a failure.</span></span> <span data-ttu-id="9a8e2-159">このシナリオでメモリ内のファイル キャッシュに格納されているすべてのデータが失われます。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-159">In this scenario, any data that is stored in the in-memory file cache will be lost.</span></span>  
  
#### <a name="zero-byte-files-received-by-the-file-adapter-are-deleted"></a><span data-ttu-id="9a8e2-160">ファイル アダプターによって受信された 0 バイトのファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-160">Zero byte files received by the File adapter are deleted</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="9a8e2-161">問題</span><span class="sxs-lookup"><span data-stu-id="9a8e2-161">Problem</span></span>  
 <span data-ttu-id="9a8e2-162">空 (0 バイト)、ファイルは、ファイルによって取得すると、受信アダプター、ファイルが削除され、次のような警告は、BizTalk server のアプリケーション ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-162">If an empty (zero byte) file is picked up by the File receive adapter, the file is deleted and a warning similar to the following is written to the application log of the BizTalk server:</span></span>  
  
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
  
##### <a name="cause"></a><span data-ttu-id="9a8e2-163">原因</span><span class="sxs-lookup"><span data-stu-id="9a8e2-163">Cause</span></span>  
 <span data-ttu-id="9a8e2-164">ファイルは、デザインによってアダプター削除ゼロ バイト ファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-164">The File receive adapter deletes zero byte files by design.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="9a8e2-165">解決策</span><span class="sxs-lookup"><span data-stu-id="9a8e2-165">Resolution</span></span>  
 <span data-ttu-id="9a8e2-166">操作は必要ありません、この動作は仕様です。</span><span class="sxs-lookup"><span data-stu-id="9a8e2-166">No action is required, this behavior is by design.</span></span>
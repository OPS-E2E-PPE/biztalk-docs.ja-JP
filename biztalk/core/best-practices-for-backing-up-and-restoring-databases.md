---
title: "バックアップおよびデータベースを復元するためのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, maintaining
- restoring, best practices
- best practices, backing up
- backing up, restoring
- backing up, best practices
- maintaining, best practices
- best practices, restoring
ms.assetid: 649ca56b-3cc1-49ad-9f74-ba1521e65ee1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2543f09c5118e58bd18ea2add113811fb733d884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a><span data-ttu-id="aaeb3-102">データベースのバックアップと復元のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="aaeb3-102">Best Practices for Backing Up and Restoring Databases</span></span>
<span data-ttu-id="aaeb3-103">BizTalk Server データベースのバックアップおよび復元を確実に行うことができるように、次のベスト プラクティスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-103">Review the following best practices to help ensure that you can backup and restore your BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="aaeb3-104">**バックアップの作成し復元戦略およびそれらをテストします。**</span><span class="sxs-lookup"><span data-stu-id="aaeb3-104">**Develop backup and restore strategies and test them.**</span></span>  
  
     <span data-ttu-id="aaeb3-105">適切なプランを作成することにより、ハードウェアの障害が発生してデータが失われても、データを迅速に復元できます。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-105">With a good plan, you can quickly recover your data if it is lost due to hardware failure.</span></span>  
  
-   <span data-ttu-id="aaeb3-106">**ディスク領域を管理し、以前のバックアップ ファイルを保存します。**</span><span class="sxs-lookup"><span data-stu-id="aaeb3-106">**Manage disk space and archive previous backup files.**</span></span>  
  
     <span data-ttu-id="aaeb3-107">BizTalk Server のバックアップ ジョブでは、期限切れのバックアップ ファイルが削除されないので、ディスク領域を節約するにはこれらのバックアップ ファイルを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-107">The Backup BizTalk Server job does not delete outdated backup files, so you need to manage those backup files to conserve disk space.</span></span> <span data-ttu-id="aaeb3-108">データベースの完全バックアップを新規作成した後で、プライマリ ディスクの領域を再利用できるように、期限切れのバックアップ ファイルをアーカイブ ストレージ デバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-108">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span>  
  
-   <span data-ttu-id="aaeb3-109">**同じコンピューターまたはディスクをバックアップするには、バックアップを格納しないでください。**</span><span class="sxs-lookup"><span data-stu-id="aaeb3-109">**Do not store backups on the same computer or disk that you are backing up.**</span></span>  
  
     <span data-ttu-id="aaeb3-110">バックアップ用のコンピューターまたはディスクには、元のデータのある場所とは別のコンピューターを指定してください。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-110">You should specify a computer or disk for your backup that is different from the computer with the original data.</span></span> <span data-ttu-id="aaeb3-111">そうしないと、ハードウェアの障害が発生した場合にすべてのデータが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-111">Otherwise, you will lose all of your data if the hardware fails.</span></span>  
  
-   <span data-ttu-id="aaeb3-112">**コピーを保持します。**</span><span class="sxs-lookup"><span data-stu-id="aaeb3-112">**Retain copies.**</span></span>  
  
     <span data-ttu-id="aaeb3-113">メディアのコピーを 3 つ以上保持してください。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-113">Keep at least three copies of the media.</span></span> <span data-ttu-id="aaeb3-114">1 つ以上のコピーをオフサイトの適切に管理された環境で保管します。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-114">Keep at least one copy off-site in a properly controlled environment.</span></span>  
  
-   <span data-ttu-id="aaeb3-115">**テスト復元を実行します。**</span><span class="sxs-lookup"><span data-stu-id="aaeb3-115">**Perform trial restorations.**</span></span>  
  
     <span data-ttu-id="aaeb3-116">テスト復元を少なくとも月に 1 度は実行し、ファイルが適切にバックアップされたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-116">Perform a trial restoration at least once a month to verify that your files were properly backed up.</span></span> <span data-ttu-id="aaeb3-117">テスト復元により、ソフトウェアが適性に動作しているかについて検証しても発見できないハードウェアの問題が明らかになります。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-117">A trial restoration can uncover hardware problems that do not show up when you verify that your software is functioning properly.</span></span> <span data-ttu-id="aaeb3-118">ハード ディスクの障害が発生する前に、システムおよびデータベースを復元できるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-118">Do not wait until your hard disk fails to see if you can restore your system and databases.</span></span>  
  
-   <span data-ttu-id="aaeb3-119">**デバイスとメディアを保護します。**</span><span class="sxs-lookup"><span data-stu-id="aaeb3-119">**Secure devices and media.**</span></span>  
  
     <span data-ttu-id="aaeb3-120">ストレージ デバイスおよびバックアップ メディアの両方をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-120">Secure both the storage device and the backup media.</span></span> <span data-ttu-id="aaeb3-121">メディアを盗んだ人間は、自分が管理者となっているサーバーでメディアのデータを復元することによりデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-121">It is possible for someone to access the data from a stolen medium by restoring the data to another server for which they are an administrator.</span></span>  
  
-   <span data-ttu-id="aaeb3-122">**バックアップを監視し、プロセスを復元します。**</span><span class="sxs-lookup"><span data-stu-id="aaeb3-122">**Monitor the backup and restore process.**</span></span>  
  
     <span data-ttu-id="aaeb3-123">バックアップおよび復元のプロセスが正常に実行されたかどうかを確認するには、BizTalk Server のバックアップおよび復元に使用する SQL Server エージェント ジョブを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaeb3-123">To ensure that the backup and restore process was successful, you should monitor the SQL Server Agent jobs used to backup and restore BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaeb3-124">参照</span><span class="sxs-lookup"><span data-stu-id="aaeb3-124">See Also</span></span>  
 [<span data-ttu-id="aaeb3-125">バックアップと、BizTalk Server データベースの復元</span><span class="sxs-lookup"><span data-stu-id="aaeb3-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)
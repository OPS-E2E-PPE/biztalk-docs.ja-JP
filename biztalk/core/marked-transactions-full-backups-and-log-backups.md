---
title: "マークされたトランザクション、完全バックアップ、およびログ バックアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, transaction logs
- backing up, full backups
- transaction logs
- backing up, backup jobs
ms.assetid: a383a16d-1e40-4b0b-a515-f1cb90bfb4d2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36c7eab426bfc19c082d8c9651cf4d02eae0075a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="marked-transactions-full-backups-and-log-backups"></a><span data-ttu-id="1d480-102">マークされたトランザクション、完全バックアップ、ログ バックアップ</span><span class="sxs-lookup"><span data-stu-id="1d480-102">Marked Transactions, Full Backups, and Log Backups</span></span>
<span data-ttu-id="1d480-103">BizTalk Server のバックアップ ジョブは、BizTalk Server のデータベースと呼ばれるトランザクションの種類と組み合わせて、データベースの完全バックアップとトランザクション ログのバックアップを使用して、すべての同期のバックアップを作成、*マークされたトランザクション*です。</span><span class="sxs-lookup"><span data-stu-id="1d480-103">The Backup BizTalk Server Job creates synchronized backups of all BizTalk Server databases by using full database backups and transaction log backups, in conjunction with a type of transaction known as a *marked transaction*.</span></span> <span data-ttu-id="1d480-104">"マークされたトランザクション" とは、そのトランザクションに参加するすべてのデータベースのトランザクション ログに対してマークを設定するトランザクションです。</span><span class="sxs-lookup"><span data-stu-id="1d480-104">Marked transactions are transactions that place a mark into the transaction log of all databases participating in the transaction.</span></span> <span data-ttu-id="1d480-105">新しい分散トランザクションの開始を抑制しながら、現在実行されている分散トランザクションの完了を待機し、適切な時期が来たらトランザクションを実行してマークを設定するというものです。</span><span class="sxs-lookup"><span data-stu-id="1d480-105">The marked transaction blocks new distributed transactions from starting, waits for the distributed transactions that are currently running to complete, and then executes to place the mark.</span></span>  
  
 <span data-ttu-id="1d480-106">ここでいうマークとは、すべてのデータベース間で同期されたトランザクション ポイントのことです。それ以降のログ バックアップでは、このマークを目安として、データベースを適切なポイントまで復元できます。</span><span class="sxs-lookup"><span data-stu-id="1d480-106">The mark represents a transaction point that is consistent across all databases; you can use the mark with subsequent log backups to restore your databases to that point.</span></span>  
  
 <span data-ttu-id="1d480-107">BizTalk Server のバックアップ ジョブを実行するたびに、すべての BizTalk Server データベースの、マークされたトランザクション ログ バックアップが作成され、指定された期間に基づく完全バックアップが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d480-107">For each BizTalk Server database, the Backup BizTalk Server job creates a marked transaction log backup every time it runs, and it creates a full backup based on a time period that you specify.</span></span>  
  
## <a name="full-backups"></a><span data-ttu-id="1d480-108">完全バックアップ</span><span class="sxs-lookup"><span data-stu-id="1d480-108">Full backups</span></span>  
 <span data-ttu-id="1d480-109">最初のバックアップ プロセスが実行される BizTalk Server のバックアップ ジョブを実行するときに*BackupFull*、各期間 (not、ジョブを実行するたびに) 1 回です。</span><span class="sxs-lookup"><span data-stu-id="1d480-109">When you run the Backup BizTalk Server job it runs the first backup process, *BackupFull*, once every period (not every time the job runs).</span></span> <span data-ttu-id="1d480-110">BizTalk Server のバックアップ ジョブをスケジュールする方法の詳細については、次を参照してください。[を BizTalk Server のバックアップ ジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)です。</span><span class="sxs-lookup"><span data-stu-id="1d480-110">For more information about how to schedule the Backup BizTalk Server job, see [How to Schedule the Backup BizTalk Server Job](../core/how-to-schedule-the-backup-biztalk-server-job.md).</span></span>  
  
 <span data-ttu-id="1d480-111">新しく設定した間隔で BizTalk Server のバックアップ ジョブが初めて実行されるときは、完全バックアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1d480-111">The first time the Backup BizTalk Server job runs during a new period, it performs a full backup.</span></span> <span data-ttu-id="1d480-112">たとえば、ジョブを 1 時間おきに実行するようにスケジュールを設定し、間隔を "毎日" に設定した場合、BizTalk Server のバックアップ ジョブは、1 日の初回実行時 (深夜 0:00 時など) に、完全バックアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1d480-112">For example, if you schedule the job to run every hour but configure the period to be daily, the Backup BizTalk Server job performs a full backup the first time it runs, and then every day at midnight.</span></span>  
  
## <a name="transaction-log-backups"></a><span data-ttu-id="1d480-113">トランザクション ログのバックアップ</span><span class="sxs-lookup"><span data-stu-id="1d480-113">Transaction log backups</span></span>  
 <span data-ttu-id="1d480-114">BizTalk Server のバックアップ ジョブを実行する 2 つ目のプロセスは*MarkAndBackupLog*です。</span><span class="sxs-lookup"><span data-stu-id="1d480-114">The second process that the Backup BizTalk Server job performs is *MarkAndBackupLog*.</span></span> <span data-ttu-id="1d480-115">ジョブを実行するたびに、このプロセスですべての BizTalk Server データベースにマークが設定され、トランザクション ログ バックアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1d480-115">This process places a mark in all BizTalk Server databases and performs a transaction log backup every time the job executes.</span></span>  
  
 <span data-ttu-id="1d480-116">使用して作成された文字列のマークは *\<ServerName >*_*\<DatabaseName >*_Log\_*\<LogMarkName >*\_ *\<タイムスタンプ >*.bak、場所、  *\<Log Mark Name >*は、SQL Server エージェント ジョブで構成します。</span><span class="sxs-lookup"><span data-stu-id="1d480-116">The mark is the string created by using *\<ServerName>*_*\<DatabaseName>*_Log\_*\<LogMarkName>*\_*\<Timestamp>*.bak, where the *\<Log Mark Name>* is configured in the SQL Server Agent job.</span></span> <span data-ttu-id="1d480-117">各データベースの最後のログを復元するときに、このマークが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d480-117">This mark must be used when restoring the last log to each database.</span></span>  
  
 <span data-ttu-id="1d480-118">詳細については、SQL Server Books Online の「トランザクション ログ バックアップ」および「関連するデータベースのバックアップと復旧」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d480-118">For more information, see "Transaction Log Backups" and "Backup and Recovery of Related Databases" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d480-119">参照</span><span class="sxs-lookup"><span data-stu-id="1d480-119">See Also</span></span>  
 [<span data-ttu-id="1d480-120">バックアップと復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="1d480-120">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)
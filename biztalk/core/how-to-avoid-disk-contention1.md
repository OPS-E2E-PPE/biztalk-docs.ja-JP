---
title: "ディスク Contention1 を回避する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702665046dbaee77412675e4be0edc602dd9e7e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-avoid-disk-contention"></a><span data-ttu-id="d3815-102">ディスクの競合を防止する方法</span><span class="sxs-lookup"><span data-stu-id="d3815-102">How to Avoid Disk Contention</span></span>
<span data-ttu-id="d3815-103">BizTalk Server は永続的なシステムとして設計されているため、高スループットのシナリオではメッセージ ボックスで深刻な競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d3815-103">BizTalk Server is designed as a persistent system whereby, for high throughput scenarios, the MessageBox can experience severe contention.</span></span> <span data-ttu-id="d3815-104">ディスクが遅い場合には事態がさらに悪化します。</span><span class="sxs-lookup"><span data-stu-id="d3815-104">This contention can be aggravated by slow disks.</span></span> <span data-ttu-id="d3815-105">ディスクが遅い (ディスク アイドル時間の割合が低い) と、SQL がロックを保持する時間が長くなります (ロック待機時間とロック タイムアウトの値が大きくなる)。そうなると、メッセージ ボックス テーブル (スプールとアプリケーション キュー) のサイズが増加して、データベースの肥大化と制限を引き起こし、最終的には全体の維持可能なスループットが低下します。</span><span class="sxs-lookup"><span data-stu-id="d3815-105">If the disks are slow (low % Disk Idle Time), this can cause SQL to hold onto locks longer (high Lock Wait Time and high Lock Timeouts) which can cause the MessageBox tables (Spool and Application Queues) to grow, causing database bloat and throttling ultimately resulting in lower overall sustainable throughput.</span></span>  
  
 <span data-ttu-id="d3815-106">ディスクの競合を防止するための推奨事項を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d3815-106">To avoid disk contention, it is recommended that you do the following:</span></span>  
  
-   <span data-ttu-id="d3815-107">高速な (マルチ スピンドルの) ディスクを使用する。</span><span class="sxs-lookup"><span data-stu-id="d3815-107">Use of high speed (multiple spindles) disks.</span></span>  
  
-   <span data-ttu-id="d3815-108">可能であれば、高速な SAN にデータベースを展開する。</span><span class="sxs-lookup"><span data-stu-id="d3815-108">If possible, deploy the databases on a high speed SAN.</span></span> <span data-ttu-id="d3815-109">複数のデータベースが同じディスクを共有している場合は、それぞれ専用のディスクで構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d3815-109">If multiple databases are sharing the same disks it is recommended to configure them on separate dedicated disks.</span></span> <span data-ttu-id="d3815-110">さらに、メッセージ ボックス データベースの MDF ファイルと LDF ファイルを別々のディスクに分けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d3815-110">In addition it is recommended to separate the MDF and LDF files for the MessageBox database onto separate disks.</span></span>  
  
-   <span data-ttu-id="d3815-111">SQL で CPU が不足している場合は、メッセージ ボックス データベースを追跡データベースとは別の専用のサーバーに分離することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d3815-111">If SQL is starved for CPU, consider separating the MessageBox database onto a dedicated server that is separate from the Tracking databases.</span></span>  
  
-   <span data-ttu-id="d3815-112">メッセージ ボックス データベースの専用のサーバーをセットアップした後は、CPU のアップグレードや、複数の CPU の追加によるスケール アップを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d3815-112">After setting up a dedicated server for the MessageBox database, consider scaling up by upgrading the CPU’s and/or adding more CPU’s.</span></span> <span data-ttu-id="d3815-113">MSDTC のログは、ローカル ドライブ (C:\WINDOWS\system32\Msdtc) に保存されるため、SQL Server のローカル ドライブを監視します。</span><span class="sxs-lookup"><span data-stu-id="d3815-113">Monitor the local drive on the SQL-Server as the MSDTC logs are saved on the local drive (C:\WINDOWS\system32\Msdtc).</span></span>  
  
-   <span data-ttu-id="d3815-114">ページファイルや MSDTC のログによってローカル ドライブで競合が発生する場合は、ページファイルや MSDTC のログを別のドライブに移してみてください。</span><span class="sxs-lookup"><span data-stu-id="d3815-114">If there is contention on the local drive due to the PageFile or MSDTC log, try moving the PageFile and/or the MSDTC log to a separate drive.</span></span>
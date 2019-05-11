---
title: ディスク Contention1 を回避する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9204fc727339a5fbab31cdf54bc8de488e588dda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342670"
---
# <a name="how-to-avoid-disk-contention"></a><span data-ttu-id="77463-102">ディスクの競合を防止する方法</span><span class="sxs-lookup"><span data-stu-id="77463-102">How to Avoid Disk Contention</span></span>
<span data-ttu-id="77463-103">BizTalk Server は、高スループットのシナリオで、メッセージ ボックスできます競合が発生する重大な永続的なシステムとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="77463-103">BizTalk Server is designed as a persistent system whereby, for high throughput scenarios, the MessageBox can experience severe contention.</span></span> <span data-ttu-id="77463-104">ディスクが遅い場合には事態がさらに悪化します。</span><span class="sxs-lookup"><span data-stu-id="77463-104">This contention can be aggravated by slow disks.</span></span> <span data-ttu-id="77463-105">ディスクが低速 (低 % Disk Idle Time) の場合は、この可能性がありますロック長くなります (ロック待機時間と高のロック タイムアウト数) に増加し、メッセージ ボックス テーブル (スプールとアプリケーション キュー) が発生することができますを保持する SQL データベースの肥大と最終的な調整全体的な持続可能なスループットが低下なります。</span><span class="sxs-lookup"><span data-stu-id="77463-105">If the disks are slow (low % Disk Idle Time), this can cause SQL to hold onto locks longer (high Lock Wait Time and high Lock Timeouts) which can cause the MessageBox tables (Spool and Application Queues) to grow, causing database bloat and throttling ultimately resulting in lower overall sustainable throughput.</span></span>  
  
 <span data-ttu-id="77463-106">ディスクの競合を回避するために、次を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77463-106">To avoid disk contention, it is recommended that you do the following:</span></span>  
  
-   <span data-ttu-id="77463-107">高速 (マルチ スピンドル) ディスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="77463-107">Use of high speed (multiple spindles) disks.</span></span>  
  
-   <span data-ttu-id="77463-108">可能であれば、高速な SAN 上のデータベースをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="77463-108">If possible, deploy the databases on a high speed SAN.</span></span> <span data-ttu-id="77463-109">複数のデータベースが同じディスクを共有している場合は、それらを個別の専用ディスクを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77463-109">If multiple databases are sharing the same disks it is recommended to configure them on separate dedicated disks.</span></span> <span data-ttu-id="77463-110">さらに別のディスク上にメッセージ ボックス データベースの MDF および LDF ファイルを分離することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="77463-110">In addition it is recommended to separate the MDF and LDF files for the MessageBox database onto separate disks.</span></span>  
  
-   <span data-ttu-id="77463-111">CPU、SQL が不足している場合は、追跡データベースから分離された専用のサーバーにメッセージ ボックス データベースを分離することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="77463-111">If SQL is starved for CPU, consider separating the MessageBox database onto a dedicated server that is separate from the Tracking databases.</span></span>  
  
-   <span data-ttu-id="77463-112">メッセージ ボックス データベースに専用のサーバーを設定した後は、CPU のアップグレードやより多くの CPU の追加によるスケール アップを検討してください。</span><span class="sxs-lookup"><span data-stu-id="77463-112">After setting up a dedicated server for the MessageBox database, consider scaling up by upgrading the CPU’s and/or adding more CPU’s.</span></span> <span data-ttu-id="77463-113">MSDTC のログはローカル ドライブ (C:\WINDOWS\system32\Msdtc) に保存されるため、SQL Server のローカル ドライブを監視します。</span><span class="sxs-lookup"><span data-stu-id="77463-113">Monitor the local drive on the SQL-Server as the MSDTC logs are saved on the local drive (C:\WINDOWS\system32\Msdtc).</span></span>  
  
-   <span data-ttu-id="77463-114">ページファイルや MSDTC のログによってローカル ドライブで競合が発生する場合は、ページファイルや MSDTC のログを別のドライブに移してみてください。</span><span class="sxs-lookup"><span data-stu-id="77463-114">If there is contention on the local drive due to the PageFile or MSDTC log, try moving the PageFile and/or the MSDTC log to a separate drive.</span></span>
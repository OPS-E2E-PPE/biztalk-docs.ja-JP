---
title: BizTalk Server データベースの監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fee5015-e818-459b-aeeb-a084ef355600
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3cb759bf377cfe77f1e346a94fca739b8532a44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002131"
---
# <a name="monitoring-biztalk-server-databases"></a><span data-ttu-id="34b5d-102">BizTalk Server データベースの監視</span><span class="sxs-lookup"><span data-stu-id="34b5d-102">Monitoring BizTalk Server Databases</span></span>
<span data-ttu-id="34b5d-103">管理、メッセージ ボックス、または DTA データベースの既知の問題を識別するために、モニターの BizTalk Server の SQL エージェント ジョブを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="34b5d-103">You can run the Monitor BizTalk Server SQL Agent job to identify any known issues in Management, Message Box, or DTA databases.</span></span> <span data-ttu-id="34b5d-104">このジョブは、BizTalk Server 管理コンソールで BizTalk グループを構成するとき、または以前のバージョンから BizTalk をアップグレードするときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="34b5d-104">The job is created when you configure a BizTalk group in BizTalk Server Administration console or upgrade BizTalk from the previous version.</span></span>  
  
## <a name="the-monitor-biztalk-server-job"></a><span data-ttu-id="34b5d-105">BizTalk Server ジョブの監視</span><span class="sxs-lookup"><span data-stu-id="34b5d-105">The Monitor BizTalk Server Job</span></span>  
 <span data-ttu-id="34b5d-106">Monitor BizTalk Server ジョブは、管理、メッセージ ボックス、および DTA データベースで次の問題をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="34b5d-106">The Monitor BizTalk Server job scans for the following issues in Management, Message Box, and DTA databases:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34b5d-107">Monitor BizTalk Server ジョブは、問題のスキャンしか行いません。</span><span class="sxs-lookup"><span data-stu-id="34b5d-107">The Monitor BizTalk Server job only scans for issues.</span></span> <span data-ttu-id="34b5d-108">検出された問題の修正は行いません。</span><span class="sxs-lookup"><span data-stu-id="34b5d-108">It does not fix the issues found.</span></span>  
  
- <span data-ttu-id="34b5d-109">参照のないメッセージ</span><span class="sxs-lookup"><span data-stu-id="34b5d-109">Messages without any references</span></span>  
  
- <span data-ttu-id="34b5d-110">参照カウントのないメッセージ</span><span class="sxs-lookup"><span data-stu-id="34b5d-110">Messages without reference counts</span></span>  
  
- <span data-ttu-id="34b5d-111">0 未満の参照カウントのあるメッセージ</span><span class="sxs-lookup"><span data-stu-id="34b5d-111">Messages with reference count less than 0</span></span>  
  
- <span data-ttu-id="34b5d-112">スプール行のないメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="34b5d-112">Message references without spool rows</span></span>  
  
- <span data-ttu-id="34b5d-113">インスタンスのないメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="34b5d-113">Message references without instances</span></span>  
  
- <span data-ttu-id="34b5d-114">インスタンスのないインスタンス状態</span><span class="sxs-lookup"><span data-stu-id="34b5d-114">Instance state without instances</span></span>  
  
- <span data-ttu-id="34b5d-115">対応するインスタンスのないインスタンス サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="34b5d-115">Instance subscriptions without corresponding instances</span></span>  
  
- <span data-ttu-id="34b5d-116">孤立した DTA サービス インスタンス</span><span class="sxs-lookup"><span data-stu-id="34b5d-116">Orphaned DTA service instances</span></span>  
  
- <span data-ttu-id="34b5d-117">孤立した DTA サービス インスタンスの例外</span><span class="sxs-lookup"><span data-stu-id="34b5d-117">Orphaned DTA service instance exceptions</span></span>  
  
- <span data-ttu-id="34b5d-118">グローバル追跡オプションが有効な場合に、TDDS はホスト インスタンスで実行されていません</span><span class="sxs-lookup"><span data-stu-id="34b5d-118">TDDS is not running on any host instance when global tracking option is enabled</span></span>  
  
  <span data-ttu-id="34b5d-119">Monitor BizTalk Server ジョブは、週に 1 回実行するよう構成および自動化されています。</span><span class="sxs-lookup"><span data-stu-id="34b5d-119">The Monitor BizTalk Server job is configured and automated to run once in a week.</span></span> <span data-ttu-id="34b5d-120">ジョブがコンピューターに負荷がないため、ダウンタイムまたは低トラフィックの期間中に実行するようにスケジュールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34b5d-120">Since the job is computationally intensive, we recommended that you schedule it to run during periods of downtime or low traffic.</span></span>  
  <span data-ttu-id="34b5d-121">すべての問題が発生した場合、ジョブが失敗しました。返されるエラー文字列には、検出された問題の数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="34b5d-121">The job fails if it encounters any issues; the error string returned contains the number of issues found.</span></span> <span data-ttu-id="34b5d-122">問題が見つからない場合は、正常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="34b5d-122">Else, it runs successfully.</span></span> <span data-ttu-id="34b5d-123">ジョブ履歴に詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="34b5d-123">You can see the details in the job history.</span></span> <span data-ttu-id="34b5d-124">管理者特権を持つジョブを実行する場合、エラー文字列がジョブ履歴と、SQL Server アプリケーション ログの両方に記録されます。</span><span class="sxs-lookup"><span data-stu-id="34b5d-124">If you run the job with Administrator privileges, the error string will be logged to both the job history and the SQL Server Application log.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="34b5d-125">このジョブの障害とは限りませんものではありませんが、重要な問題、問題を調査して、BizTalk Server データベースの定期的なメンテナンスの一環としてアドレス指定する必要がありますではなく。</span><span class="sxs-lookup"><span data-stu-id="34b5d-125">Failure of this job does not necessarily constitute a critical issue, but rather an issue that should be investigated and addressed as part of regular maintenance of the BizTalk Server databases.</span></span> <span data-ttu-id="34b5d-126">このジョブは、上記の問題のいずれかが検出された場合に、デザインによって失敗します。</span><span class="sxs-lookup"><span data-stu-id="34b5d-126">This job fails by design in the event it discovers one of the issues listed above.</span></span>
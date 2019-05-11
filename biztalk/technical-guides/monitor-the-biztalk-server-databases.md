---
title: BizTalk Server データベースの監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f137fc5-0e95-4952-8465-008771a1a377
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5a4db14f9bdebc8d368a21d6955547d65e2eb7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379450"
---
# <a name="monitor-the-biztalk-server-databases"></a><span data-ttu-id="c016f-102">BizTalk Server データベースを監視します。</span><span class="sxs-lookup"><span data-stu-id="c016f-102">Monitor the BizTalk Server Databases</span></span>
<span data-ttu-id="c016f-103">管理、メッセージ ボックス、または DTA データベースの既知の問題を識別するために、モニターの BizTalk Server の SQL エージェント ジョブを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c016f-103">You can run the Monitor BizTalk Server SQL Agent job to identify any known issues in Management, Message Box, or DTA databases.</span></span> <span data-ttu-id="c016f-104">BizTalk Server 管理コンソールで、BizTalk グループの構成または以前のバージョンから BizTalk をアップグレードするときに、ジョブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c016f-104">The job is created when you configure a BizTalk group in BizTalk Server Administration console or upgrade BizTalk from the previous version.</span></span>  
  
## <a name="the-monitor-biztalk-server-job"></a><span data-ttu-id="c016f-105">BizTalk Server ジョブの監視</span><span class="sxs-lookup"><span data-stu-id="c016f-105">The Monitor BizTalk Server Job</span></span>  
 <span data-ttu-id="c016f-106">Monitor BizTalk Server ジョブは、管理、メッセージ ボックス、および DTA データベースで、次の問題をスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="c016f-106">The Monitor BizTalk Server job scans for the following issues in Management, Message Box, and DTA databases:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c016f-107">Monitor BizTalk Server ジョブは、のみの問題をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="c016f-107">The Monitor BizTalk Server job only scans for issues.</span></span> <span data-ttu-id="c016f-108">発見された問題の修正は行いません。</span><span class="sxs-lookup"><span data-stu-id="c016f-108">It does not fix the issues found.</span></span>  
  
- <span data-ttu-id="c016f-109">参照のないメッセージ</span><span class="sxs-lookup"><span data-stu-id="c016f-109">Messages without any references</span></span>  
  
- <span data-ttu-id="c016f-110">参照カウントのないメッセージ</span><span class="sxs-lookup"><span data-stu-id="c016f-110">Messages without reference counts</span></span>  
  
- <span data-ttu-id="c016f-111">メッセージ参照数は 0 より小さい</span><span class="sxs-lookup"><span data-stu-id="c016f-111">Messages with reference count less than 0</span></span>  
  
- <span data-ttu-id="c016f-112">スプール行のないメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="c016f-112">Message references without spool rows</span></span>  
  
- <span data-ttu-id="c016f-113">インスタンスのないメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="c016f-113">Message references without instances</span></span>  
  
- <span data-ttu-id="c016f-114">インスタンスのないインスタンスの状態</span><span class="sxs-lookup"><span data-stu-id="c016f-114">Instance state without instances</span></span>  
  
- <span data-ttu-id="c016f-115">対応するインスタンスのないインスタンス サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="c016f-115">Instance subscriptions without corresponding instances</span></span>  
  
- <span data-ttu-id="c016f-116">孤立した DTA サービス インスタンス</span><span class="sxs-lookup"><span data-stu-id="c016f-116">Orphaned DTA service instances</span></span>  
  
- <span data-ttu-id="c016f-117">孤立した DTA サービス インスタンスの例外</span><span class="sxs-lookup"><span data-stu-id="c016f-117">Orphaned DTA service instance exceptions</span></span>  
  
- <span data-ttu-id="c016f-118">グローバル追跡オプションが有効な場合に、TDDS はホスト インスタンスで実行されていません</span><span class="sxs-lookup"><span data-stu-id="c016f-118">TDDS is not running on any host instance when global tracking option is enabled</span></span>  
  
  <span data-ttu-id="c016f-119">Monitor BizTalk Server ジョブが構成され、1 週間に 1 回実行する自動します。</span><span class="sxs-lookup"><span data-stu-id="c016f-119">The Monitor BizTalk Server job is configured and automated to run once in a week.</span></span> <span data-ttu-id="c016f-120">ジョブがコンピューターに負荷がないため、ダウンタイムまたは低トラフィックの期間中に実行するようにスケジュールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c016f-120">Since the job is computationally intensive, we recommended that you schedule it to run during periods of downtime or low traffic.</span></span>  
  <span data-ttu-id="c016f-121">すべての問題が発生した場合、ジョブが失敗しました。返されるエラー文字列には、検出された問題の数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c016f-121">The job fails if it encounters any issues; the error string returned contains the number of issues found.</span></span> <span data-ttu-id="c016f-122">それ以外の場合、正常に実行します。</span><span class="sxs-lookup"><span data-stu-id="c016f-122">Else, it runs successfully.</span></span> <span data-ttu-id="c016f-123">ジョブ履歴で詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c016f-123">You can see the details in the job history.</span></span> <span data-ttu-id="c016f-124">管理者特権を持つジョブを実行する場合、エラー文字列がジョブ履歴と、SQL Server アプリケーション ログの両方に記録されます。</span><span class="sxs-lookup"><span data-stu-id="c016f-124">If you run the job with Administrator privileges, the error string will be logged to both the job history and the SQL Server Application log.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c016f-125">このジョブの障害とは限りませんものではありませんが、重要な問題、問題を調査して、BizTalk Server データベースの定期的なメンテナンスの一環としてアドレス指定する必要がありますではなく。</span><span class="sxs-lookup"><span data-stu-id="c016f-125">Failure of this job does not necessarily constitute a critical issue, but rather an issue that should be investigated and addressed as part of regular maintenance of the BizTalk Server databases.</span></span> <span data-ttu-id="c016f-126">このジョブは、上記の問題のいずれかが検出された場合に、デザインによって失敗します。</span><span class="sxs-lookup"><span data-stu-id="c016f-126">This job fails by design in the event it discovers one of the issues listed above.</span></span> <span data-ttu-id="c016f-127">上記の問題に関する詳細については、これらの問題のトラブルシューティングを行うマイクロソフト製品サポート サービスでよく使用されるユーティリティにアクセスするにを参照してください[BizTalk によって特定された問題を解決するには BizTalk 終端記号の使用。MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367)します。</span><span class="sxs-lookup"><span data-stu-id="c016f-127">For more information about the issues listed above and to access utilities that are commonly used by Microsoft Product Support Services to troubleshoot these issues please see [Using BizTalk Terminator to resolve issues identified by BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367).</span></span>
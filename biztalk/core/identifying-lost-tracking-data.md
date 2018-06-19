---
title: 識別するには、追跡データが失われた |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, HAT
- reporting tools
- Orchestration Debugger
- Tracking database, data loss
- HAT, data loss
- HAT, Operation View tool
- HAT, reporting tools
- Operation View tool, MessageBox database
- MessageBox database, Operation View tool
- Operation View tool, data loss
ms.assetid: 1ac13e2c-cd5e-437e-b924-d4547931874e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2d7a61d974a51e3a811a8cce84a1e22c24a5e84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256706"
---
# <a name="identifying-lost-tracking-data"></a><span data-ttu-id="580c5-102">失われた追跡データの特定</span><span class="sxs-lookup"><span data-stu-id="580c5-102">Identifying Lost Tracking Data</span></span>
<span data-ttu-id="580c5-103">BizTalk Server 管理コンソールを使用することによって、ハードウェア障害の結果として、どの追跡データが失われたかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="580c5-103">You can use the BizTalk Server Administration console to help identify which tracking data has been lost as a result of a hardware failure.</span></span> <span data-ttu-id="580c5-104">BizTalk Server 管理コンソールは、ライブ データまたはアーカイブ済みデータについて使用できます。</span><span class="sxs-lookup"><span data-stu-id="580c5-104">You can use the BizTalk Server Administration console for live or archived data.</span></span>  
  
 <span data-ttu-id="580c5-105">BizTalk Server 管理コンソールを使用すると、どのサービスがメッセージ ボックス データベースの回復時にアクティブだったを決定します。</span><span class="sxs-lookup"><span data-stu-id="580c5-105">You can use the BizTalk Server Administration console to determine which services were active at the time the MessageBox was recovered.</span></span> <span data-ttu-id="580c5-106">データベースの復旧時点とハードウェア障害の発生時点の間には時間差があるため、一部のトランザクションの状態を特定できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="580c5-106">Because there is a gap between the time that the database was recovered and the time of the hardware failure, you may not be able to determine the state of some of the transactions.</span></span>  
  
 <span data-ttu-id="580c5-107">完了済みのサービス インスタンスや、復旧ポイント以降に開始されたサービス インスタンスを特定するには、追跡データを次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="580c5-107">You can use tracking data to identify which service instances completed and started after the point of recovery, as follows:</span></span>  
  
-   <span data-ttu-id="580c5-108">データベースの前回バックアップ時以降に完了または開始されたインスタンスを探します。</span><span class="sxs-lookup"><span data-stu-id="580c5-108">Look for which instances completed or started since the last time you backed up the database.</span></span>  
  
-   <span data-ttu-id="580c5-109">BizTalk 追跡 (BizTalkDTADb) データベースのデータを見て、開始されているにもかかわらず完了していないメッセージがあった場合、そのメッセージがデータベースに存在しなければ、前回のバックアップ後に送信されたメッセージであると判断できます。</span><span class="sxs-lookup"><span data-stu-id="580c5-109">If data in the BizTalk Tracking (BizTalkDTADb) database indicates that the message started but did not complete, and the message is not in the database, then that message was sent after the last backup.</span></span>  
  
 <span data-ttu-id="580c5-110">追跡からは、完了したすべてのサービスに加え、開始済みのサービスが報告されることもあります。</span><span class="sxs-lookup"><span data-stu-id="580c5-110">Tracking can report on any service that completed, and it can indicate that a service started.</span></span> <span data-ttu-id="580c5-111">追跡データは、まずメッセージ ボックスにステージングされ、その後、BizTalk 追跡データベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="580c5-111">Tracking data is first staged to the MessageBox and then moved to the BizTalk Tracking database.</span></span> <span data-ttu-id="580c5-112">ステージングされたデータは、BAM イベント バス サービスのバックログに紛れ込んでいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="580c5-112">The data that was staged may have been lost to the backlog of the BAM Event Bus service.</span></span>  
  
 <span data-ttu-id="580c5-113">運用上必要な操作は、すべてのデータベースを同じマークまで復元することですが、失われなかった BizTalk 追跡データベースをアーカイブ モードで使用して、マーク以降の動きを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="580c5-113">While all databases need to be restored to the same mark for operational reasons, you can use a BizTalk Tracking database (that was not lost) in Archive mode to see what happened after the mark.</span></span>  
  
 <span data-ttu-id="580c5-114">追跡によってサービス インスタンスが完了済みであることがわかれば、そのインスタンスを強制終了できます。</span><span class="sxs-lookup"><span data-stu-id="580c5-114">If tracking shows a service instance as having completed, you can terminate that instance.</span></span> <span data-ttu-id="580c5-115">追跡では、復旧ポイント以降に開始されたインスタンスが示される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="580c5-115">It may show instances that started after the point of recovery.</span></span> <span data-ttu-id="580c5-116">その場合は、該当するインスタンスによって行われたアクションに関する補正を行ってから、初期アクティベーション メッセージを再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="580c5-116">If so, you will need to compensate for any actions these instances took and then resubmit their initial activation messages.</span></span>  
  
 <span data-ttu-id="580c5-117">オーケストレーション デバッガーを使用すると、最後に実行された図形を特定し、本来、送受信されるべきであったメッセージを、メッセージ フローを使って確認できます。</span><span class="sxs-lookup"><span data-stu-id="580c5-117">You can use the Orchestration Debugger to see the last shapes that executed, and then use Message Flow to see what message should have been sent or received.</span></span>  
  
 <span data-ttu-id="580c5-118">BizTalk 追跡データベースが失われた場合、復旧ポイント後の動きはすべて、外部システムのレポート メカニズムを使って調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="580c5-118">If the BizTalk Tracking database was lost, all discovery of what happened past the point of recovery will need to be done by using the external systems reporting mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="580c5-119">参照</span><span class="sxs-lookup"><span data-stu-id="580c5-119">See Also</span></span>  
 [<span data-ttu-id="580c5-120">データ損失の解決</span><span class="sxs-lookup"><span data-stu-id="580c5-120">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)
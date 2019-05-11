---
title: 失われた追跡データの特定 |Microsoft Docs
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
ms.openlocfilehash: 01290e6bec1157baed8bbb89d73b10a904dc1250
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332533"
---
# <a name="identifying-lost-tracking-data"></a><span data-ttu-id="2af1c-102">失われた追跡データの特定</span><span class="sxs-lookup"><span data-stu-id="2af1c-102">Identifying Lost Tracking Data</span></span>
<span data-ttu-id="2af1c-103">追跡データが、ハードウェア障害の結果として失われたかを識別できるように、BizTalk Server 管理コンソールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2af1c-103">You can use the BizTalk Server Administration console to help identify which tracking data has been lost as a result of a hardware failure.</span></span> <span data-ttu-id="2af1c-104">BizTalk Server 管理コンソールを使用して、ライブまたはアーカイブ済みのデータのことができます。</span><span class="sxs-lookup"><span data-stu-id="2af1c-104">You can use the BizTalk Server Administration console for live or archived data.</span></span>  
  
 <span data-ttu-id="2af1c-105">BizTalk Server 管理コンソールを使用すると、どのサービスがメッセージ ボックス データベースの回復時にアクティブだったかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2af1c-105">You can use the BizTalk Server Administration console to determine which services were active at the time the MessageBox was recovered.</span></span> <span data-ttu-id="2af1c-106">データベースが回復された時間とハードウェア障害の発生時の間にギャップがあるために、一部のトランザクションの状態を確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="2af1c-106">Because there is a gap between the time that the database was recovered and the time of the hardware failure, you may not be able to determine the state of some of the transactions.</span></span>  
  
 <span data-ttu-id="2af1c-107">完了し、次のように、復旧ポイントの後に起動するサービス インスタンスを識別するために、追跡データを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2af1c-107">You can use tracking data to identify which service instances completed and started after the point of recovery, as follows:</span></span>  
  
- <span data-ttu-id="2af1c-108">データベースをバックアップするインスタンスが完了したか、前回の開始を探します。</span><span class="sxs-lookup"><span data-stu-id="2af1c-108">Look for which instances completed or started since the last time you backed up the database.</span></span>  
  
- <span data-ttu-id="2af1c-109">BizTalk 追跡 (BizTalkDTADb) データベース内のデータには、データベースにメッセージがないことと、メッセージの開始が完了しませんでしたが示されている場合、そのメッセージは、前回のバックアップ後に送信されました。</span><span class="sxs-lookup"><span data-stu-id="2af1c-109">If data in the BizTalk Tracking (BizTalkDTADb) database indicates that the message started but did not complete, and the message is not in the database, then that message was sent after the last backup.</span></span>  
  
  <span data-ttu-id="2af1c-110">追跡が完了すると、任意のサービスをレポートことができ、サービスが開始されていることを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="2af1c-110">Tracking can report on any service that completed, and it can indicate that a service started.</span></span> <span data-ttu-id="2af1c-111">追跡データはまずメッセージ ボックスにステージングし、その後、BizTalk 追跡データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="2af1c-111">Tracking data is first staged to the MessageBox and then moved to the BizTalk Tracking database.</span></span> <span data-ttu-id="2af1c-112">ステージングされたデータを BAM イベント バス サービスのバックログが失われたされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2af1c-112">The data that was staged may have been lost to the backlog of the BAM Event Bus service.</span></span>  
  
  <span data-ttu-id="2af1c-113">すべてのデータベースでは、運用上の理由から、同じマークに復元するのに必要がありますが、記号の後の変更点を確認するのにアーカイブのモードで (ですが、失われなかった BizTalk 追跡データベースを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2af1c-113">While all databases need to be restored to the same mark for operational reasons, you can use a BizTalk Tracking database (that was not lost) in Archive mode to see what happened after the mark.</span></span>  
  
  <span data-ttu-id="2af1c-114">追跡が完了済みのサービス インスタンスが表示される場合は、そのインスタンスを終了できます。</span><span class="sxs-lookup"><span data-stu-id="2af1c-114">If tracking shows a service instance as having completed, you can terminate that instance.</span></span> <span data-ttu-id="2af1c-115">これにより、復旧ポイント以降に開始されたインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2af1c-115">It may show instances that started after the point of recovery.</span></span> <span data-ttu-id="2af1c-116">そのため、これらのインスタンスがすべてのアクションを補正し、初期アクティベーション メッセージを再送信する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="2af1c-116">If so, you will need to compensate for any actions these instances took and then resubmit their initial activation messages.</span></span>  
  
  <span data-ttu-id="2af1c-117">オーケストレーション デバッガーを使用すると、実行、およびメッセージ フローが送信または受信メッセージがする必要がありますを使用する最後の図形を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2af1c-117">You can use the Orchestration Debugger to see the last shapes that executed, and then use Message Flow to see what message should have been sent or received.</span></span>  
  
  <span data-ttu-id="2af1c-118">BizTalk 追跡データベースが失われた、過去の復旧ポイントの変更点のすべての検出は、外部システムのレポート メカニズムを使用して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2af1c-118">If the BizTalk Tracking database was lost, all discovery of what happened past the point of recovery will need to be done by using the external systems reporting mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af1c-119">参照</span><span class="sxs-lookup"><span data-stu-id="2af1c-119">See Also</span></span>  
 [<span data-ttu-id="2af1c-120">データ損失の解決</span><span class="sxs-lookup"><span data-stu-id="2af1c-120">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)
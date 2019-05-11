---
title: 保留メッセージはメッセージ カウント のデータベース制限のしきい値に含まれる |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9eb708bb-6d6d-4494-8b8d-67aa44800a20
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e94671f91cf1d4a8a2c3bbaae6bb1cd5e91f8ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393886"
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a><span data-ttu-id="3ea98-102">[データベースのメッセージ カウント] の制限のしきい値に含まれる保留メッセージ</span><span class="sxs-lookup"><span data-stu-id="3ea98-102">Suspended Messages are Included in the Message Count in Database Throttling Threshold</span></span>
<span data-ttu-id="3ea98-103">既定では、ホスト**DB のメッセージ カウント**50,000 で、次の状況で制限の条件はトリガーの値に設定されている制限のしきい値。</span><span class="sxs-lookup"><span data-stu-id="3ea98-103">By default the host **Message count in DB** throttling threshold is set to a value of 50,000, which will trigger a throttling condition under the following circumstances:</span></span>  
  
- <span data-ttu-id="3ea98-104">サブスクライブを行うホストの作業キュー、状態キュー、および保留キューに対しこのホスト インスタンスによって公開されるメッセージの総数が、50,000 を超えた場合</span><span class="sxs-lookup"><span data-stu-id="3ea98-104">The total number of messages published by the host instance to the work, state, and suspended queues of the subscribing hosts exceeds 50,000.</span></span>  
  
- <span data-ttu-id="3ea98-105">スプール テーブルまたは追跡テーブル内のメッセージの数は 500,000 メッセージを超えています。</span><span class="sxs-lookup"><span data-stu-id="3ea98-105">The number of messages in the spool table or the tracking tables exceeds 500,000 messages.</span></span>  
  
  <span data-ttu-id="3ea98-106">保留中のメッセージが含まれているため、 **DB のメッセージ カウント**計算、発行は、BizTalk server が低発生している場合でも発生することがメッセージの負荷がまったくない調整します。</span><span class="sxs-lookup"><span data-stu-id="3ea98-106">Since suspended messages are included in the **Message count in DB** calculation, throttling of message publishing can occur even if the BizTalk server is experiencing low or no load.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="3ea98-107">推奨事項</span><span class="sxs-lookup"><span data-stu-id="3ea98-107">Recommendations</span></span>  
  
-   <span data-ttu-id="3ea98-108">保留メッセージの数が多いの発生することが予想される場合は、既定値を増やすことを検討してください、 **DB のメッセージ カウント**しきい値を含む SQL server の容量の要件を考慮に入れて、BizTalk データベース。</span><span class="sxs-lookup"><span data-stu-id="3ea98-108">If you anticipate that you may have a large number of suspended messages, consider increasing the default value for the **Message count in DB** threshold taking into consideration the space requirements of the SQL server that contains the BizTalk databases.</span></span> <span data-ttu-id="3ea98-109">増やすことを検討、**スプール乗数**と**追跡データ乗数**スプール テーブルに追加のバックログを許可する値。</span><span class="sxs-lookup"><span data-stu-id="3ea98-109">Also consider increasing the **Spool multiplier** and **Tracking data multiplier** values to allow additional backlog in the Spool table.</span></span>  
  
     <span data-ttu-id="3ea98-110">これらの値の詳細については、次を参照してください。[リソース ベースのスロットル設定の変更方法](../core/how-to-modify-resource-based-throttling-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="3ea98-110">For more information about these values, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span>  
  
-   <span data-ttu-id="3ea98-111">使用して、**メッセージ公開の制限の状態**に関連付けられているパフォーマンス モニター カウンター **BizTalk:MessageAgent**現在の制限の状態を測定するパフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="3ea98-111">Use the **Message publishing throttling state** Performance Monitor counter associated with **BizTalk:MessageAgent** performance object category to measure the current throttling state.</span></span> <span data-ttu-id="3ea98-112">このカウンターの値が 6 に戻る場合は、中断されたインスタンスを確認し、必要に応じてそのインスタンスを終了または再開します。</span><span class="sxs-lookup"><span data-stu-id="3ea98-112">If this counter returns a value of 6, then check for suspended instances and terminate or resume suspended instances as needed.</span></span>  
  
     <span data-ttu-id="3ea98-113">ホスト制限パフォーマンス カウンターの詳細については、次を参照してください。[ホスト制限パフォーマンス カウンター](../core/host-throttling-performance-counters.md)します。</span><span class="sxs-lookup"><span data-stu-id="3ea98-113">For more information about the host throttling performance counters, see [Host Throttling Performance Counters](../core/host-throttling-performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea98-114">参照</span><span class="sxs-lookup"><span data-stu-id="3ea98-114">See Also</span></span>  
 [<span data-ttu-id="3ea98-115">制限の設計時の推奨事項</span><span class="sxs-lookup"><span data-stu-id="3ea98-115">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)
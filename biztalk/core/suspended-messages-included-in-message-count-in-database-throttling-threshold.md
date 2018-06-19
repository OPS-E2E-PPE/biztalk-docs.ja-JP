---
title: '[メッセージ カウント] データベースの制限のしきい値に含まれる保留メッセージ |Microsoft ドキュメント'
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
ms.openlocfilehash: 7f8ea0643ccf2d6206ba86bc56b5dd54c0d51115
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278130"
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a><span data-ttu-id="4b3fc-102">[データベースのメッセージ カウント] の制限のしきい値に含まれる保留メッセージ</span><span class="sxs-lookup"><span data-stu-id="4b3fc-102">Suspended Messages are Included in the Message Count in Database Throttling Threshold</span></span>
<span data-ttu-id="4b3fc-103">既定では、ホスト**DB 内の数をメッセージ**は、次の状況で制限の条件をトリガーする 50,000 値に設定されている制限のしきい値。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-103">By default the host **Message count in DB** throttling threshold is set to a value of 50,000, which will trigger a throttling condition under the following circumstances:</span></span>  
  
-   <span data-ttu-id="4b3fc-104">サブスクライブを行うホストの作業キュー、状態キュー、および保留キューに対しこのホスト インスタンスによって公開されるメッセージの総数が、50,000 を超えた場合</span><span class="sxs-lookup"><span data-stu-id="4b3fc-104">The total number of messages published by the host instance to the work, state, and suspended queues of the subscribing hosts exceeds 50,000.</span></span>  
  
-   <span data-ttu-id="4b3fc-105">スプール テーブルまたは追跡テーブル内のメッセージの数は、500,000 メッセージを超えています。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-105">The number of messages in the spool table or the tracking tables exceeds 500,000 messages.</span></span>  
  
 <span data-ttu-id="4b3fc-106">保留中のメッセージが含まれているため、 **DB 内の数をメッセージ**計算、発行は、BizTalk server が低発生している場合でも発生する可能性がメッセージまたは負荷がまったくないを調整します。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-106">Since suspended messages are included in the **Message count in DB** calculation, throttling of message publishing can occur even if the BizTalk server is experiencing low or no load.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="4b3fc-107">推奨事項</span><span class="sxs-lookup"><span data-stu-id="4b3fc-107">Recommendations</span></span>  
  
-   <span data-ttu-id="4b3fc-108">保留メッセージの数が多いがありますが予想される場合は、既定値を増やすことを検討、 **DB 内の数をメッセージ**しきい値を含む SQL server の容量の要件を考慮に入れて、BizTalk データベース。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-108">If you anticipate that you may have a large number of suspended messages, consider increasing the default value for the **Message count in DB** threshold taking into consideration the space requirements of the SQL server that contains the BizTalk databases.</span></span> <span data-ttu-id="4b3fc-109">増やすことを検討、**スプール乗数**と**追跡データ乗数**値が、スプール テーブルの追加のバックログを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-109">Also consider increasing the **Spool multiplier** and **Tracking data multiplier** values to allow additional backlog in the Spool table.</span></span>  
  
     <span data-ttu-id="4b3fc-110">これらの値の詳細については、次を参照してください。[リソース ベースの調整設定の変更方法](../core/how-to-modify-resource-based-throttling-settings.md)です。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-110">For more information about these values, see [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span>  
  
-   <span data-ttu-id="4b3fc-111">使用して、**メッセージ公開の制限の状態**に関連付けられているパフォーマンス モニター カウンター **BizTalk:MessageAgent**現在の制限の状態を測定するパフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-111">Use the **Message publishing throttling state** Performance Monitor counter associated with **BizTalk:MessageAgent** performance object category to measure the current throttling state.</span></span> <span data-ttu-id="4b3fc-112">このカウンターの値が 6 に戻る場合は、中断されたインスタンスを確認し、必要に応じてそのインスタンスを終了または再開します。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-112">If this counter returns a value of 6, then check for suspended instances and terminate or resume suspended instances as needed.</span></span>  
  
     <span data-ttu-id="4b3fc-113">ホスト制限パフォーマンス カウンターの詳細については、次を参照してください。[ホスト制限パフォーマンス カウンター](../core/host-throttling-performance-counters.md)です。</span><span class="sxs-lookup"><span data-stu-id="4b3fc-113">For more information about the host throttling performance counters, see [Host Throttling Performance Counters](../core/host-throttling-performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3fc-114">参照</span><span class="sxs-lookup"><span data-stu-id="4b3fc-114">See Also</span></span>  
 [<span data-ttu-id="4b3fc-115">設計の推奨事項の調整</span><span class="sxs-lookup"><span data-stu-id="4b3fc-115">Throttling Design Recommendations</span></span>](../core/throttling-design-recommendations.md)
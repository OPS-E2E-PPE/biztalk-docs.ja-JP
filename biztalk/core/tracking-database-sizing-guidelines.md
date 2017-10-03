---
title: "追跡データベースのサイズに関するガイドライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, performance
- Tracking database, size
- Tracking Analysis Server database [BAM]
- performance, Tracking database
ms.assetid: 2188bee5-c0dd-4448-bd4a-4ffb2a0c79f1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c0293ff0a03583e51ee447ec1bd6283f1b02164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tracking-database-sizing-guidelines"></a><span data-ttu-id="2d37a-102">追跡データベースのサイズに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="2d37a-102">Tracking Database Sizing Guidelines</span></span>
<span data-ttu-id="2d37a-103">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BizTalk 追跡 (BizTalkDTADb) データベースのサイズに関する注意事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d37a-103">This section describes sizing considerations for the BizTalk Tracking (BizTalkDTADb) database in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2d37a-104">BizTalk 追跡データベースが特定の期間にどれだけ大きくなるかを判断するため、式とメッセージ変数を使用する方法を説明し、式の適用方法に関する具体的な例を示します。</span><span class="sxs-lookup"><span data-stu-id="2d37a-104">It explains how to use equations and message variables to determine how large the BizTalk Tracking database will become over a given period of time, and provides specific examples of how to apply the equations.</span></span> <span data-ttu-id="2d37a-105">また、BizTalk メッセージ、追跡設定、および追跡データベースのサイズ間の関連付けは目安です。</span><span class="sxs-lookup"><span data-stu-id="2d37a-105">This provides the rough co-relation between BizTalk messages, tracking settings and the tracking database size.</span></span> <span data-ttu-id="2d37a-106">追跡テーブルのインデックス サイズなどの他の SQL Server の係数は考慮しません。ただし、これらの係数を計算する適切な乗数を検討する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d37a-106">It does not take into account other SQL Server factors such as index size in the tracking tables; you may want to consider reasonable multipliers to account for those factors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d37a-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2d37a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="2d37a-108">追跡データベースのサイズをメッセージ変数を使用</span><span class="sxs-lookup"><span data-stu-id="2d37a-108">Using Message Variables to Size the Tracking Database</span></span>](../core/using-message-variables-to-size-the-tracking-database.md)  
  
-   [<span data-ttu-id="2d37a-109">メッセージ本文を追跡する追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="2d37a-109">Sizing the Tracking Database to Track Message Bodies</span></span>](../core/sizing-the-tracking-database-to-track-message-bodies.md)  
  
-   [<span data-ttu-id="2d37a-110">シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="2d37a-110">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)  
  
-   [<span data-ttu-id="2d37a-111">シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="2d37a-111">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)  
  
-   [<span data-ttu-id="2d37a-112">シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="2d37a-112">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)  
  
-   [<span data-ttu-id="2d37a-113">シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="2d37a-113">Scenario 4: Sizing the Tracking Database for all Messages</span></span>](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d37a-114">参照</span><span class="sxs-lookup"><span data-stu-id="2d37a-114">See Also</span></span>  
 <span data-ttu-id="2d37a-115">[追跡データベースのレコード サイズ](../core/record-size-in-tracking-databases.md) </span><span class="sxs-lookup"><span data-stu-id="2d37a-115">[Record Size in Tracking Databases](../core/record-size-in-tracking-databases.md) </span></span>  
 [<span data-ttu-id="2d37a-116">BizTalk Server データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="2d37a-116">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)
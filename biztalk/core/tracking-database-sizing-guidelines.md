---
title: 追跡データベースのサイズのガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, performance
- Tracking database, size
- Tracking Analysis Server database [BAM]
- performance, Tracking database
ms.assetid: 2188bee5-c0dd-4448-bd4a-4ffb2a0c79f1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c21ce436ac194c06481f80e80c4add3f70f48872
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313925"
---
# <a name="tracking-database-sizing-guidelines"></a><span data-ttu-id="5568d-102">追跡データベースのサイズに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="5568d-102">Tracking Database Sizing Guidelines</span></span>
<span data-ttu-id="5568d-103">このセクションで、BizTalk 追跡 (BizTalkDTADb) データベースのサイズに関する考慮事項を説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5568d-103">This section describes sizing considerations for the BizTalk Tracking (BizTalkDTADb) database in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5568d-104">式とメッセージ変数を使用して、大きさ、BizTalk 追跡データベースになります特定期間にわたってを決定する方法について説明し、数式を適用する方法の具体例を提供します。</span><span class="sxs-lookup"><span data-stu-id="5568d-104">It explains how to use equations and message variables to determine how large the BizTalk Tracking database will become over a given period of time, and provides specific examples of how to apply the equations.</span></span> <span data-ttu-id="5568d-105">これにより、BizTalk メッセージ、追跡設定と追跡データベースの間の関連付けは目安サイズ。</span><span class="sxs-lookup"><span data-stu-id="5568d-105">This provides the rough co-relation between BizTalk messages, tracking settings and the tracking database size.</span></span> <span data-ttu-id="5568d-106">SQL Server の係数は、追跡テーブルのインデックス サイズなど他のアカウントを受け取らないそれらの要因に対応する適切な乗数を検討する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5568d-106">It does not take into account other SQL Server factors such as index size in the tracking tables; you may want to consider reasonable multipliers to account for those factors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5568d-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5568d-107">In This Section</span></span>  
  
-   [<span data-ttu-id="5568d-108">追跡データベースのサイズにメッセージ変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5568d-108">Using Message Variables to Size the Tracking Database</span></span>](../core/using-message-variables-to-size-the-tracking-database.md)  
  
-   [<span data-ttu-id="5568d-109">メッセージ本文を追跡する追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="5568d-109">Sizing the Tracking Database to Track Message Bodies</span></span>](../core/sizing-the-tracking-database-to-track-message-bodies.md)  
  
-   [<span data-ttu-id="5568d-110">シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="5568d-110">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)  
  
-   [<span data-ttu-id="5568d-111">シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="5568d-111">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)  
  
-   [<span data-ttu-id="5568d-112">シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="5568d-112">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)  
  
-   [<span data-ttu-id="5568d-113">シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="5568d-113">Scenario 4: Sizing the Tracking Database for all Messages</span></span>](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="5568d-114">参照</span><span class="sxs-lookup"><span data-stu-id="5568d-114">See Also</span></span>  
 <span data-ttu-id="5568d-115">[追跡データベースのレコード サイズ](../core/record-size-in-tracking-databases.md) </span><span class="sxs-lookup"><span data-stu-id="5568d-115">[Record Size in Tracking Databases](../core/record-size-in-tracking-databases.md) </span></span>  
 [<span data-ttu-id="5568d-116">バックアップおよび BizTalk Server データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="5568d-116">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)
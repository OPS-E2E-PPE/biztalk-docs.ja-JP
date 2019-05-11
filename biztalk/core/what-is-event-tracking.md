---
title: イベントの追跡とは | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [HAT tracking], events
- DTA_Services audit table [HAT]
- HAT, events
- events, tracking
- tracking, events
- Tracking database, DTA_Services audit table
- events, HAT
ms.assetid: dd211752-d1af-4287-967a-908b8d067ebb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e516121a27a1dda41019f99a0e5c2ba0c60c628b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379682"
---
# <a name="what-is-event-tracking"></a><span data-ttu-id="ced05-103">イベントの追跡とは</span><span class="sxs-lookup"><span data-stu-id="ced05-103">What is Event Tracking?</span></span>
<span data-ttu-id="ced05-104">追跡メッセージ イベントのデータは、(たとえば、サービスを開始または停止すると場合、または、メッセージが送信または受信したときになど)、イベントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="ced05-104">Tracked message event data is based upon events (for example, when a service begins or ends, or when a message is sent or received).</span></span> <span data-ttu-id="ced05-105">メッセージ イベントの追跡プロセスは、設定した追跡フィルターに基づいて行われたすべての参照を有効にすると、発生したイベントの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="ced05-105">The message event tracking process returns a list of the events that have occurred, enabling you to see everything that happened based on the tracking filters you have set.</span></span>  
  
 <span data-ttu-id="ced05-106">開始オーケストレーションとポート、メッセージの送信および受信されたときの最後とオーケストレーション内の各図形の実行を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="ced05-106">You can track the start and end of orchestrations and ports, when messages are sent and received, as well as the execution of each shape in an orchestration.</span></span>  
  
 <span data-ttu-id="ced05-107">BizTalk 追跡 (BizTalkDTADb) データベースには、DTA_Services 監査テーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ced05-107">The BizTalk Tracking (BizTalkDTADb) database contains a DTA_Services audit table.</span></span> <span data-ttu-id="ced05-108">このテーブルには、すべてのデプロイ済みサービスの履歴が含まれています: パイプライン、トランスポート、およびオーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="ced05-108">This table contains history of all deployed services—pipelines, transports, and orchestrations.</span></span> <span data-ttu-id="ced05-109">これを追跡展開解除をします。</span><span class="sxs-lookup"><span data-stu-id="ced05-109">It does not keep track of undeployments.</span></span>  
  
 <span data-ttu-id="ced05-110">メッセージの内容およびとのメッセージの昇格させたプロパティを追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="ced05-110">You can track the contents of a message as well as the promoted properties of a message.</span></span> <span data-ttu-id="ced05-111">これらのアクションとして追跡メッセージ イベントを定義します**メッセージ本文**追跡と**メッセージ プロパティ**追跡します。</span><span class="sxs-lookup"><span data-stu-id="ced05-111">Tracking message events defines these actions as **Message Body** tracking and **Message Property** tracking.</span></span> <span data-ttu-id="ced05-112">エンベロープ メッセージ イベントの追跡の出力に表示されますが、そこからメッセージのプロパティを追跡できません。</span><span class="sxs-lookup"><span data-stu-id="ced05-112">Although envelopes appear in the message event tracking output, you cannot track message properties from them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced05-113">参照</span><span class="sxs-lookup"><span data-stu-id="ced05-113">See Also</span></span>  
 [<span data-ttu-id="ced05-114">BizTalk Server 管理コンソールの使用の追跡の構成</span><span class="sxs-lookup"><span data-stu-id="ced05-114">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)

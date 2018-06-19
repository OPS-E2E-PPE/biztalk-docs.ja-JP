---
title: イベント追跡について | Microsoft Docs
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
ms.openlocfilehash: faa53881cf42ae2769621e10ce21e1160f9b7be0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289194"
---
# <a name="what-is-event-tracking"></a><span data-ttu-id="2202e-103">イベント追跡について</span><span class="sxs-lookup"><span data-stu-id="2202e-103">What is Event Tracking?</span></span>
<span data-ttu-id="2202e-104">追跡メッセージ イベント データは、サービスの開始時や終了時、メッセージの送受信時などのイベントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="2202e-104">Tracked message event data is based upon events (for example, when a service begins or ends, or when a message is sent or received).</span></span> <span data-ttu-id="2202e-105">メッセージ イベントの追跡処理によって、発生したイベントの一覧が返され、設定した追跡フィルターに基づいて、発生したすべてのイベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2202e-105">The message event tracking process returns a list of the events that have occurred, enabling you to see everything that happened based on the tracking filters you have set.</span></span>  
  
 <span data-ttu-id="2202e-106">オーケストレーションやポートの開始と終了、メッセージの送信時と受信時、およびオーケストレーションの各図形の実行を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="2202e-106">You can track the start and end of orchestrations and ports, when messages are sent and received, as well as the execution of each shape in an orchestration.</span></span>  
  
 <span data-ttu-id="2202e-107">BizTalk 追跡 (BizTalkDTADb) データベースには、DTA_Services 監査テーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2202e-107">The BizTalk Tracking (BizTalkDTADb) database contains a DTA_Services audit table.</span></span> <span data-ttu-id="2202e-108">このテーブルには、すべてのデプロイ済みサービスの履歴が含まれています — パイプライン、トランスポート、およびオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="2202e-108">This table contains history of all deployed services—pipelines, transports, and orchestrations.</span></span> <span data-ttu-id="2202e-109">ただし、展開解除の追跡は記録されません。</span><span class="sxs-lookup"><span data-stu-id="2202e-109">It does not keep track of undeployments.</span></span>  
  
 <span data-ttu-id="2202e-110">メッセージについては、内容および昇格させたプロパティを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="2202e-110">You can track the contents of a message as well as the promoted properties of a message.</span></span> <span data-ttu-id="2202e-111">これらのアクションとして追跡メッセージ イベントを定義**メッセージ本文**追跡と**メッセージ プロパティ**追跡します。</span><span class="sxs-lookup"><span data-stu-id="2202e-111">Tracking message events defines these actions as **Message Body** tracking and **Message Property** tracking.</span></span> <span data-ttu-id="2202e-112">メッセージ イベントの追跡の出力にはエンベロープが表示されますが、そこからメッセージのプロパティを追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="2202e-112">Although envelopes appear in the message event tracking output, you cannot track message properties from them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2202e-113">参照</span><span class="sxs-lookup"><span data-stu-id="2202e-113">See Also</span></span>  
 [<span data-ttu-id="2202e-114">BizTalk Server 管理コンソールを使用して追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="2202e-114">Configuring Tracking Using the BizTalk Server Administration Console</span></span>](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)
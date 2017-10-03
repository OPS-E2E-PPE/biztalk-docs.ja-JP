---
title: "イベント追跡について | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa53881cf42ae2769621e10ce21e1160f9b7be0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-event-tracking"></a>イベント追跡について
追跡メッセージ イベント データは、サービスの開始時や終了時、メッセージの送受信時などのイベントに基づいています。 メッセージ イベントの追跡処理によって、発生したイベントの一覧が返され、設定した追跡フィルターに基づいて、発生したすべてのイベントを確認できます。  
  
 オーケストレーションやポートの開始と終了、メッセージの送信時と受信時、およびオーケストレーションの各図形の実行を追跡できます。  
  
 BizTalk 追跡 (BizTalkDTADb) データベースには、DTA_Services 監査テーブルが含まれています。 このテーブルには、すべてのデプロイ済みサービスの履歴が含まれています — パイプライン、トランスポート、およびオーケストレーションです。 ただし、展開解除の追跡は記録されません。  
  
 メッセージについては、内容および昇格させたプロパティを追跡できます。 これらのアクションとして追跡メッセージ イベントを定義**メッセージ本文**追跡と**メッセージ プロパティ**追跡します。 メッセージ イベントの追跡の出力にはエンベロープが表示されますが、そこからメッセージのプロパティを追跡することはできません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 管理コンソールを使用して追跡を構成します。](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)
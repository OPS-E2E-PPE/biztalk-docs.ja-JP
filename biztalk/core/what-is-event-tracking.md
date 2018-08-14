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
ms.openlocfilehash: 42799a084c579cfba7d696c700d887b1ae992db2
ms.sourcegitcommit: ed9590dbcd97c12a1fe5ce2cdf8d826492cccdff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39640086"
---
# <a name="what-is-event-tracking"></a>イベント追跡について
追跡メッセージ イベント データは、サービスの開始時や終了時、メッセージの送受信時などのイベントに基づいています。 メッセージ イベントの追跡処理によって、発生したイベントの一覧が返され、設定した追跡フィルターに基づいて、発生したすべてのイベントを確認できます。  
  
 オーケストレーションやポートの開始と終了、メッセージの送信時と受信時、およびオーケストレーションの各図形の実行を追跡できます。  
  
 BizTalk 追跡 (BizTalkDTADb) データベースには、DTA_Services 監査テーブルが含まれています。 このテーブルには、すべてのデプロイ済みサービスの履歴が含まれています: パイプライン、トランスポート、およびオーケストレーションします。 ただし、展開解除の追跡は記録されません。  
  
 メッセージについては、内容および昇格させたプロパティを追跡できます。 これらのアクションとして追跡メッセージ イベントを定義します**メッセージ本文**追跡と**メッセージ プロパティ**追跡します。 メッセージ イベントの追跡の出力にはエンベロープが表示されますが、そこからメッセージのプロパティを追跡することはできません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 管理コンソールの使用の追跡の構成](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)

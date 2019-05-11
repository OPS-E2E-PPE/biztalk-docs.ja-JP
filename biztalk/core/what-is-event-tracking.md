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
# <a name="what-is-event-tracking"></a>イベントの追跡とは
追跡メッセージ イベントのデータは、(たとえば、サービスを開始または停止すると場合、または、メッセージが送信または受信したときになど)、イベントに基づいています。 メッセージ イベントの追跡プロセスは、設定した追跡フィルターに基づいて行われたすべての参照を有効にすると、発生したイベントの一覧を返します。  
  
 開始オーケストレーションとポート、メッセージの送信および受信されたときの最後とオーケストレーション内の各図形の実行を追跡できます。  
  
 BizTalk 追跡 (BizTalkDTADb) データベースには、DTA_Services 監査テーブルが含まれています。 このテーブルには、すべてのデプロイ済みサービスの履歴が含まれています: パイプライン、トランスポート、およびオーケストレーションします。 これを追跡展開解除をします。  
  
 メッセージの内容およびとのメッセージの昇格させたプロパティを追跡することができます。 これらのアクションとして追跡メッセージ イベントを定義します**メッセージ本文**追跡と**メッセージ プロパティ**追跡します。 エンベロープ メッセージ イベントの追跡の出力に表示されますが、そこからメッセージのプロパティを追跡できません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 管理コンソールの使用の追跡の構成](http://msdn.microsoft.com/49b7f9d3-60b5-41bd-ba8b-029253926bef)

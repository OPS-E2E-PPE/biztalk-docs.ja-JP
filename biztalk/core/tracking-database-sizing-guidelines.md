---
title: 追跡データベースのサイズに関するガイドライン |Microsoft ドキュメント
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
ms.openlocfilehash: 1c0293ff0a03583e51ee447ec1bd6283f1b02164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279698"
---
# <a name="tracking-database-sizing-guidelines"></a>追跡データベースのサイズに関するガイドライン
このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BizTalk 追跡 (BizTalkDTADb) データベースのサイズに関する注意事項について説明します。 BizTalk 追跡データベースが特定の期間にどれだけ大きくなるかを判断するため、式とメッセージ変数を使用する方法を説明し、式の適用方法に関する具体的な例を示します。 また、BizTalk メッセージ、追跡設定、および追跡データベースのサイズ間の関連付けは目安です。 追跡テーブルのインデックス サイズなどの他の SQL Server の係数は考慮しません。ただし、これらの係数を計算する適切な乗数を検討する場合があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md)  
  
-   [メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md)  
  
-   [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)  
  
-   [シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)  
  
-   [シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)  
  
-   [シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)  
  
## <a name="see-also"></a>参照  
 [追跡データベースのレコード サイズ](../core/record-size-in-tracking-databases.md)   
 [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-biztalk-server-databases.md)
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
# <a name="tracking-database-sizing-guidelines"></a>追跡データベースのサイズに関するガイドライン
このセクションで、BizTalk 追跡 (BizTalkDTADb) データベースのサイズに関する考慮事項を説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 式とメッセージ変数を使用して、大きさ、BizTalk 追跡データベースになります特定期間にわたってを決定する方法について説明し、数式を適用する方法の具体例を提供します。 これにより、BizTalk メッセージ、追跡設定と追跡データベースの間の関連付けは目安サイズ。 SQL Server の係数は、追跡テーブルのインデックス サイズなど他のアカウントを受け取らないそれらの要因に対応する適切な乗数を検討する必要がある可能性があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md)  
  
-   [メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md)  
  
-   [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)  
  
-   [シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)  
  
-   [シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)  
  
-   [シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)  
  
## <a name="see-also"></a>参照  
 [追跡データベースのレコード サイズ](../core/record-size-in-tracking-databases.md)   
 [バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)
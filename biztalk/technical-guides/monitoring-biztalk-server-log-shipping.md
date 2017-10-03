---
title: "ログ配布の BizTalk Server の監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae4ff40-7d86-4e9b-b1cc-4f00486ae4b9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eacec106823afc8203e7cce9679cb27cd29d0b78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-biztalk-server-log-shipping"></a>ログ配布の BizTalk Server の監視
BizTalk Server データベースと復元されたログの最後の正常なバックアップ セットを調べるには、先に Master.dbo.bts_LogShippingHistory テーブルの内容を確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。 このテーブルは、BizTalk Server ログ配布のバックアップ履歴の取得ジョブによって設定されます、復元ジョブによって更新されます。 バックアップが正常に復元すると、Restored 列が 1 の値に設定されているし、RestoredDateTime が現在の日付と時刻に設定します。  
  
 すべてのサーバー設定、Master.dbo.bts_LogShippingHistory テーブルに一覧されている特定のバックアップから復元したデータベースが正常に復元されましたが、バックアップ セット ID が Master.dbo.bts_LogShippingLastRestoreSet テーブルに書き込まれます。 このテーブルは、最後に復元された設定を格納し、障害復旧イベントの発生後、移行先 BizTalk グループをオンラインに復元する必要があるログのバックアップ セットを決定するために便利です。  
  
## <a name="see-also"></a>参照  
 [ログ配布の BizTalk Server の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)
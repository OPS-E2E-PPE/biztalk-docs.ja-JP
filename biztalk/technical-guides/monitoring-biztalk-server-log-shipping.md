---
title: ログ配布の BizTalk Server の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fae4ff40-7d86-4e9b-b1cc-4f00486ae4b9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578a587bbf500d5f49244fb8a56aac9d9fe83d19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379467"
---
# <a name="monitoring-biztalk-server-log-shipping"></a>ログ配布の BizTalk Server の監視
を BizTalk Server データベースとログの復元されての成功した最後のバックアップ セットを確認するには、先に Master.dbo.bts_LogShippingHistory テーブルの内容を確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。 この表では、BizTalk Server ログ配布の履歴の取得のバックアップ ジョブによって作成され、復元ジョブによって更新されます。 バックアップが正常に復元されると、Restored 列が 1 の値に設定し、RestoredDateTime が現在の日付と時刻に設定されています。  
  
 すべて設定 Master.dbo.bts_LogShippingHistory テーブルの一覧表示されている特定のバックアップからサーバーに復元されたデータベースの正常に復元されましたが、バックアップ セット ID が Master.dbo.bts_LogShippingLastRestoreSet テーブルに書き込まれます。 このテーブルは、最後の復元設定を格納しは、ディザスター リカバリー イベントの発生後、移行先 BizTalk グループをオンラインに復元する必要があるログのバックアップ セットを決定するために便利です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のログ配布の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)
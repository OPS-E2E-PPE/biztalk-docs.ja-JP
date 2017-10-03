---
title: "バックアップを復元の履歴の表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring, history
- backing up, history
ms.assetid: 8852befa-b8e7-469d-b014-75c881907442
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa5a7fbe2b0e731920880570b0555402ba162c7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="viewing-the-history-of-restored-backups"></a>バックアップ復元履歴の表示
最後に復元に成功したバックアップ セットを確認するには、Master.dbo.bts_LogShippingHistory テーブルの内容を調べます。 このテーブルの内容は、バックアップ履歴の取得ジョブによって取得され、データベースの復元ジョブによって更新されます。 バックアップの復元に成功した場合、Restored 列に 1 が、RestoredDateTime に現在の日時が格納されます。  
  
 特定のバックアップ セットから、復元対象のすべてのデータベースが正しくサーバーに復元された場合、そのバックアップ セットの ID が Master.dbo.bts_LogShippingLastRestoreSet テーブルに書き込まれます。  
  
## <a name="gaps-in-the-restore-process"></a>復元プロセスのギャップ  
 Master.dbo.bts_LogShippingHistory テーブルのレコードを確認すると、復元済みのバックアップ セット間にギャップが存在する場合があります。 これにはいくつかの理由が考えられます。 ただし、ギャップが発生しても、復元先システム (つまり、バックアップ コンピュータ) の安定性を回復できる場合があります。 復元先のシステムを修復するには、ギャップの後に完全バックアップ セットの復元が必要です。 ギャップの後に完全バックアップ セットの復元を行わないと、復元先の環境が不安定になります。  
  
> [!NOTE]
>  本来、完全バックアップを復元する目的は、データベースの初期状態を作成したり、ログ履歴バックアップ チェーンの問題を修復したりすることです。 完全バックアップ セットは、ログ バックアップ チェーンには含まれないため、通常、完全バックアップ セットから復元することはありません。  
  
## <a name="see-also"></a>参照  
 [バックアップと復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)
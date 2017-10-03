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
# <a name="monitoring-biztalk-server-log-shipping"></a><span data-ttu-id="7469f-102">ログ配布の BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="7469f-102">Monitoring BizTalk Server Log Shipping</span></span>
<span data-ttu-id="7469f-103">BizTalk Server データベースと復元されたログの最後の正常なバックアップ セットを調べるには、先に Master.dbo.bts_LogShippingHistory テーブルの内容を確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="7469f-103">To determine the last successful backup set of BizTalk Server databases and logs that have been restored, review the contents of the Master.dbo.bts_LogShippingHistory table on the destination [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span> <span data-ttu-id="7469f-104">このテーブルは、BizTalk Server ログ配布のバックアップ履歴の取得ジョブによって設定されます、復元ジョブによって更新されます。</span><span class="sxs-lookup"><span data-stu-id="7469f-104">This table is populated by the BizTalk Server Log Shipping Get Backup History job and is updated by the restore job.</span></span> <span data-ttu-id="7469f-105">バックアップが正常に復元すると、Restored 列が 1 の値に設定されているし、RestoredDateTime が現在の日付と時刻に設定します。</span><span class="sxs-lookup"><span data-stu-id="7469f-105">When a backup is successfully restored, the Restored column is set to a value of 1 and the RestoredDateTime is set to the current date and time.</span></span>  
  
 <span data-ttu-id="7469f-106">すべてのサーバー設定、Master.dbo.bts_LogShippingHistory テーブルに一覧されている特定のバックアップから復元したデータベースが正常に復元されましたが、バックアップ セット ID が Master.dbo.bts_LogShippingLastRestoreSet テーブルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="7469f-106">When all of the databases restored to the server from a particular backup set listed in the Master.dbo.bts_LogShippingHistory table have been successfully restored, the backup set ID is written to the Master.dbo.bts_LogShippingLastRestoreSet table.</span></span> <span data-ttu-id="7469f-107">このテーブルは、最後に復元された設定を格納し、障害復旧イベントの発生後、移行先 BizTalk グループをオンラインに復元する必要があるログのバックアップ セットを決定するために便利です。</span><span class="sxs-lookup"><span data-stu-id="7469f-107">This table stores the last set restored and is useful for determining what backup set of logs need to be restored to bring the destination BizTalk group online after the occurrence of a disaster recovery event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7469f-108">参照</span><span class="sxs-lookup"><span data-stu-id="7469f-108">See Also</span></span>  
 [<span data-ttu-id="7469f-109">ログ配布の BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="7469f-109">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)
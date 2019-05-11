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
# <a name="monitoring-biztalk-server-log-shipping"></a><span data-ttu-id="fee95-102">ログ配布の BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="fee95-102">Monitoring BizTalk Server Log Shipping</span></span>
<span data-ttu-id="fee95-103">を BizTalk Server データベースとログの復元されての成功した最後のバックアップ セットを確認するには、先に Master.dbo.bts_LogShippingHistory テーブルの内容を確認[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="fee95-103">To determine the last successful backup set of BizTalk Server databases and logs that have been restored, review the contents of the Master.dbo.bts_LogShippingHistory table on the destination [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span> <span data-ttu-id="fee95-104">この表では、BizTalk Server ログ配布の履歴の取得のバックアップ ジョブによって作成され、復元ジョブによって更新されます。</span><span class="sxs-lookup"><span data-stu-id="fee95-104">This table is populated by the BizTalk Server Log Shipping Get Backup History job and is updated by the restore job.</span></span> <span data-ttu-id="fee95-105">バックアップが正常に復元されると、Restored 列が 1 の値に設定し、RestoredDateTime が現在の日付と時刻に設定されています。</span><span class="sxs-lookup"><span data-stu-id="fee95-105">When a backup is successfully restored, the Restored column is set to a value of 1 and the RestoredDateTime is set to the current date and time.</span></span>  
  
 <span data-ttu-id="fee95-106">すべて設定 Master.dbo.bts_LogShippingHistory テーブルの一覧表示されている特定のバックアップからサーバーに復元されたデータベースの正常に復元されましたが、バックアップ セット ID が Master.dbo.bts_LogShippingLastRestoreSet テーブルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="fee95-106">When all of the databases restored to the server from a particular backup set listed in the Master.dbo.bts_LogShippingHistory table have been successfully restored, the backup set ID is written to the Master.dbo.bts_LogShippingLastRestoreSet table.</span></span> <span data-ttu-id="fee95-107">このテーブルは、最後の復元設定を格納しは、ディザスター リカバリー イベントの発生後、移行先 BizTalk グループをオンラインに復元する必要があるログのバックアップ セットを決定するために便利です。</span><span class="sxs-lookup"><span data-stu-id="fee95-107">This table stores the last set restored and is useful for determining what backup set of logs need to be restored to bring the destination BizTalk group online after the occurrence of a disaster recovery event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee95-108">参照</span><span class="sxs-lookup"><span data-stu-id="fee95-108">See Also</span></span>  
 [<span data-ttu-id="fee95-109">BizTalk Server のログ配布の構成</span><span class="sxs-lookup"><span data-stu-id="fee95-109">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)
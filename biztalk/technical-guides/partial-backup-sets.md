---
title: バックアップ セットの一部 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9f15c0-4d31-4322-ac0a-8efdeed6f71e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baacc7a30a79084430ce570fc135b92e07586779
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291330"
---
# <a name="partial-backup-sets"></a>バックアップ セットの一部
ソース システム上のデータベースのバックアップ、問題がバックアップ セットの一部では、その結果発生する可能性があります。 Master.dbo.bts_LogShippingHistory テーブルには、0 にが含まれますこれが発生したときに、 **SetComplete**セット内のすべてのレコードの列。  
  
 これらのセットを復元することはできません。 その結果、ログのバックアップ セットのチェーンは解除されます。 セットを無視する必要があります、すべてのログとバックアップ セットをその後、[次へ] の完全バックアップ セットへ。 [次へ] の有効な完全バックアップ セットの復元ジョブが自動的になります。 1 つ検出されません、失敗し、復元先の環境を修復するために設定されます。  
  
 ほとんどの場合、バックアップ セットの一部が発生し、次回実行するように構成されている場合、完全バックアップ セットが自動的に生成されますには、ソース システムを検出します。  
  
> [!NOTE]  
>  この問題の最も一般的な原因は、送信先システムでファイル グループのディスク領域不足です。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)
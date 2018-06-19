---
title: バックアップ セットの一部 |Microsoft ドキュメント
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
ms.openlocfilehash: f9740cb0f45d6bb46c13a95e50e4717ef142b164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298162"
---
# <a name="partial-backup-sets"></a>バックアップ セットの一部
ソース システム上のデータベースのバックアップ時にバックアップ セットの一部になる問題が発生する可能性があります。 これが発生すると、Master.dbo.bts_LogShippingHistory テーブルが含まで 0、 **SetComplete**セット内のすべてのレコードの列です。  
  
 これらのセットを復元することはできません。 その結果、ログのバックアップ セットのチェーンが壊れています。 すべてのログとバックアップ セットをその後、次の完全バックアップ セットまで、セットを無視する必要があります。 次の有効な完全バックアップ セットの復元ジョブが自動的になります。 実行していないため、失敗し、復元先の環境を修復するために設定されます。  
  
 ほとんどの場合、送信元システムことが検出バックアップ セットの一部が発生しましたし、次回実行するように構成されている場合、完全バックアップ セットが自動的に生成されます。  
  
> [!NOTE]  
>  この問題の最も一般的な原因は、ターゲット システム上のファイル グループのディスク領域不足です。  
  
## <a name="see-also"></a>参照  
 [ログ配布のトラブルシューティング](../technical-guides/troubleshooting-log-shipping.md)
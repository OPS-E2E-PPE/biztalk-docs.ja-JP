---
title: 実行中のオーケストレーションのデータ損失の解決 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, MessageBox database
- data recovery
- data loss, recovery
- data loss, orchestrations
- data recovery, MessageBox database
- data recovery, orchestrations
- data loss, data recovery
- orchestrations, data recovery
- orchestrations, data loss
ms.assetid: dc6f1fd2-1976-40f2-ab57-41c7db40705e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eca757b80e31ee5db829d2d2079bf657d01079b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269002"
---
# <a name="resolving-data-loss-of-in-progress-orchestrations"></a>進行中のオーケストレーションのデータ損失の解決
メッセージ ボックス データベースには、現在進行中のオーケストレーションの状態情報が格納されます。 メッセージ ボックス データベースで正確にどのデータの損失があったかを検出する方法はありませんが、損失データの情報を収集するための手段はあります。  
  
-   復旧ポイント以降、現在のオーケストレーションで、どのメッセージが送信および受信されたか、また、どの外部システムが使用されたかを特定します。 たとえば、システムにメッセージおよびイベントの外部ログが保持されている場合は、そのログを調べます。 また、外部システムを手動でチェックして、どのようなアクティビティが発生したかを確認することも必要です。  
  
-   データ損失の原因を特定した後で、復元されたシステムの修正を開始できます。続行中のプロセス、終了して再開 (失われたアクティベーション メッセージを再送信) する必要のあるプロセス、および正常に完了していて終了できるプロセスを識別します。 このプロセスは、システムのアーキテクチャによって大きく異なります。これは、復旧計画の一部として考える必要があります。  
  
## <a name="see-also"></a>参照  
 [データ損失の解決](../core/resolving-data-loss.md)
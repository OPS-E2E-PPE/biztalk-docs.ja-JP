---
title: 進行中トランザクションを BAM で完了としてマークする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data recovery
- data recovery, BAM
- BAM, data loss
- data loss, BAM
ms.assetid: 8f734953-483a-481a-9ded-b48923859199
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e975893867906d9f9570741e780abfcf10625f30
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531106"
---
# <a name="marking-in-progress-transactions-as-complete-in-bam"></a>BAM の進行中トランザクションを "完了" としてマークする
ビジネス アクティビティ監視 (BAM) は、特殊なアクティブ インスタンス テーブル内の不完全なトレース インスタンスのデータを保持します。 インスタンス レコードの一部では、最後のバックアップの前に開始しましたが、バックアップ後に完了した、いるこれらのレコードはアクティブ インスタンス テーブルに残ります。 これができない、システムが機能してから、アクティブなインスタンス テーブルから移動できるようにを完了すると、これらのレコード手動でマークできます。  
  
 BAM プライマリ インポート データベースに対して次のクエリを発行して、特定のアクティビティに対する不完全な Activityid の一覧を決定できます。  
  
```  
Select ActivityID from bam_<ActivityName> where IsComplete = 0  
```  
  
 外部システムからのデータは、アクティビティ インスタンスが完了したことを示す場合、は、手動でインスタンスを完了する次のクエリを使用できます。  
  
```  
exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
```  
  
## <a name="see-also"></a>参照  
 [データ損失の解決](../core/resolving-data-loss.md)
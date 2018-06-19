---
title: BAM で完了済みとして実行中のトランザクションのマークを付ける |Microsoft ドキュメント
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
ms.openlocfilehash: 508001fcc1023acfd54b7d28bea7f246cb6a1a2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262370"
---
# <a name="marking-in-progress-transactions-as-complete-in-bam"></a>BAM の進行中トランザクションを "完了" としてマークする
ビジネス アクティビティ監視 (BAM) は、不完全なトレース インスタンスのデータを、特殊なアクティブ インスタンス テーブルに格納します。 インスタンス レコードの一部が、最後のバックアップの前に開始し、バックアップの後に完了した場合、これらのレコードはアクティブ インスタンス テーブル内に残ったままになります。 これができないシステムに機能してから、アクティブなインスタンス テーブルから移動できるようにを完了すると、これらのレコード手動でマークできます。  
  
 次のクエリを BAM プライマリ インポート データベースに対して実行することにより、特定のアクティビティに対する不完全な ActivityID を検索できます。  
  
```  
Select ActivityID from bam_<ActivityName> where IsComplete = 0  
```  
  
 外部システムのデータを見て、アクティビティ インスタンスが実際に完了していることを確認できた場合は、次のクエリを実行し、手動でインスタンスを完了させます。  
  
```  
exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
```  
  
## <a name="see-also"></a>参照  
 [データ損失の解決](../core/resolving-data-loss.md)
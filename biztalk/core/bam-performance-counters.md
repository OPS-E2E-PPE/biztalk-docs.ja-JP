---
title: BAM パフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], performance counters
- performance, counters [BAM]
ms.assetid: e23f7038-36a5-4957-bc73-47011763d109
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad0502e27bfaefb25d03e88b6d1730d0495cc189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358458"
---
# <a name="bam-performance-counters"></a>BAM パフォーマンス カウンター
パフォーマンス カウンターを使用すると、BAM イベント バス サービスによって実行される作業に関する特定の側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次の表は、ビジネス アクティビティ監視で利用できるパフォーマンス カウンターの一覧を示しています。  
  
|カウンター|説明|  
|-------------|-----------------|  
|Events being processed|BAM イベント バス サービスが現在処理しているイベントの数|  
|Batches being processed|BAM イベント バス サービスが現在処理しているバッチの数|  
|Events Committed|最後の 1 秒間に BAM イベント バス サービスが SQL Server にコミットしたイベントの数|  
|Records Committed|最後の 1 秒間に BAM イベント バス サービスが SQL Server にコミットしたレコードの数|  
|Batches Committed|最後の 1 秒間に BAM イベント バス サービスが SQL Server にコミットしたバッチの数|  
|Total Events|BAM イベント バス サービスが開始以降に処理したイベントの数|  
|Total Records|BAM イベント バス サービスが開始以降に処理したレコードの数|  
|Total Batches|BAM イベント バス サービスが開始以降に処理したバッチの数|  
|Total Failed Batches|BAM イベント バス サービスが開始以降に処理に失敗したバッチの数|  
|Total Failed Events|BAM イベント バス サービスが開始以降に処理に失敗したイベントの数|  
  
 パフォーマンス カウンターは、BizTalk:TDDS パフォーマンス オブジェクトの下のパフォーマンス モニター (perfmon) にあります。 パフォーマンス カウンターのインスタンス名は、ソース サーバーの名前とソース データベースの名前を組み合わせたものになります。 同一のコンピューター上で、2 つの BAM イベント バス サービスが、2 つの異なるソース データベースに対して実行されている場合は、2 つの BAM イベント バス サービス カウンター インスタンスが表示されます。  
  
## <a name="see-also"></a>参照  
 [BAM イベント バス サービスの管理](../core/managing-the-bam-event-bus-service.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM の管理](../core/managing-bam.md)
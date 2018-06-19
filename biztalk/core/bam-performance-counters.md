---
title: BAM パフォーマンス カウンター |Microsoft ドキュメント
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
ms.openlocfilehash: 4307f72f149405fbc04e4e6cc51efe87229c2bff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230914"
---
# <a name="bam-performance-counters"></a>BAM パフォーマンス カウンター
パフォーマンス カウンターを使用すると、BAM イベント バス サービスによって実行される作業に関する特定の側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次の表は、ビジネス アクティビティ監視で利用できるパフォーマンス カウンターの一覧を示しています。  
  
|カウンター|Description|  
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
 [BAM イベント バス サービスを管理します。](../core/managing-the-bam-event-bus-service.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM の管理](../core/managing-bam.md)
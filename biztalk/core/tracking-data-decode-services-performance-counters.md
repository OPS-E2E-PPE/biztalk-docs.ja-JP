---
title: "Tracking Data Decode Services のパフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 501e321c5ad0126a39ad9ebbd3a5d2d687f121b0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="tracking-data-decode-services-performance-counters"></a>Tracking Data Decode Services のパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:TDDS**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:TDDS|Batches being processed|SQL トランザクション内部で現在処理中のバッチの数。|  
||Batches committed|出力先データベースにコミットされたバッチの数。|  
||Events being processed|SQL トランザクション内部で現在処理中のイベントの数。|  
||Event Committed|1 秒以内に出力先データベースにコミットされたイベントの数。|  
||Records being processed|SQL トランザクション内部で現在処理中のレコードの数。|  
||Records Committed|1 秒以内に出力先データベースにコミットされたレコードの数。|  
||Total Batches|TDDS により処理されたバッチの合計数。|  
||Total Events|TDDS により処理されたイベントの合計数。|  
||Total Failed Batches|TDDS による実行に失敗したバッチの総数。|  
||Total Failed Events|TDDS による実行に失敗したイベントの総数。|  
||Total Records|TDDS により処理されたレコードの合計数。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:TDDS**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。  使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [パフォーマンスのヒントとテクニック](../core/performance-tips-and-tricks.md)   
 [維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [ホスト制限によるリソース使用率の最適化](../core/optimizing-resource-usage-through-host-throttling.md)
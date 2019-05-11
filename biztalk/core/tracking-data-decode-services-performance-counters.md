---
title: Tracking Data Decode Services のパフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 944baf51a1ca10edc157f2062a6883d77ddffeb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313897"
---
# <a name="tracking-data-decode-services-performance-counters"></a>Tracking Data Decode Services のパフォーマンス カウンター
パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:TDDS**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**[説明]**|  
|------------------|-----------------|---------------------|  
|Biztalk: Tdds|Batches being processed|現在の SQL トランザクション内部で処理されているバッチの数。|  
||コミットされたバッチ|転送先データベースにコミットされたバッチの数。|  
||Events being processed|現在の SQL トランザクション内部で処理されているイベントの数。|  
||コミットされたイベント|1 秒以内に、転送先データベースにコミットされたイベントの数。|  
||レコードの処理中|現在の SQL トランザクション内部で処理されているレコードの数。|  
||Records Committed|この 1 秒間に転送先データベースにコミットされたレコードの数。|  
||Total Batches|TDDS により処理されたバッチの総数。|  
||Total Events|TDDS により処理されたイベントの総数。|  
||Total Failed Batches|TDDS による実行に失敗したバッチの合計。|  
||Total Failed Events|TDDS による実行に失敗したイベントの合計。|  
||Total Records|TDDS により処理されたレコードの合計数します。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。  
  
2.  **パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:TDDS**パフォーマンス カウンター オブジェクトと監視するカウンターを選択します。  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。  使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。  
  
5.  カウンターを追加すると、次のようにクリックします。 **OK**します。  
  
     選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [パフォーマンスのヒントとテクニック](../core/performance-tips-and-tricks.md)   
 [維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [ホスト制限によるリソース使用率の最適化](../core/optimizing-resource-usage-through-host-throttling.md)
---
title: "追跡データベースのレコード サイズ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracking database, database size
ms.assetid: be7a891b-2674-49a3-a8e0-6aa11a918bf2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f4d09d1af92ce4777f5036885d81ea7bf3e648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="record-size-in-tracking-databases"></a>追跡データベースのレコード サイズ
次の表は、追跡データベースのさまざまなイベント レコードに予期されるレコード サイズを示しています。この表は、BizTalk のハードウェア要件を計画する際に役立ちます。  
  
|アクションの種類|サイズ|注|  
|-----------------|----------|-----------|  
|サービスの展開|1864 + シンボル情報のサイズ。|シンボル情報は、オーケストレーションのサイズによって異なります。 たとえば、1 つのメッセージを受信し、1 つのメッセージを送信し、2 つの図形を含むオーケストレーションのサイズは約 4000 バイトです。|  
|開始して正常に完了したサービスのインスタンス|通常は 252 バイト。<br /><br /> 特殊な場合には 735 バイトまで増大します。||  
|開始後、失敗したか、例外が発生したサービスのインスタンス|通常は 252 バイト + エラー情報。<br /><br /> 特殊な場合には 735 バイト + エラー情報まで増大します。|エラー情報は、BizTalk またはユーザー コンポーネントによって返されるテキスト データです。 このサイズの範囲は 100 バイト ～ 2 KB です。|  
|オーケストレーションの開始/終了図形|各 120 バイト。||  
|メッセージ送受信イベント|最小 162 バイト。<br /><br /> 最初に表示されるメッセージのサイズは 202 バイト + メッセージ プロパティ (追跡している場合) になります。<br /><br /> 2930 バイトにまで到達する極端なケースもあります。|メッセージ プロパティを追跡していない場合、平均的なサイズは 182 バイトと見なすことができます。|  
|メッセージ プロパティのサイズ|この追跡プロパティが DTA によって認識される場合は 40 ～ 288 バイト。<br /><br /> 最初にプロパティを追跡する場合は、最大で 268 バイトを追加します。||  
  
## <a name="see-also"></a>参照  
 [メッセージの追跡とは](../core/what-is-message-tracking.md)   
 [管理と追跡アーキテクチャ](../core/management-and-tracking-architecture.md)
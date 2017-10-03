---
title: "追跡データを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- instances, viewing
- service instances, viewing
- viewing, suspended instances
- messages, viewing
- viewing, service details
- viewing, orchestration details
- viewing, message details
- orchestrations, viewing
- suspended instances
- instances, suspended
ms.assetid: dcc3fbd5-cd2c-4780-a577-0ccd521cf5eb
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed30934ca154c8b6921682112b12d016c57f92be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-tracked-data"></a>追跡データについて
クエリの追跡を実行すると、クエリ結果ウィンドウ下部の結果一覧に追跡情報が表示されます。  
  
## <a name="viewing-message-details"></a>メッセージの詳細の表示  
 メッセージのプロパティを追跡できます。 できますも追跡されたメッセージ本文をファイルに保存して表示すること、Microsoft 以外のツールを使用します。  
  
-   サービス インスタンスによって参照されているメッセージを右クリックし、[メッセージの詳細] をクリックします。  
  
-   既に処理されたメッセージでも、追跡を有効にしていて追跡が行われていれば、ハード ディスクに保存して調査できます。  
  
-   オーケストレーション インスタンスに接続し、オーケストレーション デバッガーを使用できます。  
  
## <a name="viewing-service-events"></a>サービス イベントの表示  
 使用してサービスを調査するには、イベント ログに中断されたサービスが表示されたら、**メッセージ フロー**、**オーケストレーション デバッガー**、**追跡メッセージ イベントの表示**、**Live サービス インスタンスの表示**、オプションを**コンテキスト**メニュー。  
  
## <a name="viewing-orchestration-events"></a>オーケストレーション イベントの表示  
 オーケストレーション デバッガーを使用して、メッセージ インスタンスがオーケストレーションを通過したときのパスを表示できます。 パスをたどると、表示されたオーケストレーションの画像にメッセージ処理の進行状況が示されたり、オーケストレーション内にデバッグ用のブレークポイントを設けることができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メッセージの追跡とは](../core/what-is-message-tracking.md)  
  
-   [イベントの追跡とは](../core/what-is-event-tracking.md)
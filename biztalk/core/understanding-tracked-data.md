---
title: 追跡対象のデータの理解 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f8119c78bdab44279feebef3a4460303b3ae78c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292775"
---
# <a name="understanding-tracked-data"></a>追跡データについて
追跡クエリを実行すると、クエリ結果 ウィンドウの下部に結果の一覧で追跡される情報が表示されます。  
  
## <a name="viewing-message-details"></a>メッセージの詳細を表示します。  
 メッセージのプロパティを追跡できます。 追跡されたメッセージ本文をファイルに保存し、それらを表示できるサードパーティ製のツールを使用します。  
  
-   サービス インスタンスによって参照されるすべてのメッセージを右クリックし、メッセージの詳細を選択できます。  
  
-   メッセージの処理が既にが追跡されている場合: 追跡を有効にする必要があるので、-、ハード_ディスクに保存して調査できます。  
  
-   オーケストレーション インスタンスに接続し、オーケストレーション デバッガーを使用できます。  
  
## <a name="viewing-service-events"></a>サービスのイベントを表示します。  
 使用してサービスを調査するには、イベント ログに中断されたサービスが表示されたら、**メッセージ フロー**、**オーケストレーション デバッガー**、**追跡メッセージ イベントの表示**、**Live サービス インスタンスの表示**、オプションを**コンテキスト**メニュー。  
  
## <a name="viewing-orchestration-events"></a>オーケストレーションのイベントを表示します。  
 オーケストレーションで使用してメッセージ インスタンス パスを表示するオーケストレーション デバッガーがかかりました。 をステップ実行して、オーケストレーションの表示の画像、メッセージの進行状況を示しています。 デバッグのためのオーケストレーションにブレークポイントを配置することができます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メッセージ追跡について](../core/what-is-message-tracking.md)  
  
-   [イベント追跡について](../core/what-is-event-tracking.md)
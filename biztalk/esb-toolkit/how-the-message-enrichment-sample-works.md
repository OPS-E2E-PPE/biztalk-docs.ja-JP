---
title: メッセージ強化サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1188c1c9-b133-4438-b41c-ea6cffcf40fd
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d304fbcaaf13b6f2b00b6de0e4813f3084203d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279096"
---
# <a name="how-the-message-enrichment-sample-works"></a>メッセージ強化サンプルのしくみ
 Message Enrichment サンプルを再利用可能な汎用サービスとしての統合パターンをカプセル化することを示します。 この場合、サンプルは、コンテンツ エンリッチャー パターンを実装します。 順番に参照については、外部サービスに送信するメッセージを準備する変換とからのデータが含まれる新しいメッセージに応答を組み込むことにし、別の変換を使用してコンテンツ エンリッチャー パターンが通常は、元のメッセージ。 汎用的な方法で、パターンを実装するためには、メッセージ強化サンプルは、最大で 2 つの競合回避モジュールを使用して、外部ソースから情報を使用してメッセージの強化を構成できますオーケストレーションに基づく itinerary サービスを提供します。
  
 最初の競合回避モジュールは、ルーティング情報を返す必要があります。返すこともできますも並行して情報を変換します。 受信メッセージにルーティングされる前に、変換が適用される指定した場合、競合回避モジュールで指定された場所にします。 提供されているサンプル旅行プランでは、Wcf-custom アダプターのプロバイダーは GetOrderDetails をという名前の GlobalBankESB データベース内の SQL ストアド プロシージャを実行し、結果を返すに使用されます。  
  
 必要に応じて、2 つ目の競合回避モジュールに指定できます。 指定した場合、2 つ目の競合回避モジュールは、変換の情報を含める必要があります。 この変換は、元のメッセージと、入力として、どのデータ ソースに接続がによって返される結果に与えられます。 サンプルの旅程をテーブル ループ functoid を使用して、元のメッセージ、およびストアド プロシージャの結果から情報をプルし、結果として得られる InventoryOrder メッセージ内に含めるマップが参照されます。

---
title: メッセージ強化サンプルのしくみ |Microsoft ドキュメント
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
ms.openlocfilehash: 5ef516b992acbcee2936edb6341cbf1434ba4c79
ms.sourcegitcommit: 7497f6f23d7aadfa8535d0530493f8b4a2a50a0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
ms.locfileid: "22303674"
---
# <a name="how-the-message-enrichment-sample-works"></a>メッセージ強化サンプルのしくみ
 Message Enrichment サンプルは、汎用の再利用可能なサービスとの統合パターンをカプセル化することを示します。 ここでは、サンプルは、コンテンツ Enricher パターンを実装します。 参照情報を表示する順序での外部サービスに送信するメッセージを準備するための変換とからのデータが含まれる新しいメッセージに応答を組み込むし、別の変換を使用してコンテンツ Enricher パターンが一般的には、元のメッセージ。 汎用的なやり方で、パターンを実装するためには、Message Enrichment サンプルを最大 2 つの競合回避モジュールを使用して、外部ソースから情報を使用して、メッセージの強化を構成するオーケストレーションに基づく itinerary サービスを提供します。
  
 最初の競合回避モジュールは、ルーティング情報を返す必要があります。返すことも平行して情報を変換します。 ルーティングされる前に受信メッセージに変換が適用される、指定した場合、競合回避モジュールで指定された場所にします。 提供されたサンプル行程 GetOrderDetails をという名前の GlobalBankESB データベース内の SQL ストアド プロシージャを実行し、結果を返す、Wcf-custom アダプター プロバイダーが使用されます。  
  
 必要に応じて、2 番目の競合回避モジュールを含めることできます。 指定した場合、2 番目の競合回避モジュールは、変換情報を含める必要があります。 この変換は、元のメッセージと、入力として、どのデータ ソースに接続がによって返される結果に与えられます。 サンプル行程が元のメッセージと、ストアド プロシージャの結果から情報をプルし、結果として得られる InventoryOrder メッセージ内に含めることに、テーブル ループ functoid を使用するマップが参照されます。

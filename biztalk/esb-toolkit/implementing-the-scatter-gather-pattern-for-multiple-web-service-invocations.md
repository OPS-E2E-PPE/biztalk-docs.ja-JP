---
title: "複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 912512a4-9649-40df-bb82-b8f4b85c8ca6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03fb129d23b0884fdca518dca574be64d7672c6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-scatter-gather-pattern-for-multiple-web-service-invocations"></a>複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装
このユース ケースを含むメッセージを 1 つ以上の外部サービスを指定する itinerary サービス ステップ[!INCLUDE[prague](../includes/prague-md.md)]アクセスする必要があります。 サービスの場所を決定する動的な解決を使用し、エンドポイントと省略可能な BizTalk サービスが、返されたデータを変換するマップします。 このサービスを実装するオーケストレーションが、変換と、呼び出しを実行し、すべてのサービスの呼び出しが非同期に行わします。 すべてのサービスの呼び出しが完了すると、itinerary サービスは 1 つの応答メッセージに応答を集計し、動的に割り当てられているエンドポイントを使用してクライアントにメッセージを送信します。 図 1 は、このユース ケースを示しています。  
  
 ![散布図を実装するギャザー パターン](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3 ImplementingScatter")  
  
 **図 1**  
  
 **複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装**  
  
 スキャッター/ギャザー サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。  
  
 詳細については、次を参照してください。[をインストールすると、スキャッター/ギャザー サンプルを実行している](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)です。
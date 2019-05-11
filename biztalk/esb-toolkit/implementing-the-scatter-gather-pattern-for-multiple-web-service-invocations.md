---
title: 複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912512a4-9649-40df-bb82-b8f4b85c8ca6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 172515418b17f9b79ac86b3315b8189f5139fea4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400119"
---
# <a name="implementing-the-scatter-gather-pattern-for-multiple-web-service-invocations"></a>複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装
このユース ケースでは、メッセージには、BizTalk Server にアクセスする 1 つ以上の外部サービスを指定するスケジュール サービス ステップが含まれています。 サービスの場所を決定する動的な解決を使用して、エンドポイントと、省略可能な BizTalk サービスが、返されるデータを変換するためにマップされます。 このサービスを実装するオーケストレーションが変換と、呼び出しを実行し、すべてのサービス呼び出しを非同期に実行します。 すべてのサービス呼び出しが完了すると、スケジュール サービスは 1 つの応答メッセージに応答を集計し、動的に割り当てられたエンドポイントを使用してクライアントにメッセージを送信します。 図 1 は、このユース ケースを示しています。  
  
 ![ギャザー パターンの散布図を実装する](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3 ImplementingScatter")  
  
 **図 1**  
  
 **複数の Web サービス呼び出しのスキャッター/ギャザー パターンの実装**  
  
 スキャッター/ギャザー サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。  
  
 詳細については、次を参照してください。[をインストールすると、スキャッター/ギャザー サンプルを実行している](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)します。
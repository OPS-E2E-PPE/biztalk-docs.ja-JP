---
title: 変換して、複数のエンドポイントにメッセージをルーティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 544db12c-95fc-4321-b397-ec9e7410e37d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c0fc2b3b9893607f760c564d03fc6090a7f1ea0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010243"
---
# <a name="transforming-and-routing-a-message-to-multiple-endpoints"></a>変換して、複数のエンドポイントにメッセージのルーティング
このユース ケースでは、ESB は、行程 Web サービスに着手を通じて送信されたメッセージの変換を実行します。 動的解決の参照は、マップ名を決定し、受信メッセージを変換します。 さらに、旅行計画には、行程サービスを動的に解決して、変換後のメッセージをルーティングするターゲット エンドポイントの n の数を指定します。 図 1 に示すように、すべての操作は、メッセージング レイヤーで発生します。  
  
 ![複数のエンドポイントを変換する](../esb-toolkit/media/ch3-transformingmultipleendpoints.gif "Ch3 TransformingMultipleEndpoints")  
  
 **図 1**  
  
 **変換して、複数のエンドポイントにメッセージのルーティング**  
  
 動的解決サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 ESB のパイプライン コンポーネントを具体的には、ESB ディスパッチ逆アセンブラーを使用する方法を示していますを使用せず、メッセージ レベルでマップを動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し、解決するにはおよび BizTalk Server を実行します。オーケストレーションです。 また、一方向と双方向の両方のメッセージング パターンを示します。  
  
 詳細については、次を参照してください。[をインストールすると、動的の解決サンプルを実行している](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)と[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)です。
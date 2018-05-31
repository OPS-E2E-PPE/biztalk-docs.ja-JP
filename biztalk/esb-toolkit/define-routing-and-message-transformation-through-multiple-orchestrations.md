---
title: ルーティングの定義と、メッセージの日程を使用して複数のオーケストレーションを通じて変換 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63141b83-798e-40d0-908d-6b7649923e69
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c5a87b06700794dca6c4aae9588c3068b98d995
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294018"
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a>定義するルーティングと旅程を使用して複数のオーケストレーションでメッセージの変換
このユース ケースでは、処理のために送信メッセージには、サービスを実行して、解決の要件の一覧を記述する itinerary の SOAP ヘッダーが含まれています。 旅行計画では、メッセージが、処理サイクル中に通過する 1 つ以上の Microsoft BizTalk Server オーケストレーションを指定します。 必要に応じて、旅行計画には、エンドポイントまたはメッセージの変換要件を決定するため、動的なルーティング情報を含めることができます。 図 1 は、プロセスの概略を示します。  
  
 ![複数のオーケストレーションのルーティングの定義](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3 DefiningRoutingMultipleOrchestrations")  
  
 **図 1**  
  
 **日程を使用して複数のオーケストレーションを通じてルーティングおよびメッセージの変換を定義します。**  
  
 含まれている行程入り口サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 含む解像度、ルーティング、日程を作成し、一連の定義を itinerary 手順としてサービスの呼び出し命令する方法を示して 方法、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]し、BizTalk Server は、入力メッセージを処理します。 一方向と要求-応答のサンプルが含まれます。  
  
 詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。
---
title: "ルーティングの定義と、日程を使用して変換サービスの呼び出しをメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6f2448e-a5a7-496c-86d3-47f12e6f1251
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 975c830f73e0de362b25f312a8d41c4b15368cfd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a>定義するルーティングと旅程を使用してメッセージ変換サービスの呼び出し
このユース ケースでは、処理のために送信メッセージには、サービスを実行して、解決の要件の一覧を記述する itinerary の SOAP ヘッダーが含まれています。 具体的には、変換およびルーティング サービスは、Universal Description、検出、および Integration (UDDI)、ビジネス ルール エンジン ポリシー、XML パス言語 (XPath)、または静的参照を通じて解決を必要に応じて各が必要です。 このユース ケースは、メッセージの発行時に、旅行計画に他のサービスを追加することによって拡張できます。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Itinerary ランプ上の 2 つの型を提供します。 一方向の通信および要求-応答シナリオをサポートするものをサポートするものです。 動的解決メカニズムは、エンドポイントを確認したり、エンドポイントに動的にバインドする、旅行計画の情報を使用できます、ために、特定のエンドポイントのルーティングの詳細を格納する Microsoft BizTalk Server の要件はありません。 図 1 は、プロセスの概略を示します。  
  
 ![ルーティング サービスの呼び出しを定義する](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3 DefiningRoutingServiceInvocation")  
  
 **図 1**  
  
 **日程を使用してルーティングおよびメッセージの変換サービス呼び出しを定義します。**  
  
 含まれている行程入り口サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 含む解像度、ルーティング、日程を作成し、一連の定義を itinerary 手順としてサービスの呼び出し命令する方法を示して 方法、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] BizTalk Server は、発行を使用してメッセージを処理し、サブスクライブの機能BizTalk Server です。 一方向と要求-応答のサンプルが含まれます。  
  
 詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。
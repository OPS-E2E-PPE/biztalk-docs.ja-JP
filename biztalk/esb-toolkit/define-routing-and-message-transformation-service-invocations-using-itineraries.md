---
title: ルーティングの定義と、メッセージのスケジュールを使用して変換サービスの呼び出し |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6f2448e-a5a7-496c-86d3-47f12e6f1251
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0145bb07e700133be91878f040f5a3db4825db5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394679"
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a>定義のルーティングとスケジュールを使用してメッセージ変換サービスの呼び出し
このユース ケースでは、処理のために送信されたメッセージには、サービスを実行して、解決の要件の一覧を記述するスケジュールの SOAP ヘッダーが含まれています。 具体的には、変換およびルーティング サービスは、必要に応じて各 Universal Description、検出、および Integration (UDDI)、ビジネス ルール エンジン ポリシー、XML Path Language (XPath) または静的な参照を通じて解決を必要とします。 このユース ケースは、メッセージの発行時に、旅行計画に他のサービスを追加することによって拡張できます。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]の 2 種類のグラデーションでの旅程を提供します。 一方向の通信および要求-応答シナリオをサポートするものをサポートするものです。 動的解決の機構は、旅行計画の情報を使用してエンドポイントを検索したり、エンドポイントに動的にバインドしたり、ために、特定のエンドポイントのルーティングの詳細を格納する Microsoft BizTalk Server の要件はありません。 図 1 は、プロセスの概略を示します。  
  
 ![ルーティング サービスの呼び出しを定義する](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3 DefiningRoutingServiceInvocation")  
  
 **図 1**  
  
 **スケジュールを使用してルーティングおよびメッセージの変換サービス呼び出しを定義します。**  
  
 含まれている行程導入サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 解像度、ルーティングが含まれているスケジュールを作成し、呼び出し命令をサービスとして、一連のスケジュールの手順を定義する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]し、BizTalk Server では、発行を使用してメッセージを処理します-サブスクライブの機能。BizTalk Server です。 一方向および要求-応答のサンプルが含まれています。  
  
 詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。
---
title: サンプル複数の Web サービスの日程 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f67a4c6-b547-4261-ab3f-db78603ac588
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8beeda266ae29eb4bb3e7c2a373c9ac6fc2b2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295106"
---
# <a name="the-sample-multiple-web-services-itineraries"></a>サンプル複数の Web サービスの日程
次の表は、複数の Web サービス サンプルに含まれるすべての定義済み itinerary ファイルを一覧表示します。 これらは \Source\Samples\MultipleWebServices\Itineraries フォルダーにあります。  
  
|ファイル名|Description|  
|---------------|-----------------|  
|OneWayMessagingMultipleServices.xml|この一方向の日程は CNOrderDoc メッセージに、NAOrderDoc メッセージを変換し、Candian 順序を出口 DynamicResolutionSolicitResp を使用してサービスにルーティングします。 応答がトランス フォームのメッセージング ベースのサービスを使用して、CNOrderDoc メッセージに変換後、され、カナダの順序を使用してサービス出口 DynamicResolutionSolicitResp もう一度、ルーティングがされます。 返される応答は、ルーティング サービスを使用して、Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーにルーティングされます。|  
|TwoWayMessagingMultipleServices.xml|この双方向の日程は CNOrderDoc メッセージに、NAOrderDoc メッセージを変換し、カナダの注文サービスにルーティングします。 カナダの注文サービスからの応答を受け取り、CNOrderDoc メッセージに変換およびカナダの注文サービスに再ルーティングします。 結果は、呼び出し元に返されます。 すべての変換およびルーティングはメッセージング サービスを配置します。 両方を無効にする傾斜 DynamicResolutionSolicitRespForwarder 送信ポートを使用します。|  
|TwoWayMessagingOrchestrationMultipleServices.xml|この双方向の日程が NAOrderDoc CNOrderDoc メッセージにメッセージを変換するメッセージのサービスを使用して、DynamicResolutionSolicitRespForwarder 送信ポートを使用して、カナダ順序サービスにそのメッセージをルーティングします。 変換サービスのオーケストレーションに基づく実装を使用して、応答が変換されるし、カスタム Microsoft.Practices.ESB.Routing.TwoWay オーケストレーションに基づく itinerary サービス サンプルの一部として提供に渡されます。 このサービスは、(ここでは、カナダの注文サービス)、関連する競合回避モジュールで指定された Web サービスにメッセージを送信および受信し、サービスから応答が返されます。 この応答は、呼び出し元に送信されます。|  
|TwoWayOrchestrationsMultipleServices.xml|この双方向の日程 NAOrderDoc CNOrderDoc メッセージにメッセージを変換するメッセージング サービスを使用して、使用して Microsoft.Practices.ESB.Routing.TwoWay オーケストレーションをカナダの注文サービスにそのメッセージをルーティングし、結果を返します。 メッセージが CNOrderDoc をオーケストレーションに基づく変換サービスを使用してメッセージに変換し、その後、サービスを使用して、Microsoft.Practices.ESB.Routing.TwoWay オーケストレーションに基づく itinerary カナダ順序サービスに送信されます。 結果は、呼び出し元に返されます。|  
|TwoWay Partial-セレクター Required.xml|この 2 つ itinerary 方法を使用して、NAOrderDoc にルーティングするメッセージング サービスは、カナダ順序を介してサービスに、DynamicResolutionSolicitResp 出口メッセージします。 NAOrderDoc は CNOrderDoc トランス フォームのメッセージング ベースのサービスとというカナダのサービスを使用して変換されます。 応答は、呼び出し元に返されます。|
---
title: サンプル複数の Web サービスのスケジュール |Microsoft Docs
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
ms.openlocfilehash: f08f85b3fb82c105f21a921fb73c35470179a8f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399668"
---
# <a name="the-sample-multiple-web-services-itineraries"></a>サンプル複数の Web サービスのスケジュール
次の表は、複数の Web サービスのサンプルに含まれるすべての定義済みスケジュール オンランプ ファイルを一覧表示します。 これらは \Source\Samples\MultipleWebServices\Itineraries フォルダーに配置されます。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|OneWayMessagingMultipleServices.xml|この一方向のスケジュールは CNOrderDoc メッセージに、NAOrderDoc メッセージを変換し、Candian 順序を傾斜オフ DynamicResolutionSolicitResp を使用してサービスにルーティングします。 トランス フォームのメッセージング ベースのサービスを使用して CNOrderDoc メッセージに変換し、応答され、ランプ オフ DynamicResolutionSolicitResp を使用して、カナダの注文サービスにもう一度そのルーティングがされます。 返される応答は、ルーティング サービスを使用して Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーにルーティングされます。|  
|TwoWayMessagingMultipleServices.xml|この双方向の日程は CNOrderDoc メッセージに、NAOrderDoc メッセージを変換し、カナダの注文サービスにルーティングします。 カナダ、受注サービスから応答を受け取り、CNOrderDoc メッセージに変換およびカナダの注文サービスに再ルーティングします。 結果は、呼び出し元に返されます。 すべての変換およびルーティングでは、メッセージング サービスを配置します。 オフランプ在庫の両方では、DynamicResolutionSolicitRespForwarder の送信ポートを使用します。|  
|TwoWayMessagingOrchestrationMultipleServices.xml|この双方向のスケジュールでは、メッセージング サービスを使用して、NAOrderDoc CNOrderDoc メッセージにメッセージを変換し、DynamicResolutionSolicitRespForwarder 送信ポートを使用して、カナダの注文サービスにそのメッセージをルーティングします。 変換サービスのオーケストレーションに基づく実装を使用して、応答が変換され、カスタム Microsoft.Practices.ESB.Routing.TwoWay オーケストレーションに基づくスケジュール オンランプ提供されるサービスをサンプルの一部として渡されます。 このサービスは、(この場合はカナダの注文サービス) に関連付けられている競合回避モジュールで指定された Web サービスにメッセージを送信および受信し、サービスからの応答を返します。 この応答は、呼び出し元に送信されます。|  
|TwoWayOrchestrationsMultipleServices.xml|この双方向の旅程 NAOrderDoc CNOrderDoc メッセージにメッセージを変換するメッセージング サービスを使用して、Microsoft.Practices.ESB.Routing.TwoWay オーケストレーション カナダの注文サービスにそのメッセージをルーティングし、結果を使用しています。 変換のオーケストレーションに基づくサービスを使用して CNOrderDoc メッセージに変換し、メッセージその後、Microsoft.Practices.ESB.Routing.TwoWay オーケストレーションに基づくスケジュール サービスを使用して、カナダの注文サービスに送信されます。 結果は、呼び出し元に返されます。|  
|TwoWay-Partial-Selector-Required.xml|この 2 つスケジュール方法の使用-傾斜オフ DynamicResolutionSolicitResp を介してカナダ注文サービスにメッセージのルーティング、NAOrderDoc メッセージング サービスです。 NAOrderDoc は CNOrderDoc トランス フォームのメッセージング ベースのサービスと呼ばれるカナダのサービスを使用して変換されます。 応答は、呼び出し元に返されます。|
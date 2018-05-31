---
title: サンプルの Itinerary シナリオ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d438580-2b24-493c-a7d9-27632a75459c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9359a6fb3d0ce4d4f0d8fbd787c0d6a30f0f499
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22297186"
---
# <a name="the-sample-itinerary-scenarios"></a>サンプルの Itinerary シナリオ
次の表には、行程入り口サンプルに含まれるすべての定義済み行程ファイルが一覧表示します。 これらは \Source\Samples\Itinerary\Itineraries フォルダーにあります。  
  
|ファイル名|Description|  
|---------------|-----------------|  
|Disassembler_OneWay MessageTransform MessageRouting MessgeSendPort.xml|この行程が、定義済みのメッセージ フロー、行程入り口に送信されるときに指示を送信されたメッセージに対してマップを実行し、n の数によって、カスタムの動的な場所に変換されたメッセージをルーティングし、Microsoft BizTalk を示します送信ポート。 サービスに関連付けられている競合回避モジュールの数は、ルートの数を決定します。 ESB ディスパッチャー パイプライン コンポーネントでサポートされる省略可能なルーティング メッセージ サービスを使用してすべて変換およびルーティングが、BizTalk メッセージング レイヤーで発生します。 旅行計画内のサービスに関連付けられている競合回避モジュールには、ルーティングの位置が決まります。 この日程を実行するには、次のメッセージが生成されます。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 通のメッセージ: FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 通のメッセージ: MQS://localhost/ESB です。 DEPSample.QueueManager/TEST です。OUT/%MessageID.xml|  
|Disassembler_OneWay MessageTransform-MessgeSendPort.xml|この行程では、こと、指示を送信されたメッセージに対してマップを実行し、ルーティングし、BizTalk、行程入り口に送信されるときに変換されたメッセージによって、カスタムの動的な場所の n の数を送信ポートの定義済みのメッセージ フローを示します。 サービスに関連付けられている競合回避モジュールの数は、ルートの数を決定します。 すべての変換およびルーティングは、BizTalk メッセージング レイヤーで行われます。 旅行計画内のサービスに関連付けられている競合回避モジュールには、ルーティングの位置が決まります。 この日程を実行するには、次のメッセージが生成されます。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 通のメッセージ: FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 通のメッセージ: MQS://localhost/ESB です。 DEPSample.QueueManager/TEST です。OUT/%MessageID.xml|  
|OneWay MessageTransform MessageRouting MessgeSendPort.xml|この行程では、こと、指示を送信されたメッセージに対してマップを実行し、ルーティングし、BizTalk、行程入り口に送信されるときに、カスタムの動的なを介して 1 つの場所に変換後のメッセージ送信ポートの定義済みのメッセージ フローを示します。 ESB ディスパッチャー パイプライン コンポーネントでサポートされる省略可能なルーティング メッセージ サービスを使用してすべて変換およびルーティングが、BizTalk メッセージング レイヤーで発生します。 この日程を実行すると、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーに 1 つのメッセージが生成されます。|  
|OneWay MessageTransform-MessgeSendPort.xml|この行程では、こと、指示を送信されたメッセージに対してマップを実行し、ルーティングし、BizTalk、行程入り口に送信されるときに、カスタムの動的なを介して 1 つの場所に変換後のメッセージ送信ポートの定義済みのメッセージ フローを示します。 すべての変換およびルーティングは、BizTalk メッセージング レイヤーで行われます。 この日程を実行すると、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーに 1 つのメッセージが生成されます。|  
|OneWay MessgeSendPort.xml|この行程は、BizTalk にルーティングするよう指示、行程入り口に送信されるときに、カスタムの動的なを介して 1 つの場所にメッセージ送信ポートの定義済みのメッセージ フローを示します。 すべてのルーティングは、BizTalk メッセージング レイヤーで発生します。 この日程を実行すると、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーに 1 つのメッセージが生成されます。|  
|OneWay OrchTransform OrchRoutingGroup MessgeSendPort.xml|この行程では、定義済みのメッセージの例をフローすることで、行程入り口に送信されるときに指示をカスタム オーケストレーション サービスを使用して送信されたメッセージに対してマップを実行する BizTalk を示しています。 2 番目のカスタム オーケストレーション サービスは、出力を処理し、3 つの場所に 4 つのメッセージをルーティングします。 このサービスに関連付けられている競合回避モジュールには、次のルーティングの場所を決定します。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 通のメッセージ: FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 通のメッセージ: MQS://localhost/ESB です。 DEPSample.QueueManager/TEST です。OUT/%MessageID.xml|  
||最後に、旅行計画は、カスタムの動的送信ポートを通じて 1 つの場所 (\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダー) に元のメッセージをルーティングします。 すべての変換し、ルーティング サービスが BizTalk メッセージングとオーケストレーションの組み合わせによって発生します。 この itinerary サンプルを実行するには、5 つのメッセージが生成されます。|  
|TwoWay MessageTransform MessageRouting MessageTwoWaySendPort.xml|この行程では、定義済み双方向 (要求/応答) メッセージをフローすることを行程入り口に送信されるときに指示 BizTalk に送信されたメッセージに対してマップを実行し、経由で Web サービスに変換されたメッセージをルーティングを示しています、カスタムの動的な双方向送信ポートです。 この例では、ESB ディスパッチャー パイプライン コンポーネントでサポートされる省略可能なルーティング メッセージ サービスを使用します。 すべての変換とルーティング、BizTalk メッセージング レイヤーで発生します。 この行程サンプルを実行している、この場合は、行程テスト クライアントで旅行計画は、呼び出し元にルーティング、1 つの応答メッセージが生成されます。|  
|TwoWay-MessageTransform-MessageRouting-MessageTwoWaySendPort-MessageTransform.xml|この行程では、定義済み双方向 (要求/応答) メッセージをフローすることを行程入り口に送信されるときに指示 BizTalk に送信されたメッセージに対してマップを実行し、経由で Web サービスに変換されたメッセージをルーティングを示しています、カスタムの動的な双方向送信ポートです。 Web サービスから応答が返されるとき、行程は BizTalk 応答メッセージに対してマップを実行するように指示します。 この例では、ESB ディスパッチャー パイプライン コンポーネントでサポートされる省略可能なルーティング メッセージ サービスを使用します。 すべての変換とルーティング、BizTalk メッセージング レイヤーで発生します。 この行程サンプルを実行している、この場合は、行程テスト クライアントで旅行計画は、呼び出し元にルーティング、1 つの応答メッセージが生成されます。|  
|TwoWay MessageTransform-MessageTwoWaySendPort.xml|この行程では、定義済み双方向 (要求/応答) メッセージをフローすることを行程入り口に送信されるときに指示 BizTalk に送信されたメッセージに対してマップを実行し、経由で Web サービスに変換されたメッセージをルーティングを示しています、カスタムの動的な双方向送信ポートです。 すべての変換とルーティング、BizTalk メッセージング レイヤーで発生します。 この行程サンプルを実行している、この場合は、行程テスト クライアントで旅行計画は、呼び出し元にルーティング、1 つの応答メッセージが生成されます。|  
|TwoWay MessageTransform MessageTwoWaySendPort MessageTransform.xml|この行程では、定義済み双方向 (要求/応答) メッセージをフローすることを行程入り口に送信されるときに指示 BizTalk に送信されたメッセージに対してマップを実行し、経由で Web サービスに変換されたメッセージをルーティングを示しています、カスタムの動的な双方向送信ポートです。 Web サービスから応答が返されるとき、行程は BizTalk 応答メッセージに対してマップを実行するように指示します。 すべての変換とルーティング、BizTalk メッセージング レイヤーで発生します。 この行程サンプルを実行するには、旅行計画が (この場合は、行程テスト クライアント) を呼び出し元にルーティングされ、1 つの応答メッセージが生成されます。|  
|TwoWay MessageTransform OrchRoutingGroup OrchTwoWayCustom.xml|この行程では、定義済み双方向 (要求/応答) メッセージをフローすることで、行程入り口に送信されるときに指示メッセージング サービスを使用して送信されたメッセージに対してマップを実行する BizTalk を示しています。 旅行計画は、出力をそれを処理するカスタム オーケストレーション サービスに渡します。 サービスに関連付けられている競合回避モジュールには、次の 4 つのルーティング場所を決定します。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 通のメッセージ: FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 通のメッセージ: MQS://localhost/ESB です。 DEPSample.QueueManager/TEST です。OUT/%MessageID.xml|  
||最後に、旅行計画は、(この場合は、行程テスト クライアント) を最初の呼び出し元に戻す応答メッセージをルーティングする別のカスタムの双方向の直接バインド オーケストレーション サービスに、元のメッセージを渡します。 すべての変換およびルーティングは、BizTalk メッセージングとオーケストレーションのサービスの組み合わせによって行われます。|  
|TwoWay OrchTransform OrchRoutingGroup OrchTwoWayCustom.xml|この行程では、定義済み双方向 (要求/応答) メッセージをフローすることを行程入り口に送信されるときに指示をカスタム オーケストレーション サービスを使用して送信されたメッセージに対してマップを実行する BizTalk を示しています。 旅行計画は、出力をそれを処理するカスタム オーケストレーション サービスに渡します。 サービスに関連付けられている競合回避モジュールには、次の 4 つのルーティング場所を決定します。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 通のメッセージ: FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 通のメッセージ: MQS://localhost/ESB です。 DEPSample.QueueManager/TEST です。OUT/%MessageID.xml|  
||最後に、旅行計画は、(この場合は、行程テスト クライアント) を最初の呼び出し元に戻す応答メッセージをルーティングする別のカスタムの双方向の直接バインド オーケストレーション サービスに、元のメッセージをルーティングします。 すべての変換およびルーティングは、BizTalk メッセージングとオーケストレーションのサービスの組み合わせによって行われます。|  
|TwoWay TwoWayCustom (直接バインド) .xml|この行程では、定義済み双方向 (要求/応答) メッセージをフローすることを行程入り口に送信されるときに指示をカスタムの双方向の直接バインド オーケストレーション サービスを実行する BizTalk を示しています。 このサービスは、この場合は、行程テスト クライアントで、呼び出し元に戻す応答メッセージをルーティングします。|
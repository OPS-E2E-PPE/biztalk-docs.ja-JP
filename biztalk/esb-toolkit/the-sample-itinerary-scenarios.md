---
title: サンプル スケジュール シナリオ |Microsoft Docs
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
ms.openlocfilehash: 721a01015fe58b60642894b54423d7fa1309330a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399678"
---
# <a name="the-sample-itinerary-scenarios"></a>サンプル スケジュール シナリオ
次の表は、行程導入サンプルに含まれるすべての定義済みスケジュール ファイルを一覧表示します。 これらは \Source\Samples\Itinerary\Itineraries フォルダーに配置されます。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|Disassembler_OneWay MessageTransform MessageRouting MessgeSendPort.xml|このスケジュールは、定義済みのメッセージ フロー、日程入口に送信されたときに指示を送信されたメッセージに対してマップを実行し、n 個のカスタムの動的なによっての場所を変換されたメッセージをルーティングし、Microsoft BizTalk を示します送信ポート。 サービスに関連付けられている競合回避モジュールの数は、ルートの数を決定します。 ESB ディスパッチャーのパイプライン コンポーネントでサポートされる省略可能なルーティング メッセージ サービスすべてを使用して、BizTalk メッセージング層で変換およびルーティングが発生します。 旅行プラン内のサービスに関連付けられている競合回避モジュールは、ルーティングの場所を決定します。 この旅行プランを実行するには、次のメッセージが生成されます。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 メッセージ:FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 メッセージ:MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
|Disassembler_OneWay-MessageTransform-MessgeSendPort.xml|このスケジュールは、指示を送信されたメッセージに対してマップを実行し、ルーティングし、BizTalk、日程入口に送信されるときは、変換されたメッセージによって、カスタムの動的な場所の n の数をポートと送信、定義済みのメッセージ フローを示します。 サービスに関連付けられている競合回避モジュールの数は、ルートの数を決定します。 すべての変換およびルーティングは、BizTalk メッセージング層で行われます。 旅行プラン内のサービスに関連付けられている競合回避モジュールは、ルーティングの場所を決定します。 この旅行プランを実行するには、次のメッセージが生成されます。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 メッセージ:FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 メッセージ:MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
|OneWay-MessageTransform-MessageRouting-MessgeSendPort.xml|このスケジュールは、BizTalk に送信されたメッセージに対してマップを実行し、指示、日程入口に送信されるときは、変換されたメッセージ、カスタムの動的なを通じて 1 つの場所をポートと送信、定義済みのメッセージ フローを示します。 ESB ディスパッチャーのパイプライン コンポーネントでサポートされる省略可能なルーティング メッセージ サービスすべてを使用して、BizTalk メッセージング層で変換およびルーティングが発生します。 この旅行プランを実行すると、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーで 1 つのメッセージが生成されます。|  
|OneWay-MessageTransform-MessgeSendPort.xml|このスケジュールは、BizTalk に送信されたメッセージに対してマップを実行し、指示、日程入口に送信されるときは、変換されたメッセージ、カスタムの動的なを通じて 1 つの場所をポートと送信、定義済みのメッセージ フローを示します。 すべての変換およびルーティングは、BizTalk メッセージング層で行われます。 この旅行プランを実行すると、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーで 1 つのメッセージが生成されます。|  
|OneWay-MessgeSendPort.xml|この旅行プランは、BizTalk をルーティングするよう指示します、日程入口に送信されると、カスタムの動的なを介して 1 つの場所にメッセージ送信ポートの定義済みのメッセージ フローを示します。 すべてのルーティングは、BizTalk メッセージング層で発生します。 この旅行プランを実行すると、\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダーで 1 つのメッセージが生成されます。|  
|OneWay OrchTransform OrchRoutingGroup MessgeSendPort.xml|このスケジュールは、定義済みのメッセージの例をフローする、スケジュール上のランプ、送信されたときに指示カスタム オーケストレーション サービスを使用して送信されたメッセージに対してマップを実行する BizTalk を示します。 2 番目のカスタム オーケストレーション サービスは、出力を処理し、3 つの場所に 4 つのメッセージをルーティングします。 このサービスに関連付けられている競合回避モジュールは、次のルーティングの場所を決定します。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 メッセージ:FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 メッセージ:MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
||最後に、旅行プランは、カスタムの動的送信ポートを通じて 1 つの場所 (\Source\Samples\DynamicResolution\Test\Filedrop\Out フォルダー) に元のメッセージをルーティングします。 すべての変換、ルーティング、BizTalk のメッセージングおよびオーケストレーション サービスの組み合わせによって発生します。 このスケジュール オンランプ サンプルを実行するには、5 つのメッセージが生成されます。|  
|TwoWay-MessageTransform-MessageRouting-MessageTwoWaySendPort.xml|この旅行プランを示して、定義済み双方向 (要求/応答) メッセージ フロー、日程入口に送信されると指示 BizTalk 送信されたメッセージに対してマップを実行し、を介して Web サービスに変換されたメッセージをルーティングします。カスタムの動的な双方向送信ポートです。 この例では、ESB ディスパッチャーのパイプライン コンポーネントでサポートされる省略可能なルーティング メッセージ サービスを使用します。 すべての変換、ルーティング、BizTalk メッセージング層で発生します。 この旅行プラン サンプルを実行する、この場合、スケジュールのテスト クライアントで旅行プランは、呼び出し元にルートを 1 つの応答メッセージが生成されます。|  
|TwoWay-MessageTransform-MessageRouting-MessageTwoWaySendPort-MessageTransform.xml|この旅行プランを示して、定義済み双方向 (要求/応答) メッセージ フロー、日程入口に送信されると指示 BizTalk 送信されたメッセージに対してマップを実行し、を介して Web サービスに変換されたメッセージをルーティングします。カスタムの動的な双方向送信ポートです。 Web サービスから応答を返します、旅行計画 BizTalk 応答メッセージに対してマップを実行するように指示します。 この例では、ESB ディスパッチャーのパイプライン コンポーネントでサポートされる省略可能なルーティング メッセージ サービスを使用します。 すべての変換、ルーティング、BizTalk メッセージング層で発生します。 この旅行プラン サンプルを実行する、この場合、スケジュールのテスト クライアントで旅行プランは、呼び出し元にルートを 1 つの応答メッセージが生成されます。|  
|TwoWay-MessageTransform-MessageTwoWaySendPort.xml|この旅行プランを示して、定義済み双方向 (要求/応答) メッセージ フロー、日程入口に送信されると指示 BizTalk 送信されたメッセージに対してマップを実行し、を介して Web サービスに変換されたメッセージをルーティングします。カスタムの動的な双方向送信ポートです。 すべての変換、ルーティング、BizTalk メッセージング層で発生します。 この旅行プラン サンプルを実行する、この場合、スケジュールのテスト クライアントで旅行プランは、呼び出し元にルートを 1 つの応答メッセージが生成されます。|  
|TwoWay-MessageTransform-MessageTwoWaySendPort-MessageTransform.xml|この旅行プランを示して、定義済み双方向 (要求/応答) メッセージ フロー、日程入口に送信されると指示 BizTalk 送信されたメッセージに対してマップを実行し、を介して Web サービスに変換されたメッセージをルーティングします。カスタムの動的な双方向送信ポートです。 Web サービスから応答を返します、旅行計画 BizTalk 応答メッセージに対してマップを実行するように指示します。 すべての変換、ルーティング、BizTalk メッセージング層で発生します。 この旅行プラン サンプルを実行するには、旅行プランを (この例では、旅行プランのテスト クライアント) では呼び出し元にルーティングされ、1 つの応答メッセージが生成されます。|  
|TwoWay-MessageTransform-OrchRoutingGroup-OrchTwoWayCustom.xml|このスケジュールは、定義済み双方向 (要求/応答) メッセージ フロー、日程入口に送信されると指示メッセージング サービスを使用して送信されたメッセージに対してマップを実行する BizTalk を示します。 旅行プランは、出力を処理するカスタム オーケストレーション サービスに渡します。 サービスに関連付けられている競合回避モジュールは、次の 4 つのルーティング場所を決定します。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 メッセージ:FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 メッセージ:MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
||最後に、旅行プランは、元のメッセージを (この例では、旅行プランのテスト クライアント) では最初の呼び出し元に戻す応答メッセージをルーティングするもう 1 つのカスタムの双方向の直接バインドされたオーケストレーション サービスに渡します。 すべての変換およびルーティングは BizTalk のメッセージングおよびオーケストレーション サービスの組み合わせによって行われます。|  
|TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml|このスケジュールは、定義済み双方向 (要求/応答) メッセージ フロー、日程入口に送信されると指示カスタム オーケストレーション サービスを使用して送信されたメッセージに対してマップを実行する BizTalk を示します。 旅行プランは、出力を処理するカスタム オーケストレーション サービスに渡します。 サービスに関連付けられている競合回避モジュールは、次の 4 つのルーティング場所を決定します。|  
||フォルダー \Source\Samples\DynamicResolution\Test\Filedrop\Out で 2 つのメッセージ|  
||FTP フォルダーに 1 メッセージ:FTP://localhost/out/%MessageID%.xml|  
||MQSeries キューに 1 メッセージ:MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
||最後に、旅行プランは、(この例では、旅行プランのテスト クライアント) では最初の呼び出し元に戻す応答メッセージをルーティングするカスタムの双方向の直接バインドされたオーケストレーション サービスを別に、元のメッセージをルーティングします。 すべての変換およびルーティングは BizTalk のメッセージングおよびオーケストレーション サービスの組み合わせによって行われます。|  
|TwoWay TwoWayCustom (直接バインド) .xml|このスケジュールは、定義済み双方向 (要求/応答) メッセージ フロー、日程入口に送信されると指示、カスタムの双方向の直接バインドされたオーケストレーション サービスを実行する BizTalk を示します。 このサービスは、この場合は、旅行プランのテスト用クライアントの最初の呼び出し元に戻す応答メッセージをルーティングします。|
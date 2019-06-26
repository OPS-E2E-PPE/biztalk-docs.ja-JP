---
title: 定義済みスケジュール オンランプ ランプでサンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4400193-20ac-479a-8bf9-b1c99eb35231
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bed5278e4373b82a2f384f96bee44512aefc1b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400299"
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a>定義済みスケジュール オンランプ ランプでサンプルを実行します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]実行できる 20 の定義済みスケジュール ユース ケースが含まれています。 これらのリストについては、ユース ケースを参照してください[、サンプル スケジュール シナリオ](../esb-toolkit/the-sample-itinerary-scenarios.md)します。  
  
> [!NOTE]
>  サンプルを実行する前に、GlobalBank.ESB BizTalk アプリケーションに適切なスケジュール オンランプ バインド ファイル \Source\Samples\Itinerary\Install\Binding フォルダーから手動でインポートする必要があります。 このバインド ファイルでは、2 つの動的送信ポートのプロパティをリセットします。 GlobalBank.ESB.Itinerary_Bindings.xml をという名前のバインド ファイルをインポートします。  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a>定義済みの旅程導入サンプルの 1 つを実行するには  
  
1. GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  
  
2. Windows エクスプ ローラーでは、サブフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。Itinerary.Test\bin\Debug BizTalk ESB Toolkit のサンプルをインストールしてアプリケーションを開始した場所では、Esb.Itinerary.Test.exe という名前です。  
  
3. をクリックして、 **LoadItinerary**ボタンをクリックし、TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml \Source\Samples\Itinerary\Itineraries フォルダーからをという名前のサンプルの旅行プランを選択します。  
  
4. **Web サービス オプション**セクションで、**双方向サービス**チェック ボックスをオンします。 これには、テスト用クライアントの要求-応答のスケジュール サービス操作を実行するように指示します。  
  
5. (省略可能)選択、 **WCF サービスを使用して**する場合は、アプリケーション、OnRamp.Itinerary.Response.WCF を使用する チェック ボックスの受信場所、既定ではなく OnRamp.Itinerary.Response.SOAP 受信場所。  
  
6. をクリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。  
  
7. をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。 図 1 は、結果を示します。  
  
   ![傾斜の itinerary](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6 ItineraryOnRamp")  
  
   **図 1**  
  
   **行程導入サンプルの 1 つの操作を実行しているスケジュール入口クライアント アプリケーション**  
  
   スケジュールの定義で指定されたサービスの名前が対応に直接、 **ServiceName**サンプルがサブスクライブしているサービスのプロパティ。 前の手順 (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml) で実行されるスケジュール オンランプ サンプルは、実行される最初のサービスは、変換を実行するオーケストレーション ベースのサービスが。 旅行計画の次のセクションでは、このサービスを指定します。  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 このオーケストレーション サービス **\<サービス\>** 要素を図 2 に示すようにフィルターのプロパティを持つ直接バインドされたオーケストレーションを指定します。 オーケストレーションが値を持つメッセージのみにサブスクライブしていることに注意してください**Microsoft.Practices.ESB.Services.Transform**の、 **ServiceName**コンテキスト プロパティ、値 **。保留中**の**ServiceState**コンテキスト プロパティ、およびオーケストレーションの値を**ServiceType**コンテキスト プロパティ。  
  
 ![フィルター式](../esb-toolkit/media/ch6-filterexpression.gif "Ch6 FilterExpression")  
  
 **図 2**  
  
 **行程導入サンプルで使用する直接バインドされたオーケストレーションのフィルター式**
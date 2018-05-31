---
title: 定義済みの Itinerary ランプでサンプルを実行 |Microsoft ドキュメント
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
ms.openlocfilehash: 38320cc6877815ccbf7b078190a3c2be1c6f74b0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976680"
---
# <a name="run-a-predefined-itinerary-on-ramp-sample"></a>定義済みの Itinerary ランプでサンプルを実行します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]実行できる 20 の定義済み行程ユース ケースが含まれています。 これらのリストについては、ユース ケースを参照してください[、サンプル行程シナリオ](../esb-toolkit/the-sample-itinerary-scenarios.md)です。  
  
> [!NOTE]
>  サンプルを実行する前に、GlobalBank.ESB BizTalk アプリケーションに、\Source\Samples\Itinerary\Install\Binding フォルダーから、適切な itinerary バインド ファイルを手動でインポートする必要があります。 このバインド ファイルは、2 つの動的送信ポートのプロパティをリセットします。 GlobalBank.ESB.Itinerary_Bindings.xml をという名前のバインド ファイルをインポートします。  
  
### <a name="to-run-one-of-the-pre-defined-itinerary-on-ramp-samples"></a>定義済みの日程入り口サンプルの 1 つを実行するには  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
2.  Windows エクスプ ローラーでは、サブフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。ここで、BizTalk ESB Toolkit のサンプルをインストールしてそのアプリケーションを起動して、Itinerary.Test\bin\Debug Esb.Itinerary.Test.exe の名前です。  
  
3.  クリックして、 **LoadItinerary**ボタンをクリックし、サンプル itinerary TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml \Source\Samples\Itinerary\Itineraries フォルダーからという名前を選択します。  
  
4.  **Web サービス オプション** セクションで、選択、**双方向サービス**チェック ボックスをオンします。 これは、要求-応答 itinerary サービス操作を実行するテスト クライアントを指示します。  
  
5.  (省略可能)選択、 **WCF サービスを使用して**する場合は、アプリケーション、OnRamp.Itinerary.Response.WCF を使用する チェック ボックスの受信場所、既定ではなく OnRamp.Itinerary.Response.SOAP 受信場所。  
  
6.  クリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。  
  
7.  クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。 図 1 は、結果を示します。  
  
 ![ごとの傾斜増加の itinerary](../esb-toolkit/media/ch6-itineraryonramp.gif "Ch6 ItineraryOnRamp")  
  
 **図 1**  
  
 **行程入り口サンプルの 1 つの操作を実行している行程入り口クライアント アプリケーション**  
  
 Itinerary 定義で指定されたサービスの名前に直接対応して、 **ServiceName**サンプルがサブスクライブして、サービスのプロパティです。 前の手順 (TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml) で実行される itinerary サンプルでは、最初に実行されるサービスは、オーケストレーションに基づくサービス、変換を行います。 旅行計画の次のセクションでは、このサービスを指定します。  
  
```  
<Service uuid="" beginTime="" completeTime=""   
    name="Microsoft.Practices.ESB.Services.Transform"  
    type="Orchestration" state="Pending" isRequestResponse="false"  
    position="0" serviceInstanceId="" />  
```  
  
 このオーケストレーション サービス**\<サービス\>** 要素は図 2 に示すようにフィルターのプロパティを持つ直接バインド オーケストレーションを指定します。 オーケストレーションは、値を持つメッセージのみにサブスクライブしていることを確認**Microsoft.Practices.ESB.Services.Transform**の**ServiceName**コンテキスト プロパティ、値**保留中**の**ServiceState**コンテキスト プロパティ、およびオーケストレーションの値を**ServiceType**コンテキスト プロパティです。  
  
 ![フィルター式](../esb-toolkit/media/ch6-filterexpression.gif "Ch6 FilterExpression")  
  
 **図 2**  
  
 **行程入り口サンプルで使用される直接バインド オーケストレーションのフィルター式**
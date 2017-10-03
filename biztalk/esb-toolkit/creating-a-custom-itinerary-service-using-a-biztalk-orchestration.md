---
title: "BizTalk オーケストレーションを使用してカスタム Itinerary サービスを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723c0bc93192267f404d42e7fe859bb37ea59895
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a>BizTalk オーケストレーションを使用してカスタム Itinerary サービスを作成します。
Itinerary フレームワークの一部である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]オーケストレーションを使用して、itinerary 手順の実行をサポートします。 以下のことがありますが、機能の要件に基づいて、Microsoft BizTalk Server オーケストレーションとしてカスタム itinerary サービスを実装することができます。  
  
-   複数のサービスの呼び出し (に示すように、[をインストールして、スキャッター/ギャザー サンプルを実行している](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))  
  
-   プロトコル仲介およびメッセージの相関関係 (たとえば、HTTP、MQSeries)  
  
-   複雑なルーティングの決定に基づいてメッセージを強化外部データからソース  
  
-   ビジネス処理のロジック  
  
 BizTalk Server オーケストレーションを使用して実装すべて itinerary サービスは、次の場合です。  
  
-   例外と ESB 例外処理のフレームワークまたは (一方向の日程) の再送信をサポートする省略可能なカスタム例外ハンドラーを使用して、エラー処理  
  
-   旅行計画を進めると、次の itinerary サービス ステップが実行できるように、BizTalk Server を経由して送信メッセージを発行  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a>BizTalk Server オーケストレーションを使用してカスタム itinerary サービスを作成するには  
  
1.  新しいオーケストレーション; を含む新しい BizTalk Server プロジェクトを作成します。たとえば、MyCustomeItineraryService.odx です。  
  
2.  次のアセンブリへの参照を追加します。  
  
    -   **Microsoft.Practices.ESB.Itinerary**  
  
    -   **Microsoft.Practices.ESB.Itinerary.Schemas**  
  
    -   **Microsoft.Practices.ESB.ExceptionHandling**  
  
    -   **Microsoft.Practices.ESB.ExceptionHandling.Faults**  
  
3.  論理の直接バインドを定義するポートとアクティブ化された受信図形をオーケストレーションで受信します。  
  
4.  オーケストレーションが実行されるように、メッセージの itinerary コンテキストからオーケストレーションをアクティブ化するためのサブスクリプション フィルターを定義、 **MyCustomItineraryService**手順です。 次のコードでは、適切なフィルターの例を示します。  
  
    ```csharp  
    (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
        == "MyCustomItineraryService")   
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
        == "Orchestration")  
    ```  
  
5.  型のオーケストレーションを定義する**Microsoft.Practices.ESB.Itinerary.ItineraryStep**です。 次のコードに示すように、この変数を設定するオーケストレーションに式アクティビティを追加します。  
  
    ```csharp  
    // Retrieve the current itinerary step.  
    itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
    step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
    itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
    step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
    ```  
  
6.  手順については、[次へ] itinerary; 送信メッセージを作成する旅行計画に、カスタム実装を追加します。たとえば、OutboundMsg です。  
  
7.  受信メッセージからメッセージ コンテキストを使用する次の式アクティビティを使用して旅程を進めます。  
  
    ```csharp  
    OutboundMessage(*) = InboundMessage(*);   
    itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
    ```  
  
8.  [次へ] の itinerary サービスを有効に直接バインドの送信ポートを通じて更新行程、送信メッセージを送信します。  
  
 BizTalk Server オーケストレーションを使用してカスタム itinerary サービスの実装の詳細については、次を参照してください[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)と[インストールしてスキャッター/ギャザーを実行する。サンプル](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)です。
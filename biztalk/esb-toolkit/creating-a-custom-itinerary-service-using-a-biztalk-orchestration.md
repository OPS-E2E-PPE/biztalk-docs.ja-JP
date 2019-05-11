---
title: BizTalk オーケストレーションを使用して、カスタム スケジュール サービスを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1c95a4da43896f0bed6fdd0b9350ca25ccba7e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399397"
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a>BizTalk オーケストレーションを使用して、カスタム スケジュール サービスを作成します。
スケジュール オンランプ フレームワークの一部である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]オーケストレーションを使用して、itinerary 手順の実行をサポートしています。 カスタム スケジュール サービスは、次の機能要件に基づいて、Microsoft BizTalk Server オーケストレーションとして実装できます。  
  
- 複数のサービス呼び出し (に示すように、[をインストールして、スキャッター/ギャザー サンプルを実行している](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))  
  
- プロトコル、仲介とメッセージの関連付け (たとえば、HTTP、MQSeries)  
  
- メッセージの強化外部データからソースをに基づいて複雑なルーティングの決定  
  
- ビジネス処理ロジック  
  
  BizTalk Server オーケストレーションを使用して実装されているすべてのスケジュール サービスは、次を担当です。  
  
- 例外と ESB 例外処理のフレームワークまたは再送信 (一方向のスケジュール) をサポートするオプションのカスタム例外ハンドラーを使用して、エラー処理  
  
- 旅行計画を進めると、次のスケジュール サービス ステップが実行できるように、BizTalk Server を経由して送信メッセージを公開  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a>BizTalk Server オーケストレーションを使用して、カスタム スケジュール サービスを作成するには  
  
1. 新しいオーケストレーションでは; を含む新しい BizTalk Server プロジェクトを作成します。たとえば、MyCustomeItineraryService.odx です。  
  
2. 次のアセンブリへの参照を追加します。  
  
   -   **Microsoft.Practices.ESB.Itinerary**  
  
   -   **Microsoft.Practices.ESB.Itinerary.Schemas**  
  
   -   **Microsoft.Practices.ESB.ExceptionHandling**  
  
   -   **Microsoft.Practices.ESB.ExceptionHandling.Faults**  
  
3. 論理の直接バインドを定義する受信ポートとアクティブ化された受信図形をオーケストレーションします。  
  
4. オーケストレーションが実行されるようにスケジュール オンランプのメッセージ コンテキストからオーケストレーションをアクティブ化するサブスクリプション フィルターを定義、 **MyCustomItineraryService**手順。 次のコードでは、適切なフィルターの例を示します。  
  
   ```csharp  
   (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
       == "MyCustomItineraryService")   
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
       == "Orchestration")  
   ```  
  
5. オーケストレーションの種類の定義**Microsoft.Practices.ESB.Itinerary.ItineraryStep**します。 次のコードに示すように、この変数を設定するオーケストレーションに式アクティビティを追加します。  
  
   ```csharp  
   // Retrieve the current itinerary step.  
   itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
   step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
   itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
   step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
   ```  
  
6. スケジュール オンランプ法; 送信メッセージを作成するスケジュールに、カスタム実装を追加します。たとえば、OutboundMsg です。  
  
7. 受信メッセージからメッセージ コンテキストを使用して次の式アクティビティを使用してスケジュールを進めます。  
  
   ```csharp  
   OutboundMessage(*) = InboundMessage(*);   
   itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
   ```  
  
8. [次へ] のスケジュール サービスをアクティブに直接バインドされた送信ポートを通じて更新のスケジュールと送信メッセージを送信します。  
  
   BizTalk Server オーケストレーションを使用して、カスタム スケジュール サービスを実装する方法の詳細については、次を参照してください[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)と[インストールし、スキャッター/ギャザーの実行。サンプル](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)します。
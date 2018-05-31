---
title: オーケストレーションを使用して、Itinerary サービス サブスクライバーとして |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f496884d0aed8d5f351f681ca8cfe59e05684240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295322"
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a>Itinerary サービス サブスクライバーとして、オーケストレーションを使用します。
オーケストレーション itinerary サービスとして動作することもできます。 参加するには、行程でオーケストレーション直接バインド; としてを最初にデザインする必要があります。これを行うと類似の前のトピックでは、送信ポート フィルター サブスクリプションを使用して[行程サービス サブスクライバーとして、送信ポートを使用して](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)です。 図 1 は、次の条件を満たすすべてのメッセージを取得するのに適切なオーケストレーションのフィルター式の例を示します。  
  
-   **ServiceName = Microsoft.Practices.ESB.Services.Transform**  
  
-   **ServiceState = 保留中**  
  
-   **ServiceType オーケストレーションを =**  
  
 ![オーケストレーション](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 オーケストレーション")  
  
 **図 1**  
  
 **サブスクライバーとして日程に参加するオーケストレーションのフィルター式の例**  
  
 Microsoft BizTalk Server で ESB 入り口を介してメッセージを受信と、ESB パイプラインで検証手順には、受信メッセージの BizTalk コンテキスト プロパティにフィルターのプロパティのプロパティ値を書き込みますこれは、メッセージ コンテキストにそれらを昇格します。 Itinerary サービスは常に、設定、 **ServiceName**プロパティを次に、処理するサービスの名前に、現在アクティブなサービスを**ServiceState**のプロパティの値**保留中**です。 サブスクリプションを設定する必要が少なくとも 1 つ目、次のプロパティのうち 3 つ。  
  
-   **サービス名。** これはサービスの名前 ESB 行程に格納されている、任意の名前を指定できます。 旅行計画では、この名前を使ってを実行するサービスを識別します。  
  
-   **ServiceState です。** これは、実行する現在の itinerary サービス ステップの状態です。 サービスの現在の手順 (次の処理) が、値が常に**保留**、いずれか、ESB itinerary パイプライン コンポーネント、ESB 行程セレクター パイプライン コンポーネントによって設定するかを呼び出すコード、**先行**行程 API のメソッドです。  
  
-   **ServiceType です。** このプロパティは、オーケストレーションまたは BizTalk のメッセージング サブシステムから発生するかどうかを示す、サービスの種類を定義します。  
  
-   **IsRequestResponse です。** このオプションのプロパティと同じ値を持つ必要があります、 **IsRequestResponse**サービスのプロパティです。
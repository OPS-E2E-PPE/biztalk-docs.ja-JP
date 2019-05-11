---
title: スケジュール サービス サブスクライバーとしてオーケストレーションを使用して |Microsoft Docs
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
ms.openlocfilehash: 707c9b37f671191b743912cb391c8e41d67d007b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396465"
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a>スケジュール サービス サブスクライバーとしてオーケストレーションを使用します。
オーケストレーション スケジュール サービスとしても機能します。 スケジュールに参加するに直接バインドされた; としてオーケストレーションを最初にデザインする必要があります。これを行うと類似の前のトピックでは、送信ポート フィルター サブスクリプションを使用して、[送信ポートを使用して、スケジュール サービス サブスクライバーとして](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)します。 図 1 は、次の条件を満たすすべてのメッセージを取得する適切なオーケストレーションのフィルター式の例を示します。  

- **ServiceName = Microsoft.Practices.ESB.Services.Transform**  

- **ServiceState = 保留中**  

- **ServiceType オーケストレーションを =**  

  ![オーケストレーション](../esb-toolkit/media/ch4-orchestration.jpg "Ch4 オーケストレーション")  

  **図 1**  

  **サブスクライバーとして、スケジュールに参加するオーケストレーションのフィルター式の例**  

  Microsoft BizTalk Server で ESB 入り口を介してメッセージを受信と、ESB パイプラインの検証手順には、受信メッセージの BizTalk コンテキスト プロパティにフィルターのプロパティのプロパティ値を書き込みますこれは、メッセージ コンテキストにそれらを昇格します。 スケジュール サービスが常に設定、 **ServiceName**プロパティを次に、処理するサービスの名前に、現在アクティブなサービスを**ServiceState**プロパティ値の**保留中**します。 サブスクリプションを設定する必要が少なくとも最初の 3 つの次のプロパティ。  

- **サービス名。** これにより、ESB 行程に格納されている、サービスの名前は、および任意の名前を指定できます。 旅行プランを実行するのにには、どのサービスを識別するためにこの名前を使用します。  

- **ServiceState します。** これは、実行する現在のスケジュール サービス ステップの状態です。 (次の処理) の現在のサービス ステップには、値は常に**保留**か ESB スケジュール オンランプ パイプライン コンポーネントによって、ESB スケジュール セレクター パイプライン コンポーネントで、設定、またはを呼び出すコード、**事前**行程 API のメソッド。  

- **ServiceType します。** このプロパティは、オーケストレーションまたは BizTalk のメッセージング サブシステムから発生するかどうかを示す、サービスの種類を定義します。  

- **IsRequestResponse します。** この省略可能なプロパティと同じ値が必要、 **IsRequestResponse**サービスのプロパティ。

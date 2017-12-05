---
title: "処理命令の詳細 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed5d92fb-d53b-49a2-b2c7-8558708d6554
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf0a726d2c8c4f6242ed19a7dcd1e5430775e63
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="processing-instructions-in-detail"></a>処理命令の詳細
このトピックでは、形式と旅程処理に必要ないくつかのコンテキスト プロパティを定義するシステム Properties.xsd プロパティ スキーマの構造について説明します。 メッセージが受信され、BizTalk Server パイプライン; を通して処理されたときに、これらのプロパティは昇格されます。昇格させたプロパティがいるため、BizTalk Server コンポーネントを利用可能です。 次のプロパティは、システム Properties.xsd プロパティ スキーマで定義されます。  
  
-   **ItineraryHeader です。** このプロパティには、すべての itinerary 情報および itinerary ステップの順序で呼び出される itinerary サービスの一覧が含まれています。 行程 API は、このプロパティを内部的に使用します。  
  
-   **サービス名。** このプロパティには、処理する場合は、現在 itinerary サービスの名前が含まれています。  
  
-   **ServiceState です。** このプロパティには、現在の itinerary サービスの状態が含まれています:**保留**、**完了**、または**Active**です。 すべてのサービスのサブスクライブを含む itinerary ステップに、 **ServiceState**の値**保留**です。  
  
-   **ServiceType です。** このプロパティは itinerary ステップの種類を定義 (**メッセージング**または**オーケストレーション**)。  
  
-   **IsRequestResponse です。** このプロパティをメッセージ型を定義します (一方向または要求-応答)。  
  
 行程サービスの値に応じて、2 つの方法のいずれかで itinerary 手順を実行する、 **ServiceType**プロパティ。  
  
-   Itinerary パイプライン コンポーネントでのすべての itinerary 手順を実行する、 **ServiceType**プロパティ**メッセージング**です。 開発者は、カスタム パイプラインと旅程 API を使用してこのプロセスを拡張することができます。  
  
-   ときに、 **ServiceType**プロパティは**オーケストレーション**、itinerary コンテキスト プロパティへのサブスクリプションによってアクティブ化、オーケストレーションは itinerary のステップを実行します。  
  
 行程サービス itinerary 手順を処理するとき、サービスは、旅行計画を進めると、さらに処理する、発行を使用して新しい itinerary コンテキストを持つメッセージをディスパッチ-BizTalk Server の機能をサブスクライブします。 Itinerary サービスは、メッセージ コンテキストの日程のフル コントロールを持ち、その内部ロジックと、メッセージの内容に基づいて、適切な手順を進めることができます。  
  
 Itinerary 処理メカニズムでは、1 つの日程内のメッセージングおよびオーケストレーションの itinerary 手順の組み合わせをサポートします。 開発者は、itinerary のカスタムのサービスを定義し、カスタムの itinerary ステップを構成することができますも。  
  
 行程の詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。  
  
 カスタムの itinerary サービスとカスタムの itinerary 手順の詳細については、次を参照してください。[カスタム行程サービスを作成する](../esb-toolkit/creating-a-custom-itinerary-service.md)です。
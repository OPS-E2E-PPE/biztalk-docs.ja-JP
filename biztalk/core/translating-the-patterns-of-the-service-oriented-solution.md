---
title: "指向ソリューションのパターンのサービスの変換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], translating patterns to orchestration shapes
- artifacts, patterns
- orchestrations, patterns
- patterns [process management solutions], connections
- patterns [service solutions], orchestration boundaries
- patterns [process management solutions], translating patterns to orchestrations
- orchestrations, boundaries
- patterns [service solutions], translating patterns to artifacts
ms.assetid: ff17cc41-2a7b-4304-b5bd-96b1174cea7f
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95285c93bdb290adbee988305dbcd365e4e729a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="translating-the-patterns-of-the-service-oriented-solution"></a>指向ソリューションのパターンのサービスの変換
このセクションでは、このソリューションでパターン ダイアグラムがどのように BizTalk Server のアイテムに変換されるかを説明します。  
  
 ![サービス &#45; 指向のソリューション パターン](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
## <a name="connections-and-completeness-conditions"></a>接続および完全性の条件  
 BizTalk Server コンポーネントへのパターンの変換は、どこからでも開始できます。 ただし、コンポーネントにとっての実質的なインフラストラクチャはコンポーネント間の接続なので、ここから開始することをお勧めします。 また、アグリゲータ パターンの場合は、必要なすべての情報が揃っていることをどのように示すかを決定する必要があります。 これは、他のコンポーネントへの接続およびそのデザインに影響を及ぼします。  
  
 ソリューションは、便利で一貫した使用方法を提供する必要があります。 他のアプリケーションがソリューションをどのように使用するかは、サービス インターフェイスによって指定されます。 このソリューションでは IBM WebSphere MQ を使用しているレガシ アプリケーションと通信する必要があるので、IBM WebSphere MQ をサービス インターフェイスの一部にする必要があります。 ところが、これより新しいアプリケーションでは、明らかに Web サービス インターフェイスが選択されているようです。 Web サービス インターフェイスを使用すれば、サービスを使用する他のアプリケーションに対する柔軟性を最大限に高めることができます。 ここでは、BizTalk Server の柔軟性を使用して、デュアル サービス インターフェイスとします。 オーケストレーションを Web サービスとして公開する方法については、次を参照してください。 [Web サービスにオーケストレーションをマップする方法](../core/how-to-map-orchestrations-to-web-services.md)です。  
  
 その他に、サービス インターフェイスと受信者の一覧の間の接続、受信者の一覧とバックエンド アプリケーションの間の接続、およびバックエンド アプリケーション、アグリゲータ、サービス インターフェイス間の接続があります。  
  
 受信者の一覧への接続が同期接続である場合、受信者の一覧へのすべてのメッセージの送受信が確実に行われるように関連付けを使用する必要はありません。 同じ理由で、バックエンド アプリケーションと、アグリゲーター間の接続は同期していることができます。 アグリゲータは、クエリの応答を完了するために、3 つのバックエンド アプリケーションすべてからの応答を必要とします。 同期接続を適切に行い、ソリューションを単純化するために応答時間を短縮する必要があります。  
  
 通常、アグリゲータ パターンには、完全性条件が存在します。 複数のバックエンド サーバーが存在し、応答時間が遅い場合は、たとえば、一定の期間内に 1 つ以上の応答を受信することなどが完全性条件になります。 このサービス指向ソリューションでは、最終的なメッセージを構築するために 3 つの応答すべてが必要になります。 したがって、この場合の完全性条件は、3 つの応答すべてを受信することです。  
  
> [!NOTE]
>  IBM WebSphere MQ 経由で要求を受信するときに、ソリューションはコピーして関連付け識別子を追加、 **MQMD_MsgId**値を**MQMD_CorrelId**応答メッセージのです。 これは、予想される競合状態を回避するために要求 - 応答で IBM MQSeries アダプタを使用する標準的な方法の一部です。 詳細については、次を参照してください。[を相互に関連付けるメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)です。  
  
## <a name="determining-orchestration-boundaries"></a>オーケストレーションの境界の決定  
 ソリューションは、Web サービス インターフェイスを使用する要求だけでなく、IBM WebSphere MQ キューからの要求も許可する必要があります。 サービス インターフェイスを 1 つのオーケストレーションに配置し、IBM WebSphere MQ 入力を別のオーケストレーションに配置して、処理の大部分を 3 番目のオーケストレーションに配置すると、外部通信が処理から切り離されます。  
  
## <a name="translating-the-components-into-orchestration-shapes"></a>コンポーネントのオーケストレーション図形への変換  
 図形に変換するパターンはすべて、最終的なソリューションでは単一のオーケストレーションに含められます。 メッセージ ボックス サブスクリプションを作成するなど、コンテンツ ベースのルーターを BizTalk Server に作成する方法は多数あります。 このソリューションでは、メッセージ ボックス サブスクリプションを使用してルーティングが行われます。 式図形は、必須フィールドの値がメッセージに含まれているかどうかを評価します。 判断図形は、式図形内の変数セットを評価し、オーケストレーションを使用してパスを選択します。  
  
 **CustomerService**オーケストレーションでは、並列図形を使用してバックエンド アプリケーションにメッセージを送信し、同時に応答を受信します。 次の要求を行う前に 1 つのアプリケーションが完了するまで待機する必要はありません。 アプリケーションの数が頻繁に変更されたり、アプリケーションへの通信の信頼性が低い場合は、オーケストレーションはパターンを個別に変換する必要があります。  
  
 このソリューションで、アグリゲータは 3 つの応答メッセージの要素を結合する必要があります。 並列図形を使用すると、バックエンド システムとの通信は並列になります。 また、図形はすべての応答を受信するかタイムアウトが発生するまで終了しないので、アグリゲータは処理を進めることができるタイミングを常に認識しています。 オーケストレーションは、次の 3 つのバックエンド応答メッセージと元の要求メッセージから応答メッセージ内の要素までの要素をマップする変換図形を使用します。  
  
> [!NOTE]
>  バックエンド システムとの通信でタイムアウトが発生する場合もあります。タイムアウト期間を設定するにはそれを囲むによって、**受信**図形に、**スコープ**図形と設定、**タイムアウト**スコープのプロパティです。  
  
 オーケストレーション図形の一覧については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)です。  
  
## <a name="see-also"></a>参照  
 [パターンで、サービス指向ソリューション](../core/patterns-in-the-service-oriented-solution.md)   
 [コンポーネントのサービス指向ソリューション](../core/components-of-the-service-oriented-solution.md)
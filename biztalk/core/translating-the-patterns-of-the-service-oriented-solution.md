---
title: 指向ソリューションのサービスのパターンの変換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71d95653dbfcbf3937509ceedfe0ff304c602a8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243088"
---
# <a name="translating-the-patterns-of-the-service-oriented-solution"></a>指向ソリューションのサービスのパターンの変換
このセクションでは、ソリューションが BizTalk Server アイテムにパターンの図に変換される方法について説明します。  
  
 ![サービス&#45;ソリューション パターンを指向](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
## <a name="connections-and-completeness-conditions"></a>接続と完全性条件  
 BizTalk Server コンポーネント、パターンに変換するすべての場所で開始非常にことができます。 ただし、コンポーネント間の接続は、実際には、インフラストラクチャ コンポーネントを開始点として見えますようにします。 また、アグリゲータ パターンの場合にどのように示すか、すべての必要な情報があると思われる必要があります。 これは、その設計と同様に他のコンポーネントへの接続に影響します。  
  
 ソリューションは、使用状況の便利で一貫した方法を提供する必要があります。 サービス インターフェイスでは、他のアプリケーションが使用できる方法を指定します。 ソリューションは、IBM WebSphere MQ を使用してレガシ アプリケーションと通信する必要があります、ために、IBM WebSphere MQ をサービス インターフェイスの一部にする必要があります。 ただし、新しいアプリケーションでは、Web サービスのインターフェイスでは、最適に見えます。 Web サービス インターフェイスは、他のアプリケーション サービスを使用して最大限の柔軟性を提供します。 ここでは、BizTalk Server の柔軟性、デュアル サービス インターフェイスに使用できます。 オーケストレーションを Web サービスとして公開する方法の詳細については、次を参照してください。 [Web サービスにオーケストレーションをマップする方法](../core/how-to-map-orchestrations-to-web-services.md)します。  
  
 その他の接続は、サービス インターフェイスと、受信者の一覧と、バックエンド アプリケーション間、およびバックエンド アプリケーション、アグリゲーター、およびサービスのインターフェイス間で、受信者の一覧。  
  
 受信者の一覧への接続が同期の場合、ソリューションが相関関係を使用して、受信者の一覧にすべてのメッセージが送信され、受信したことを確認する必要はありません。 バックエンド アプリケーションと、アグリゲーター間の接続は、同じ理由で同期されることができます。 アグリゲーターでは、3 つのクエリの応答を完了するバックエンド アプリケーションすべてから応答が必要です。 応答時間は、同期接続が適切なが、ソリューションを簡素化されるように、短いことがあります。  
  
 アグリゲーター パターンでは通常は、完全性条件です。 複数のバック エンド サーバーが存在し、応答時間がかかる場合は、完全性条件可能性があります、たとえば、応答の受信を少なくとも 1 つ、一定時間内で。 このサービス指向ソリューションでは、最後のメッセージを構築するために 3 つすべての応答が必要です。 そのため、ここでは、完全性条件が受信して 3 つすべての応答。  
  
> [!NOTE]
>  コピーすることで、ソリューションが関連付け識別子を追加します IBM WebSphere MQ 経由で要求を受信するときに、 **MQMD_MsgId**値を**MQMD_CorrelId**の応答メッセージ。 これは、要求/応答で競合状態を回避するために、MQSeries アダプターを使用する標準的な方法の一部です。 詳細については、次を参照してください。[関連付けメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)します。  
  
## <a name="determining-orchestration-boundaries"></a>オーケストレーションの境界を決定します。  
 要求だけでなく、Web サービス インターフェイスを通じて、IBM WebSphere MQ キューからソリューションを許可する必要があります。 1 つのオーケストレーション、IBM WebSphere MQ 入力を別には、第 3 の処理の大部分に、サービス インターフェイスを配置するには、処理から切り離されて外部通信が保持されます。  
  
## <a name="translating-the-components-into-orchestration-shapes"></a>コンポーネントのオーケストレーション図形への変換  
 図形に変換するパターンは、最終的なソリューションでに 1 つのオーケストレーション。 BizTalk Server メッセージ ボックス サブスクリプションの作成などのコンテンツ ベースのルーターを作成するさまざまな方法はあります。 ソリューションでは、ルーティング、メッセージ ボックス サブスクリプションを使用します。 式図形では、メッセージには、必要なフィールドの値が含まれて かどうかを評価します。 判断図形は、式図形内の変数セットを評価し、オーケストレーションを使用してパスを選択します。  
  
 **CustomerService**オーケストレーションでは、並列図形を使用してバックエンド アプリケーションにメッセージを送信し、応答を同時に受信します。 1 つのアプリケーションが、次の要求を行う前に完了を待機する必要はありません。 アプリケーションの数が多くの場合、変更された場合、またはアプリケーションへの接続の信頼性が低い場合は、オーケストレーションはパターンを異なる方法で変換する必要があります。  
  
 ソリューションで、アグリゲータは 3 つの応答メッセージから要素を組み合わせる必要があります。 並列図形を使用してにより、バックエンド システムとの通信が並列であります。 また、続行すると、アグリゲーターが常に把握、図形がすべての応答またはタイムアウトを受信するまで終了しないためです。 オーケストレーションでは、3 つのバックエンド応答メッセージと元の要求メッセージから応答メッセージ内の要素までの要素をマップする変換図形を使用します。  
  
> [!NOTE]
>  バックエンド システムとの通信がタイムアウトで場合もあります。囲むことで、タイムアウト期間を設定することができます、**受信**で図形を**スコープ**図形と設定、**タイムアウト**スコープのプロパティ。  
  
 オーケストレーション図形の一覧については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)します。  
  
## <a name="see-also"></a>参照  
 [パターン、サービス指向ソリューション](../core/patterns-in-the-service-oriented-solution.md)   
 [サービス指向ソリューションのコンポーネント](../core/components-of-the-service-oriented-solution.md)
---
title: "メッセージングの使い分けとオーケストレーション Itinerary サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 694f929a-c830-4906-8e97-4fbd50e70133
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f98f48cc93e973b7170c854590359029a60ebf57
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="choosing-between-messaging-and-orchestration-itinerary-services"></a>メッセージングの使い分けとオーケストレーション Itinerary サービス
メッセージング サブシステムまたは BizTalk Server のオーケストレーションのサブシステムのいずれかで発生する、itinerary サービスを構成することができます。 これら ESB itinerary メッセージング サービスは、メッセージを処理するように構成がおよび、(入り口または出口) は、BizTalk Server パイプラインで実行することがあります。 このオプションにより、正確にここで、パイプラインで、サービスは実行を定義する開発者。 必然的に、オーケストレーション サブシステムでのプロセスに構成されているサービスは、BizTalk オーケストレーションで実行されます。  
  
## <a name="esb-itinerary-messaging-services"></a>ESB Itinerary メッセージング サービス  
 メッセージが BizTalk Server パイプラインで処理されるときには、メッセージの待ち時間が削減され ESB itinerary メッセージング サービスを使用します。 バックツー バック サービスを実装する、1 つのパイプラインで、メッセージを複数回を変換し、そのエンドポイントにのみ、1 つの永続化によって、メッセージ ボックス データベースにメッセージをルーティングすることができます。 さらに、メッセージ ベースの処理には、オーケストレーションの処理の他のリソース コストが削減されます。 一般に、メッセージ ベースの処理は以下のリソースを消費であり、オーケストレーションに基づいた処理よりも高速に処理を提供します。 パイプラインで、ESB ディスパッチャーと ESB ディスパッチャーの逆アセンブル パイプライン コンポーネントによって提供される[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージ インターセプターとして機能し、メッセージ ベースの itinerary サービス、ルーティングは、変換、またはカスタム サービスを実行します。 これらのコンポーネントを構成する方法の詳細については、次を参照してください。 [ESB ディスパッチャー コンポーネント](../esb-toolkit/the-esb-dispatcher-component.md)と[ESB ディスパッチャーを逆アセンブル コンポーネント](../esb-toolkit/the-esb-dispatcher-disassemble-component.md)です。  
  
## <a name="esb-itinerary-orchestration-services"></a>ESB Itinerary オーケストレーション サービス  
 動的ルーティングする必要がありますが発生した場合の間で、オーケストレーション プロセスの後に、itinerary サービス オーケストレーション ベースの処理で使用します。 既定では、オーケストレーション ベースのサービスには、XML ドキュメントとしてメッセージが表示されます。 ルーティング オーケストレーションは、競合回避モジュール マネージャーを使用して、itinerary で識別されたエンドポイントを解決しようとしています。 アダプター マネージャーは、エンドポイントの詳細をメッセージ コンテキストに昇格するリゾルバー マネージャーからの応答を使用し、メッセージは直接バインドの論理ポートを使用して、メッセージ ボックス データベースに公開します。 この時点では、通常 BizTalk ルーティングが発生し、メッセージの昇格させたプロパティを使用して、動的送信ポートを構成します。  
  
 含まれる行程サービス オーケストレーションでは、カスタム オーケストレーションに基づく itinerary のサービスを作成する適切な開始点を提供します。 道順のカスタムのサービスの作成の詳細については、次を参照してください。[変更および拡張 BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)です。
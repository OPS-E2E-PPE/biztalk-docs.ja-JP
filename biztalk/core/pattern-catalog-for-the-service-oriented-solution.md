---
title: パターン カタログ サービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Calling Pipelines from Code pattern [service solutions]
- Recipient List pattern [service solutions]
- filters, design patterns
- Filter pattern [service solutions]
- caching, patterns [service solutions]
- Service Interface pattern [service solutions]
- Content-Based Routing pattern [service solutions]
- Inline Invocation of Back-End Processes pattern [service solutions]
- content-based routing, patterns [service solutions]
- messages, Translator pattern [service solutions]
- aggregations, patterns [service solutions]
- Translator pattern, service solutions
- Caching pattern [service solutions]
- Aggregation pattern [service solutions]
- patterns [service solutions], pattern types
- back-end processes
- services, interface pattern [service solutions]
ms.assetid: 5d8135c5-d5de-4e61-b3e8-2aa7f6de98c8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e014520057a47145daeeb0ee2a1e03a4f88e1af6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291880"
---
# <a name="pattern-catalog-for-the-service-oriented-solution"></a>パターン カタログ サービス指向ソリューション
サービス指向ソリューションのパターンには、前のセクションでの BizTalk Server に固有のプログラミングのパターンとエンタープライズ統合パターンが含まれます。 このセクションの一覧には、両方のパターンが含まれています。  
  
## <a name="pattern-types"></a>パターンの種類  
 について簡単に、次のトピックで説明されているエントリはパターンを説明し、ソリューションが、パターンを使用する方法について説明するその他のトピックをポイントします。 場合は、フィルターなどの一般的なパターンは、エントリは、一般的なトピックをポイントします。  
  
### <a name="aggregation-pattern"></a>集計パターン  
 集計は、複数のソースから情報を受け取って、1 つのメッセージに統合するパターンです。 サービス指向ソリューションでは、1 つの応答に次の 3 つの異なるソースから信用情報を結合します。 作成するソリューションの性質によって、さまざまな方法がいくつかの集計を行うことができます。 場合によっては、すべての応答を待機する必要があります。 それ以外の場合など、ローンの引用符で囲まれたことができますに最小値である限り、応答を取得しません。 サービス指向ソリューションは、3 つすべてを返す完全なクレジットのレポートが存在するために必要とするため、3 つすべての応答があるまでに待機します。 詳細については、次を参照してください。[サービス指向ソリューションのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)します。  
  
### <a name="calling-pipelines-from-code-pattern"></a>コード パターンからのパイプラインの呼び出し  
 コード、およびオーケストレーションからパイプラインを呼び出すことができます。 これは、パイプラインの再利用を許可され、パイプライン ステージからオーケストレーションの分離の維持にも役立ちます。 詳細については、次を参照してください。[からサービス指向ソリューションを使用してパイプライン](../core/using-pipelines-from-the-service-oriented-solution.md)します。  
  
### <a name="caching-pattern"></a>キャッシュ パターン  
 キャッシュは、一般的な戦略が要求されるたびに、データ ストアから取得するのではなく、情報を格納するのです。 エンタープライズ シングル サインオン システムから参照または構成データを取得するソリューションを制限する要素にすることがわかりました。 ソリューションでは、情報をキャッシュし、キャッシュを定期的に更新します。 詳細については、次を参照してください。[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)します。 ビジネス プロセス管理ソリューションでは、少し異なるプロセスを使用しています、SSO 情報もキャッシュします。 詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)します。  
  
### <a name="content-based-routing-pattern"></a>コンテンツ ベースのルーティング パターン  
 エンタープライズ統合パターンのでは、コンテンツ ベースのルーティングよりも多岐 BizTalk でです。 エンタープライズ統合パターンのコンテンツ ベース ルーティング、メッセージの内容の一部に基づいてメッセージの受信者の決定です。 サービス指向ソリューションは、コンテンツ ベース ルーティングの非常に単純な形式を使用して、オーケストレーションの単一の判断図形は、2 つの場所のいずれかのメッセージを送信します。 詳細についてを参照してください「の変換、コンポーネントのオーケストレーション図形へ」[サービス指向ソリューションのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)します。  
  
### <a name="filter-pattern"></a>フィルタ パターン  
 フィルタ パターンは、処理のための特定の条件を満たすメッセージを選択します。 BizTalk server のフィルタ パターンは、ほぼ常にポートのフィルター式になります。 ポートのフィルタの詳細については、次を参照してください。[を使用してフィルターと、受信メッセージ図形](../core/using-filters-with-the-receive-message-shape.md)します。  
  
### <a name="inline-invocation-of-back-end-processes-pattern"></a>バックエンド プロセスのパターンのインライン呼び出し  
 ソリューションのインライン バージョンでは、カスタム アセンブリを介してバックエンド プロセスのインライン呼び出しを使用します。 これは、大幅に強化されたパフォーマンスの利点があります。 なりますが、コスト、ただし、トランスポート プロトコルにオーケストレーションが密結合の。 詳細については、次を参照してください。[バックエンドの呼び出しをインライン展開](../core/inlining-back-end-invocation.md)します。  
  
### <a name="recipient-list-pattern"></a>受信者の一覧パターン  
 抽象的な意味では、サービス指向ソリューションは、その 3 つの異なるシステムにメッセージを送信に受信者の一覧を実装します。 実際には、デプロイされたアプリケーションは、特定の場所に論理ポートをマッピングすることによって、受信者を決定します。 アプリケーションのインライン バージョンの場合、接続は、SSO の構成情報を通じて行われます。 詳細については、次を参照してください。[サービス指向ソリューションのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)します。  
  
### <a name="service-interface-pattern"></a>サービス インターフェイス パターン  
 サービス指向ソリューションは、サービスを行うことが多くの方法のいずれかにのみ、Web サービスとしてそれ自体を表示します。 Web サービスとしてのオーケストレーションを使用する方法の詳細については、次を参照してください。 [Web サービスを使用する](../core/using-web-services.md)します。  
  
### <a name="translator-pattern"></a>変換者パターン  
 トランスレーターのエンタープライズ パターン-は、変換、メッセージの 1 つの形式から別の形式に、最も多くの場合、BizTalk Server マップに変換します。 BizTalk Server マップについての詳細については、次を参照してください。[を作成するマップを使用して BizTalk マッパー](../core/creating-maps-using-biztalk-mapper.md)します。  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューションのパターン](../core/patterns-in-the-service-oriented-solution.md)
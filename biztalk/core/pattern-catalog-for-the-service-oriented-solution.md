---
title: サービスのパターン カタログ指向ソリューション |Microsoft ドキュメント
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
ms.openlocfilehash: 9441ead974cdcaba66dd9d038e786a5a8c7b156e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265498"
---
# <a name="pattern-catalog-for-the-service-oriented-solution"></a>指向ソリューションのサービスのパターン カタログ
サービス指向ソリューションのパターンには、前のセクションのエンタープライズ統合パターンと BizTalk Server 固有のプログラミング手法のパターンが含まれます。 このセクションの一覧は、両方のパターンを含みます。  
  
## <a name="pattern-types"></a>パターンの種類  
 次のトピックのエントリでは、パターンについて簡潔に説明し、ソリューションでパターンが使用される方法を説明する他のトピックを記載しています。 フィルタなどの一般的なパターンの場合、エントリは、さらに一般的なトピックを示します。  
  
### <a name="aggregation-pattern"></a>集計パターン  
 集計は、複数のソースから情報を取得して単一のメッセージに統合するパターンです。 サービス指向ソリューションは、3 つの異なるソースからのクレジット情報を 1 つの応答に結合します。 作成するソリューションの種類に応じて、さまざまな方法で集計を実行できます。 すべての応答を待つことが必要になる場合もあります。 ローンの見積もりなどの場合は、最小値である限り、応答を取得しないこともあります。 サービス指向ソリューションは、完全なクレジット記録を返すために 3 つのすべての応答が必要なので、3 つのすべての応答を受け取るまで待機します。 詳細については、次を参照してください。[サービス指向ソリューションのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)です。  
  
### <a name="calling-pipelines-from-code-pattern"></a>コード パターンからのパイプラインの呼び出し  
 使用しているコードおよびオーケストレーションからパイプラインを呼び出すことができます。 これは、パイプラインの再利用でき、パイプライン ステージからオーケストレーションの分離を維持するため。 詳細については、次を参照してください。[サービス指向ソリューションからパイプラインを使用して](../core/using-pipelines-from-the-service-oriented-solution.md)です。  
  
### <a name="caching-pattern"></a>キャッシュ パターン  
 キャッシュは、一般的な戦略が要求されるたびに、データ ストアから取得するのではなく、情報を格納するのです。 エンタープライズ シングル サインオン システムから参照または構成データを常時、取得していると、ソリューションは性能が制限されます。 そこで、情報をキャッシュし、定期的にキャッシュを更新します。 詳細については、次を参照してください。[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)です。 ビジネス プロセス管理ソリューションは、少し異なるプロセスを使用しますが、SSO 情報もキャッシュします。 詳細については、次を参照してください。[を使用して SSO の効率的なビジネス プロセス管理ソリューションで](../core/using-sso-efficiently-in-the-business-process-management-solution.md)です。  
  
### <a name="content-based-routing-pattern"></a>コンテンツ ベースのルーティング パターン  
 エンタープライズ統合パターンのコンテンツ ベースのルーティングは、BizTalk よりも多岐にわたると考えられます。 エンタープライズ統合パターンのコンテンツ ベースのルーティングは、メッセージのコンテンツの一部に基づいて、メッセージの受信者を決定します。 サービス指向ソリューションは、コンテンツ ベース ルーティングの非常に単純な形式を使用して、オーケストレーションの単一の判断図形は、2 つの場所のいずれかのメッセージを送信します。 詳細についてを参照してください「の変換、コンポーネントのオーケストレーション図形へ」[サービス指向ソリューションのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)です。  
  
### <a name="filter-pattern"></a>フィルタ パターン  
 フィルタ パターンは、処理に使用する特定の基準を満たすメッセージを選択します。 ほとんどの場合、BizTalk Server のフィルタ パターンは、ポートのフィルタ式になります。 ポートのフィルターの詳細については、次を参照してください。[を使用してフィルターと、受信メッセージ図形](../core/using-filters-with-the-receive-message-shape.md)です。  
  
### <a name="inline-invocation-of-back-end-processes-pattern"></a>バックエンド プロセスのインライン呼び出しパターン  
 インライン バージョンのこのソリューションは、カスタム アセンブリでバックエンド プロセスのインライン呼び出しを行います。 これにより、パフォーマンスが大幅に向上する利点があります。 ただし、トランスポート プロトコルとオーケストレーションが密に結合するという代償を払います。 詳細については、次を参照してください。[バックエンドの呼び出しをインライン展開](../core/inlining-back-end-invocation.md)です。  
  
### <a name="recipient-list-pattern"></a>受信者の一覧パターン  
 抽象的な意味で、サービス指向ソリューションは、メッセージを 3 つの異なるシステムに送信するため、受信者の一覧を実装しています。 つまり、展開されたアプリケーションは、論理ポートを特定の場所にマップして、受信者を決定します。 インライン バージョンのアプリケーションの場合、SSO の構成情報を通じて接続が行われます。 詳細については、次を参照してください。[サービス指向ソリューションのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)です。  
  
### <a name="service-interface-pattern"></a>サービス インターフェイス パターン  
 サービス指向ソリューションは、サービスを実行する多くの方法の 1 つである Web サービスとして使用されます。 詳細については、Web サービスとしてのオーケストレーションを使用して、次を参照してください。 [Web サービスを使用する](../core/using-web-services.md)です。  
  
### <a name="translator-pattern"></a>変換者パターン  
 翻訳者のエンタープライズ パターン-は、メッセージの変換を 1 つの形式から別の形式に — 最も多くの場合、BizTalk Server マップに変換します。 BizTalk Server マップに関する概要については、次を参照してください。[を作成するマップを使用して BizTalk マッパー](../core/creating-maps-using-biztalk-mapper.md)です。  
  
## <a name="see-also"></a>参照  
 [パターンで、サービス指向ソリューション](../core/patterns-in-the-service-oriented-solution.md)
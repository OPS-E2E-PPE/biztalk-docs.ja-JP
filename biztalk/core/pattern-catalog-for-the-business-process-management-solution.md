---
title: "ビジネス プロセス管理ソリューションのカタログのパターンを |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Canonical Message pattern [process management solutions]
- Nested Scopes pattern [process management solutions]
- Filter pattern [process management solutions]
- Per-Instance Pipeline Configuration pattern [process management solutions]
- Translator pattern, process management solutions
- patterns [process management solutions], pattern types
- Interruptible Orchestration pattern [process management solutions]
- Decoupled Orchestration pattern [process management solutions]
- Code Retry and Exception Handling pattern [process management solutions]
- Process Manager pattern [process management solutions]
- Asynchronous Reply pattern [process management solutions]
- Custom Exceptions pattern [process management solutions]
- Message Broker pattern [process management solutions]
- Coordination Using Delivery Notification pattern [process management solutions]
- Convoy pattern [process management solutions]
- Versioning pattern [process management solutions]
- Error Routing pattern [process management solutions]
- Application Reference pattern [process management solutions]
- Inverse Direct Partner Binding pattern [process management solutions]
ms.assetid: 246b109e-6006-404d-88b9-e6324ce3473c
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b352cce73e45103437407a013691e604b7b959
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="pattern-catalog-for-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのパターン カタログ
ビジネス プロセス管理ソリューションのパターンとしては、前のセクションのエンタープライズ統合パターンや BizTalk Server をプログラミングする一般的なパターンがあります。 このセクションの一覧は、両方のパターンを含みます。  
  
## <a name="pattern-types"></a>パターンの種類  
 次のエントリでは、パターンについて簡潔に説明し、ソリューションでパターンが使用される方法を説明する他のトピックを記載しています。 フィルタなどの一般的なパターンの場合、エントリは、さらに一般的なトピックを示します。  
  
### <a name="application-reference-patterns"></a>アプリケーション参照パターン  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、他のアプリケーションへの参照を追加して、同じグループ内の別のアプリケーションのアイテムを使用できます。 ビジネス プロセス管理ソリューションは、テスト ソリューションの設計メイン ソリューションでアプリケーション参照を使用します。 ソリューション内のアプリケーション参照の詳細については、次を参照してください。[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。  
  
### <a name="asynchronous-reply-patterns"></a>非同期応答パターン  
 注文マネージャ ステージと注文処理ステージ間の通信は、非同期です。 つまり、応答を受信するまで、マネージャが処理を続行します。 これらのステージでは、マネージャに応答を送信する自己関連付けを行う動的ポートを使用します。 自己関連付けを行うポートを使用すると、関連付けセットを管理する注文マネージャが不要になります。 ポートが動的なので、注文マネージャは、応答用のポートのアドレスを注文ステージに送信できます。 ソリューションでのポートの詳細については、次を参照してください。[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)です。  
  
### <a name="canonical-message-patterns"></a>正規メッセージ パターン  
 ソリューション処理を簡単にするには、多くの場合、外部メッセージを内部形式に変換します。 この形式には、正規メッセージがあります。 注文ブローカのオーケストレーションは、すべての注文メッセージを 1 つ以上の正規型の注文メッセージに変換します。 注文マネージャのオーケストレーションおよび処理ステージで、この一般的な注文形式が使用されます。 詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)です。  
  
### <a name="code-retry-and-exception-handling-patterns"></a>コードの再試行および例外処理パターン  
 ソリューションを集中化例外処理の多く、 **ExceptionHandler**オーケストレーションです。 このソリューションは、切断されたネットワーク接続で再試行すると処理が成功する可能性がある場合にこのオーケストレーションを使用します。 オーケストレーションを使用して、 **Recaller**を失敗したコードを再実行するオブジェクト。 オーケストレーションの詳細については、次を参照してください。[ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md)です。 参照してください[ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md)です。 使用の詳細について、 **Recaller**オブジェクトを参照してください[Recaller Object](../core/the-recaller-object.md)です。  
  
### <a name="convoy-pattern"></a>コンボイ パターン  
 注文マネージャのオーケストレーション OrderManager では、コンボイ パターンを使用して、処理する注文に対して後で変更を行います。 注文マネージャのコンボイ パターンの詳細についてを参照してください「注文の更新」[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)です。  
  
### <a name="coordination-using-delivery-notification"></a>配信通知を使用した調整  
 **OrderBroker**オーケストレーションでは、配信通知を使用して、2 つ目の注文処理ステージで、履歴が更新される前に、履歴データベースにエントリが作成されたことを確認してください (**CableOrder2**)。 詳細についてを参照してください「の段階で調整」[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)です。 配信通知の概要については、次を参照してください。[を使用して受信確認](../core/using-acknowledgments.md)です。  
  
### <a name="custom-exceptions-pattern"></a>カスタム例外パターン  
 再試行できない例外に対して、このソリューションは、カスタム例外処理と通常の BizTalk Server 例外処理を行います。 カスタム例外処理では、より詳細な例外処理を行います。 また、操作のすべての部分がロールバックされるようにするために、入れ子になったスコープ間のフラグとしても使用されます。 カスタム例外は、ソリューションの使用に関する詳細については、次を参照してください。[カスタム例外](../core/custom-exceptions.md)です。 スコープの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)です。  
  
### <a name="decoupled-orchestration-patterns"></a>分離したオーケストレーションのパターン  
 ビジネス プロセス管理ソリューションの設計では、オーケストレーションを可能な限り分離します。 オーケストレーションを分離すると、ソリューションの部分のバージョン管理や他のサーバーまたはグループへの移動が簡単になります。 注文ブローカと注文マネージャの間のリレーションシップに関する詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)と[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)です。  
  
### <a name="error-routing-pattern"></a>エラー ルーティング パターン  
 このソリューションは、BizTalk Server の新しいエラー報告機能を使用します。 この機能は、報告用または処理用のサブスクライブの対象となるポートに失敗したメッセージをルーティングします。 エラー報告の概要については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)です。  
  
### <a name="filter-pattern"></a>フィルタ パターン  
 フィルタ パターンは、処理に使用する特定の基準を満たすメッセージを選択します。 ほとんどの場合、BizTalk のフィルタ パターンは、ポートのフィルタ式になります。 ポートのフィルターの詳細については、次を参照してください。[を使用してフィルターと、受信メッセージ図形](../core/using-filters-with-the-receive-message-shape.md)です。  
  
### <a name="interruptible-orchestration-pattern"></a>割り込み可能なオーケストレーション パターン  
 このソリューションは、最初に現在の注文を中断して、注文の更新や取り消しを行います。 このソリューションのオーケストレーションは、Interrupt オーケストレーションを使用して、割り込みを処理します。 詳細については、次を参照してください。[ビジネス プロセス管理ソリューションでの処理を中断](../core/interrupt-handling-in-the-business-process-management-solution.md)です。  
  
### <a name="inverse-direct-partner-binding-pattern"></a>逆のパートナーの直接バインド パターン  
 このソリューションは、直接バインドを逆に行い、注文マネージャの注文処理ステージを分離します。 逆の直接バインドの詳細については、次を参照してください。[逆パートナーの直接バインド](../core/inverse-direct-partner-binding.md)です。  
  
### <a name="message-broker-pattern"></a>メッセージ ブローカ パターン  
 メッセージ ブローカ パターンを使用すると、送信者が送信先を認識しなくても済むように、このソリューションでメッセージの送信先を決めることができます。 ビジネス プロセス管理ソリューションを実装したメッセージ ブローカを**OrderBroker**オーケストレーションです。 **OrderBroker**オーケストレーションの注文を受け取り、注文するサービスの種類を決定、および正しい注文マネージャに注文をルーティングします。 メッセージ ブローカの詳細については、 **OrderBroker**を参照してください[OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)です。  
  
### <a name="nested-scopes-pattern"></a>入れ子になったスコープのパターン  
 **OrderBroker**オーケストレーションは入れ子になったスコープを使用して永続化ポイントを最小限に抑えると、そのため、効率を向上させるためにします。 詳細についてを参照してください「向上パフォーマンスで入れ子になったスコープ」 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)です。  
  
### <a name="per-instance-pipeline-configuration"></a>インスタンスごとのパイプラインの構成  
 このソリューションは既定のパイプラインを使用しますが、メッセージのエンベロープを指定するため、新しいインスタンスごとのパイプラインの構成を広範に使用します。 詳細については、次を参照してください。[パイプラインを展開する方法](../core/how-to-deploy-pipelines.md)と[ビジネス プロセス管理ソリューションのコンポーネント](../core/components-of-the-business-process-management-solution.md)です。  
  
### <a name="process-manager-pattern"></a>プロセス マネージャ パターン  
 このソリューションは、比較的一般的な注文マネージャを使用して、注文処理ステージのフローを制御します。 このため、注文処理の管理からビジネス ロジックを分離できます。 OrderManager オーケストレーションがプロセス マネージャーとして機能する方法の詳細については、次を参照してください。[プロセス マネージャのロジック](../core/process-manager-logic.md)です。  
  
### <a name="terminate-shape-at-end-of-orchestration"></a>オーケストレーションの終了時の終了図形  
 いくつかのオーケストレーションでは、オーケストレーションが正常終了する場合でも、エラーに対する終了図形を使用します。 終了図形を使用すると、失敗したインスタンスおよびエラーを追跡できます。 詳細については、次を参照してください。[カスタム例外](../core/custom-exceptions.md)です。  
  
### <a name="translator-pattern"></a>変換者パターン  
 トランスレーターのエンタープライズ パターン-は、メッセージの変換を 1 つの形式から別の形式に、ほとんどの場合、BizTalk マップに変換します。 BizTalk マップに関する概要については、次を参照してください。[を作成するマップを使用して BizTalk マッパー](../core/creating-maps-using-biztalk-mapper.md)です。  
  
### <a name="versioning-patterns"></a>バージョン管理パターン  
 ビジネス プロセス管理ソリューションでは、オーケストレーションを分離してスキーマの名前空間のバージョン番号付け機能を使用することにより、ソリューション コンポーネントのバージョン管理を簡単に行えるようにしています。 詳細については、次を参照してください。[ビジネス プロセス管理ソリューションのバージョン管理](../core/versioning-the-business-process-management-solution.md)です。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのパターン](../core/patterns-in-the-business-process-management-solution.md)
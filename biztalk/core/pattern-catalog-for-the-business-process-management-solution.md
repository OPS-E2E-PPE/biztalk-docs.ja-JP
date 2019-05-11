---
title: ビジネス プロセス管理ソリューションのカタログのパターン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed13b415b0bb026f9c948cafbd48c1fa3e73a3cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291904"
---
# <a name="pattern-catalog-for-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのパターン カタログ
ビジネス プロセス管理ソリューションのパターンには、前のセクションで、エンタープライズ統合パターンと、BizTalk Server のプログラミングの一般的なパターンが含まれます。 このセクションの一覧には、両方のパターンが含まれています。  
  
## <a name="pattern-types"></a>パターンの種類  
 次のエントリの簡単なパターンについて説明し、ソリューションがパターンを使用する方法について説明するその他のトピックをポイントします。 場合は、フィルターなどの一般的なパターンは、エントリは、一般的なトピックをポイントします。  
  
### <a name="application-reference-patterns"></a>アプリケーション参照パターン  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 同じグループ内の別のアプリケーションで他のアプリケーションへの参照を追加することで、成果物を使用するアプリケーションを有効にします。 ビジネス プロセス管理ソリューションは、テスト ソリューションもメイン ソリューションの設計では、アプリケーションの参照を使用します。 ソリューション内のアプリケーション参照の詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションの一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)します。  
  
### <a name="asynchronous-reply-patterns"></a>非同期応答パターン  
 注文マネージャ ステージと注文処理ステージ間の通信は非同期です。 マネージャーは、受信するまで処理を続行する、応答します。 ステージでは、自己関連付けを行う動的ポートを使用して、マネージャーへの返信を送信します。 自己関連付けポートには、関連付けセットを管理する注文マネージャにする必要があります。 ポートの動的な側面は、応答のポートのアドレスを注文ステージに送信するマネージャーを順序にできます。 ソリューション内のポートの詳細については、次を参照してください。[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)します。  
  
### <a name="canonical-message-patterns"></a>正規メッセージ パターン  
 ソリューションの多くの場合、処理を簡略化するには、外部メッセージを内部形式に変換します。 この形式は、標準的なメッセージの例を示します。 注文ブローカのオーケストレーションでは、すべての注文メッセージを 1 つ以上の正規の順序のメッセージに変換します。 注文マネージャーのオーケストレーションと処理ステージでは、この一般的な注文形式を使用します。 詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)します。  
  
### <a name="code-retry-and-exception-handling-patterns"></a>コードの再試行および例外処理パターン  
 ソリューションでは、例外処理の多くを一元化、 **ExceptionHandler**オーケストレーションします。 ソリューションを使用してこのオーケストレーション、可能性がある場合に、切断されたネットワーク接続が再試行された場合、操作が成功可能性のあるのと同様。 オーケストレーションを使用して、 **Recaller**を失敗したコードを再実行するオブジェクト。 オーケストレーションの詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md)します。 参照してください[、ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)します。 詳細については、使用、 **Recaller**オブジェクトを参照してください[「Recaller オブジェクト](../core/the-recaller-object.md)します。  
  
### <a name="convoy-pattern"></a>コンボイ パターン  
 注文マネージャのオーケストレーション OrderManager では、キャッチし、以降の変更処理中の注文を処理するコンボイ パターンを使用します。 注文マネージャのコンボイ パターンの詳細についてを参照してください「注文の更新」[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)します。  
  
### <a name="coordination-using-delivery-notification"></a>配信通知を使用した調整  
 **OrderBroker**オーケストレーションでは、配信通知を使用して、2 番目の注文処理ステージで、履歴が更新される前に、履歴データベースでエントリを作成することを確認します (**CableOrder2**)。 詳細についてを参照してください「の段階で調整」[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)します。 配信通知の詳細については、次を参照してください。[を使用して受信確認](../core/using-acknowledgments.md)します。  
  
### <a name="custom-exceptions-pattern"></a>カスタム例外パターン  
 再試行できない例外の場合は、ソリューションは、通常 BizTalk Server 例外がカスタム例外処理と共に処理を使用します。 カスタム例外処理では、特定の例外処理を提供します。 操作のすべての部分がロールバックすることを確認する入れ子になったスコープ間のフラグとしても機能します。 カスタム例外の詳細については、ソリューションの使用は、次を参照してください。[カスタム例外](../core/custom-exceptions.md)します。 スコープの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)します。  
  
### <a name="decoupled-orchestration-patterns"></a>分離したオーケストレーション パターン  
 ビジネス プロセス管理ソリューションの設計では、可能な最大の範囲のオーケストレーションを分離します。 オーケストレーションを分離して、により、ソリューションの部分のバージョンを簡単に、ソリューションを他のサーバーまたはグループの移動が簡単です。 注文ブローカと注文マネージャの関係の詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)と[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)します。  
  
### <a name="error-routing-pattern"></a>エラー ルーティング パターン  
 ソリューションでは、新しい BizTalk Server エラーの報告機能を使用します。 この機能のルートには、レポートまたは処理のためにサブスクライブしているポートにメッセージが失敗しました。 エラー報告の詳細については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)します。  
  
### <a name="filter-pattern"></a>フィルタ パターン  
 フィルタ パターンは、処理のための特定の条件を満たすメッセージを選択します。 、BizTalk のフィルタ パターンは、ほぼ常にポートのフィルター式になります。 ポートのフィルタの詳細については、次を参照してください。[を使用してフィルターと、受信メッセージ図形](../core/using-filters-with-the-receive-message-shape.md)します。  
  
### <a name="interruptible-orchestration-pattern"></a>割り込み可能なオーケストレーション パターン  
 ソリューションは、最初に現在の注文を中断することによって、注文の更新や取り消しを処理します。 ソリューションのオーケストレーションでは、Interrupt オーケストレーションを使用して、割り込みを処理します。 詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションでの処理を中断](../core/interrupt-handling-in-the-business-process-management-solution.md)します。  
  
### <a name="inverse-direct-partner-binding-pattern"></a>逆のパートナーの直接バインド パターン  
 ソリューションは、注文処理ステージ注文マネージャからを分離するために直接バインドの使用を反転させます。 逆の直接バインドの詳細については、次を参照してください。[逆パートナーの直接バインド](../core/inverse-direct-partner-binding.md)します。  
  
### <a name="message-broker-pattern"></a>メッセージ ブローカ パターン  
 メッセージ ブローカ パターンにより、送信者は、変換先を知る必要がないように、メッセージの送信先を決定するソリューションです。 ビジネス プロセス管理ソリューションの実装でのメッセージ ブローカー、 **OrderBroker**オーケストレーションします。 **OrderBroker**オーケストレーションが注文を受け取り、注文するサービスの種類を決定しますおよび順序を正しい注文マネージャにルーティングします。 メッセージ ブローカの詳細については、 **OrderBroker**を参照してください[OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)します。  
  
### <a name="nested-scopes-pattern"></a>入れ子になったスコープのパターン  
 **OrderBroker**オーケストレーションは、永続化ポイントを最小限に抑えるために入れ子になったスコープを使用し、そのため、効率を向上させます。 詳細についてを参照してください「の向上パフォーマンスで入れ子になったスコープ」 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)します。  
  
### <a name="per-instance-pipeline-configuration"></a>インスタンスごとのパイプラインの構成  
 ソリューションは、既定のパイプラインを使用して、メッセージのエンベロープを指定する新しいインスタンスごとのパイプラインの構成の広範な使用になります。 詳細については、次を参照してください。[パイプラインをデプロイする方法](../core/how-to-deploy-pipelines.md)と[、ビジネス プロセス管理ソリューションのコンポーネント](../core/components-of-the-business-process-management-solution.md)します。  
  
### <a name="process-manager-pattern"></a>プロセス マネージャ パターン  
 ソリューションでは、注文処理ステージでフローを制御するのに、比較的一般的な注文マネージャを使用します。 これにより、注文プロセスの管理からビジネス ロジックを分離します。 OrderManager オーケストレーションがプロセス マネージャーとして機能する方法の詳細については、次を参照してください。[プロセス マネージャのロジック](../core/process-manager-logic.md)します。  
  
### <a name="terminate-shape-at-end-of-orchestration"></a>オーケストレーションの終了時の終了図形  
 いくつかのオーケストレーションでは、終了図形を使用して、場合でも、オーケストレーションはその時点で終了した通常のエラーで終了します。 終了図形は、失敗したインスタンスおよびエラーを追跡できるようにします。 詳細については、次を参照してください。[カスタム例外](../core/custom-exceptions.md)します。  
  
### <a name="translator-pattern"></a>変換者パターン  
 トランスレーターのエンタープライズ パターン-は、変換、メッセージの 1 つの形式から別の形式に、最も多くの場合、BizTalk マップに変換します。 BizTalk マップについての詳細については、次を参照してください。[を作成するマップを使用して BizTalk マッパー](../core/creating-maps-using-biztalk-mapper.md)します。  
  
### <a name="versioning-patterns"></a>バージョン管理パターン  
 ビジネス プロセス管理ソリューションは、オーケストレーションを分離してスキーマの名前空間のバージョン番号を使用して、ソリューション コンポーネントのバージョン管理が簡単に設計されています。 詳細については、次を参照してください。[ビジネス プロセス管理ソリューションのバージョン管理](../core/versioning-the-business-process-management-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのパターン](../core/patterns-in-the-business-process-management-solution.md)
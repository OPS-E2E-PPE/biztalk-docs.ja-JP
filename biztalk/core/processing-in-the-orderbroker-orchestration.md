---
title: OrderBroker オーケストレーションで処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, nested scopes
- nested scopes, performance
- processing, examples
- nested scopes, orchestrations
- orchestrations, performance
- performance, orchestrations
- performance, nested scopes
- examples, orchestration processing [process management solution]
- scopes, nesting
ms.assetid: c296e00c-b3ad-4161-baf7-258899185c34
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6a6571ece3190b6195b207b4c45969ce25ddec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266634"
---
# <a name="processing-in-the-orderbroker-orchestration"></a>OrderBroker オーケストレーションでの処理
このセクションの内容について説明しますが、どのように**OrderBroker**オーケストレーションが注文を受け付けるし、準備がプロセス マネージャー。 まず、オーケストレーションの一般的な動作について説明します。 次に、オーケストレーションがメッセージを処理する方法を説明します。 最後に、オーケストレーションがアトミック トランザクションを使用してパフォーマンスを向上させるしくみを明らかにします。  
  
> [!NOTE]
>  長さの長さのため、 **OrderBroker**コード、オーケストレーションを Microsoft® Visual Studio で開いてこのセクションを参照する可能性があります。  
  
## <a name="why-an-order-broker"></a>注文ブローカとは  
 目的、 **OrderBroker**オーケストレーションでは、注文を正しいプロセス マネージャにルーティングします。 この前処理は、履歴データベース、サービス提供システム、および受注確認のための情報メッセージの生成から成ります。 **OrderBroker**カスタマー サービス要求から一般的な注文メッセージも作成されます。 この注文の正規化によって、ビジネスプロセスの要素による注文の汎用使用が可能になります。  
  
 注文メッセージはマルチパート メッセージであり、ルーティング情報と注文情報に分かれています。 ルーティング情報も汎用的で、どの注文マネージャでも使用できるように設計されています。 こうすることで、ソリューションを拡張しやすくなります。 マルチパート メッセージの詳細については、次を参照してください。[マルチパート メッセージの種類を使用する方法](../core/how-to-use-multi-part-message-types.md)です。  
  
 ブローカ機能を分離すると、それを別の BizTalk グループに移動することもできます。 **OrderBroker**をメッセージ ボックス データベースに公開: つまり、これは直接バインド: も簡単に別のグループに、ブローカーは、オーケストレーションを変更することがなく、ブローカーを行うことができます。 配置の詳細については、 **OrderBroker**別のグループで、次を参照してください。 [OrderBroker と OrderManager 間の通信](../core/communication-between-orderbroker-and-ordermanager.md)です。  
  
> [!NOTE]
>  **OrderBroker**オーケストレーション、1 つだけがあるため**OrderManager** 、通信するために割り当てるだけ定数文字列を**OrderMgrType**フィールドの順序メッセージのマネージャーです。 通常、複数の注文マネージャがあるアプリケーションでは、アプリケーションがビジネス ルール エンジンを使用して、このフィールドの値と正しい注文経路を決定します。 ビジネス ルール エンジンの詳細については、次を参照してください。[を使用してビジネス ルールの作成と](../core/creating-and-using-business-rules.md)です。  
  
## <a name="order-processing"></a>注文処理  
 **OrderBroker**オーケストレーションは、最初の 2 つ**受信**内の図形は、**リッスン**図形です。 1 つ**受信**図形はカスタマー サポート システムからのメッセージは、ベンダ システムから、他のメッセージ。 どちらのソースのメッセージも同じスキーマです。  
  
 オーケストレーションがメッセージから戻り値のアドレスを抽出し、動的ポートのアドレスを設定するため**CSRPort**です。 オーケストレーションはこのポートを使用して受信確認やエラーメッセージを送信します。  
  
 次のステップで、 **OrderBroker**履歴メッセージ、サービス メッセージ、確認のメッセージ、および注文メッセージを送信するオーケストレーションが作成、 **OrderManager**オーケストレーションです。 オーケストレーションを使用して、 **InsertOrderBody**履歴メッセージに、注文メッセージを追加するユーティリティ関数です。  
  
> [!NOTE]
>  状況によっては、配信されても使用されないメッセージをソリューションが生成することがあります。 オーダー ブローカ オーケストレーションは送信ポートを使用して、履歴データベースに情報を挿入します。 この送信ポートは配信通知を使用します。 構成は、次の 2 つのポートを含む送信ポート グループに、送信ポートをマップ: テスト構成の 1 つのポート (**HISTORYINSERT-SP テスト**)、正規の構成のいずれか (**HISTORYINSERT-SP**)。 グループの両方のポートを開けておくと、両方のポートにメッセージが送信されます。 したがって、2 つの配信通知が要求されますが、処理されるのは 1 つだけです。  
>   
>  このような状況を避けるためには、テスト ポートを参加解除 (**HISTORYINSERT-SP テスト**)、または停止する、アプリケーションのテスト版**BTSScn.BPM.OrderBrokerApp.Test**です。 配信通知の詳細については、次を参照してください。[を使用して受信確認](../core/using-acknowledgments.md)です。  
  
 送信するメッセージを構築するときに、 **OrderManager**オーケストレーション、 **OrderBroker**オーケストレーションは、マルチパート メッセージを 2 つの部分を作成します。 1 つの部分にはルーティング情報、もう一方には注文自体が含まれています。 メッセージのルーティングの部分**OrderMgrMsg.Routing**で c# クラスによって定義されたスキーマを使用して、 **SchemaClasses**アセンブリ。 ブローカーは、順序、ジェネリックでは、メッセージの一部または種類に関係なく、XML ドキュメントを処理 (**System.Xml.XmlDocument**) に割り当てます**OrderMgrMsg.Order**です。  
  
 ルーティング情報、注文マネージャにとって特に重要な 2 つのフィールドがある**OrderMgrMsg.Routing.OrderMgrType**と**OrderMgrMsg.Routing.Status**です。 ブローカーの設定、 **OrderMgrType**は注文を処理する注文マネージャの型にします。 ソリューションには注文マネージャが 1 つだけあり、そのフィールドが CABLEORDER に設定されます。 また、ブローカを設定、**ステータス**フィールドを ACCEPTED にします。 この値は、メッセージが新しい注文であることを注文マネージャに知らせます。 ソリューションでは、注文マネージャ**OrderManager**オーケストレーションを使用して、**受信**CABLEORDER と状態 accepted と同じ注文タイプのフィルター処理する図形です。  
  
 残りの手順を**OrderBroker**オーケストレーションが適切なポートに別のメッセージを送信します。  
  
## <a name="improving-performance-with-nested-scopes"></a>入れ子になったスコープのパフォーマンスの向上  
 について目立つ点の 1 つ、 **OrderBroker**オーケストレーションは、入れ子になったスコープを使用します。 入れ子になったスコープが使用されている理由の 1 つは、永続化ポイントを制限してパフォーマンスを向上させることです。  
  
 オーケストレーション エンジンは、永続化ポイントと呼ばれる実行ポイントでオーケストレーション全体の状態を定期的に保存します。 オーケストレーション エンジンを含め、複数のオーケストレーション図形を自動的に処理する**送信**永続化ポイントとしての図形です。 永続化ポイントとその詳細情報の一覧は、次を参照してください。[永続性と、オーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)です。  
  
 5 つ**送信**、図形、 **OrderBroker**オーケストレーションは、5 つの永続化ポイントを持つ必要があります。 ただし、グループ**送信**アトミック トランザクション スコープ内部の図形、エンジンは、認識のスコープの 1 つの永続性ポイントしか必要があります。 の 4 つの**送信**図形に**OrderBroker**オーケストレーションは、例外ハンドラーの一部ではないと何も行う必要があります、送信後に、アトミック トランザクション スコープに移動することができます。 これによって永続化ポイントの数が減ります。 アトミック トランザクションの詳細については、次を参照してください。[アトミック トランザクション](../core/atomic-transactions.md)です。  
  
 また、トランザクションがすべて同時に終了する場合、入れ子になったトランザクションについて、オーケストレーションが使用する永続化ポイントは 1 つだけです。 方法は、そのため、 **OrderBroker**オーケストレーションがトランザクションを入れ子さらに、永続化ポイントの削減: オーケストレーションが単一の永続化の使用によるポイント**スコープ**図形です。  
  
> [!TIP]
>  オーケストレーションの永続化ポイントの数を最小限にすると、パフォーマンスを向上させることができます。 グループ化できます**送信**単一の永続化を生成するために、アトミック トランザクション内の図形がすべてのポイント、**送信**図形です。 入れ子になったトランザクションのスコープをすべて同時に終了すると、生成されるトランザクションの永続化ポイントは 1 つだけになります。  
  
 アトミック トランザクションのスコープでは例外ハンドラを設定することができません。 このため、オーケストレーションは、長時間実行されるトランザクションの入れ子としてアトミック スコープを配置します。 この外側のトランザクションは、例外ハンドラーを持つことができ、この例外を処理するハンドラーは、**送信**図形です。  
  
> [!TIP]
>  アトミック トランザクションを長時間実行されるトランザクションの入れ子にする方法は、例外処理を可能にする一般的なパターンです。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションでの処理](../core/processing-in-the-business-process-management-solution.md)   
 [プロセス マネージャのロジック](../core/process-manager-logic.md)   
 [ビジネス プロセス管理ソリューションでの処理を中断します。](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)
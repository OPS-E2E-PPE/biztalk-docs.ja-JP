---
title: OrderBroker オーケストレーションの処理 |Microsoft Docs
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
ms.openlocfilehash: d21d91cb8d03adadbd93296f1875efb681b674b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255202"
---
# <a name="processing-in-the-orderbroker-orchestration"></a>OrderBroker オーケストレーションの処理
このセクションについて説明しますが、どのように**OrderBroker**オーケストレーションの注文の受け取りし、戻しプロセス マネージャー用に準備します。 セクションは、オーケストレーションの一般的な機能の説明から始めます。 次の部分では、オーケストレーションがメッセージを処理する方法について説明します。 パフォーマンスを向上させるために、オーケストレーションがアトミックのトランザクションを使用し、強調表示されます。  
  
> [!NOTE]
>  長さの長くなるため、 **OrderBroker**コード、オーケストレーションを Microsoft® Visual Studio で開いてこのセクションを参照する可能性があります。  
  
## <a name="why-an-order-broker"></a>注文のブローカでしょうか。  
 目的、 **OrderBroker**オーケストレーションは、注文を正しいプロセス マネージャにルーティングします。 この前処理は、履歴データベース、サービスのシステムと注文の受信を確認するための情報メッセージの生成で構成されます。 **OrderBroker**カスタマー サービス要求から一般的な注文メッセージも作成されます。 注文のこの正規化を使うと、ビジネス プロセスの要素により、注文の汎用使用します。  
  
 注文メッセージは、マルチパート メッセージ注文情報から区切られた、ルーティング情報です。 ルーティング情報は、汎用的です。 や、どの注文マネージャが使用するように設計します。 これは、さらに、しやすく、ソリューションを展開します。 マルチパート メッセージの詳細については、次を参照してください。[マルチパート メッセージの種類を使用する方法](../core/how-to-use-multi-part-message-types.md)します。  
  
 ブローカ機能を分離では別の BizTalk グループに移動することもできます。 **OrderBroker**をメッセージ ボックス データベースに公開-これは直接バインドがある-も簡単に別のグループに、ブローカーは、オーケストレーションを変更することがなくブローカを移動できます。 配置の詳細については、 **OrderBroker**別のグループで、次を参照してください。 [OrderBroker と OrderManager 間の通信](../core/communication-between-orderbroker-and-ordermanager.md)します。  
  
> [!NOTE]
>  **OrderBroker**オーケストレーション、1 つだけがあるため、 **OrderManager**との通信に割り当てるだけです、定数文字列を**OrderMgrType**順序でフィールドマネージャーのメッセージ。 通常、アプリケーションで複数の注文マネージャが、あるアプリケーションのこのフィールドは注文のルーティングを適切な値を決定するビジネス ルール エンジンで使用されます。 ビジネス ルール エンジンの詳細については、次を参照してください。[を使用してビジネス ルールの作成と](../core/creating-and-using-business-rules.md)します。  
  
## <a name="order-processing"></a>注文処理  
 **OrderBroker**オーケストレーションは、最初の 2 つ**受信**内の図形は、**リッスン**図形。 1 つ**受信**図形はカスタマー サポート システムからのメッセージは、ベンダ システムから、他のメッセージ。 いずれかのソースからのメッセージは、同一のスキーマを指定します。  
  
 オーケストレーションがメッセージから戻り値のアドレスを抽出し、動的ポートのアドレスを設定するため**CSRPort**します。 オーケストレーションは、受信確認とエラー メッセージを送信するのに、このポートを使用します。  
  
 次のステップで、 **OrderBroker**履歴メッセージ、サービス メッセージ、確認のメッセージ、および注文メッセージを送信するオーケストレーションが作成、 **OrderManager**オーケストレーションします。 オーケストレーションを使用して、 **InsertOrderBody**履歴メッセージに、注文メッセージを追加するユーティリティ関数。  
  
> [!NOTE]
>  状況によっては、ソリューションにメッセージを配信されても消費されないことがあります。 注文ブローカのオーケストレーションでは、送信ポートを使用して、履歴データベースに情報を挿入します。 この送信ポートは、配信通知を使用します。 構成、送信ポートを 2 つのポートを含む送信ポート グループにマップされます: テスト構成の 1 つのポート (**HISTORYINSERT-SP テスト**)、通常の構成のいずれか (**HISTORYINSERT-SP**)。 実行しているグループの両方のポートの場合、ソリューションは、両方のポートでメッセージを送信します。 したがって、2 つの配信通知を要求する、1 つのみを処理します。  
>   
>  このような状況を避けるためには、テスト ポートを参加解除 (**HISTORYINSERT-SP テスト**)、または停止する、アプリケーションのテスト版**BTSScn.BPM.OrderBrokerApp.Test**します。 配信通知の詳細については、次を参照してください。[を使用して受信確認](../core/using-acknowledgments.md)します。  
  
 送信するメッセージを構築するときに、 **OrderManager**オーケストレーション、 **OrderBroker**オーケストレーションは、2 つの部分でマルチパート メッセージを作成します。 1 つの部分には、ルーティング情報; が含まれています。その他、注文自体。 メッセージのルーティングの部分**OrderMgrMsg.Routing**、によって定義されるスキーマを使用して、C#クラス、 **SchemaClasses**アセンブリ。 ブローカーの処理順序として、ジェネリックでは、メッセージの一部または種類に関係なく、XML ドキュメント (**System.Xml.XmlDocument**) に割り当てます**OrderMgrMsg.Order**します。  
  
 ルーティング情報、注文マネージャに特に重要な 2 つのフィールドがある**OrderMgrMsg.Routing.OrderMgrType**と**OrderMgrMsg.Routing.Status**します。 ブローカー セット、 **OrderMgrType**注文を処理する注文マネージャの型にします。 ソリューションでは、1 つだけ注文マネージャがあるし、フィールドが CABLEORDER に設定されます。 また、ブローカーを設定、**状態**フィールドを ACCEPTED にします。 これは、メッセージが新しい注文を注文マネージャに指示する値です。 ソリューションでは、注文マネージャ**OrderManager**オーケストレーションを使用して、**受信**CABLEORDER と ACCEPTED と同じ状態に等しい順序の種類をフィルター処理する図形。  
  
 残りのステップは、 **OrderBroker**オーケストレーションが適切なポートに別のメッセージを送信します。  
  
## <a name="improving-performance-with-nested-scopes"></a>入れ子になったスコープによるパフォーマンスの向上  
 について注目すべき点の 1 つ、 **OrderBroker**オーケストレーションは、入れ子になったスコープを使用します。 入れ子になったスコープは、一部を永続化ポイントを制限することでパフォーマンスを向上させるです。  
  
 オーケストレーション エンジンは、永続化ポイントと呼ばれる実行ポイントでオーケストレーション全体の状態を定期的に保存します。 オーケストレーション エンジンなど、いくつかのオーケストレーション図形を自動的に処理する**送信**永続化ポイントとしての図形。 永続化ポイントとその詳細情報の一覧は、次を参照してください。[永続性とオーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)します。  
  
 5 つ**送信**、図形、 **OrderBroker**オーケストレーションは 5 つの永続化ポイントである必要があります。 ただし、グループ**送信**アトミック トランザクション スコープ内部の図形、エンジンが認識スコープの永続化ポイントを 1 つだけ必要があります。 の 4 つの**送信**図形に**OrderBroker**オーケストレーションは、例外ハンドラーの一部ではないと何も行う必要がある、送信後に、アトミック トランザクションのスコープ内に出ることができます。 これは、永続化ポイントの数を減らします。 アトミック トランザクションの詳細については、次を参照してください。[アトミック トランザクション](../core/atomic-transactions.md)です。  
  
 さらに、オーケストレーション エンジンは使用、1 つの永続性ポイント入れ子になったトランザクションの場合、すべてのトランザクションが同時に終了します。 そのため、方法は、 **OrderBroker**さらにトランザクションを入れ子オーケストレーションは、永続化ポイントを削減: オーケストレーションが 1 つの永続化ポイントを使用するため**スコープ**図形。  
  
> [!TIP]
>  オーケストレーションの永続化ポイントの数を最小限に抑えることでパフォーマンスを向上できます。 グループ化できます**送信**のすべてのポイントの 1 つの永続化を生成するために、アトミック トランザクション内の図形、**送信**図形。 入れ子になったトランザクションを終了のスコープで生成されるが同じトランザクションの 1 つの永続性ポイント。  
  
 アトミック トランザクション スコープは、例外ハンドラーを持つことはできません。 このため、オーケストレーションは、実行時間の長いトランザクション内でアトミックのスコープをネストします。 この外側のトランザクションは、例外ハンドラーを持つことができ、この例外を処理するハンドラーが、**送信**図形。  
  
> [!TIP]
>  実行時間の長いトランザクション内でアトミック トランザクションの入れ子は、例外処理のために一般的なパターンです。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションでの処理](../core/processing-in-the-business-process-management-solution.md)   
 [プロセス マネージャのロジック](../core/process-manager-logic.md)   
 [ビジネス プロセス管理ソリューションでの処理を中断します。](../core/interrupt-handling-in-the-business-process-management-solution.md)   
 [ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)
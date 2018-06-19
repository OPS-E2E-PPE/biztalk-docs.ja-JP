---
title: トランザクション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, transactions
- Orchestration Designer, BizTalk Server Orchestration Engine
- BizTalk Server Orchestration Engine
- Orchestration Designer, transactions
ms.assetid: d9a748c7-be9f-4965-a30f-6b05bd6b42a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74827beade56e6e54414371c9796454d3b48609e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279186"
---
# <a name="transactions"></a>トランザクション
BizTalk Server オーケストレーション エンジンは、状態を管理し、ビジネス ロジックを適用し、複雑な処理やトランザクション セットの実行をサポートするアプリケーションを呼び出します。  
  
 ビジネス プロセスは、アトミック トランザクションを使用した個々の作業として構成することが可能で、エラーや長時間実行されるトランザクションが発生した場合は、自動的にすべての変更をロールバックします。ネストされたトランザクションを含めたり、エラーから回復するためにカスタム例外処理を使用することも可能です。 このようなトランザクション セマンティクスは通常、オーケストレーション デザイナーの Scope コンストラクターを使用して管理します。  
  
 長時間プロセスは、完了するまでに数日から数週間以上かかる場合があります。 長時間プロセスは、通常、送信されるメッセージを受信したメッセージを関連付けるために相関関係を使用します。 オーケストレーション エンジンは通常、このようなインスタンスを退避してシステム リソースを保持し、関連付けられたメッセージを受け取るとプロセスを回復させます。 オーケストレーション エンジンは、一定のチェックポイントでオーケストレーションの状態をメッセージ ボックス データベースに格納し、アプリケーション例外またはシステム例外からの復旧に使用します。  
  
 BizTalk オーケストレーション エンジンに提供されているトランザクション プログラミング モデルでは、例外処理や失敗したトランザクションからの復旧のほか、エラーや長時間実行されるトランザクションが発生した場合に自動的に作業内容をロールバックするアトミック トランザクションをサポートしています。これには、カスタム例外処理に加え、他のトランザクションを含めることも可能です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アトミック トランザクション](../core/atomic-transactions.md)  
  
-   [アトミック トランザクションの使用シナリオ](../core/scenarios-using-atomic-transactions.md)  
  
-   [実行時間の長いトランザクション](../core/long-running-transactions.md)  
  
-   [実行時間の長いトランザクションの使用シナリオ](../core/scenarios-using-long-running-transactions.md)  
  
-   [オーケストレーションの永続性](../core/persistence-in-orchestrations.md)
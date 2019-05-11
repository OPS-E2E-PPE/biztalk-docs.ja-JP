---
title: トランザクション |Microsoft Docs
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
ms.openlocfilehash: 376d27c4d0371a207cae974c8a9f74da0cd36e9d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399203"
---
# <a name="transactions"></a>トランザクション
BizTalk Server オーケストレーション エンジンは、状態を管理、ビジネス ロジックを適用し、複雑なプロセスやトランザクション セットのサポートのアプリケーションを呼び出します。  
  
 ビジネス プロセスは、個別の作業のエラーが発生した場合、すべての変更を自動的にロールバックするアトミックのトランザクションの使用または実行時間が長いと、入れ子になったトランザクションを含めることができ、カスタム例外処理を使用して、エラーから復旧しているとして構成することができます。シナリオ。 このようなトランザクション セマンティクスが管理には通常、オーケストレーション デザイナーの Scope コンス トラクターを使用します。  
  
 実行時間の長いプロセスは、日、週、およびより長い期間にまたがることができます。 実行時間の長いプロセスは、通常、送信されるメッセージを受信したメッセージを関連付ける相関関係を利用します。 通常、オーケストレーション エンジンはシステム リソースを節約するためにこれらのインスタンスを退避し、これらの関連付けられたメッセージの受信時にプロセスを再入力します。 オーケストレーション エンジンは、任意のアプリケーションまたはシステム例外から回復する既知のチェックポイントでメッセージ ボックス データベースにオーケストレーションの状態を保持します。  
  
 BizTalk オーケストレーション エンジンには、例外処理、および失敗したトランザクションからの復旧のサポートが含まれています指定されたトランザクション プログラミング モデル、アトミック トランザクションを自動的にロールバック アクション、エラーが発生した、または。その他のトランザクションとカスタム例外処理に含めることができる実行時間の長いトランザクション。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [自動トランザクション](../core/atomic-transactions.md)  
  
-   [アトミック トランザクションの使用シナリオ](../core/scenarios-using-atomic-transactions.md)  
  
-   [長時間トランザクション](../core/long-running-transactions.md)  
  
-   [長時間トランザクションの使用シナリオ](../core/scenarios-using-long-running-transactions.md)  
  
-   [オーケストレーションでの永続化](../core/persistence-in-orchestrations.md)
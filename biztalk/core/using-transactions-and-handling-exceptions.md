---
title: トランザクションを使用して、例外の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions, orchestrations
- orchestrations, transactions
- orchestrations, errors
- transactions
- errors, orchestrations
- transactions, BizTalk Server Orchestration Engine
- errors, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], errors
- Scope shape [Orchestration Designer], transactions
ms.assetid: bb38f5eb-6641-4e7c-8e2a-c474fc739999
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eac1ae71e9ff176156691fbb30a79c9d423b58da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396749"
---
# <a name="using-transactions-and-handling-exceptions"></a>トランザクションを使用して、例外の処理
オーケストレーションを設計するときは慎重に考慮する問題が発生する可能性とそれらに対処する最適な方法です。 多くのオーケストレーションでは、いくつかの潜在的な障害点があります。 問題は、任意の数の他の理由が発生します。たとえば、サーバー ダウンまたはメッセージの形式が正しくありません。  
  
 これは、方法は、正確かつ最小限の労力で、問題を解決できるように、発生したエラーを報告して、状態の追跡を維持する時間の長い実行または複雑なオーケストレーションの特に重要です。 考えたものとしてバックアップ、トランザクションの一部が行われる別されない場合は、トランザクション全体をロールバックできるように、密接に関連する操作の一連の整合性を維持するためのオーケストレーションにも同様に重要です。  
  
 BizTalk オーケストレーションでは、作業の原子性を保証することができます、つまり、関連するアクションの整合性も外部システムに参加しているトランザクションです。 トランザクション、補正、および例外処理を通じて発生する問題を解決して、オーケストレーションの状態を維持するために、エラーを処理する手段を提供します。  
  
 オーケストレーション デザイナーには、トランザクションと例外処理のフレームワークとして、**スコープ**図形。 スコープには、トランザクションの種類、補正、および任意の数の例外ハンドラーを設定できます。  
  
 トランザクションと例外処理を設定するための手順は次のとおりです。  
  
-   スコープを作成します。  
  
-   必要なトランザクションの種類を識別します。  
  
-   補正する必要がありますを決定します。  
  
-   潜在的なエラーを特定します。  
  
-   適切な例外ハンドラーと補正コードを追加します。  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a>トランザクション、例外処理および補正の使用例  
  
-   [エラー処理 (BizTalk Server サンプル フォルダー)](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [補正 (BizTalk Server サンプル)](../core/compensation-biztalk-server-sample.md)  
  
-   SDK サンプル「オーケストレーション アトミック トランザクションと COM + サービス コンポーネントで」からダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
-   「を使用して、SQL アダプターとアトミック トランザクション オーケストレーションでの」SDK サンプルからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
-   SDK サンプル「オーケストレーションでの実行時間の長いトランザクションの使用」をからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
-   SDK サンプル「オーケストレーションで例外を処理」をからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [スコープ](../core/scopes.md)  
  
-   [スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)  
  
-   [オーケストレーションのトランザクション化](../core/making-orchestrations-transactional.md)  
  
-   [例外](../core/exceptions.md)  
  
-   [補正](../core/compensation.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk メッセージング エンジンを使用します。](../core/using-the-biztalk-messaging-engine.md)
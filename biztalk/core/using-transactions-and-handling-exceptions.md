---
title: トランザクションを使用して、例外の処理 |Microsoft ドキュメント
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
ms.openlocfilehash: ab32729aa6b4f12aada623587f52728c6bd23240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288434"
---
# <a name="using-transactions-and-handling-exceptions"></a>トランザクションを使用して、例外の処理
オーケストレーションのデザイン時には、問題が発生する可能性のある場所とその最善の対処方法について十分に考慮する必要があります。 オーケストレーションの多くは、エラーが発生する可能性のあるいくつかの処理を抱えています。 問題が発生する理由は他にも考えられます。たとえば、サーバーのダウンやメッセージ形式の誤りなどです。  
  
 長時間実行または複雑なオーケストレーションでは、状態を追跡してエラー発生時に報告し、問題を的確に、最小限の労力で解決できるようにすることが特に重要です。 これは、方法と考えたようバックアップ全体のトランザクションをロールバックできます行われるトランザクションの一部別されない場合は、できるように、密接に関連するアクションのセットの整合性を維持するためのオーケストレーションの同様に重要です。  
  
 BizTalk オーケストレーションでは、トランザクションに外部システムがかかわっている場合でも、作業の原子性 (関連するアクションの整合性) が確保されます。 エラーを処理し、オーケストレーションの状態を維持し、トランザクション、補正、および例外処理を通じて発生する問題を修正する手段を提供します。  
  
 オーケストレーション デザイナーにはトランザクションと例外処理のフレームワーク、として、**スコープ**図形です。 スコープには、トランザクションの種類、補正、および任意の数の例外ハンドラーを設定できます。  
  
 トランザクションと例外処理を設定する手順を次に示します。  
  
-   スコープを作成します。  
  
-   必要なトランザクションの種類を特定します。  
  
-   補正する必要のあるものを決定します。  
  
-   発生する可能性のあるエラーを特定します。  
  
-   適切な例外ハンドラーと補正コードを追加します。  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a>トランザクションの使用、例外処理および補正の例  
  
-   [エラー処理 (BizTalk Server Samples フォルダ)](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [補正 (BizTalk Server サンプル)](../core/compensation-biztalk-server-sample.md)  
  
-   サンプルをダウンロードする SDK「オーケストレーション アトミック トランザクションと COM + サービス コンポーネントで」から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。  
  
-   サンプルをダウンロードする SDK「を使用して、アダプターとアトミック トランザクション オーケストレーションでの SQL」から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。  
  
-   サンプルをダウンロードする SDK「オーケストレーションでの実行時間の長いトランザクションの使用」から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。  
  
-   SDK サンプル「オーケストレーションで例外を処理」をダウンロード[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [スコープ](../core/scopes.md)  
  
-   [スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)  
  
-   [トランザクション オーケストレーションを行う](../core/making-orchestrations-transactional.md)  
  
-   [例外](../core/exceptions.md)  
  
-   [補正](../core/compensation.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk メッセージング エンジンを使用します。](../core/using-the-biztalk-messaging-engine.md)
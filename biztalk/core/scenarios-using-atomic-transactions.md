---
title: アトミック トランザクションの使用シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], examples
- Scope shape [Orchestration Designer], atomic transactions
- transactions, examples
- transactions, atomic
- atomic transactions, examples
- examples, atomic transactions
ms.assetid: f3481b4e-7e7e-47f0-b8f4-6012a2fc5310
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d959fdb9135a804346a869811072f826906b5876
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308165"
---
# <a name="scenarios-using-atomic-transactions"></a>アトミック トランザクションの使用シナリオ
次のシナリオでは、アトミック トランザクションの使用方法について説明します。  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a>シナリオ 1:アトミックのトランザクションと COM + ServicedComponent  
 次のオーケストレーションを使用する方法を示しています、 **RetryTransactionException**とアトミック トランザクション。 例外ハンドラーが直接にすることはできませんが、アトミックのスコープに含まれる、スコープは、例外ハンドラーを持つことができますを非トランザクション スコープを含めることができます。 **ServicedComponent**は同じ DTC トランザクションに参加し、コンポーネントによって発生する例外がキャッチされ、再度としてスロー **RetryTransactionException**します。 (が、**再試行**プロパティに設定されて**True**アトミックのスコープに対して)。  
  
 オーケストレーション中断されたとメッセージの割り当て図形の操作がロールバックされる場合でも、 **RetryTransactionException**はスローされません。 このパターンでは、ただし、により、アプリケーションの回復性を高める、再試行が自動的に発生します。  
  
 **アトミックのトランザクションと COM + ServicedComponent**  
  
 ![アトミック トランザクションと COM&#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a>シナリオ 2: アトミック トランザクションのトランザクション アダプターを使用します。  
 次のオーケストレーションは、SQL アダプターとアトミック トランザクションを使用する方法を示します。 オーケストレーション全体は、2 つの論理部分の作業の個々 のアトミック トランザクションの実行時間が長いでマークされます。顧客の新しい顧客と注文の挿入の詳細を挿入しています。  
  
 何らかの理由で注文の挿入が失敗する場合は、顧客の挿入ロールバックするか。 サンプルでは、データベースの作業を行う SQL アダプタを使用します。 前述のように、メッセージ ボックス データベースにメッセージが送信されるときに、アトミック トランザクションに関連付けられたスコープを完了します。 つまり、エンジンが Scope_InsertCustomer および Scope_InsertOrder スコープでメッセージの送信に成功した後は、各スコープのコミットすることです。 SQL アダプターは、顧客または注文の実際の挿入に対して新しいトランザクションを作成します。  
  
 ポートでは、メッセージが送信ポートから正常に送信された検証するためプロパティ「配信通知」があります。 配信通知プロパティが「送信済み」に設定されている場合、受信サブスクリプションは、送信操作のトランザクション コミット ポイントの前に配置されます。 ただし、アトミックのスコープの場合は、受信サブスクリプションは、外側の親スコープに配置されます。  
  
 InsertOrder SQL トランザクションが失敗するシナリオでは、戻る ボタンと"Scope_InsertOrder"コミット"Nack"が送信されます。 送信ポートが構成されている再試行では、後に、DeliveryFailureException が生成されます。 この例外は、既定の補正プロセスが実行される既定の例外ハンドラーによってキャッチされます。 これにより、Scope_InsertCustomer および Scope_InsertOrder、顧客情報の挿入元に戻す操作の原因に関連付けられている補正ハンドラーが呼び出されます。  
  
> [!NOTE]
>  長時間スコープ内の 2 つのスコープの入れ子と長時間スコープの例外ハンドラーから補正図形 (実行時間の長いトランザクションを対象とする) を呼び出すことが前述のように同じ動作に発生します。 オーケストレーション全体でしたいないアトミックとしてマークするアトミック トランザクションは、入れ子になったトランザクションを許可しません。  
  
 **トランザクション アダプターとアトミック トランザクション**  
  
 ![アダプターとアトミック トランザクションをトランザクション](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")
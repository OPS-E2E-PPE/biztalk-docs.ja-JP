---
title: アトミック トランザクションの使用シナリオ |Microsoft ドキュメント
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
ms.openlocfilehash: e73cfea7a99e2fafbf115a367dbf0840de3369c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270946"
---
# <a name="scenarios-using-atomic-transactions"></a>アトミック トランザクションの使用シナリオ
次のシナリオでは、アトミック トランザクションの使用方法について説明します。  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a>シナリオ 1: アトミック トランザクションと COM + ServicedComponent  
 次のオーケストレーションを使用する方法を示しています、 **RetryTransactionException**とアトミック トランザクションです。 例外ハンドラーはアトミックのスコープに直接含めることはできませんが、例外ハンドラーを持つ非トランザクション スコープはアトミックのスコープに含めることができます。 **ServicedComponent**は同じ DTC トランザクションに参加し、コンポーネントによって発生する例外がキャッチされ、として再スロー **RetryTransactionException**です。 (を想定しています、**再試行**プロパティに設定されている**True**アトミックのスコープに対して)。  
  
 オーケストレーションは中断し、メッセージの割り当て図形の操作がロールバックされることを確認場合でも、 **RetryTransactionException**はスローされません。 ただし、このパターンは、再試行が自動的に行われるアプリケーションでは回復性を高めることができます。  
  
 **アトミックのトランザクションと COM + ServicedComponent**  
  
 ![アトミック トランザクションと COM & #43 です。ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a>シナリオ 2: とアトミック トランザクションのトランザクション アダプターの使用  
 次のオーケストレーションでは、SQL アダプターをアトミック トランザクションと共に使用する方法について説明します。 オーケストレーション全体は、新しい顧客の挿入とその顧客の注文明細の挿入という 2 つの論理的な作業に対応する個別のアトミック トランザクションを含む長時間のオーケストレーションとしてマークされています。  
  
 注文の挿入が失敗した場合は、理由にかかわらず、顧客の挿入をロールバックする必要があります。 この例では、データベース操作を行う SQL アダプターを使用します。 前述したように、アトミック トランザクションに関連付けられたスコープは、メッセージがメッセージ ボックス データベースに送信された時点で完了します。 これは、エンジンが Scope_InsertCustomer スコープと Scope_InsertOrder スコープのメッセージを正常に送信した後で、各スコープがコミットすることを意味しています。 SQL アダプターは、顧客または注文の実際の挿入に対して新しいトランザクションを作成します。  
  
 ポートには、メッセージが送信ポートから正常に送信されたことを確認するための “配信通知” プロパティがあります。 “配信通知” プロパティが “送信済み” に設定されている場合、受信サブスクリプションは送信操作のトランザクション コミット ポイントの前に配置されます。 ただし、アトミック スコープの場合、受信サブスクリプションはそれを含んでいる親スコープ内に配置されます。  
  
 InsertOrder SQL トランザクションが失敗するシナリオでは、"NACK" が返信され、"Scope_InsertOrder" はコミットします。 送信ポートが構成された回数の再試行を終えると、DeliveryFailureException が発生します。 この例外は既定の例外ハンドラーによってキャッチされ、既定の補正プロセスが実行されます。 これにより、Scope_InsertCustomer および Scope_InsertOrder に関連付けられた補正ハンドラーが呼び出され、顧客情報の挿入を元に戻す操作が行われます。  
  
> [!NOTE]
>  長時間スコープ内に 2 つのスコープを入れ子にし、長時間スコープの例外ハンドラーから長時間トランザクションをターゲットとする補正図形を呼び出すと、前述したものと同じ動作が行われます。 アトミック トランザクションでは入れ子になったトランザクションを許可していないため、オーケストレーション全体をアトミックとしてマークすることはできません。  
  
 **トランザクション アダプターとアトミック トランザクション**  
  
 ![アダプターとアトミック トランザクションをトランザクション](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")
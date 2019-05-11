---
title: 実行時間の長いトランザクションの使用シナリオ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions, long-running
- long-running transactions, timeouts
- transactions, examples
- long-running transactions, examples
- long-running compensations
- examples, long-running transactions
- examples, custom compensations
ms.assetid: 76b3e0f8-44dc-419e-a73a-c2908b1d8795
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91f0dccf2429452f8133edbb9069de3f283e4313
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308053"
---
# <a name="scenarios-using-long-running-transactions"></a>長時間トランザクションの使用シナリオ
次のシナリオでは、長時間トランザクションの使用方法について説明します。  
  
## <a name="scenario-1-using-long-running-transactions-with-timeouts"></a>シナリオ 1:長時間トランザクションとタイムアウトを使用してください。  
 長時間スコープはタイムアウトに関連付けることができます。タイムアウトは、長時間実行される作業の実行時間の上限を表す論理時間です。 スコープが、定義済みのシステム例外、指定した時間内に完了しない場合**TimeoutException**が発生します。  
  
 長時間プロセスは、オーケストレーション全体を長時間トランザクションとしてマークするか、外側の長時間スコープ内に他のスコープをネストすることによって作成できます。 前者のシナリオではシステムに用意されている例外ハンドラーが実行され、後者のシナリオでは特定の例外ハンドラーを外側のスコープに関連付けることが可能になります。 システムに用意されている既定の例外ハンドラーは、ネストされたトランザクション スコープのうち正常に完了したスコープごとに、完了の順番とは逆の順番で補正ハンドラーを実行します。 長時間トランザクションの例外ハンドラーで補正図形を使用して自己補正を行った場合も、同じ結果が得られます。  
  
 次のオーケストレーションは、タイムアウトを長時間トランザクションと関連付ける方法を表しています。  
  
 **実行時間の長いトランザクションとタイムアウト**  
  
 ![長時間トランザクションとタイムアウト](../core/media/bts-trans-orch-fig7.gif "BTS_Trans_Orch_Fig7")  
  
 場合によっては、バッチ方式で動作するレガシ システムとの連携が必要になることがあります。 このシナリオでは、レガシ システムとの間で注文書が送受信されています。 レガシ システムは注文書を処理し、注文書の受信確認を返します。 送信操作では注文書番号によって関連付けセットが初期化され、その関連付けセットに従って受信操作が行われます。 受信操作も、タイムアウト値が設定された長時間スコープ内にあります。  
  
 受信を待機しているオーケストレーション インスタンスは、オーケストレーション エンジンによって退避されます。 関連付けにより、メッセージの受信後に必ず同じオーケストレーション インスタンスが呼び出されるようになっています。 タイムアウト値で指定された時間間隔内では、購買注文の受信確認が配信されない場合、 **TimeoutException**がスローされます。  
  
## <a name="scenario-2-using-long-running-transactions-with-custom-compensation"></a>シナリオ 2: 長時間トランザクションとカスタム補正を使用してください。  
 次のオーケストレーションは、オーケストレーション全体に関連付けられているカスタム補正の関連付けと呼び出しの方法を示しています。 このシナリオでは、新しい顧客が挿入され、その顧客の注文明細が挿入されます。 オーケストレーションのロジックによると、注文の挿入が失敗した場合は顧客の挿入をロールバックする必要があります。 顧客の挿入はレガシ システムで行われる可能性があるため、別個の呼び出し可能なオーケストレーションで示されています。 呼び出されたオーケストレーションが、**カスタム**補正処理を行う別のシートを提供する補正のプロパティの設定。 補正を実行すると、新しく挿入した顧客が削除されます。  
  
 呼び出し元オーケストレーションには、注文の挿入を行うための長時間スコープがあります。 このスコープは、外側の長時間スコープ内にネストされています。 外側のスコープには、例外をキャッチする例外ハンドラーが関連付けられています。 このハンドラーは、呼び出し先オーケストレーションに関連付けられているカスタム例外を補正図形で呼び出し、そのオーケストレーションの呼び出しで発生した可能性のある変更をすべてロールバックします。  
  
 **実行時間の長いトランザクションとカスタム補正**  
  
 ![長時間トランザクションとカスタム補正](../core/media/bts-trans-orch-fig8.gif "BTS_Trans_Orch_Fig8")  
  
 **呼び出し先オーケストレーション (メイン)**  
  
 ![呼び出されたオーケストレーション (&) #40 です。 メイン (&) #41;](../core/media/bts-trans-orch-fig9.gif "BTS_Trans_Orch_Fig9")  
  
 **呼び出し先オーケストレーション (補正)**  
  
 ![呼び出し先オーケストレーション (&) #40 です。 補正 (&) #41;](../core/media/bts-trans-orch-fig10.gif "BTS_Trans_Orch_Fig10")
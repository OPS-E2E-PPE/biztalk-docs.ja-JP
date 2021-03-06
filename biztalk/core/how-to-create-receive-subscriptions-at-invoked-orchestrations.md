---
title: 作成する方法について呼び出されたオーケストレーションに受信サブスクリプション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3423309a-cb5a-40a5-9582-6ee3ac82b538
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4c1e32e6d14673ba0a06a45e08d25c531824e1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385475"
---
# <a name="how-to-create-receive-subscriptions-at-invoked-orchestrations"></a>作成する方法について呼び出されたオーケストレーションに受信サブスクリプション
メッセージをパラメーターとして渡すことができますが、**オーケストレーションの開始**図形の後に呼び出されたオーケストレーションに呼び出し元オーケストレーションからメッセージを送信する一部のシナリオで、オーケストレーションを開始すると、呼び出し。 たとえば、呼び出し時に渡すメッセージご存知ないかもしれませんまたは他のオーケストレーションが呼び出されたオーケストレーションにメッセージを動的に送信する必要があります。  
  
 呼び出されたオーケストレーションにメッセージを送信する方法では、呼び出されたオーケストレーションは、相関関係により、定義し、そのサブスクリプションを使用して、メッセージを受信するサブスクリプションを作成できるように、相関関係に渡します。 ただし、ことはできませんだけを渡して、関連付けと呼び出し先オーケストレーションの相関関係に基づいてサブスクリプションを作成するし、サブスクリプションでメッセージを受信します。 アプローチを使用する場合、エラーは、「、パブリッシュされたメッセージがルーティングでしたサブスクライバーが見つからなかったためです」呼び出し元オーケストレーションから呼び出されたオーケストレーションに送信するメッセージが発生します。 これは、次の理由によりします。  
  
- 呼び出されたオーケストレーションに競合状態があります。  
  
- 呼び出されたオーケストレーションのルーティング、メッセージを受信できるように、メッセージ ボックス データベースにサブスクリプションを送信するためのコミット ポイントはありません。  
  
  この問題を解決する方法、次の手順を実行することです。  
  
1. 呼び出し元オーケストレーションでは、アクティブ化メッセージを受信する受信があります。 経由の直接バインド ポートを受信する、自己関連付けと呼び出し先オーケストレーションでメッセージが表示される、関連付けセットを初期化、および関連付けセットを渡して、**オーケストレーションの開始**図形。 渡されたポートが呼び出されたオーケストレーションの送信ポートとメッセージの送信に使用するが、呼び出し元オーケストレーションと同期します。  
  
2. 呼び出されたオーケストレーションでは、自己関連付けポートを通じて、呼び出し元オーケストレーションにメッセージを送信します。 これは、競合状態を防ぐために、呼び出されたオーケストレーションでのルーティング用のメッセージ ボックスへの受信サブスクリプションを作成するときにコミット ポイントを提供して、呼び出し元オーケストレーションと同期されます。  
  
3. 呼び出し元オーケストレーションは、自己関連付けポートを通じてメッセージを受信し、呼び出されたオーケストレーションと同期します。 自己関連付けポートの受信には、フォロー関連付けには必要ありません。 これで安全にメッセージを送信できます、呼び出し元オーケストレーションから呼び出されたオーケストレーションに、呼び出されたオーケストレーションは、関連付けに基づいてメッセージを受信する.  
  
   前の方法では、目標を実現することも、ほうが効果的に渡すメッセージを受信する相関関係を初期化します。 自己関連付けポートを通じて呼び出されたオーケストレーションと呼び出し先オーケストレーションを同期するときに、関連付けの初期化に必要なメッセージで常に渡すことをお勧めします。 次の手順では、信頼性とパフォーマンスが最も高いアプローチを提供します。  
  
4. 呼び出し元オーケストレーションでは、アクティブ化メッセージを受信する受信があります。 メッセージを渡すし、を介して直接バインド ポートを受信する、自己関連付けメッセージが表示されたら、**オーケストレーションの開始**図形。 渡すメッセージが呼び出されたオーケストレーションで関連付けを初期化するために使用されます。 渡されたポートが呼び出されたオーケストレーションの送信ポートとメッセージの送信に使用するが、呼び出し元オーケストレーションと同期します。  
  
5. 呼び出されたオーケストレーションでは、相関関係を初期化し、呼び出し元オーケストレーションにメッセージを送信します。 これは、競合状態を防ぐために、呼び出されたオーケストレーションでのルーティング用のメッセージ ボックスへの受信サブスクリプションを作成するときにコミット ポイントを提供して、呼び出し元オーケストレーションと同期されます。  
  
6. 呼び出し元オーケストレーションは、自己関連付けポートを通じてメッセージを受信し、呼び出されたオーケストレーションと同期します。 注、自己関連付けポートを受信するには、フォロー関連付けは必要ありません。 これで安全にメッセージを送信できます、呼び出し元オーケストレーションから呼び出されたオーケストレーションに、呼び出されたオーケストレーションは、関連付けに基づいてメッセージを受信する.  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでの相関関係の使用](../core/using-correlations-in-orchestrations.md)   
 [自己関連付けを行う Direct を使用する方法のポートのバインド](../core/how-to-use-self-correlating-direct-bound-ports.md)
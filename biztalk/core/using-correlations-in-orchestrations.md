---
title: オーケストレーションでの相関関係の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, orchestrations
- messages, correlation sets
- correlation sets
- orchestrations, messages
- messages, validating
ms.assetid: d919afa9-bada-406a-bf4b-7b46c831c6d5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b16c54f4c49a1a81ea412c5b980ba23e60e8290
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401624"
---
# <a name="using-correlations-in-orchestrations"></a>オーケストレーションでの関連付けの使用
関連付けは、受信メッセージをオーケストレーションの適切なインスタンスに一致させるプロセスです。 たとえば、オーケストレーションからメッセージを送信して応答を受信したり、同じオーケストレーションに応答を返信します。 以下の 3 つの関連付けメッセージ交換パターンがあります。  
  
- 従来のハンドシェイク  
  
- シーケンシャルなコンボイ  
  
- パラレルなコンボイ  
  
  従来のハンドシェイク パターンの場合、ハンドシェイクはオーケストレーションまたはビジネス プロセス間でのメッセージの交換の間に存在します。ハンドシェイクを実現するには、オーケストレーションで関連付けセットを定義します。このオーケストレーションでは、関連付けセットが、特定のオーケストレーション インスタンスへメッセージをルーティングするために使用する特定の値の昇格させたプロパティの一覧になります。  
  
  たとえば、オーケストレーションが注文書の発行、請求書の受信、および支払いの送金を目的としている場合は、その時点で多くの注文書が処理される可能性があるため、対応する注文書の送信元と同じオーケストレーションが請求書メッセージを受信するようにする必要があります。 この例では、注文書の識別番号を関連付けセットでパラメーターとして使用して、注文書メッセージと請求書メッセージを関連付けることができます。 次のシナリオは、この例のフローを示しています。  
  
1. オーケストレーション A は、注文書メッセージをオーケストレーション B に送信します。注文書メッセージを送信する前に、関連付けセットが初期化されます。  
  
2. 注文書を処理し、請求書を生成して返信するオーケストレーション B では、最初の受信図形が同じ関連付けセットに従って注文書メッセージを受信します。  
  
3. 注文書メッセージの処理後に、請求書メッセージをオーケストレーション A に返信するときにも、同じ関連付けセットに従います。  
  
4. オーケストレーション A で、オーケストレーション B から返信された請求書メッセージを受信する受信図形でも同じ関連付けセットに従って、関連付けられた請求書メッセージを定義済みの関連付けセットに基づいて受け取れるようにします。  
  
   シーケンシャルなコンボイ パターンとパラレル コンボイ パターンは、個々の項目が単独では実現できない処理を可能にするために複数の単一項目を関連付ける必要がある状況に存在します。 詳細については、次を参照してください。[コンボイ シナリオの](../core/working-with-convoy-scenarios.md)します。  
  
   関連付けられたメッセージ交換パターンに加えて、オーケストレーションには、次の 2 種類の関連付けが存在します。  
  
- 手動の関連付け  
  
- 自動の関連付け  
  
  手動の関連付けシナリオでは、オーケストレーションを手動で構成して関連付けセットを初期化し、その関連付けセットに従ってメッセージを適切なインスタンスに関連付けます。 自動の関連付けシナリオでは、オーケストレーションで要求 - 応答ポートや自己関連付けを行うポートを設定する場合などに、メッセージング エンジンがメッセージをインスタンスに自動的に関連付けます。  
  
  アクティブ化受信ポート、要求 - 応答ポート、自己関連付けを行うポートなど、オーケストレーションにメッセージをインスタンスに関連付ける明示的な方法がない場合は常に関連付けを使用する必要があります。  
  
## <a name="examples-of-using-correlations"></a>関連付けの使用例  
  
-   [PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)  
  
-   「関連付けメッセージとオーケストレーション インスタンスの」SDK サンプルからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
-   SDK サンプル「パラレルなコンボイ」のダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [関連付けセット](../core/correlation-sets.md) 
  
-   [関連付けの種類](../core/correlation-types.md) 
  
-   [追加および関連付けセットを削除する方法](../core/how-to-add-and-remove-correlation-sets.md) 
  
-   [関連付けセットを構成する方法](../core/how-to-configure-correlation-sets.md)  
  
-   [関連付けの種類を構成する方法](../core/how-to-configure-correlation-types.md)  
  
-   [コンボイ シナリオの活用](../core/working-with-convoy-scenarios.md)  
  
## <a name="see-also"></a>参照  
 [自己関連付けを行う Direct を使用する方法のポートのバインド](../core/how-to-use-self-correlating-direct-bound-ports.md)
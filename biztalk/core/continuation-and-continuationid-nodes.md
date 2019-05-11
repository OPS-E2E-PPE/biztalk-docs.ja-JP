---
title: Continuation ノードと ContinuationID ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- Continuation nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- BAM, correlating activities
- activities, linking
- activities, continuation tokens
- ContinuationID nodes [Tracking Profile Editor]
ms.assetid: aa050660-66f7-4084-b6bf-b9319ce625af
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e0cd305241b04bbbb7a09a8cf716820978594e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354592"
---
# <a name="continuation-and-continuationid-nodes"></a>Continuation ノードと ContinuationID ノード
Continuation は、次の情報に関するガイダンスを BAM インフラストラクチャに提供します。  
  
- イベントの発生順序  
  
- イベント項目が関連付けられている一意 ID が変更された場合の処理方法  
  
  別の方法ではこの状態では、継続は、アクティビティに関係者間のこの情報の転送を定義します。 転送は、次の状況で発生します。  
  
- アクティビティの開始時刻と終了の間の ActivityID に変更があります。 たとえば、発注番号、販売注文番号などの 2 つの関連するメッセージがあるとします。 それぞれが、注文書番号 123456、販売注文番号 987654 などに、それに割り当てられた一意の番号です。 Continuation を使用して、注文書の一意の識別子を時と見なされ、Sales Order ようにする一意識別子に関係なく、一般的なアクティビティにイベントを関連付けることができますが、受信イベントに関連付け。  
  
- 1 つの実行時環境から別の遷移があります。 たとえば、オーケストレーションとオーケストレーションを起動し、出荷通知を送信するアプリケーションに制御を渡しますし、BizTalk Server メッセージング パイプラインに注文書を提供するアプリケーションがあるシナリオで必要がある 2 つ環境の遷移: メッセージング パイプラインから、オーケストレーションとメッセージング パイプラインをオーケストレーションから。  
  
  Continuation を使用するプロパティを選択する際に重要な点は、同じコンテキストからプロパティをマップする必要があります。  
  
  たとえば、次のように、プロパティ Message.InterchangeID と servicecontext がある場合です。InterchangeID、InterchangeID を使用して continuation を作成することでしたが表示されます。 メッセージが別のコンテキストから取得する場合は、continuation を確実に作成する、InterchangeID (またはその他のプロパティ) を使用できません。  
  
## <a name="working-with-continuation-nodes"></a>Continuation ノードの操作  
 Continuation ノードにはとも呼ばれる、一意のインスタンス ID を示すデータ項目が含まれています、*継続トークン*します。 継続トークンを使用すると、開発者は、ContinuationID ノードを使用して他のアクティビティにリンクできます。  
  
 Continuation と ContinuationID ノードを使用する 3 つの基本的なシナリオがあります。  
  
- オーケストレーションからオーケストレーションへ  
  
- BizTalk ソリューションにオーケストレーション  
  
- BizTalk ソリューションからオーケストレーションへ  
  
  シナリオ、TPE のオーケストレーションで Continuation ノードと ContinuationID ノードを定義する必要があり、bam アクティビティを関連付けるために、ノードが同じ名前を持つ必要があります。  
  
  BizTalk ソリューションのシナリオにオーケストレーションでは、TPE を使用して Continuation ノードを定義して、開発者は、継続の継続先部分を処理するために、BAM API を使用するソリューションを作成します.  
  
  オーケストレーションを BizTalk ソリューションで、開発者は、BAM API を使用して continuation ペアの発信元を指定して、TPE を使用して、ContinuationID ノードを定義します。  
  
> [!NOTE]
>  双方向のポートは、ポートを通過するデータの傍受できます、によって BizTalk ソリューションの動作が必要に、continuation を有効にすることを意味するいずれかの方向で動作できます。 たとえば、アクティビティ レコードの"PortEndTime"を BizTalk Server がメッセージング (項目名は、たとえば、"MessageReceived"および"MessageSent"をこの順序で) 場合、どちらの方向のポートの数が場合は、間に continuation を作成する必要があります。 Continuation が必要です、いつ以上の 1 つのイベント ストリームは、BAM アクティビティに貢献し、実装の接点 (BTS メッセージング、BTS メッセージング送信、オーケストレーション、カスタム アプリケーション、および Web サービスなど) ごとに個別のイベント ストリームがあります。  
  
## <a name="see-also"></a>参照  
 [Continuation を作成する方法](../core/how-to-create-a-continuation.md)   
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)
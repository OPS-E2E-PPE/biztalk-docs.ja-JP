---
title: "Continuation ノードと ContinuationID ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa8956721d4a44b51b8d2c7776560aaa878f864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="continuation-and-continuationid-nodes"></a>Continuation ノードと ContinuationID ノード
Continuation は、次の情報に関するガイダンスを BAM インフラストラクチャに提供します。  
  
-   イベントの発生順序  
  
-   イベント項目が関連付けられている一意 ID が変更された場合の処理方法  
  
 つまり、関係者間の情報をアクティビティに転送する方法を定義するのが Continuation です。 次の状況で転送が行われます。  
  
-   アクティビティの開始から終了までに ActivityID が変わった場合。 たとえば、注文書番号と販売注文番号など、2 つの関連するメッセージがあるとします。 それぞれのメッセージには、注文書番号 123456、販売注文番号 987654 などの一意の数字が割り当てられています。 Continuation を使用すると、注文書と販売注文の一意の ID を同等と見なすことができるので、受信したイベントがどちらの ID に関連付けられているかにかかわらず、イベントを共通のアクティビティに関連付けることができます。  
  
-   実行環境の移行が生じる場合。 たとえばを BizTalk Server メッセージング パイプライン、オーケストレーションとオーケストレーションを起動し、出荷通知を送信するアプリケーションに制御を渡しますに発注書を提供するアプリケーションが存在するシナリオでがある 2 つ環境の遷移: メッセージング パイプラインから、オーケストレーションとメッセージング パイプラインをオーケストレーションからです。  
  
 Continuation に使用するプロパティを選択するときに重要なことは、プロパティが同じコンテキストからマップされていなければならないということです。  
  
 たとえば、プロパティ Message.InterchangeID と servicecontext.InterchangeID がある場合、InterchangeID を使用して Continuation を作成できるように見えます。 しかし、メッセージの元になっているコンテキストが異なる場合は、InterchangeID (または他のプロパティ) を使用して Continuation を確実に作成することはできません。  
  
## <a name="working-with-continuation-nodes"></a>Continuation ノードの操作  
 Continuation ノードにはとも呼ばれる、一意のインスタンス ID を示すデータ項目が含まれています、*継続トークン*です。 継続トークンを使用することで、ContinuationID ノードを使用する他のアクティビティにリンクできます。  
  
 Continuation ノードと ContinuationID ノードを使用する基本的なシナリオは、次の 3 つです。  
  
-   オーケストレーションからオーケストレーションへ  
  
-   オーケストレーションから BizTalk ソリューションへ  
  
-   BizTalk ソリューションからオーケストレーションへ  
  
 オーケストレーション間のシナリオでは、まず TPE で Continuation ノードと ContinuationID ノードを定義する必要があります。次に、BAM でアクティビティの関連付けを行うために、2 つのノードに同じ名前を付ける必要があります。  
  
 オーケストレーションから BizTalk ソリューションへのシナリオでは、TEP を使用して Continuation ノードを定義し、Continuation の継続先部分を処理する、BAM API を使用したソリューションを作成します。  
  
 BizTalk ソリューションからオーケストレーションへのシナリオでは、BAM API で Continuation ペアの起点を指定し、TPE で ContinuationID ノードを定義します。  
  
> [!NOTE]
>  双方向のポートは、どちらの方向でも機能します。つまり、BizTalk ソリューションの動作によっては、そのポートを通過するデータを受信するために、Continuation を有効にする必要があります。 たとえば、項目名を "MessageReceived" および "MessageSent" (順序はこのとおり) とした場合に、BizTalk Server メッセージング ポートをいずれかの方向で有効にしたときにアクティビティが "PortEndTime" を記録する場合、2 つの項目間に Continuation を作成する必要があります。 複数のイベント ストリームが BAM アクティビティに関与していて、実装の接点 (BTS メッセージング受信、BTS メッセージング送信、オーケストレーション、カスタム アプリケーション、Web サービスなど) ごとに個別のイベント ストリームが存在する場合、常に Continuation が必要です。  
  
## <a name="see-also"></a>参照  
 [Continuation を作成する方法](../core/how-to-create-a-continuation.md)   
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)
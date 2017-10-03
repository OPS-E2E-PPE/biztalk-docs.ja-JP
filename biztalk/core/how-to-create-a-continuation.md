---
title: "Continuation を作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities, relating events
- tracking profiles, relating events
- continuations, tracking profiles
- activities, continuations
- events, relating
- orchestrations, business events
- tracking profiles, updating
- activities, tracking profiles
- tracking profiles, continuations
- tracking profiles, connecting activities
ms.assetid: 31d6fc24-676e-418c-8e78-1a46b045905d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e63983b290f0f4d7dff544cd2faea45f6cf46adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-continuation"></a>Continuation を作成する方法
Continuation は、接続されたアクティビティを構築することによって、1 つ以上のオーケストレーション内のどのビジネス イベントが関連付けられているのかを示すために作成します。  
  
> [!IMPORTANT]
>  追跡プロファイルを更新する場合に、アクティビティに BAM の Continuation が含まれていると、実行中のアクティビティ インスタンスに影響することがあります。 具体的には、追跡プロファイルの更新によって、既に記録されているアクティビティ項目に対してデータの下流傍受が指定されると、元の値が上書きされる可能性があります。 各ストリーム オブジェクトは、アクティビティまたはストリームが開始された時点で配置されたプロファイルの特定のバージョンに関連付けられているため、すべての単一のイベント ストリームは、実質的には追跡プロファイルの更新対象のアプリケーションによる影響を受けません。  ただし、Continuation は複数のイベント ストリームを関連付ける手段なので、プロファイルの更新の時点でまだ開始されていなかったストリームは、更新中に変更内容を取得します。その結果、上記のようなデータの上書きが発生する可能性があります。  
  
> [!NOTE]
>  メッセージを処理しないオーケストレーションを使用して、Continuation を作成できます。 メッセージを処理するオーケストレーションと同等の機能を実現するには、オーケストレーション間の実行呼び出しでパラメーターを渡し、Continuation の処理で BAM API を使用します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BAM アクティビティ定義および接続先のオーケストレーションを展開しておく必要があります。  
  
### <a name="to-create-a-continuation"></a>Continuation を作成するには  
  
1.  既存の追跡プロファイルを開くか、追跡プロファイルを作成します。 追跡プロファイルを作成する方法の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)です。  
  
2.  識別、*継続トークン、*は両方のアクティビティに使用される固有の情報の一部であります。 たとえば場合、 **CreditHistory**アクティビティがから送信されたメッセージによってアクティブ化、 **LoanProcess**内のアクティビティ、 **EquityLoan**オーケストレーションの SSN フィールド、メッセージは、両方のアクティビティに一般的になっているために、継続トークンとして使用できます。  
  
3.  アクティビティを右クリックし **新しい Continuation** continuation (CreditHistory) を作成します。 作成した Continuation のノードに名前を付けます。  
  
4.  オーケストレーション スケジュール ビューから、手順 2. で選択した継続トークン (この場合は送信アクションの SSN) を選択し、手順 3. で作成した Continuation のノードにドロップします。  
  
5.  アクティビティを右クリックし [**新しい continuationid]** Continuation ID ノードを作成します。 作成したノードに、手順 3. で指定した名前を付け、対応するデータ項目 (この場合は受信アクションの SSN) を含むノードにドロップします。  
  
6.  **ファイル** メニューのをクリックして**名前を付けて保存**追跡プロファイルを BizTalk 管理データベースに .btt ファイルとして保存し、既存の .btt ファイルが上書きされないようにします。  
  
## <a name="see-also"></a>参照  
 [Continuation ノードと ContinuationID ノード](../core/continuation-and-continuationid-nodes.md)   
 [追跡プロファイルを作成します。](../core/creating-tracking-profiles.md)
---
title: 主要メッセージとフィールド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 77db0706-dfdc-48b0-8ca4-bae7ab2d7641
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 524b5f361495d9509809a9229362d28a18712239
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263930"
---
# <a name="key-messages-and-fields"></a>キー メッセージおよびフィールド
このセクションでは、主なメッセージおよびによって処理されるフィールドにについて簡単に説明、 **OrderBroker**と**OrderManager**オーケストレーションです。 アプリケーション内のメッセージの一覧については、次を参照してください。[ビジネス プロセス管理ソリューションのメッセージ リファレンス](../core/message-reference-for-the-business-process-management-solution.md)です。  
  
## <a name="order-messages"></a>注文メッセージ  
 メッセージの順序、 **OrderBroker**マルチパート メッセージが表示されます。 ルーティング情報を格納する部分と、注文情報を格納する部分があります。 ルーティング メッセージ部分のフィールドは、この部分を定義する .NET クラスにより、すべて識別フィールドになっています。これは、オーケストレーションがすべてのクラス メンバをメッセージのプロパティとしてアクセスできるようにするためです。 また、メッセージをルーティングすることができるように、ルーティング クラスには昇格フィールドが含められています。 これらの昇格フィールドも、プログラムの記述に使用し、簡単な表記で参照できるように、識別フィールドになっています。  
  
 .NET クラスを使用してメッセージを定義する方法の詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。  
  
## <a name="identifying-orders"></a>注文の識別  
 このソリューションでは、ルーティング情報の 3 つのフィールドを使用して、注文を識別します。 これら 3 つの 2 つのフィールドで注文: 注文識別子 (**OrderID**) と、顧客の識別子 (**CustomerID**)。 この 2 つのフィールドで注文を識別できますが、注文のインスタンスが複数存在することもあります。 たとえば、顧客が新しい標準ケーブルの設置を注文し、その後電話をかけ直して新しいデラックス ケーブルを設置するよう注文を変更したとします。 更新された注文が到着する前に元の注文が完了する可能性は少なく、 この結果、注文のインスタンスが 2 つ作成されることになります。  
  
 注文の各インスタンスを区別するために、ソリューションが注文シーケンス番号を使用して (**SeqNum**)。 3 つのフィールド**OrderID**、 **CustomerID**、および**SeqNum**注文のインスタンスを一意に識別します。  
  
 最後に、ソリューションの増加する数字を使用しているため、 **SeqNum**、ソリューションは、元の注文と更新を区別することができます:、更新プログラムより高い**SeqNum**です。  
  
> [!NOTE]
>  ソリューションに昇順の値を割り当てるには、注文要求を作成するシステムに依存**SeqNum**です。 入力 web サービス用 ASP ページのコードを参照してください**CSRMainForm.aspx.cs**とに、注文に、要求を変換するマップ**CSR_OrderRequest_To_Order.btm**フィールドの名前に関係します。  
  
## <a name="status"></a>[状態]  
 **OrderBroker**、 **OrderManager**、それらのサテライト オーケストレーションは、状態を追跡するために、注文メッセージのルーティング部分で 2 つのフィールドを使用して:**ステータス**、および**ステージ**です。 **ステータス**フィールドは、注文ステータスを追跡します。 次の表に、値を**ステータス**フィールドです。  
  
|値|設定場所|Description|  
|-----------|---------------|-----------------|  
|ACCEPTED|OrderBroker|注文を OrderManager に渡すことができます。|  
|COMPLETED|OrderManager|注文全体の処理が正常に完了しました。|  
|ERROR|OrderManager|注文にエラーが検出されました。|  
|ORDERMANAGER-EXCEPTION|OrderManager|注文を処理中に、OrderManager に例外が発生しました。|  
|STAGE_n_COMPLETED|OrderManager|ステージ n (n は番号) が正常に完了しました。|  
|STARTED|OrderManager|注文処理が開始されました。|  
|TERMINATED|OrderManager|注文処理が、キャンセルにより中止されました。|  
  
## <a name="stage"></a>段階  
 **OrderManager**を使用して、**ステージ**メッセージの処理ステージを示すために、ルーティングの部分でフィールドです。 このフィールドは、メッセージをどのサテライト オーケストレーションで処理するかを決定するフィルタで使用されます。 **OrderManager**に初期設定**ステージ**(1) 1 つにします。 順序が終了または完了すると、ときに、 **OrderManager**設定**ステージ**オーケストレーション変数の値に**停止**です。  
  
## <a name="requesttype"></a>RequestType  
 **OrderManager**も使用して、 **RequestType**注文メッセージのフィールドです。 フィールドの値が TERMINATE の場合、注文は中止されます。 オーケストレーションの他のすべての値を無視する、 **RequestType**フィールドし、注文の更新や重複を認識するように、注文シーケンス番号に依存しています。 それ以外の場合、 **OrderBroker**設定、 **RequestType**フィールドの値を**ステータス**フィールド仕入先または顧客サービスのシステムからのメッセージにします。  
  
## <a name="ordertypecode-ordertype-and-serviceclass"></a>OrderTypeCode、OrderType、ServiceClass  
 注文の種類、 **OrderTypeCode**注文メッセージのフィールドです。 **OrderBroker**の値をその値を設定、 **OrdTypeCode**フィールド、カスタマ サービス システムまたはベンダ システムから受信したメッセージにします。 次の表は、可能な値を示しています**OrderTypeCode**:。  
  
|値|Description|  
|-----------|-----------------|  
|NS|新しい標準ケーブルの設置|  
|ND|新しいデラックス ケーブルの設置|  
|XS|標準ケーブルの設置をキャンセル|  
|XD|デラックス ケーブルの設置をキャンセル|  
|CS|標準ケーブルの設置を変更|  
|CD|デラックス ケーブルの設置を変更|  
|UNKNOWN|不明。|  
  
 後で、**検証**オーケストレーションはビジネス ルール エンジンを使用して、2 つの個別のフィールドにこれらの値を変換する**OrderType**と**ServiceClass**です。 **検証**オーケストレーションは、最初の注文処理ステージ、によって呼び出されます。 **CableOrder1**です。  
  
 次の表は、値を**OrderType**:  
  
|OrderTypeCode の値|OrderType の値|  
|--------------------------|---------------------|  
|NS、ND|ACTIVATE|  
|XS、XD|CANCEL|  
|CS、CD|CHANGE|  
|無効な組み合わせです。|INVALID|  
  
 値は、 **ServiceClass**は、対応する 1 つの文字を**S** standard、または**D**のデラックスです。  
  
## <a name="additional-identifiers"></a>その他の識別子  
 ソリューションでは、個別の各注文に対しても識別子を使用します。 この識別子**RequestId**、すべての注文を通して一意にする必要があります。 入力 Web サービスでは、自動的にこの識別子に GUID が割り当てられます。 バッチ入力で送信するメッセージには、このフィールドの値を含めておく必要があります。 フィールドが**RequestID**スキーマです。 **OrderBroker**、ただし、使用、 **CSR_OrderRequest**注文を処理するスキーマです。 フィールドとして表示されます**ReqId**このスキーマで識別プロパティです。  
  
 ソリューションを使用して、 **RequestId** BAM 追跡システムで使用されるアクティビティ識別子を形成します。  
  
## <a name="see-also"></a>参照  
 [プロセス マネージャのロジック](../core/process-manager-logic.md)   
 [プロセス マネージャでの注文の流れ](../core/order-flow-through-the-process-manager.md)   
 [ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md)   
 [ビジネス プロセス管理ソリューションのメッセージ リファレンス](../core/message-reference-for-the-business-process-management-solution.md)
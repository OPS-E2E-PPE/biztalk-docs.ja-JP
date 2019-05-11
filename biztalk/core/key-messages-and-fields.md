---
title: 主要メッセージとフィールド |Microsoft Docs
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
ms.openlocfilehash: 9f97e13b50dd0ccce127ae862972cd0448c4d56a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329485"
---
# <a name="key-messages-and-fields"></a>主要メッセージとフィールド
主要メッセージとフィールドは、このセクションを簡単に説明、 **OrderBroker**と**OrderManager**オーケストレーションします。 アプリケーション内のメッセージの完全な一覧を参照してください。 [、ビジネス プロセス管理ソリューションのメッセージ リファレンス](../core/message-reference-for-the-business-process-management-solution.md)します。  
  
## <a name="order-messages"></a>注文メッセージ  
 メッセージの順序、 **OrderBroker**マルチパート メッセージします。 1 つの部分には、ルーティング情報; が含まれています。その他の部分、注文情報。 ルーティング メッセージ部分を定義する .NET クラスは、オーケストレーションがすべてのメッセージのプロパティとしてクラスのメンバーにアクセスできるように、すべてのフィールドの識別フィールドです。 クラスも含める昇格フィールド、ルーティング クラスにメッセージがルーティング可能です。 すべての昇格させたフィールドも識別フィールドに対してプログラムを作成して単純な表記で参照できるようにします。  
  
 .NET クラスを使用してメッセージを定義する方法の詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。  
  
## <a name="identifying-orders"></a>注文を識別します。  
 ソリューションは、注文を識別するために、ルーティング情報内で 3 つのフィールドを使用します。 これらの 3 つの 2 つのフィールドで注文: 注文識別子 (**OrderID**) と、顧客の識別子 (**CustomerID**)。 ただし、これら 2 つのフィールドで注文を識別していますが、注文の 1 つ以上のインスタンスがあります。 たとえば、顧客では、設置新しい標準ケーブルの設置可能性がありますして、新しいデラックス ケーブルのインストールに順序を変更するから後で呼び出します。 更新された注文が到着する前に元の注文が完了する可能性が高いことはできません。 これには、順序の 2 つのインスタンスが作成されます。  
  
 注文の各インスタンスを区別するために、ソリューションが注文シーケンス番号を使用して (**SeqNum**)。 3 つのフィールド**OrderID**、 **CustomerID**、および**SeqNum**注文のインスタンスを一意に識別します。  
  
 最後に、ソリューションの増加する数字を使用するため、 **SeqNum**、ソリューションは、元の注文から更新を区別することができます:、更新された**SeqNum**します。  
  
> [!NOTE]
>  ソリューションに昇順の値を割り当てるには、注文要求を作成するシステムに依存**SeqNum**します。 入力 web サービス用 ASP ページの背後にあるコードを参照してください。 **CSRMainForm.aspx.cs**、とを注文要求を変換するマップ**CSR_OrderRequest_To_Order.btm**フィールドの名前に関係します。  
  
## <a name="status"></a>状態  
 **OrderBroker**、 **OrderManager**、それらのサテライト オーケストレーションの状態を追跡するために、注文メッセージのルーティング部分で 2 つのフィールドを使用するとします。**ステータス**、および**ステージ**します。 **状態**フィールドは、注文の状態を追跡します。 次の表の値、**状態**フィールド。  
  
|値|設定されています。|説明|  
|-----------|---------------|-----------------|  
|受け入れ|OrderBroker|順序は、OrderManager 移動できます。|  
|完了しました|OrderManager|エラーが発生せず、注文全体の処理が完了しました。|  
|ERROR|OrderManager|エラーは順番が検出されました。|  
|ORDERMANAGER 例外|OrderManager|注文マネージャに注文の処理中に例外が発生しました。|  
|STAGE_n_COMPLETED|OrderManager|ステージ n、n は、番号、エラーなく完了したことを示します。|  
|STARTED|OrderManager|注文処理を開始します。|  
|終了|OrderManager|注文処理をキャンセルにより停止しました。|  
  
## <a name="stage"></a>ステージ  
 **OrderManager**を使用して、**ステージ**フィールドに、ルーティングの部分をメッセージの処理ステージを示します。 フィールドは、どのサテライト オーケストレーションはメッセージを処理するフィルターで使用されます。 **OrderManager**が初期設定**ステージ**(1) 1 つにします。 順序が終了または完了すると、ときに、 **OrderManager**設定**ステージ**オーケストレーション変数の値に**停止**します。  
  
## <a name="requesttype"></a>RequestType  
 **OrderManager**を使用しても、 **RequestType**注文メッセージのフィールド。 フィールドの値が TERMINATE の場合は、順序は中止されます。 オーケストレーションの他のすべての値を無視する、 **RequestType**フィールドし、注文の更新プログラムと重複部分を認識して、注文シーケンス番号に依存しています。 それ以外の場合、 **OrderBroker**設定、 **RequestType**フィールドの値を**状態**ベンダーまたは顧客サービスのシステムからのメッセージ フィールド。  
  
## <a name="ordertypecode-ordertype-and-serviceclass"></a>OrderTypeCode、OrderType、serviceclass  
 注文の種類は、 **OrderTypeCode**注文メッセージのフィールド。 **OrderBroker**の値にその値を設定、 **OrdTypeCode**カスタマ サービス システムまたはベンダ システムから受信したメッセージのフィールド。 次の表に、可能な値**OrderTypeCode**:  
  
|値|説明|  
|-----------|-----------------|  
|NS|新しい標準ケーブルの設置します。|  
|ND|新しいデラックス ケーブルの設置インストールします。|  
|XS|標準ケーブルの設置をキャンセルします。|  
|XD|デラックス ケーブルの設置をキャンセルします。|  
|CS|標準ケーブルの設置を変更します。|  
|CD|デラックス ケーブルの設置を変更します。|  
|UNKNOWN|不明です。|  
  
 後で、**検証**オーケストレーションはビジネス ルール エンジンを使用して、2 つの個別のフィールドにこれらの値を変換する**OrderType**と**ServiceClass**します。 **検証**オーケストレーションが最初の注文処理ステージでは、によって呼び出される**CableOrder1**します。  
  
 次の表の値を示します、 **OrderType**:  
  
|OrderTypeCode の値|OrderType の値|  
|--------------------------|---------------------|  
|NS、ND|アクティブ化します。|  
|XS、XD|キャンセル|  
|CS、CD|変更|  
|無効な組み合わせです。|無効です|  
  
 値は、 **ServiceClass**は対応する 1 文字、 **S** standard、または**D**のデラックスします。  
  
## <a name="additional-identifiers"></a>その他の識別子  
 ソリューションでは、個別の注文ごとの識別子も使用します。 この識別子は、 **RequestId**、すべての注文を通して一意である必要があります。 入力 web サービスは、自動的に GUID を割り当てます。 入力バッチで送信するメッセージには、フィールドの値を含める必要があります。 フィールドが**RequestID**注文スキーマ。 **OrderBroker**、ただし、使用、 **CSR_OrderRequest**注文を処理するスキーマ。 フィールドとして表示されます**ReqId**このスキーマで識別プロパティです。  
  
 ソリューションを使用して、 **RequestId** BAM 追跡システムで使用されるアクティビティ識別子を形成します。  
  
## <a name="see-also"></a>参照  
 [プロセス マネージャのロジック](../core/process-manager-logic.md)   
 [プロセス マネージャでの注文の流れ](../core/order-flow-through-the-process-manager.md)   
 [ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md)   
 [ビジネス プロセス管理ソリューションのメッセージ リファレンス](../core/message-reference-for-the-business-process-management-solution.md)
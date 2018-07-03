---
title: '手順 7 (オンプレミス): オーケストレーションの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c0b6d0e-cf00-4eee-9b89-28210bad46f4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc072b664b453a3f10b624f75fe161a515ecc902
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975819"
---
# <a name="step-7-on-premises-create-an-orchestration"></a>手順 7 (オンプレミス): オーケストレーションを作成します。
後に、ビジネス シナリオに従って[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]販売注文メッセージを受信、Service Bus キューからメッセージの注文数量が 100 より大きいかどうかを確認する必要があります。 メッセージが挿入された数量が 100 より大きい場合、 **SalesOrder**テーブル。 そうでない場合は、共有ファイルの場所にメッセージが送信されます。 Northwind はオーケストレーションを作成することによってこのビジネス ロジックを実現します。 このトピックでは、オーケストレーションの作成方法を、手順を追って説明します。  
  
### <a name="to-add-an-orchestration-to-the-includebtsbiztalkservernoversionincludesbtsbiztalkservernoversion-mdmd-project"></a>[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトにオーケストレーションを追加するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトを右クリックをポイントして、既に作成した、**追加**、順にクリックします**新しい項目の**します。  
  
2. **新しい項目の**ダイアログ ボックスで、 **BizTalk オーケストレーション**、マップ名として入力`OrderProcessing.odx`、順にクリックします**追加**。  
  
## <a name="create-messages-for-the-orchestration"></a>オーケストレーションのメッセージの作成  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは通常、対応するスキーマによって定義された型の変数です。 ここで、オーケストレーションのメッセージを作成し、先に生成したスキーマにリンクする必要があります。 以下の 3 つのメッセージを作成してください。  
  
|メッセージ名|対応するスキーマ|  
|------------------|---------------------------|  
|Message1_SO_Inbound|このメッセージは、のインスタンス、 **ECommerceSalesOrder.xsd**スキーマ。|  
|Message2_SO_Inbound|このメッセージのコピーである、 **Message1_SO_Inbound**します。 ベスト プラクティスとして、メッセージのコピーを作成し、元のメッセージを残したまま、新しいメッセージを修正してください。 詳細については、次を参照してください。 [BizTalk Server メッセージ](http://msdn.microsoft.com/library/aa560436)します。|  
|Message1_SO_Outbound|このメッセージは、のインスタンス、 **TableOperations.dbo.SalesOrder (Insert)** スキーマ。|  
  
#### <a name="to-create-the-messages"></a>メッセージを作成するには  
  
1.  開く、**オーケストレーション**がまだ開いていない場合、BizTalk プロジェクトのウィンドウ。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
2.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
3.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  
  
    |プロパティ名|実行するアクション|  
    |-------------------|--------------------|  
    |[Identifier]|入力します `Message1_SO_Inbound`|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *OrderProcessingDemo.ECommerceSalesOrder*ここで、 *OrderProcessingDemo* BizTalk の名前を指定しますプロジェクトです。 *ECommerceSalesOrder*は、Service Bus キューから受信した販売注文メッセージのスキーマです。|  
  
5.  手順を繰り返し、以下の情報を使ってメッセージを作成します。  
  
    |メッセージ名||  
    |------------------|-|  
    |Message2_SO_Inbound|-設定**識別子**に `Message2_SO_Inbound`<br />-設定**メッセージの種類**に*OrderProcessingDemo.ECommerceSalesOrder*|  
    |Message1_SO_Outbound|-設定**識別子**に `Message1_SO_Outound`<br />-設定**メッセージの種類**に*OrderProcessingDemo.TableOperation_dbo_SalesOrder.Insert*|  
  
## <a name="add-shapes-to-the-orchestration"></a>オーケストレーションへの図形の追加  
 オーケストレーション図形は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションのフローを定義します。 このセクションでは、オーケストレーションに必要な図形を追加します。  
  
#### <a name="to-add-shapes-to-the-orchestration"></a>オーケストレーションに図形を追加するには  
  
1.  最初に、追加する必要があります、**受信**図形。 この図形は、Service Bus キューから送信される販売注文メッセージを受け取ります。 受信図形に以下のプロパティを設定します。  
  
    1.  設定**アクティブ**に**True**します。  
  
    2.  設定**メッセージ**に**Message1_SO_Inbound**します。  
  
    3.  設定**名前**に**ReceiveOrder**します。  
  
2.  先に述べたように、オーケストレーションで受信した元の販売注文メッセージのコピーを作成する必要があります。  
  
    1.  ドラッグ アンド ドロップ、**メッセージの構築**図形の下、 **ReceiveOrder**図形。 Message2_SO_Inbound の種類のメッセージを構築するには、この図形を使用するための設定、**構築メッセージ**プロパティを**Message2_SO_Inbound**します。  
  
    2.  追加、**メッセージの割り当て**図形内、**メッセージの構築**図形。 図形をダブルクリックして式エディターを開き、以下を追加します。  
  
        ```  
        Message2_SO_Inbound = Message1_SO_Inbound; //copy the message  
        Message2_SO_Inbound(*) = Message1_SO_Inbound(*); //copy the context properties on the message  
        ```  
  
         **[OK]** をクリックします。  
  
3.  ビジネス シナリオに従って、注文項目の数量に応じて別の宛先にメッセージを送信しなければならない場合があります。 このため、受信する販売注文メッセージから、数量の値を抽出する必要があります。  
  
    1.  **数量**受信メッセージ (ECommerceSalesOrder.xsd) 内の要素には、注文数量の値が含まれています。 オーケストレーションの式でその要素を使用できるよう、プロパティを昇格させる必要があります。 プロパティを昇格するを開き、 **ECommerceSalesOrder.xsd**スキーマを右クリックして**数量**、 をポイント**昇格**、順にクリックします**クイック昇格**.  
  
    2.  数量の値を格納するための変数を作成します。 変数を作成する、**オーケストレーション**、右クリック**変数**、順にクリックします**新しい変数**します。 変数に以下のプロパティを設定します。  
  
        |プロパティ名|値|  
        |-------------------|-----------|  
        |[Identifier]|入力します `quantityOrdered`|  
        |型|選択**Int32**します。|  
  
    3.  値を割り当てる必要があります、**数量**要素を**quantityOrdered**変数。 ドラッグ アンド ドロップ、**式エディター**後、**メッセージの構築**図形。 エディターを開き、以下の式を入力します。  
  
        ```  
        quantityOrdered = Message2_SO_Inbound.Quantity;  
        ```  
  
         **[OK]** をクリックします。  
  
4.  注文数量を抽出したら、次に、メッセージ フローがたどる 2 つの異なるパスを配置するための判断ブロックを作成する必要があります。 追加することで、オーケストレーションで判断ブロックを作成する、**判断**図形。  
  
    1.  ドラッグ アンド ドロップ、**判断**図形の後に、**式エディター**図形。  
  
    2.  選択、 **[rule_1]** 図形および、**プロパティ**ウィンドウで、次を指定します。  
  
        |プロパティ名|値|  
        |-------------------|-----------|  
        |[Identifier]|入力`Yes`します。 **注:** という名前の既定値によって、その他のルートが**Else**します。|  
        |式|入力`quantityOrdered > 100`します。|  
  
         これで、2 つのルートが利用可能になりました。 場合の値、 **quantityOrdered**変数が 100 より大きい場合、メッセージは、**はい**ルート。 それ以外の場合、かかる、 **Else**ルート。 ここで、各ルート内で実行するアクションを定義する必要があります。  
  
5.  ビジネス シナリオに従って、注文数量が 100 を超える場合、メッセージを SalesOrder テーブルに挿入する必要があります。 そのためで、 **[はい]** ルート、ECommerceSalesOrder.xsd スキーマを TableOperations.SalesOrder.Insert スキーマを変換する必要があります。 トピックの挿入スキーマを作成した[手順 5 (オンプレミス): メッセージする SalesOrder テーブルを挿入するためのスキーマを生成](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)します。 スキーマを変換した後、メッセージを、SQL Server データベース テーブルに送信する必要があります。  
  
    1.  内で、**はい**ルーティングにドラッグ アンド ドロップ、**メッセージの構築**図形。 設定、**構築メッセージ**に図形のプロパティ**Message1_SO_Outbound**します。  
  
    2.  内で、**メッセージの構築**図形を追加、**変換**図形。 図形をダブルクリックして開き、**変換の構成** ダイアログ ボックス。 次の操作を行います。  
  
        1.  選択、**既存のマップ**オプション。  
  
        2.  **完全修飾マップ名**ドロップダウン リストで選択**OrderProcessingDemo.SalesOrder_SQL**します。  
  
        3.  **ソース**、 **Message2_SO_Inbound**します。  
  
        4.  **先**、 **Message1_SO_Outound**します。  
  
    3.  後に、**メッセージの構築**図形にドラッグ アンド ドロップ、**送信**図形し、設定、**メッセージ**に図形のプロパティ`Message1_SO_Outbound`します。  
  
6.  ビジネス シナリオに従って、注文数量が 100 を下回る場合、メッセージを共有のファイルの場所に送信する必要があります。 そのためで、 **Else**ルート送信図形を追加する必要があります。  
  
    1.  内で、 **Else**ルーティングにドラッグ アンド ドロップ、**送信**図形し、設定、**メッセージ**に図形のプロパティ`Message2_SO_Inbound`します。  
  
        > [!NOTE]
        >  [メッセージ] を Message2_SO_Inbound に設定するのは、Service Bus キューから受け取った同じメッセージが、処理されずにファイルの場所に送信されるためです。 Message2_SO_Inbound は、Service Bus キューによって受信されたメッセージを表しています。  
  
## <a name="add-ports-to-the-orchestration"></a>オーケストレーションへのポートの追加  
 ポートは、オーケストレーションに関連したメッセージの入力および出力の媒体を表しています。 メッセージは、受信ポートを使用してオーケストレーションによって処理され、送信ポートを使用して送信されます。 ビジネス シナリオにおいて、メッセージは 1 つの媒体 (Service Bus キュー) から受信され、その後メッセージの処理に応じて、2 つの異なる場所 (SQL Server データベースまたはファイル共有場所) に送信されます。 このため、オーケストレーションに 1 つの受信ポートと 2 つの送信ポートを作成する必要があります。  
  
#### <a name="to-add-ports"></a>ポートを追加するには  
  
1.  ドラッグ アンド ドロップ、**ポート**図形を**ポート画面**のウィンドウ、**オーケストレーション デザイナー**を起動する、**ポート構成ウィザード**します。 **へようこそ**  ページで **次**します。  
  
2.  **ポートのプロパティ** ページで、名前とポート`ReceiveSO`順にクリックします**次**します。  
  
3.  **ポートの種類を選択**ページで、選択**新しいポートの種類を作成**オプションを選択、**一方向**通信パターン、アクセスの制限については、既定のままにし、クリックして**次**します。  
  
4.  **ポートのバインド**] ページで、ポート方向を選択します**常にこのポートでメッセージを受信**、既定値には、ポートのバインドのままにし、[クリックして**次**.  
  
5.  最後のページで次のようにクリックします。**完了**します。  
  
6.  手順を繰り返して 2 つの送信ポートを作成します。 ポートを作成する際は以下の値を指定します。  
  
    |ポート名|[プロパティ]|  
    |---------------|----------------|  
    |SendToSQL|-設定**名前**に**SendToSQL**<br />-**新しいポートの種類の作成**<br />通信パターンのセット**一方向**<br />-ポートの方向に設定**は常にメッセージを送信しますこのポートで**|  
    |SendToFile|-設定**名前**に**SendToFile**<br />-**新しいポートの種類の作成**<br />通信パターンのセット**一方向**<br />-ポートの方向に設定**は常にメッセージを送信しますこのポートで**|  
  
## <a name="connect-ports-and-message-shapes"></a>ポートとメッセージ図形の接続  
 次に、ポートとメッセージ図形を接続して、オーケストレーションを完成させます。 オーケストレーションの開始、メッセージを受信したときに、 **ReceiveOrder** 2 つの送信図形でメッセージが送信されるときに図形とオーケストレーションが終了します。 この基準に基づいて、ポートとメッセージ図形を接続する必要があります。  
  
#### <a name="to-connect-ports-with-message-shapes"></a>ポートをメッセージ図形に接続するには  
  
1.  接続、 **ReceiveSO**受信ポートを**ReceiveOrder**図形。  
  
2.  送信図形を接続、**はい**へのルーティング、 **SendToSQL**送信ポート。 表しますメッセージがこのルートに入る場合 (**quantityOrdered** > 100) に送信される、 **SalesOrder** SQL Server データベースのテーブル。  
  
3.  送信図形を接続、 **Else**へのルーティング、 **SendToFile**送信ポート。 表しますメッセージがこのルートに入る場合 (**quantityOrdered** < = 100)、指定したファイルの場所に送信されます。  
  
     オーケストレーションは次のようになります。  
  
     ![オーケストレーション](../core/media/bts2010r2-tut1-orch.jpg "BTS2010R2_Tut1_Orch")  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)
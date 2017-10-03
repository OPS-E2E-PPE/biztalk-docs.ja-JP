---
title: "手順 3 c: SQL Server データベースに営業案件の詳細を挿入 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f6f9bbe-6f25-4393-8f92-aeeba9736acf
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d0055c05e0c9af9f4dddc4a7275c01ff49d779
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-insert-opportunity-details-into-a-sql-server-database"></a>手順 3 c: SQL Server データベースに営業案件の詳細を挿入
ここまでに、Salesforce にクエリ要求を送信し、応答を受信するためのオーケストレーションをビルドしました。 このセクションで Salesforce からの応答を挿入するようにオーケストレーションが更新されます、 **OrderDetails** 、内部設置型 SQL Server データベースのテーブルに**Orders**です。 これを達成するには、次のようなさまざまな手順を実行します。  
  
-   作成、 **OrderDetails**テーブルに、 **Orders**内部設置型 SQL Server データベース内のデータベースです。  
  
-   使用して、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]で利用可能な[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]で挿入操作のスキーマを生成する、 **OrderDetails**テーブル。  
  
-   メッセージに挿入するために、Salesforce 応答メッセージを変換するマップを作成する**OrderDetails** SQL Server テーブルにします。  
  
-   オーケストレーションを更新するには、応答メッセージを挿入する変換を使用する、 **OrderDetails**テーブル。  
  
## <a name="create-sql-server-database-and-table"></a>SQL Server データベースとテーブルを作成する  
  
#### <a name="to-create-the-database-and-table"></a>データベースとテーブルを作成するには  
  
1.  SQL Server Management Studio を開き、管理者として接続します。  
  
2.  右クリックし、**データベース**ノードとクリック**新しいデータベース**です。 データベース名として指定`Orders`と新しいデータベースを作成するには、他の詳細を指定します。  
  
3.  クエリ エディターを開き、次のクエリを作成する実行、 **OrderDetails**テーブルに、 **Orders**データベース。  
  
    ```  
    USE [Orders]  
    GO  
    /****** Object:  Table [dbo].[OrderDetails]    Script Date: 07-12-2012 22:15:47 ******/  
    SET ANSI_NULLS ON  
    GO  
    SET QUOTED_IDENTIFIER ON  
    GO  
    SET ANSI_PADDING ON  
    GO  
    CREATE TABLE [dbo].[OrderDetails]([ID] [int] IDENTITY(1,1) NOT NULL,  
    [TITLE] [varchar](200) NULL,  
    [ProductName] [varchar](200) NULL,  
    [Quantity] [float] NULL,  
    [Amount] [float] NULL,  
    PRIMARY KEY CLUSTERED   
    (  
    [ID] ASC  
    )WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
    GO  
    SET ANSI_PADDING OFF  
    GO  
    ```  
  
## <a name="create-schema-for-insert-operation-on-orderdetails-table"></a>[OrderDetails] テーブルで挿入操作を行うスキーマを作成する  
 インストールする[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]提供、[!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]内で使用できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で挿入操作のスキーマを生成するプロジェクト、 **OrderDetails**テーブル。 このセクションでは、次のメッセージ スキーマを作成する手順を説明します。  
  
#### <a name="to-create-the-schema-for-insert-operation"></a>挿入操作を行うスキーマを作成するには  
  
1.  右クリックし、 **BtsSalesforceIntegration**プロジェクトをポイントし、**追加**、クリックして**生成した項目の追加**です。 **生成した項目の追加**ダイアログ ボックスで、をクリックして**アダプター サービスの使用**、クリックして**追加**です。  
  
2.  [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]、バインディングのドロップダウン リストの選択 をクリックして**sqlBinding**、クリックして**構成**です。  
  
3.  **アダプターの構成**ダイアログ ボックスで、**セキュリティ**] タブの**クライアント資格情報の種類**[ **Windows** Windows を使用するにはSQL Server データベースへの接続に認証します。  
  
4.  **アダプターの構成**ダイアログ ボックスで、 **URI プロパティ** タブの**初期カタログ**(Orders) に接続するデータベース名を指定します。 **サーバー**に接続している SQL Server がインストールされているコンピューター名を指定します。 かどうか、SQL Server データベースと同じコンピューターには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト、ピリオドだけ配置できます (**.**)。 **[OK]**をクリックします。  
  
5.  [!INCLUDE[consumeadapterservshort](../includes/consumeadapterservshort-md.md)]クリックして**接続**です。 接続が確立されると、選択したコントラクト型として**クライアント (送信操作)**です。 下にある、**カテゴリを選択**ボックスで、展開**テーブル**、 をクリックして**OrderDetails**テーブル、および右側のウィンドウでをクリックして**挿入** をクリックし、**追加**です。  
  
6.  指定して、**ファイル名のプレフィックス**を生成されたスキーマに id をプレフィックスする場合。 このチュートリアルでは、プレフィックスとしてを指定しましょう**InsertOrders**  をクリックし、 **OK**です。  
  
     プロジェクトには多数のスキーマが追加されます。 メッセージを挿入するために使用するスキーマ、 **OrderDetails**テーブルが**InsertOrdersTableOperation.dbo.OrderDetails.xsd**です。  
  
## <a name="map-salesforce-response-and-insert-schemas"></a>Salesforce 応答と挿入スキーマをマップする  
 これでが両方のスキーマ (Salesforce への挿入と応答**OrderDetails**)、おの挿入スキーマには、Salesforce から応答スキーマをマップする必要があります**OrderDetails**できるように、Salesforce からの応答メッセージは、SQL Server データベース テーブルに挿入することができます。  
  
#### <a name="to-map-the-schemas"></a>スキーマをマップするには  
  
1.  右クリックし、 **BtsSalesforceIntegration**プロジェクトをポイントし、**追加**、 をクリックして**新しい項目の**、順にクリック**マップ**です。 マップ名として指定`QueryResult_Orders.btm` をクリックし、**追加**です。  
  
2.  送信元スキーマ、マップ画面で選択**QueryResult** 、送信先スキーマの選択と**InsertOrdersTableOperation.dbo.OrderDetails.xsd**し、その、 **挿入**ノード。  
  
3.  次のスクリーンショットに示されているように 2 つのスキーマをマップします。  
  
     ![挿入スキーマに Salesforce 応答にマップする](../core/media/bts-sf-map-response-insert.jpg "BTS_SF_Map_Response_Insert")  
  
     マップの使用に注意してください、**ループ**間の functoid、**レコード**と**OrderDetails**リンクします。 これにより、すべて 1 つまたは複数の下にあるノードの出現**レコード**同じ数の下にあるノードにマップされて、 **OrderDetails**です。  
  
4.  マップへの変更を保存します。  
  
## <a name="update-the-orchestration-to-insert-messages-into-sql-server"></a>SQL Server にメッセージを挿入するオーケストレーションを更新する  
 このセクションでは、オーケストレーション内のマップを使用して、Salesforce 応答メッセージを SQL Server のテーブルに注文詳細を挿入するためのメッセージに変換します。 さらに、SQL Server にそのメッセージを送信するためのポートも追加します。  
  
#### <a name="to-update-the-orchestration"></a>オーケストレーションを更新するには  
  
1.  挿入スキーマのメッセージ変数を作成します。 オーケストレーションの種類を右クリックし、**メッセージ**ノードをクリックして**新しいメッセージ**です。 メッセージの名前を設定**InsertOrders**メッセージの種類と**BtsSalesforceIntegration.InsertOrdersTableOperation_dbo_OrderDetails.Insert**です。  
  
2.  後のメッセージの構築図形を追加、 **ReceiveQueryResult**図形です。 図形の名前を設定`ConstructOrders`設定と、**構築メッセージ**プロパティを**InsertOrders**です。  
  
3.  内で、 **ConstructOrders**図形を追加、**変換**図形です。 変換図形をダブルクリックして、[変換の構成] ダイアログ ボックスを開きます。 ダイアログ ボックスで、選択、**既存のマップ**オプション、し、ドロップダウン リストから選択**BtsSalesforceIntegration.QueryResult_Orders**です。 設定**ソース**に**QueryResultMsg**、**先**に**InsertOrders**、順にクリック**[ok]**です。  
  
4.  後に、 **ConstructOrders**図形、送信図形を追加します。 図形の名前は`SendOrders`としてメッセージの種類を設定および**InsertOrders**です。  
  
5.  Salesforce に注文詳細を挿入するためのポートを追加します。 ポート構成ウィザードで、次のオプションを選択します。  
  
    -   ポート名を指定`SendToSQL`です。  
  
    -   新しいポート種類を作成するオプションを選択します。  
  
    -   設定**通信パターン**に*一方向*です。  
  
    -   設定**ポートの通信方向**に*すればを常にメッセージを送信するこのポートで*設定と**ポートのバインド**に*後で、指定*です。  
  
     接続、**要求**にポートの操作、 **SendOrders**送信図形をオーケストレーションを完了します。 次のスクリーンショットは、完了したオーケストレーションをエンド ツー エンドで示します。  
  
     ![Salesforce の統合のオーケストレーションを完了する](../core/media/bts-sf-complete-orch.jpg "BTS_SF_Complete_Orch")  
  
     厳密な名前のキー ファイルをプロジェクトに追加し、プロジェクトへの変更を保存します。  
  
 このトピックの手順を使用し、Salesforce から営業案件通知を受信し、営業案件に関する詳細について Salesforce にクエリを送信し、クエリ応答を SQL Server データベースに挿入するためのオーケストレーションが完成しました。 次のトピックでは、Salesforce で認証を行い、Salesforce 応答を BizTalk Server で処理するために使用するソリューションのその他の主要なコンポーネントのいくつかをビルドします。  
  
## <a name="see-also"></a>参照  
 [手順 3: Visual Studio での BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)
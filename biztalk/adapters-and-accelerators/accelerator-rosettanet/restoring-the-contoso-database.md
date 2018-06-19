---
title: Contoso データベースの復元 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, restoring databases
- databases, restoring
ms.assetid: 291178c1-826e-49e0-a1d2-cbffee749659
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77c242fe6477baac53b6a3e1b2fda545a7e4365
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210226"
---
# <a name="restoring-the-contoso-database"></a>Contoso データベースの復元
ここでは、SQL Server Management Studio を使用して SQL スクリプトを実行し、Contoso データベースとそれに関連付けられたストアド プロシージャを復元します。 また、データベース テーブルに準備データを追加します。  
  
### <a name="to-restore-the-contoso-database"></a>Contoso データベースを復元するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。  
  
2.  サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスで、クリックして**接続**です。  
  
    > [!NOTE]
    >  SQL Server エージェントが開始されていない場合を右クリックし、をクリックして**開始**です。  
  
3.  Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。  
  
4.  [クエリ] ペインで、次の SQL スクリプトをコピーし、[クエリ] ウィンドウに貼り付けます。  
  
    ```  
    CREATE DATABASE Contoso  
    GO  
    USE Contoso  
    GO  
    CREATE TABLE Products (  
    [ProductID] [varchar] (255) NOT NULL ,  
    [Name] [varchar] (255) NOT NULL ,  
    [Description] [varchar] (800) NULL ,  
    [Price] [money] NULL ,  
    [NumberAvailable] [int] NOT NULL   
    ) ON [PRIMARY]  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901234', 'ADM Line Card','',200.65,820 )  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901235','Analog Line Card','',165.24,769 )  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901236', 'Mapper/MUX','',150.54,948)  
    GO  
    CREATE TABLE StatusCodes (  
    [statusID] [int] NOT NULL ,  
    [statusCode] [nvarchar] (50) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    CREATE PROCEDURE GetInventoryForProductID  
    @ProductID varchar(255),  
    @NumberAvailable INT OUTPUT,  
    @Price MONEY OUTPUT  
    AS  
    SET NOCOUNT ON  
    SELECT @NumberAvailable = NumberAvailable,  
     @Price = Price  
    FROM Products  
    WHERE  ProductID = @ProductID  
    RETURN(0)  
    GO  
    CREATE PROCEDURE SP_GetInventoryForProductID  
    @ProductID varchar(255)  
    AS  
    SET NOCOUNT ON  
    SELECT *  
    FROM Products  
    WHERE ProductID = @ProductID  
    for xml auto  
    RETURN(0)  
    ```  
  
5.  **[実行]** をクリックします。  
  
### <a name="to-set-permissions-on-the-contoso-database"></a>Contoso データベースにアクセス許可を設定するには  
  
1.  Microsoft SQL Server Management Studio の オブジェクト エクスプ ローラーで展開**データベース**、展開、 **Contoso**データベースを展開し、展開**セキュリティ**です。 **[ユーザー]** を右クリックし、 **[新しいユーザー]** をクリックします。  
  
2.  データベース ユーザー - 新規 ダイアログ ボックスの**ログイン名**、省略記号ボタンをクリックします。  
  
3.  [ログインの選択] ダイアログ ボックスで、**参照**です。  
  
4.  オブジェクト ダイアログ ボックスの参照で、次のように選択します。 **BizTalk Application Users**、をクリックし、 **OK**です。  
  
5.  [ログインの選択] ダイアログ ボックスで、 **OK**です。  
  
6.  データベース ユーザー - 新規 ダイアログ ボックスで、**データベース ロールのメンバーシップ**ペインで、 **db_datareader**と**db_datawriter**です。 **ユーザー名**、入力**BizTalk Application Users**です。 **[OK]** をクリックします。  
  
7.  手順 1. ~ 6. を繰り返します**BizTalk Isolated Host Users**を選択すると、 **db_datareader**と**db_datawriter**の**データベース ロールのメンバーシップ**、」と入力して**BizTalk Isolated Host Users**の**ユーザー名**です。  
  
8.  手順 1. ~ 6. を繰り返します**BizTalk Server 管理者**を選択すると、 **db_owner**の**データベース ロールのメンバーシップ**、」と入力して**BizTalk Server管理者**の**ユーザー名**です。  
  
## <a name="see-also"></a>参照  
 [生成して、証明書の有効化](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)
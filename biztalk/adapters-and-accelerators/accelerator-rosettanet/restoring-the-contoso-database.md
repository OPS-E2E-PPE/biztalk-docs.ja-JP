---
title: Contoso データベースの復元 |Microsoft Docs
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
ms.openlocfilehash: 4d434d3817a8e00f01e458dd96850b1bff6bb79a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282401"
---
# <a name="restoring-the-contoso-database"></a>Contoso データベースの復元
この手順では、Contoso データベースとその関連付けられたストアド プロシージャを復元するのに SQL スクリプトを実行するのに SQL Server Management Studio を使用します。 予備的なデータをデータベース テーブルを作成します。  
  
### <a name="to-restore-the-contoso-database"></a>Contoso データベースを復元するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  
  
2.  サーバー] ダイアログ ボックスへの接続で、 **SQL Server**ボックスで、[ **Connect**します。  
  
    > [!NOTE]
    >  SQL Server エージェントが開始されていない場合を右クリックし、順にクリックします**開始**します。  
  
3.  Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。  
  
4.  クエリ ウィンドウでコピーしてクエリ ウィンドウに次の SQL スクリプトを貼り付けます。  
  
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
  
1.  Microsoft SQL Server Management Studio の オブジェクト エクスプ ローラー**データベース**、展開、 **Contoso**データベースを展開し、展開**セキュリティ**します。 **[ユーザー]** を右クリックし、 **[新しいユーザー]** をクリックします。  
  
2.  データベース ユーザー - 新規 ダイアログ ボックスでの**ログイン名**、省略記号をクリックします。  
  
3.  ログインの選択] ダイアログ ボックスで、[**参照**します。  
  
4.  [参照] ダイアログ ボックスのオブジェクトで選択**BizTalk Application Users**、順にクリックします**OK**します。  
  
5.  ログインの選択] ダイアログ ボックスで、[ **OK**します。  
  
6.  データベース ユーザー - 新規 ダイアログ ボックスで、**データベース ロールのメンバーシップ**ペインで、 **db_datareader**と**db_datawriter**します。 **ユーザー名**、入力**BizTalk Application Users**します。 **[OK]** をクリックします。  
  
7.  手順 1. ~ 6. を繰り返します**BizTalk 分離ホスト ユーザー**選択**db_datareader**と**db_datawriter**の**データベース ロールのメンバーシップ**、入力と**BizTalk 分離ホスト ユーザー**の**ユーザー名**します。  
  
8.  手順 1. ~ 6. を繰り返します**BizTalk Server 管理者**選択**db_owner**の**データベース ロールのメンバーシップ**、入力と**BizTalk Server管理者**の**ユーザー名**します。  
  
## <a name="see-also"></a>参照  
 [証明書の生成と有効化](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)
---
title: "アーカイブ データベースでパーティション ビューの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases, partitioning
- partitioning
- Archive database [BAM], partitioning
ms.assetid: f9ef7480-2e37-4477-92c8-b5686ae9b54b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f6000c95b94570b5f058073537fa926fd1651c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a>アーカイブ データベースでのパーティション ビューの作成
BAM データ保守パッケージ (BAM_DM_`<activity name>`) を実行すると、BAM プライマリ インポート データベースの各パーティションが BAM アーカイブ データベースの個別のテーブルにコピーされます。 アーカイブ データベースを接続解除した後、クエリを実行するために再接続する場合、クエリでデータを検索するのが困難になります。  
  
 データの検索を容易にするために、BAM アーカイブ データベースでパーティション ビューを作成できます。 BAM では最大 253 のパーティションをサポートしています。 BAM によってアクティビティごとに 1 つの BAM データ保守 DTS パッケージが生成され、アクティビティ データが BAM アーカイブ データベースにコピーされ、BAM プライマリ インポート データベースから削除されます。 データをコピーした後、次のバックアップの前にアーカイブ データベースに障害が発生すると、データは失われます。  
  
 データ損失を防ぐための対策として、アーカイブ パッケージを 1 つ作成し、最初にすべてのアクティビティの古いデータをコピーします。その後、BAM アーカイブ データベースをバックアップして、最後に BAM プライマリ インポート データベースからコピーしたパーティションを削除します。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a>SQL Server 2008 SP1 または SQL Server 2008 R2 で BAM アーカイブ データベースにパーティションを区切ったビューを作成するには  
  
1.  SQL Server Management Studio を開きます。  
  
2.  BAM アーカイブ データベースを選択し、クリックして**新しいクエリ**です。  
  
3.  **クエリ** メニューのをポイント**結果に** をクリックし、**結果をテキスト**です。  
  
4.  次の SQL スクリプトをクエリ ウィンドウにコピーします。 置換\<アクティビティ名 >、アクティビティ名、および置換`<view type>`いずれかで**インスタンス**のインスタンスを表示または**リレーションシップ**リレーションシップ ビューの場合。  
  
    ```  
    set nocount on  
  
    declare @activityName as nvarchar(128)  
    declare @viewType as nvarchar(50)  
    set @activityName = N'<activity name>'-- Substitute your activity name here  
    set @viewType = N'<view type>'-- Substitute the view type here, either "Instances" or "Relationships"  
  
    declare @tableName nvarchar(128)  
    declare @viewName nvarchar(128)  
    declare @isFirstTable bit  
    declare @scriptLine nvarchar(300)  
  
    set @viewName = N'bam_' + @activityName + '_' + @viewType + 'View'  
    select N'SELECT Name FROM sysobjects where name = N''' + @viewName + ''' and type = ''V'''   
     + char(13) + char(10) + 'IF @@ROWCOUNT > 0 DROP VIEW ' + @viewName   
     + char(13) + char(10) + 'GO'  
  
    select 'CREATE VIEW ' +  @viewName + ' AS ' + char(13) + char(10)  
  
    declare instance_cursor cursor local for  
    select name from sysobjects   
    where name like N'bam_' + @activityName + '_' + @viewType + '_%' and type = 'U'  
  
    SET @isFirstTable = 1  
    OPEN instance_cursor  
    FETCH NEXT FROM instance_cursor INTO @tableName  
  
    WHILE @@fetch_status = 0   
    BEGIN  
  
    if @isFirstTable = 1  
    BEGIN  
    SET @scriptLine = N'SELECT * FROM [' + @tableName + ']'  
    SET @isFirstTable = 0  
    END  
    ELSE  
    SET @scriptLine = N'UNION ALL SELECT * FROM [' + @tableName + ']'  
  
    SELECT @scriptLine  
  
    FETCH NEXT FROM instance_cursor INTO @tableName  
    END  
    CLOSE instance_cursor  
    DEALLOCATE instance_cursor  
  
    select 'GO'  
    set nocount off  
    ```  
  
5.  クエリを実行します。  
  
## <a name="see-also"></a>参照  
 [BAM DTS パッケージ](../core/bam-dts-packages.md)   
 [バックアップ方法、BAM 分析および Tracking Analysis Server データベース](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)
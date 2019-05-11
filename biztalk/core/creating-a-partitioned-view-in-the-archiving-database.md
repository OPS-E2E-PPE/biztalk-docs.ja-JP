---
title: アーカイブ データベースでパーティション ビューの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases, partitioning
- partitioning
- Archive database [BAM], partitioning
ms.assetid: f9ef7480-2e37-4477-92c8-b5686ae9b54b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4a1b688356ca665f98903099c1acef293a21e64
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354097"
---
# <a name="creating-a-partitioned-view-in-the-archiving-database"></a>アーカイブ データベースでパーティション分割されたビューを作成します。
BAM データ保守パッケージを実行すると (bam_dm _`<activity name>`) BAM は、各パーティションを BAM プライマリ インポート データベースで BAM アーカイブ データベースに別のテーブルにコピーします。 アーカイブ データベースをデタッチし、クエリを実行するために再接続する場合、クエリのデータを見つけるが難しくなります。  
  
 BAM アーカイブ データベースをデータの検索を容易にするには、パーティション ビューを作成できます。 BAM では、最大 253 のパーティションをサポートします。 各アクティビティの場合は、BAM には、1 つ BAM データ保守 DTS パッケージ、BAM アーカイブ データベースにアクティビティ データをコピーし、BAM プライマリ インポート データベースから削除されますが生成されます。 データをコピーした後、アーカイブ データベースが失敗した場合は、次のバックアップの前に、データは失われます。  
  
 データの損失を防ぐために解決策は 1 つのアーカイブ パッケージを最初に、すべての活動から古いデータをコピーし、BAM アーカイブ データベースをバックアップし、最後に、BAM プライマリ インポート データベースからコピーされたパーティションを削除します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-create-a-partitioned-view-in-the-bam-archive-database-in-sql-server-2008-sp1-or-sql-server-2008-r2"></a>SQL Server 2008 SP1 または SQL Server 2008 R2 で BAM アーカイブ データベースでパーティション ビューを作成するには  
  
1.  SQL Server Management Studio を開きます。  
  
2.  BAM アーカイブ データベースを選択し、クリックして**新しいクエリ**します。  
  
3.  **クエリ**メニューで、**結果を** をクリックし、**結果をテキスト**します。  
  
4.  クエリ ペインには、次の SQL スクリプトをコピーします。 置換\<アクティビティ名\>アクティビティ名、および置換と`<view type>`いずれかで**インスタンス**インスタンス ビューの場合または**リレーションシップ**リレーションシップ ビューの場合。  
  
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
 [BAM 分析および Tracking Analysis Server データベースをバックアップする方法](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)
---
title: "追跡分析サーバー データベースへの参照の更新 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a403325-1394-4668-946f-01b610cb686e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ed784eeca992d32f431a7c6794b7051b7595e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="update-references-to-the-tracking-analysis-server-database"></a>追跡分析サーバー データベースへの参照を更新します。
Tracking Analysis Server データベースは、省略可能なオンライン分析処理 (OLAP) キューブが含まれています。 これらの OLAP キューブは、BizTalk 追跡データベースに含まれるデータの集計です。  
  
 Tracking Analysis Server データベースを復元するには使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分析マネージャーで、MessageMetrics キューブおよび ServiceMetrics キューブを処理します。 手順については、次を参照してください。[管理バックアップと復旧 (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (http://go.microsoft.com/fwlink/?LinkId=130939) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック。  
  
 別のコンピューターに、Tracking Analysis Server データベースを復元するも、次の手順を使用して、BizTalk 管理データベースにデータベース名への参照を更新する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。  
  
### <a name="to-update-references-to-the-tracking-analysis-server-database-name"></a>Tracking Analysis Server データベース名への参照を更新するには  
  
1.  送信先システムでをクリックして**開始**をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリック**SQL Server Management Studio**.  
  
2.  **サーバーへの接続**ダイアログ ボックスで、**サーバーの種類**として**データベース エンジン**サーバー名を指定、サーバー、ot の接続に資格情報を提供し、をクリックして**接続**です。  
  
3.  ダブルクリックするをクリックして、適切なサーバーを開く**データベース**、 **BizTalkMgmtDb**、クリックして**テーブル**です。  
  
4.  詳細ウィンドウで右クリック**adm_Group**、順にポイントして**テーブルを開く**です。  
  
5.  新しいデータベースの適切な値を参照するように、元のデータベースに対応する列を変更します。  
  
    > [!NOTE]  
    >  *\<DBType >*データベースおよび *\<DBType >* DBName は、データベースの場所を示す、  *\<DBType >*の種類に対応しています、データベースを TrackingAnalysis です。  
  
6.  テーブルを閉じて新しい値を保存します。  
  
## <a name="see-also"></a>参照  
 [データベース参照の更新](../technical-guides/updating-database-references.md)
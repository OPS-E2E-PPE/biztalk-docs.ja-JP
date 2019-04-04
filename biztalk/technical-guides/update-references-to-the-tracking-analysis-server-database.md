---
title: 追跡分析サーバー データベースへの参照の更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a403325-1394-4668-946f-01b610cb686e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 417569d99b7326b435422b5fa0dff28019006116
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014707"
---
# <a name="update-references-to-the-tracking-analysis-server-database"></a>追跡分析サーバー データベースへの参照を更新します。
Tracking Analysis Server データベースであり、省略可能なオンライン分析処理 (OLAP) キューブが含まれています。 これらの OLAP キューブは、BizTalk 追跡データベースに含まれるデータの集計です。  
  
 Tracking Analysis Server データベースを復元する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分析マネージャー、MessageMetrics キューブおよび ServiceMetrics キューブを処理します。 手順については、[管理バックアップと復元 (Analysis Services)](http://go.microsoft.com/fwlink/?LinkId=130939) (<http://go.microsoft.com/fwlink/?LinkId=130939>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「を参照してください。  
  
 Tracking Analysis Server データベースを別のコンピューターを復元するには、次の手順を使用して、BizTalk 管理データベースにデータベース名への参照を更新することも必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。  
  
### <a name="to-update-references-to-the-tracking-analysis-server-database-name"></a>Tracking Analysis Server データベース名への参照を更新するには  
  
1.  送信先システムで、をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008**、 をクリックし、 **SQL Server Management Studio**.  
  
2.  **サーバーへの接続**ダイアログ ボックスで、**サーバーの種類**として**データベース エンジン**サーバー名を指定、サーバー、ot の接続に資格情報を提供し、クリックして**Connect**します。  
  
3.  ダブルクリックするをクリックして、適切なサーバーを開く**データベース**、 **BizTalkMgmtDb**、 をクリックし、**テーブル**します。  
  
4.  詳細ペインで右クリックして**adm_Group**、順にポイント**テーブルを開く**します。  
  
5.  新しいデータベースの適切な値を参照するように、元のデータベースに対応する列を変更します。  
  
    > [!NOTE]  
    >  *\<DBType\>*  DBServerName および*\<DBType\>* DBName は、データベースの場所を示す、 *\<DBType\>* 、データベースは、TrackingAnalysis の型に対応します。  
  
6.  テーブルを閉じて新しい値を保存します。  
  
## <a name="see-also"></a>参照  
 [データベース参照の更新](../technical-guides/updating-database-references.md)
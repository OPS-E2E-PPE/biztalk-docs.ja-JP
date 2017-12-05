---
title: "BAM を SQL Server Reporting Services と統合する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a55d0fa09267cc23d54533427da326e5028d3f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a>BAM と SQL Server Reporting Services を統合する方法
BAM インフラストラクチャに基づいてレポートを作成するには、SQL Server の他のデータ ソース用のレポートを作成するための一般的なタスクを使用します。 レポート デザイナーによるレポートの作成の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437)です。  
  
## <a name="prerequisites"></a>前提条件  
 レポートの作成に必要なデータへのアクセス許可が必要です。  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a>SQL Server Reporting Services を使用して BAM でレポートを作成する方法  
  
1.  レポートを作成するデータ ソースを選択します。  
  
     BAM には、Reporting Services から参照可能な 2 つのデータ ソースが用意されています。  
  
    |[データ ソース]|Description|  
    |-----------------|-----------------|  
    |BAM プライマリ インポート データベース|アクティビティ インスタンスとリアルタイム集計に関するビューが含まれています。 種類を選択 ="Microsoft SQL Server"、Connection String ="データ ソース =\<*サーバー名*\>です。Initial Catalog =\<*データベース名*\>"ここで、 \<*サーバー名*\>と\<*データベース名前*\> Bam プライマリ インポート データベースのサーバーとデータベースの名前を示します。|  
    |BAM 分析データベース|分析キューブに対してクエリを実行するために使用するデータが格納されています。 種類を選択 ="Microsoft SQL Server Analysis Server"、Connection String ="データ ソース =\<*サーバー名*\>です。Initial Catalog =\<*データベース名*\>"ここで、 \<*サーバー名*\>と\<*データベース名前*\> BAM 分析データベースのサーバーとデータベースの名前を示します。|  
  
2.  クエリをデザインします。 BAM プライマリ インポート データベースでは、2 種類のビューがあります。  
  
    |ビュー名|Description|  
    |---------------|-----------------|  
    |dbo.bam_\<*ビュー名*\>_\<*アクティビティ名*\>View_View です。|このビューにはインスタンス データが含まれています。|  
    |dbo.bam_\<*ビュー名*\>_\<*リアルタイム集計のピボット テーブル名*\>_RTAView|このビューには、リアルタイム集計で使用するデータが含まれています。|  
  
    > [!NOTE]
    >  入力することができます**選択\*ビューから**を目的の結果を返すに設定します。 BAM 分析データベースのクエリ ビルダー をクリックし、ディメンションとキューブをという名前のメジャーをドラッグして\<*ビュー名*\>を目的の結果を返すに設定します。  
  
## <a name="next-steps"></a>次の手順  
 レポート ウィザードの手順を実行して、表示するデータとそのデータの表示方法を指定します。  
  
## <a name="see-also"></a>参照  
 [BAM データベースの管理](../core/managing-bam-databases.md)
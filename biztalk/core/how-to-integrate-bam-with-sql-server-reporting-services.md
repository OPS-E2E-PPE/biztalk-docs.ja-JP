---
title: BAM を SQL Server Reporting Services と統合する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cba4a9fe610167105f9bf2b89c78f3a4b0ced0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336949"
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a>BAM を SQL Server Reporting Services と統合する方法
レポートを作成するデータに基づく BAM インフラストラクチャの使用中の他の SQL Server データ ソースのレポートの作成に関連する一般的なタスク。 レポート デザイナーによるレポートの作成の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437)します。  
  
## <a name="prerequisites"></a>前提条件  
 レポートを作成するために必要なデータにアクセスするアクセス許可が必要です。  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a>SQL Server Reporting Service を使用して、BAM でレポートを作成する方法  
  
1.  レポートの作成元となるデータ ソースを選択します。  
  
     BAM では、Reporting Services をポイントできます 2 つのデータ ソースを提供します。  
  
    |[データ ソース]|説明|  
    |-----------------|-----------------|  
    |BAM プライマリ インポート データベース|アクティビティのインスタンスとリアルタイム集計のビューが含まれています。 種類の選択 ="Microsoft SQL Server"、Connection String ="データ ソース =\<*サーバー名*\>;Initial Catalog =\<*データベース名*\>"ここで、 \<*サーバー名*\>と\<*データベース名前*\>は、Bam プライマリ インポート データベースのサーバーとデータベースの名前です。|  
    |BAM 分析データベース|分析キューブをクエリに使用されるデータが含まれています。 種類の選択 ="Microsoft SQL Server Analysis Server"、Connection String ="データ ソース =\<*サーバー名*\>;Initial Catalog =\<*データベース名*\>"ここで、 \<*サーバー名*\>と\<*データベース名前*\>は、BAM 分析データベースのサーバーとデータベースの名前です。|  
  
2.  クエリをデザインします。 BAM プライマリ インポート データベースの場合は、2 種類のビューがあります。  
  
    |ビュー名|説明|  
    |---------------|-----------------|  
    |dbo.bam_\<*ビュー名*\>_\<*アクティビティ名*\>View_View します。|このビューには、インスタンス データが含まれています。|  
    |dbo.bam_\<*ビュー名*\>_\<*リアルタイム集計のピボット テーブル名*\>_RTAView|このビューには、リアルタイム集計で使用されるデータが含まれています。|  
  
    > [!NOTE]
    >  入力することができます**選択\*ビューから**を目的の結果を取得する設定。 BAM 分析データベースのクエリ ビルダーをクリックし、ディメンションとキューブをという名前のメジャーをドラッグ\<*ビュー名*\>を目的の結果を取得する設定。  
  
## <a name="next-steps"></a>次の手順  
 存在して、データの表示方法をするデータを指定するレポート ウィザードの手順を完了します。  
  
## <a name="see-also"></a>参照  
 [BAM データベースの管理](../core/managing-bam-databases.md)
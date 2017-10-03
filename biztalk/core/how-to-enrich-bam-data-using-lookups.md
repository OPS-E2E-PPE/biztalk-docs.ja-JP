---
title: "参照を使用して BAM データを強化する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BAM, data lookups
ms.assetid: 8d10659e-97d6-4cd1-9b4d-307afd43c763
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43b42b42158bc3b3c179d624340a97a890072a17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enrich-bam-data-using-lookups"></a>照合を使用して BAM データを強化する方法
操作時に使用できるデータに、レポート処理で必要となるデータがすべて含まれているとは限らない場合があります。 たとえば、実行時に、ProductID があっても ProductName がない場合があります。 BAM アクティビティは実際のデータ収集方法に依存しない抽象概念を表すので、レポートに最終的に表示するデータとして "ProductName" という名前の項目を含める必要があります。 この項目は、他の項目と同様に、マイルストーン グループ、期間、ディメンション、メジャーなどの解釈型の構成要素で使用できます。 ProductName が実行時に使用できないので、ProductID など、照合の実行に必要な追加データを取得しなければなりません。  
  
 レポートに必要なデータに代わるデータを同じ列に収集します。 たとえば、実行時には ProductName ではなく ProductID を収集します。 さらに多くの列が必要な場合は、アクティビティに多くの項目を作成することはできますが、これらをビューで使用することはできません。  
  
### <a name="to-enrich-bam-data-via-lookups"></a>照合によって BAM データを強化するには  
  
1.  BAM 定義を展開します。  
  
2.  SQL Server Management Studio で、必要なデータが入ったサーバーをリモート サーバーとして追加します。  
  
3.  BAM_AN_`<View Name>` というデータ分析パッケージを探します。 たとえば、ビューが SalesMgr の場合は BAM_AN_SalesMgr を探します。  
  
4.  パッケージのビューを拡大表示するためにズーム (たとえば、100%) を設定します。  
  
5.  照合に使用する SQL 接続を追加します。  
  
6.  "クリーンアップ ステージング" ステップの後にデータ変換タスクを配置します。 このタスクでは、PrimaryImport データベースから StarSchema データベースにデータを移動します。 このタスクの 2 つのインスタンス: 完了したアクティビティと、1 つの進行中の別のいずれか。 両方のタスクに残りのすべてのステップを適用します。  
  
7.  [変換] をクリックします。  
  
8.  [照合] をクリックします。照合接続を使用して "LookupProductByID" という照合を追加します (照合については、SQL Server Books Online を参照してください)。 たとえば、照合が ProductID 列と ProductName 列を含む単純なテーブル "LookupProduct" の場合、照合のテキストは次のようになります。  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. [変換] タブをクリックします。既定のデータ変換 "Transform" を削除し、代わりに ActiveX 変換を作成します。 変換元列をクリックしてすべての列を追加し、 変換先列をクリックしてすべての列を追加します。  
  
10. [全般] タブ、し、[プロパティ] をクリックします。 この結果、次のような簡単なコピー変換を実行するスクリプトが自動的に生成されます。  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. 次のように、照合を使用して値を変更します。  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. パッケージを保存してから実行します。  
  
13. 最終的に正しいデータが OLAP キューブに含まれることを確認します。 パッケージには、BAM から自動生成されたステップだけでなくカスタム コードが含まれているため、パッケージを VBScript または構造化ストレージ ファイルとして保存する必要があります。  
  
> [!NOTE]
>  検索は、DTS と OLAP を使用して実行するスケジュールされたレポートに対してのみ機能します。 リアルタイム集計で収集したデータとは異なるデータが必要な場合は、BAM API を呼び出す前にデータを取得する必要があります。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティの使用の監視](../core/using-business-activity-monitoring.md)   
 [ローカライズされた BAM XML ファイルの配置](../core/deploying-localized-bam-xml-files.md)
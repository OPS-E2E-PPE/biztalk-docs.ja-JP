---
title: 参照を使用して BAM データを強化する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data lookups
ms.assetid: 8d10659e-97d6-4cd1-9b4d-307afd43c763
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d27a44d67ce7b95e06e07fd2be425688733b7bc8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385067"
---
# <a name="how-to-enrich-bam-data-using-lookups"></a>照合を使用して BAM データを強化する方法
これで操作時に、使用可能なデータを含まないレポート目的で必要なすべてのケースがあります。 たとえば、実行時に、ProductID、ProductName ではないがあります。 BAM アクティビティ データが実際に収集する方法に依存しない抽象化を表すためには、"ProductName"レポートに表示する最終的なデータとしてという名前の項目を含めることが必要があります。 その他のアイテムと同様はマイルス トーン グループ、期間、ディメンション、メジャーなどの解釈型の構造でこれを使用できます。 ProductName が実行時に使用できないため、ProductID など、照合を実行するための十分な追加データを取得する必要があります。  
  
 レポートに必要なデータではなく、同じ列のデータを収集する必要があります。 たとえば、実行時に ProductName ではなく ProductID を収集する必要があります。 多くの列が必要な場合、アクティビティの他のアイテムを作成することが任意のビューでは使用しないが。  
  
### <a name="to-enrich-bam-data-via-lookups"></a>照合によって BAM データを強化するには  
  
1.  BAM 定義を展開します。  
  
2.  SQL Server Management studio では、リモート サーバーとして関心のあるデータを格納しているサーバーを追加します。  
  
3.  Bam_an _ という名前のデータ分析パッケージを探します`<View Name>`します。 たとえば、ビューが SalesMgr の場合は bam_an_salesmgr します。  
  
4.  パッケージ (たとえば、100%) のビューを拡大するズームを設定します。  
  
5.  照合に使用する場合は、SQL の接続を追加します。  
  
6.  「クリーンアップ ステージング」ステップの後に、データ変換タスクを探します。 これは、データを移動する、PrimaryImport から StarSchema データベースにします。 このタスクの 2 つのインスタンスがある-完了したアクティビティと進行中にあるものの 1 つ。 両方のタスクには、すべての残りの手順を適用します。  
  
7.  [変換] をクリックします。  
  
8.  検索を選択します。"lookupproductbyid"参照の接続を使用しての追加 (SQL オンライン ブックの参照を参照してください)。 たとえば、参照には、単純なテーブル"LookupProduct"の場合、ProductID、ProductName の列を持つ検索のテキストになります。  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. [変換] タブをクリックします。既定のデータ変換"Transform"を削除し、代わりに ActiveX 変換を作成します。 ソース列 をクリックし、すべての列を追加します。 変換先列をクリックし、すべての列を追加します。  
  
10. [全般] タブ、および [プロパティ] をクリックします。 これは、結果に示すように自明なコピー変換を実行するスクリプトの自動生成。  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. 示すように、参照を使用して、値を変更します。  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. 保存し、そのパッケージを実行します。  
  
13. 正しいデータが OLAP キューブ終了することを確認します。 BAM から自動生成されたステップだけでなくが、カスタム コードが含まれているために、VBScript または構造化ストレージ ファイルとしてパッケージを保存する必要があります。  
  
> [!NOTE]
>  検索は、DTS と OLAP を使用して実行するスケジュールされたレポートに対してのみ機能します。 リアルタイム集計で収集される情報とは異なるデータが必要な場合は、BAM API を呼び出す前に、データを取得する必要があります。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティの使用の監視](../core/using-business-activity-monitoring.md)   
 [ローカライズされた BAM XML ファイルの展開](../core/deploying-localized-bam-xml-files.md)
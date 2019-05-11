---
title: カスタム分析タスクを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, DTS tasks
- DTS tasks
- DTS packages, tasks
- BAM, processing
ms.assetid: 6046c113-fb58-4e72-8f48-5470e52be9a8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2afeae7dba801e1724e30e88d68ea454d87b228f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340081"
---
# <a name="how-to-create-a-custom-analysis-task"></a>カスタム分析タスクを作成する方法
BAM データを処理するためのカスタム DTS タスクを作成する最も簡単な方法では、BAM によって自動生成であるパッケージから始めることですし、実際のすべてのデータ処理を置き換えます。  
  
### <a name="to-create-a-custom-dts-task"></a>カスタム DTS タスクを作成するには  
  
1. OLAP キューブを必要とする BAM 定義を作成します。 たとえば、Excel のウィザードを使用し、1 つの PivotTable® レポートを RTA 以外のビューとしてのままにします。  
  
2. BAM を作成するキューブの処理のための DTS パッケージを開きます。 BAM では、各ビューは、bam_an _ と呼ばれるこのような 1 つのパッケージを作成します。\<*ビュー名*\>します。  
  
3. DTS デザイナーでパッケージを開き、最初の 2 つの手順と、最後の手順を除くすべての手順を削除します。 プライマリ インポート データベースへの接続を維持することもできます。  
  
4. ActiveX® の最初のタスクのプロパティを編集します。 削除の手順を参照しているため、DTSGlobalVariables.Parent.Steps が含まれているすべての行を削除します。 スクリプトから始まります。  
  
   ```  
   serverName = "<your server here>"   
   databaseName = "<your analysis database here>"  
   cubeName = "<your cube name here>"  
   ```  
  
   > [!NOTE]
   >  タスク データ分析開始""(パッケージ内の 2 番目のタスク) は、パッケージを提供するために非常に重要です。  
   > 
   > - 完了したアクティビティ (動的 SQL ビュー _ (BamView) _View (Activity) _CompletedInstancesWindow という名前の増分処理用の移動ウィンドウ  
   >   -   進行状況 - bam をという名前のテーブルに含まれるアクティビティのスナップショット\_(BamView) _View (Activity) _ActiveInstancesSnapshot します。  
  
5. ビューとテーブルを挿入しないデータ、データが、プライマリ インポート データベースの瞬間のスナップショットを表すように、短いトランザクションで取得します。 ビューとデータの入力としてテーブルに基づいて、実際のデータ変換の 1 つまたは複数の手順を実装します。 分析タスクの目的が OLAP キューブの設定以外の場合は、ジョブが、最後にコミットされ、最初の ActiveX タスクこのタイムスタンプをグローバル変数に代入するコードを置き換えますのタイムスタンプを保持ください"Completedcubelastprocesstime"に割り当てる。 2 番目のタスクでは、この変数を使用して、失敗したデータがないことと、2 回、クラッシュが発生した場合にデータが処理があるかどうかを確認し、DTS パッケージの再起動します。  
  
6. 最後に、「データ分析終了」である最後のタスクを呼び出す必要があります。 このタスクは、アーカイブして、オンライン時間帯外にあるときと、プライマリ インポートから削除できるように、処理された完了したアクティビティを解放します。  
  
## <a name="see-also"></a>参照  
 [ビジネス アクティビティの使用の監視](../core/using-business-activity-monitoring.md)
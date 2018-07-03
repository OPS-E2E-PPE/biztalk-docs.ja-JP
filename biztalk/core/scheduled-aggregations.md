---
title: スケジュール済みの集計 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- scheduling, aggregations [BAM]
- aggregations [BAM], scheduling
ms.assetid: 4e2da2eb-b1fc-4b27-98d6-564e6df719e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04aaf0a3eefb018dbe23f3e05e7e684b595820d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998476"
---
# <a name="scheduled-aggregations"></a>スケジュール済みの集計
BAM では、動的に生成された OLAP キューブとデータ変換サービス (DTS) パッケージに基づいてスケジュール済みの集計を行います。 スケジュール済みの集計に含まれるデータは、DTS パッケージを実行したときのビジネス アクティビティのスナップショットを表します。 これを実現する分析のための DTS パッケージの最初の手順には、ストアド プロシージャの呼び出し**bam_Metadata_BeginAnalysis**から成るスナップショットを取得します。  
  
- 実行中のすべてのアクティビティ インスタンスのスナップショット コピー  
  
- 前回 DTS パッケージを実行してからスナップショットが生成されるまでの間に完了したアクティビティ インスタンスの増加時間帯を表すビュー  
  
  BAM では、集計を行う際、非常に短い時間だけアクティビティ ストレージに排他ロックを保持して、同時にデータが書き込まれないようにしています。 BAM でスナップショットの生成が開始されると、DTS パッケージの実行に時間がかかることがありますが、BAM では処理中に受け取った新しいデータは無視されます。 このアクティビティは、次の図のようになります。  
  
  ![](../core/media/ebiz-prog-bam-data-maint-fig9.gif "ebiz_prog_bam_data_maint_fig9")  
  BAM のスケジュール済みの集計  
  
  上の図では、BAM は完了したアクティビティ インスタンスに関するデータを完成したインスタンスの OLAP キューブに移動しています。 BAM では、このキューブを増分処理します。  
  
  同時に、実行中のアクティビティに関するデータは、DTS パッケージにより完全処理されるアクティブなインスタンスのキューブに移動します。 BAM では、どの時点においても、実行中のアクティビティの数は比較的少ないことが想定されているため、このようなデータの移動により問題が発生することはありません。  
  
  スケジュール済みの集計データは、完了したアクティビティと実行中のアクティビティ間の差分を埋め合わせている仮想キューブから利用できます。 詳細については、次を参照してください。[スケジュールされた集計データのクエリを実行する](../core/querying-scheduled-aggregated-data.md)します。  
  
## <a name="see-also"></a>参照  
 [集計について](../core/what-is-an-aggregation.md)
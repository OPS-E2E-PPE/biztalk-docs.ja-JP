---
title: スケジュールされているクエリを実行する集計データ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, scheduled data
- queries [BAM], scheduled data
ms.assetid: fb785ec0-7862-4d83-bb6f-0ebd69a28ce6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aed1d63b1ebd1e54fd229236a94f3ac9a5f6837
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970864"
---
# <a name="querying-scheduled-aggregated-data"></a>スケジュール済み集計データに対するクエリの実行
BAM 分析データベースで動的に作成された OLAP キューブを使用して、スケジュール済み集計データに対してクエリを実行できます。  
  
 このキューブの名前は、BAM 定義 XML 内にある View 要素の Name 属性に該当し、Excel ウィザードに入力されたビュー名と同じです。 データ変換サービス (DTS) パッケージ bam_an _ を実行するときに、BAM がこのキューブを更新\<*ViewName*\>、場所、 \< *ViewName* \>Excel ウィザードに使用するビューの名前の説明です。  
  
 スケジュール済み集計のデータに対してクエリを実行する際は、次の条件に特に注意してください。  
  
-   このキューブは、DTS パッケージの実行が開始した時点のビジネスのスナップショットを含んでいる仮想キューブです。 完了したアクティビティと進行中のアクティビティの両方の集計が含まれています。 進捗ディメンションに従って集計をフィルター処理またはグループ化できます。  
  
-   対応する実際のキューブのクエリを実行できます (たとえば、非常に高速完了) 場合、現在の活動に関心は場合\< *ViewName*\>#Completed です。  
  
-   リアルタイムの集計も行う場合は、リアルタイムの集計用に設定したオンライン ウィンドウよりも頻繁にキューブを更新するように DTS パッケージをスケジュールします。 そうしないと、集計が行われない時間帯が生じます。  
  
## <a name="see-also"></a>参照  
 [BAM データのクエリ](../core/querying-bam-data.md)
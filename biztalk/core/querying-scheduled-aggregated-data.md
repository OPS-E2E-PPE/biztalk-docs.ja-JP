---
title: スケジュールされたクエリを実行する集計データ |Microsoft Docs
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
ms.openlocfilehash: 2d088f0affe630ecf2df727cc89ceffc6f82855d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398267"
---
# <a name="querying-scheduled-aggregated-data"></a>スケジュール済み集計データに対するクエリの実行
スケジュール済み集計データは、BAM 分析データベースで動的に作成された OLAP キューブを使用してクエリを使用できます。  
  
 このキューブの名前は、Excel ウィザードに入力されたビュー名と同じである、BAM 定義 XML 内の View 要素の Name 属性の場合と同じです。 BAM データ変換サービス (DTS) パッケージ bam_an _ を実行するときに、このキューブを更新します\<*ViewName*\>、場所、 \< *ViewName* \>Excel ウィザードに使用するビューの名前の説明です。  
  
 スケジュール済み集計データを照会するときに、次の条件を確認する必要があります。  
  
-   これは、DTS パッケージの実行が開始される正確な時点で、ビジネスのスナップショットを含む仮想キューブです。 完了したアクティビティとものの両方の集計が含まれている実行中です。 使用できます、進捗ディメンションのフィルターまたはグループに集計それに応じて。  
  
-   対応する実際のキューブのクエリを実行できることはありません (たとえば、高速なして完了した) 場合、現在のアクティビティにしたい場合\< *ViewName*\>#Completed します。  
  
-   リアルタイム集計もある場合は、リアルタイム集計を設定したオンライン ウィンドウよりも頻繁にキューブを更新するための DTS パッケージのスケジュールを設定します。 それ以外の場合、集計のない時間帯があります。  
  
## <a name="see-also"></a>参照  
 [BAM データのクエリ](../core/querying-bam-data.md)
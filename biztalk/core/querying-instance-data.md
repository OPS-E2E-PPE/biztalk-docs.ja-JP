---
title: インスタンス データの照会 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, instance data
- queries [BAM], instance data
ms.assetid: ae4a8854-d5c2-4b36-a0ef-3f74e138306e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e43310756cf12c0c2a48eb6716221afc5395ecb0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971832"
---
# <a name="querying-instance-data"></a>インスタンス データへのクエリ
BAM プライマリ インポート データベースに動的に作成される SQL ビューのクエリには、個別のアクティビティ インスタンスについての情報を使用できます。  
  
 クエリでのビューの名前は次のようになります。  
  
 **bam _\<**  *ViewName*  **\>_\<**  *ActivityName*  **\>_View**  
  
 場所  
  
 **\<***ViewName*  **\>**  BAM 定義 XML 内の View 要素の Name 属性は、関連する Microsoft Excel ウィザードに入力されたビュー名と同じです。  
  
 **\<***ActivityName*  **\>**  BAM 定義 XML 内の Activity 要素の Name 属性は、Excel ウィザードに入力されたアクティビティ名と同じです。  
  
 インスタンス データにクエリを実行する際は、次の条件に注意することが重要です。  
  
-   DirectEventStream を使用してアクティビティ データを BAM に送信すると、インスタンス データは、呼び出し元アプリケーションでトランザクションをコミットすると直ちに表示されます。つまり、待機時間がありません。  
  
-   BufferedEventStream を使用してアクティビティ データを BAM に送信すると、インスタンス データは数秒後にクエリに表示されます。待機時間は、BAM イベント バス サービスと、BAM プライマリ インポート データベースをホストする SQL Server の負荷によって異なります。  
  
-   このビューに含まれるテーブルの実際の構造は、ここで説明したよりも複雑であり、最新または最近のアクティビティのデータをクエリで使用できるようにすることと、完了してアクティビティ クエリに必要なくなったアクティビティのデータを、システムをオフラインにすることなくアーカイブまたは削除することを両立しています。 詳細については、次を参照してください。[アクティビティ データのストレージ](../core/activity-data-storage.md)です。  
  
## <a name="see-also"></a>参照  
 [アクティビティ データのストレージ](../core/activity-data-storage.md)   
 [BAM データのクエリ](../core/querying-bam-data.md)
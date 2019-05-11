---
title: インスタンス データのクエリ |Microsoft Docs
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
ms.openlocfilehash: 083bbe25734f5305c2c7e49837955f648a65a52d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398305"
---
# <a name="querying-instance-data"></a>インスタンス データへのクエリ
個々 のアクティビティ インスタンスに関するデータが BAM プライマリ インポート データベースに動的に作成された SQL ビューでのクエリの使用です。  
  
 クエリでのビューの名前は次のようになります。  
  
 **bam _\<**  *ViewName* **\>_\<** *ActivityName* **\>表示 (_v)**  
  
 場所  
  
 **\<** *ViewName* **\>** は、BAM 定義 XML 内の View 要素の Name 属性、関連する Microsoft Excel ウィザードに入力されたビューの名前と同じです。  
  
 **\<** *ActivityName* **\>** BAM 定義 XML 内の Activity 要素の Name 属性は、Excel ウィザードに入力されたアクティビティ名と同じです。  
  
 インスタンス データを照会するときに、次の条件を確認する必要があります。  
  
-   DirectEventStream を使用して bam アクティビティ データを送信する場合は、インスタンス データに表示される瞬時に呼び出し元のアプリケーションでトランザクションがコミットされたときに、待機時間はありません。  
  
-   BufferedEventStream を使用して bam アクティビティ データを送信する場合、インスタンス データが表示されます、BAM イベント バス サービスと、BAM プライマリ インポート データベースをホストする SQL server の負荷に応じて数秒後を照会します。  
  
-   このビューの背後にあるテーブルの実際の構造は、現在または最近のアクティビティのデータがクエリでは、使用可能な活動が完了し、アクティブなクエリが不要のデータをアーカイブまたは削除中にあることを確認するより複雑ですせず、システムをオフラインにします。 詳細については、次を参照してください。[アクティビティ データのストレージ](../core/activity-data-storage.md)します。  
  
## <a name="see-also"></a>参照  
 [アクティビティ データのストレージ](../core/activity-data-storage.md)   
 [BAM データのクエリ](../core/querying-bam-data.md)
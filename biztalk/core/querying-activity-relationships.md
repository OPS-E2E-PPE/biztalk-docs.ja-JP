---
title: "アクティビティの関係を照会 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, activity relationships
- queries [BAM], relationships
ms.assetid: e3d42b7c-cc11-4707-9095-cfc518902b26
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70c94644e505409f863e5104168740232d57c664
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="querying-activity-relationships"></a>アクティビティ リレーションシップに対するクエリの実行
アクティビティ リレーションシップ情報は、アクティビティごとに動的に生成される SQL ビューで閲覧できます。 クエリでのビューの名前は次のようになります。  
  
 **bam _\<**  *アクティビティ*  **\>_AllRelationships**  
  
 ここで\<*アクティビティ*\> BAM 定義 XML 内の Activity 要素の Name 属性は、Excel 用 BAM アドインを使用して入力されたアクティビティ名と同じです。  
  
 リレーションシップ イベントは、特定のアクティビティのコンテキスト内で発生します。 たとえば、発注と出荷間のリレーションシップは、発注アクティビティのコンテキストで発生する場合、リレーションシップ レコードに表示されます**bam_PurchaseOrder_AllRelationships**ではなく**bam_Shipment_AllRelationships**です。 詳細については、次を参照してください。[アクティビティ リレーションシップ](../core/activity-relationships.md)です。  
  
 購入に関連するアクティビティの順序、両方のビューをクエリする必要がありますすべてを検索する**bam_PurchaseOrder_AllRelationships**のすべてのビューだけでなく**bam _\<***OtherActivity*  **\>_AllRelationships**ここで、 \< *OtherActivity* \>同じ BAM ビューで、アクティビティです。  
  
 リレーションシップ レコードは、アクティビティ インスタンスの一部および」の説明に従って、インスタンス データとの同期を管理、[アクティビティ データのストレージ](../core/activity-data-storage.md)です。  
  
## <a name="see-also"></a>参照  
 [BAM データのクエリ](../core/querying-bam-data.md)
---
title: アクティビティ リレーションシップのクエリを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, activity relationships
- queries [BAM], relationships
ms.assetid: e3d42b7c-cc11-4707-9095-cfc518902b26
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eb6c74ddd5a480f3e4048079e346cf23570c1f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398320"
---
# <a name="querying-activity-relationships"></a>アクティビティ リレーションシップに対するクエリの実行
アクティビティ リレーションシップ情報は、アクティビティごとに動的に生成される SQL ビューで閲覧できます。 クエリでのビューの名前は次のようになります。  
  
 **bam _\<**  *アクティビティ*  **\>_AllRelationships**  
  
 場所\<*アクティビティ*\> BAM 定義 XML 内の Activity 要素の Name 属性は、Excel 用 BAM アドインを使用して入力されたアクティビティ名と同じです。  
  
 リレーションシップ イベントは、特定のアクティビティのコンテキスト内で発生します。 たとえば、発注と出荷間のリレーションシップが発注アクティビティのコンテキストで発生した場合、リレーションシップ レコードに表示**bam_PurchaseOrder_AllRelationships**ではなく**bam_Shipment_AllRelationships**します。 詳細については、次を参照してください。[アクティビティ リレーションシップ](../core/activity-relationships.md)します。  
  
 購入に関連するアクティビティの順序、両方のビューをクエリする必要がありますすべてを検索する**bam_PurchaseOrder_AllRelationships**すべてのビューと**bam _\<**<em>OtherActivity</em>  **\>_AllRelationships**ここで、 \< *OtherActivity* \>同じ BAM ビューでアクティビティします。  
  
 リレーションシップ レコードはアクティビティ インスタンスの一部であり、」の説明に従って、インスタンス データとの同期でサポートされており[アクティビティ データのストレージ](../core/activity-data-storage.md)します。  
  
## <a name="see-also"></a>参照  
 [BAM データのクエリ](../core/querying-bam-data.md)
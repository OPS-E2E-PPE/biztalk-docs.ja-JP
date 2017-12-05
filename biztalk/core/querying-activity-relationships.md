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
# <a name="querying-activity-relationships"></a><span data-ttu-id="f64da-102">アクティビティ リレーションシップに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="f64da-102">Querying Activity Relationships</span></span>
<span data-ttu-id="f64da-103">アクティビティ リレーションシップ情報は、アクティビティごとに動的に生成される SQL ビューで閲覧できます。</span><span class="sxs-lookup"><span data-stu-id="f64da-103">The activity relationship information is available in a dynamically created SQL view for each activity.</span></span> <span data-ttu-id="f64da-104">クエリでのビューの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f64da-104">The name of this view is</span></span>  
  
 <span data-ttu-id="f64da-105">**bam _\<**  *アクティビティ*  **\>_AllRelationships**</span><span class="sxs-lookup"><span data-stu-id="f64da-105">**bam_\<** *Activity* **\>_AllRelationships**</span></span>  
  
 <span data-ttu-id="f64da-106">ここで\<*アクティビティ*\> BAM 定義 XML 内の Activity 要素の Name 属性は、Excel 用 BAM アドインを使用して入力されたアクティビティ名と同じです。</span><span class="sxs-lookup"><span data-stu-id="f64da-106">Where \<*Activity*\> is the Name attribute of the Activity element in the BAM definition XML, which is the same as the Activity name entered using the BAM Add-in for Excel.</span></span>  
  
 <span data-ttu-id="f64da-107">リレーションシップ イベントは、特定のアクティビティのコンテキスト内で発生します。</span><span class="sxs-lookup"><span data-stu-id="f64da-107">The relationship events occur in the context of a specific activity.</span></span> <span data-ttu-id="f64da-108">たとえば、発注と出荷間のリレーションシップは、発注アクティビティのコンテキストで発生する場合、リレーションシップ レコードに表示されます**bam_PurchaseOrder_AllRelationships**ではなく**bam_Shipment_AllRelationships**です。</span><span class="sxs-lookup"><span data-stu-id="f64da-108">For example, if the relationship between Purchase Order and Shipment occurs in the context of the Purchase Order activity, the Relationship record will show up in **bam_PurchaseOrder_AllRelationships**, but not in **bam_Shipment_AllRelationships**.</span></span> <span data-ttu-id="f64da-109">詳細については、次を参照してください。[アクティビティ リレーションシップ](../core/activity-relationships.md)です。</span><span class="sxs-lookup"><span data-stu-id="f64da-109">For more information, see [Activity Relationships](../core/activity-relationships.md).</span></span>  
  
 <span data-ttu-id="f64da-110">購入に関連するアクティビティの順序、両方のビューをクエリする必要がありますすべてを検索する**bam_PurchaseOrder_AllRelationships**のすべてのビューだけでなく**bam _\<***OtherActivity*  **\>_AllRelationships**ここで、 \< *OtherActivity* \>同じ BAM ビューで、アクティビティです。</span><span class="sxs-lookup"><span data-stu-id="f64da-110">To find all the related activities to a purchase order you need to query both the view **bam_PurchaseOrder_AllRelationships** as well as all views **bam_\<***OtherActivity***\>_AllRelationships**, where \<*OtherActivity*\> is the activity in the same BAM view.</span></span>  
  
 <span data-ttu-id="f64da-111">リレーションシップ レコードは、アクティビティ インスタンスの一部および」の説明に従って、インスタンス データとの同期を管理、[アクティビティ データのストレージ](../core/activity-data-storage.md)です。</span><span class="sxs-lookup"><span data-stu-id="f64da-111">The relationship records are part of the activity instance and they are maintained in synchronization with the instance data as described in [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f64da-112">参照</span><span class="sxs-lookup"><span data-stu-id="f64da-112">See Also</span></span>  
 [<span data-ttu-id="f64da-113">BAM データのクエリ</span><span class="sxs-lookup"><span data-stu-id="f64da-113">Querying BAM Data</span></span>](../core/querying-bam-data.md)
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
# <a name="querying-instance-data"></a><span data-ttu-id="505c3-102">インスタンス データへのクエリ</span><span class="sxs-lookup"><span data-stu-id="505c3-102">Querying Instance Data</span></span>
<span data-ttu-id="505c3-103">個々 のアクティビティ インスタンスに関するデータが BAM プライマリ インポート データベースに動的に作成された SQL ビューでのクエリの使用です。</span><span class="sxs-lookup"><span data-stu-id="505c3-103">The data about individual activity instances is available for queries in a dynamically created SQL View in the BAM Primary Import Database.</span></span>  
  
 <span data-ttu-id="505c3-104">クエリでのビューの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="505c3-104">The name of this view is</span></span>  
  
 <span data-ttu-id="505c3-105">**bam _\<**  *ViewName* **\>_\<** *ActivityName* **\>表示 (_v)**</span><span class="sxs-lookup"><span data-stu-id="505c3-105">**bam_\<** *ViewName* **\>_\<** *ActivityName* **\>_View**</span></span>  
  
 <span data-ttu-id="505c3-106">場所</span><span class="sxs-lookup"><span data-stu-id="505c3-106">Where</span></span>  
  
 <span data-ttu-id="505c3-107">**\<** *ViewName* **\>** は、BAM 定義 XML 内の View 要素の Name 属性、関連する Microsoft Excel ウィザードに入力されたビューの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="505c3-107">**\<** *ViewName* **\>** is the Name Attribute of the View element in the BAM Definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="505c3-108">**\<** *ActivityName* **\>** BAM 定義 XML 内の Activity 要素の Name 属性は、Excel ウィザードに入力されたアクティビティ名と同じです。</span><span class="sxs-lookup"><span data-stu-id="505c3-108">**\<** *ActivityName* **\>** is the Name Attribute of the Activity element in the BAM Definition XML, which is the same as the Activity Name entered in the Excel wizards.</span></span>  
  
 <span data-ttu-id="505c3-109">インスタンス データを照会するときに、次の条件を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="505c3-109">It is important to note the following conditions when querying instance data:</span></span>  
  
-   <span data-ttu-id="505c3-110">DirectEventStream を使用して bam アクティビティ データを送信する場合は、インスタンス データに表示される瞬時に呼び出し元のアプリケーションでトランザクションがコミットされたときに、待機時間はありません。</span><span class="sxs-lookup"><span data-stu-id="505c3-110">If you send activity data to BAM via the DirectEventStream, the instance data has no latency, meaning that it appears instantaneously when the transaction in the calling application commits.</span></span>  
  
-   <span data-ttu-id="505c3-111">BufferedEventStream を使用して bam アクティビティ データを送信する場合、インスタンス データが表示されます、BAM イベント バス サービスと、BAM プライマリ インポート データベースをホストする SQL server の負荷に応じて数秒後を照会します。</span><span class="sxs-lookup"><span data-stu-id="505c3-111">If the activity data is sent to BAM via the BufferedEventStream, the instance data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service and the SQL server that hosts the BAM Primary Import Database.</span></span>  
  
-   <span data-ttu-id="505c3-112">このビューの背後にあるテーブルの実際の構造は、現在または最近のアクティビティのデータがクエリでは、使用可能な活動が完了し、アクティブなクエリが不要のデータをアーカイブまたは削除中にあることを確認するより複雑ですせず、システムをオフラインにします。</span><span class="sxs-lookup"><span data-stu-id="505c3-112">The actual structure of tables behind this view is more complex to ensure that the data for the current or recent activities is available for queries, while data for activities that have completed and is no longer required for active queries is archived or purged without taking the system offline.</span></span> <span data-ttu-id="505c3-113">詳細については、次を参照してください。[アクティビティ データのストレージ](../core/activity-data-storage.md)します。</span><span class="sxs-lookup"><span data-stu-id="505c3-113">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="505c3-114">参照</span><span class="sxs-lookup"><span data-stu-id="505c3-114">See Also</span></span>  
 <span data-ttu-id="505c3-115">[アクティビティ データのストレージ](../core/activity-data-storage.md) </span><span class="sxs-lookup"><span data-stu-id="505c3-115">[Activity Data Storage](../core/activity-data-storage.md) </span></span>  
 [<span data-ttu-id="505c3-116">BAM データのクエリ</span><span class="sxs-lookup"><span data-stu-id="505c3-116">Querying BAM Data</span></span>](../core/querying-bam-data.md)
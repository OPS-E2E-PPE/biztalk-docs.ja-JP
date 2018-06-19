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
# <a name="querying-instance-data"></a><span data-ttu-id="ebb08-102">インスタンス データへのクエリ</span><span class="sxs-lookup"><span data-stu-id="ebb08-102">Querying Instance Data</span></span>
<span data-ttu-id="ebb08-103">BAM プライマリ インポート データベースに動的に作成される SQL ビューのクエリには、個別のアクティビティ インスタンスについての情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebb08-103">The data about individual activity instances is available for queries in a dynamically created SQL View in the BAM Primary Import Database.</span></span>  
  
 <span data-ttu-id="ebb08-104">クエリでのビューの名前は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ebb08-104">The name of this view is</span></span>  
  
 <span data-ttu-id="ebb08-105">**bam _\<**  *ViewName*  **\>_\<**  *ActivityName*  **\>_View**</span><span class="sxs-lookup"><span data-stu-id="ebb08-105">**bam_\<** *ViewName* **\>_\<** *ActivityName* **\>_View**</span></span>  
  
 <span data-ttu-id="ebb08-106">場所</span><span class="sxs-lookup"><span data-stu-id="ebb08-106">Where</span></span>  
  
 <span data-ttu-id="ebb08-107">**\<***ViewName*  **\>**  BAM 定義 XML 内の View 要素の Name 属性は、関連する Microsoft Excel ウィザードに入力されたビュー名と同じです。</span><span class="sxs-lookup"><span data-stu-id="ebb08-107">**\<** *ViewName* **\>** is the Name Attribute of the View element in the BAM Definition XML, which is the same as the View Name entered in the related Microsoft Excel wizards.</span></span>  
  
 <span data-ttu-id="ebb08-108">**\<***ActivityName*  **\>**  BAM 定義 XML 内の Activity 要素の Name 属性は、Excel ウィザードに入力されたアクティビティ名と同じです。</span><span class="sxs-lookup"><span data-stu-id="ebb08-108">**\<** *ActivityName* **\>** is the Name Attribute of the Activity element in the BAM Definition XML, which is the same as the Activity Name entered in the Excel wizards.</span></span>  
  
 <span data-ttu-id="ebb08-109">インスタンス データにクエリを実行する際は、次の条件に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ebb08-109">It is important to note the following conditions when querying instance data:</span></span>  
  
-   <span data-ttu-id="ebb08-110">DirectEventStream を使用してアクティビティ データを BAM に送信すると、インスタンス データは、呼び出し元アプリケーションでトランザクションをコミットすると直ちに表示されます。つまり、待機時間がありません。</span><span class="sxs-lookup"><span data-stu-id="ebb08-110">If you send activity data to BAM via the DirectEventStream, the instance data has no latency, meaning that it appears instantaneously when the transaction in the calling application commits.</span></span>  
  
-   <span data-ttu-id="ebb08-111">BufferedEventStream を使用してアクティビティ データを BAM に送信すると、インスタンス データは数秒後にクエリに表示されます。待機時間は、BAM イベント バス サービスと、BAM プライマリ インポート データベースをホストする SQL Server の負荷によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ebb08-111">If the activity data is sent to BAM via the BufferedEventStream, the instance data will show up for queries a few seconds later, depending on the load of the BAM Event Bus service and the SQL server that hosts the BAM Primary Import Database.</span></span>  
  
-   <span data-ttu-id="ebb08-112">このビューに含まれるテーブルの実際の構造は、ここで説明したよりも複雑であり、最新または最近のアクティビティのデータをクエリで使用できるようにすることと、完了してアクティビティ クエリに必要なくなったアクティビティのデータを、システムをオフラインにすることなくアーカイブまたは削除することを両立しています。</span><span class="sxs-lookup"><span data-stu-id="ebb08-112">The actual structure of tables behind this view is more complex to ensure that the data for the current or recent activities is available for queries, while data for activities that have completed and is no longer required for active queries is archived or purged without taking the system offline.</span></span> <span data-ttu-id="ebb08-113">詳細については、次を参照してください。[アクティビティ データのストレージ](../core/activity-data-storage.md)です。</span><span class="sxs-lookup"><span data-stu-id="ebb08-113">For more information, see [Activity Data Storage](../core/activity-data-storage.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb08-114">参照</span><span class="sxs-lookup"><span data-stu-id="ebb08-114">See Also</span></span>  
 <span data-ttu-id="ebb08-115">[アクティビティ データのストレージ](../core/activity-data-storage.md) </span><span class="sxs-lookup"><span data-stu-id="ebb08-115">[Activity Data Storage](../core/activity-data-storage.md) </span></span>  
 [<span data-ttu-id="ebb08-116">BAM データのクエリ</span><span class="sxs-lookup"><span data-stu-id="ebb08-116">Querying BAM Data</span></span>](../core/querying-bam-data.md)
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
# <a name="querying-scheduled-aggregated-data"></a><span data-ttu-id="87899-102">スケジュール済み集計データに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="87899-102">Querying Scheduled Aggregated Data</span></span>
<span data-ttu-id="87899-103">BAM 分析データベースで動的に作成された OLAP キューブを使用して、スケジュール済み集計データに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="87899-103">Scheduled aggregation data is available to queries through dynamically created OLAP cubes in the  BAM Analysis database.</span></span>  
  
 <span data-ttu-id="87899-104">このキューブの名前は、BAM 定義 XML 内にある View 要素の Name 属性に該当し、Excel ウィザードに入力されたビュー名と同じです。</span><span class="sxs-lookup"><span data-stu-id="87899-104">The name of this cube is the same as the Name attribute of the View element in the BAM definition XML, which is the same as the view name entered in the Excel wizards.</span></span> <span data-ttu-id="87899-105">データ変換サービス (DTS) パッケージ bam_an _ を実行するときに、BAM がこのキューブを更新\<*ViewName*\>、場所、 \< *ViewName* \>Excel ウィザードに使用するビューの名前の説明です。</span><span class="sxs-lookup"><span data-stu-id="87899-105">BAM refreshes this cube when you run the Data Transformation Services (DTS) package BAM_AN_\<*ViewName*\>, where the \<*ViewName*\> is the name of the view described you used in the Excel wizards.</span></span>  
  
 <span data-ttu-id="87899-106">スケジュール済み集計のデータに対してクエリを実行する際は、次の条件に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="87899-106">It is important to note the following conditions when querying scheduled aggregated data:</span></span>  
  
-   <span data-ttu-id="87899-107">このキューブは、DTS パッケージの実行が開始した時点のビジネスのスナップショットを含んでいる仮想キューブです。</span><span class="sxs-lookup"><span data-stu-id="87899-107">This is a virtual cube containing a snapshot of the business at the exact moment that the DTS package execution started.</span></span> <span data-ttu-id="87899-108">完了したアクティビティと進行中のアクティビティの両方の集計が含まれています。</span><span class="sxs-lookup"><span data-stu-id="87899-108">It contains aggregations both for the completed activities and for the ones still in progress.</span></span> <span data-ttu-id="87899-109">進捗ディメンションに従って集計をフィルター処理またはグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="87899-109">You can use the progress dimension to filter or group the aggregations accordingly.</span></span>  
  
-   <span data-ttu-id="87899-110">対応する実際のキューブのクエリを実行できます (たとえば、非常に高速完了) 場合、現在の活動に関心は場合\< *ViewName*\>#Completed です。</span><span class="sxs-lookup"><span data-stu-id="87899-110">If you are never interested in the current activities (for example, if they complete very fast) you can query the corresponding real cube \<*ViewName*\>#Completed.</span></span>  
  
-   <span data-ttu-id="87899-111">リアルタイムの集計も行う場合は、リアルタイムの集計用に設定したオンライン ウィンドウよりも頻繁にキューブを更新するように DTS パッケージをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="87899-111">If you also have real-time aggregations, schedule the DTS package for refreshing the cube more frequently than the online window you set for the real-time aggregations.</span></span> <span data-ttu-id="87899-112">そうしないと、集計が行われない時間帯が生じます。</span><span class="sxs-lookup"><span data-stu-id="87899-112">Otherwise, there will be a window of time for which you do not have aggregations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87899-113">参照</span><span class="sxs-lookup"><span data-stu-id="87899-113">See Also</span></span>  
 [<span data-ttu-id="87899-114">BAM データのクエリ</span><span class="sxs-lookup"><span data-stu-id="87899-114">Querying BAM Data</span></span>](../core/querying-bam-data.md)
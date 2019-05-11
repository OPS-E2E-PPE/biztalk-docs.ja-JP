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
# <a name="querying-scheduled-aggregated-data"></a><span data-ttu-id="8976e-102">スケジュール済み集計データに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="8976e-102">Querying Scheduled Aggregated Data</span></span>
<span data-ttu-id="8976e-103">スケジュール済み集計データは、BAM 分析データベースで動的に作成された OLAP キューブを使用してクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8976e-103">Scheduled aggregation data is available to queries through dynamically created OLAP cubes in the  BAM Analysis database.</span></span>  
  
 <span data-ttu-id="8976e-104">このキューブの名前は、Excel ウィザードに入力されたビュー名と同じである、BAM 定義 XML 内の View 要素の Name 属性の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="8976e-104">The name of this cube is the same as the Name attribute of the View element in the BAM definition XML, which is the same as the view name entered in the Excel wizards.</span></span> <span data-ttu-id="8976e-105">BAM データ変換サービス (DTS) パッケージ bam_an _ を実行するときに、このキューブを更新します\<*ViewName*\>、場所、 \< *ViewName* \>Excel ウィザードに使用するビューの名前の説明です。</span><span class="sxs-lookup"><span data-stu-id="8976e-105">BAM refreshes this cube when you run the Data Transformation Services (DTS) package BAM_AN_\<*ViewName*\>, where the \<*ViewName*\> is the name of the view described you used in the Excel wizards.</span></span>  
  
 <span data-ttu-id="8976e-106">スケジュール済み集計データを照会するときに、次の条件を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8976e-106">It is important to note the following conditions when querying scheduled aggregated data:</span></span>  
  
-   <span data-ttu-id="8976e-107">これは、DTS パッケージの実行が開始される正確な時点で、ビジネスのスナップショットを含む仮想キューブです。</span><span class="sxs-lookup"><span data-stu-id="8976e-107">This is a virtual cube containing a snapshot of the business at the exact moment that the DTS package execution started.</span></span> <span data-ttu-id="8976e-108">完了したアクティビティとものの両方の集計が含まれている実行中です。</span><span class="sxs-lookup"><span data-stu-id="8976e-108">It contains aggregations both for the completed activities and for the ones still in progress.</span></span> <span data-ttu-id="8976e-109">使用できます、進捗ディメンションのフィルターまたはグループに集計それに応じて。</span><span class="sxs-lookup"><span data-stu-id="8976e-109">You can use the progress dimension to filter or group the aggregations accordingly.</span></span>  
  
-   <span data-ttu-id="8976e-110">対応する実際のキューブのクエリを実行できることはありません (たとえば、高速なして完了した) 場合、現在のアクティビティにしたい場合\< *ViewName*\>#Completed します。</span><span class="sxs-lookup"><span data-stu-id="8976e-110">If you are never interested in the current activities (for example, if they complete very fast) you can query the corresponding real cube \<*ViewName*\>#Completed.</span></span>  
  
-   <span data-ttu-id="8976e-111">リアルタイム集計もある場合は、リアルタイム集計を設定したオンライン ウィンドウよりも頻繁にキューブを更新するための DTS パッケージのスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="8976e-111">If you also have real-time aggregations, schedule the DTS package for refreshing the cube more frequently than the online window you set for the real-time aggregations.</span></span> <span data-ttu-id="8976e-112">それ以外の場合、集計のない時間帯があります。</span><span class="sxs-lookup"><span data-stu-id="8976e-112">Otherwise, there will be a window of time for which you do not have aggregations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8976e-113">参照</span><span class="sxs-lookup"><span data-stu-id="8976e-113">See Also</span></span>  
 [<span data-ttu-id="8976e-114">BAM データのクエリ</span><span class="sxs-lookup"><span data-stu-id="8976e-114">Querying BAM Data</span></span>](../core/querying-bam-data.md)
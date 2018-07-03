---
title: BAM 集計を定義する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, BAM
- aggregations [BAM], creating
- Excel add-in [BAM], security
- Excel add-in [BAM], creating aggregations
- managing [BAM], creating aggregations
ms.assetid: a5ef3a15-b1de-4099-8e94-64af4b5ec746
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57df4978f2b133794efd8fbdc99819bcedf144cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015907"
---
# <a name="how-to-define-bam-aggregations"></a><span data-ttu-id="37662-102">BAM 集計を定義する方法</span><span class="sxs-lookup"><span data-stu-id="37662-102">How to Define BAM Aggregations</span></span>
<span data-ttu-id="37662-103">BAM では、次の 2 種類のデータ集計がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="37662-103">BAM supports two types of data aggregation:</span></span>  
  
- <span data-ttu-id="37662-104">オンライン分析処理 (OLAP) 集計</span><span class="sxs-lookup"><span data-stu-id="37662-104">Online analytical processing (OLAP) aggregations</span></span>  
  
- <span data-ttu-id="37662-105">リアルタイム集計 (RTA)</span><span class="sxs-lookup"><span data-stu-id="37662-105">Real-time aggregations (RTA)</span></span>  
  
  <span data-ttu-id="37662-106">BAM では、OLAP 集計を実装するために Microsoft SQL Analysis Services が使用されます。</span><span class="sxs-lookup"><span data-stu-id="37662-106">BAM uses Microsoft SQL Server Analysis Services to implement OLAP aggregations.</span></span>  
  
  <span data-ttu-id="37662-107">RTA を定義する BAM プライマリ インポート データベースでは、トリガーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37662-107">You must configure the triggers on the BAM Primary Import database that define RTA.</span></span>  
  
### <a name="to-define-olap-aggregations"></a><span data-ttu-id="37662-108">OLAP 集計を定義するには</span><span class="sxs-lookup"><span data-stu-id="37662-108">To define OLAP aggregations</span></span>  
  
1.  <span data-ttu-id="37662-109">BAM Excel ブックで、ビューを作成し、PivotTable レポートにディメンションとメジャーを少なくとも 1 つずつ追加し、RTA ツール バー ボタンを非表示にしてブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="37662-109">In the BAM Excel workbook, create a view, add at least one dimension and one measure to the PivotTable report, clear the RTA toolbar button, and then save the workbook.</span></span>  
  
    -   <span data-ttu-id="37662-110">BAM ブックを開く方法の詳細については、ビューを作成し、ディメンション、メジャーを追加するを参照してください[BAM ビューを定義する](../core/defining-a-bam-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="37662-110">For information about opening the BAM workbook, creating a view, and adding dimensions and measures, see [Defining a BAM View](../core/defining-a-bam-view.md).</span></span>  
  
2.  <span data-ttu-id="37662-111">ブックを展開します。</span><span class="sxs-lookup"><span data-stu-id="37662-111">Deploy the workbook.</span></span>  
  
    -   <span data-ttu-id="37662-112">ブックを展開する手順については、 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)します。</span><span class="sxs-lookup"><span data-stu-id="37662-112">To deploy the workbook, follow the instructions in [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
3.  <span data-ttu-id="37662-113">ソリューション開発者は、使用、 **DirectEventStream**クラスは、BAM プライマリ インポート データベースにイベントをインポートします。</span><span class="sxs-lookup"><span data-stu-id="37662-113">A solutions developer uses the **DirectEventStream** class to import events into the BAM Primary Import database.</span></span>  
  
    -   <span data-ttu-id="37662-114">については、 **DirectEventStream**クラスを参照してください[DirectEventStream クラス](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="37662-114">For information about the **DirectEventStream** class, see [DirectEventStream Class](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span></span>  
  
4.  <span data-ttu-id="37662-115">キューブ更新データ変換サービス (DTS) パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="37662-115">Run the update cube Data Transformation Services (DTS) package.</span></span>  
  
    -   <span data-ttu-id="37662-116">キューブを更新する DTS パッケージの実行方法の詳細については、次を参照してください。[の BAM DTS パッケージ](../core/bam-dts-packages.md)します。</span><span class="sxs-lookup"><span data-stu-id="37662-116">For information about running the update cube DTS package, see [BAM DTS Packages](../core/bam-dts-packages.md).</span></span>  
  
5.  <span data-ttu-id="37662-117">ブックのライブ データの最新コピーを開き、OLAP 集計を表示します。</span><span class="sxs-lookup"><span data-stu-id="37662-117">Open the most recent live data copy of the workbook to see the OLAP aggregations.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="37662-118">セキュリティ上の理由により、BAM ではブックの既存ライブ データのコピーが削除されません。</span><span class="sxs-lookup"><span data-stu-id="37662-118">For security reasons, BAM does not delete existing live data copies of the workbook.</span></span> <span data-ttu-id="37662-119">代わりに、ライブ データのコピーのファイル名がインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="37662-119">Instead, BAM increments the file name of the live data copy.</span></span>  
  
### <a name="to-define-the-rta"></a><span data-ttu-id="37662-120">RTA を定義するには</span><span class="sxs-lookup"><span data-stu-id="37662-120">To define the RTA</span></span>  
  
1.  <span data-ttu-id="37662-121">BAM Excel ブックで、ビューを作成し、PivotTable レポートに 1 つ以上のディメンションと 1 つのメジャーを追加し、RTA ツール バー ボタンを選択してブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="37662-121">In the BAM Excel workbook, create a view, add at least one dimension and one measure to the PivotTable report, select the RTA toolbar button, and then save the workbook.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="37662-122">同じ BAM アクティビティを使用する RTA を複数定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="37662-122">Do not define multiple RTAs that use the same BAM activity.</span></span> <span data-ttu-id="37662-123">そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。</span><span class="sxs-lookup"><span data-stu-id="37662-123">If you do so, the RTA data will be incorrect when you archive the BAM data.</span></span>  
  
    -   <span data-ttu-id="37662-124">BAM ブックを開く方法の詳細については、ビューを作成し、ディメンション、メジャーを追加するを参照してください「ビジネス アクティビティ ビューの定義」および「集計の定義、*インフォメーション ワーカー ユーザー ガイド*します。</span><span class="sxs-lookup"><span data-stu-id="37662-124">For information about opening the BAM workbook, creating a view, and adding dimensions and measures, see "Defining a Business Activity View" and "Defining Aggregations" in the *Information Workers User Guide*.</span></span>  
  
2.  <span data-ttu-id="37662-125">ブックを展開します。</span><span class="sxs-lookup"><span data-stu-id="37662-125">Deploy the workbook.</span></span>  
  
    -   <span data-ttu-id="37662-126">ブックを展開する手順については、 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)します。</span><span class="sxs-lookup"><span data-stu-id="37662-126">To deploy the workbook, follow the instructions in [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
3.  <span data-ttu-id="37662-127">ソリューション開発者は、使用、 **DirectEventStream**クラスは、BAM プライマリ インポート データベースにイベントをインポートします。</span><span class="sxs-lookup"><span data-stu-id="37662-127">A solutions developer uses the **DirectEventStream** class to import events into the BAM Primary Import database.</span></span>  

  
4.  <span data-ttu-id="37662-128">ブックのライブ データの最新コピーを開き、RTA を表示します。</span><span class="sxs-lookup"><span data-stu-id="37662-128">Open the most recent live data copy of the workbook to see the RTAs.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="37662-129">セキュリティ上の理由により、BAM ではブックの既存ライブ データのコピーが削除されません。</span><span class="sxs-lookup"><span data-stu-id="37662-129">For security reasons, BAM does not delete existing live data copies of the workbook.</span></span> <span data-ttu-id="37662-130">代わりに、ライブ データのコピーのファイル名がインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="37662-130">Instead, BAM increments the file name of the live data copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37662-131">参照</span><span class="sxs-lookup"><span data-stu-id="37662-131">See Also</span></span>  
 <span data-ttu-id="37662-132">[BAM DTS パッケージ](../core/bam-dts-packages.md) </span><span class="sxs-lookup"><span data-stu-id="37662-132">[BAM DTS Packages](../core/bam-dts-packages.md) </span></span>  
 <span data-ttu-id="37662-133">[BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="37662-133">[How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md) </span></span>  
 <span data-ttu-id="37662-134">[OLAP および RTA 接続文字列プロパティを更新しています](../core/updating-olap-and-rta-connection-string-properties.md) </span><span class="sxs-lookup"><span data-stu-id="37662-134">[Updating OLAP and RTA Connection String Properties](../core/updating-olap-and-rta-connection-string-properties.md) </span></span>  
 [<span data-ttu-id="37662-135">BAM 動的インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="37662-135">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)
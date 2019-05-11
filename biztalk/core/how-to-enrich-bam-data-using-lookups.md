---
title: 参照を使用して BAM データを強化する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data lookups
ms.assetid: 8d10659e-97d6-4cd1-9b4d-307afd43c763
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d27a44d67ce7b95e06e07fd2be425688733b7bc8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385067"
---
# <a name="how-to-enrich-bam-data-using-lookups"></a><span data-ttu-id="e6173-102">照合を使用して BAM データを強化する方法</span><span class="sxs-lookup"><span data-stu-id="e6173-102">How to Enrich BAM Data Using Lookups</span></span>
<span data-ttu-id="e6173-103">これで操作時に、使用可能なデータを含まないレポート目的で必要なすべてのケースがあります。</span><span class="sxs-lookup"><span data-stu-id="e6173-103">There are cases in which the data that is available at operation time does not contain everything you need for reporting purposes.</span></span> <span data-ttu-id="e6173-104">たとえば、実行時に、ProductID、ProductName ではないがあります。</span><span class="sxs-lookup"><span data-stu-id="e6173-104">For example, you may have a ProductID but not a ProductName at runtime.</span></span> <span data-ttu-id="e6173-105">BAM アクティビティ データが実際に収集する方法に依存しない抽象化を表すためには、"ProductName"レポートに表示する最終的なデータとしてという名前の項目を含めることが必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6173-105">Since the BAM Activity represents an abstraction independent of how the data is actually collected, it should contain an item named as the final data that you want to see in the report "ProductName".</span></span> <span data-ttu-id="e6173-106">その他のアイテムと同様はマイルス トーン グループ、期間、ディメンション、メジャーなどの解釈型の構造でこれを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6173-106">Just like any other item, you can use this in interpretive constructs such as milestone groups, durations, dimensions, and measures.</span></span> <span data-ttu-id="e6173-107">ProductName が実行時に使用できないため、ProductID など、照合を実行するための十分な追加データを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6173-107">Since the ProductName is not available at runtime, you must get some additional data that is sufficient for performing a lookup, such as the ProductID.</span></span>  
  
 <span data-ttu-id="e6173-108">レポートに必要なデータではなく、同じ列のデータを収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6173-108">You should collect the data in the same column, instead of the data that you need for reports.</span></span> <span data-ttu-id="e6173-109">たとえば、実行時に ProductName ではなく ProductID を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6173-109">For example, you should collect the ProductID instead of ProductName at runtime.</span></span> <span data-ttu-id="e6173-110">多くの列が必要な場合、アクティビティの他のアイテムを作成することが任意のビューでは使用しないが。</span><span class="sxs-lookup"><span data-stu-id="e6173-110">If more columns are required, you may create more items in the activity but not use them in any View.</span></span>  
  
### <a name="to-enrich-bam-data-via-lookups"></a><span data-ttu-id="e6173-111">照合によって BAM データを強化するには</span><span class="sxs-lookup"><span data-stu-id="e6173-111">To enrich BAM data via lookups</span></span>  
  
1.  <span data-ttu-id="e6173-112">BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="e6173-112">Deploy your BAM definition.</span></span>  
  
2.  <span data-ttu-id="e6173-113">SQL Server Management studio では、リモート サーバーとして関心のあるデータを格納しているサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6173-113">In SQL Server Management Studio, add the server that contains the data of interest as a remote server.</span></span>  
  
3.  <span data-ttu-id="e6173-114">Bam_an _ という名前のデータ分析パッケージを探します`<View Name>`します。</span><span class="sxs-lookup"><span data-stu-id="e6173-114">Locate the data analysis package named BAM_AN_`<View Name>`.</span></span> <span data-ttu-id="e6173-115">たとえば、ビューが SalesMgr の場合は bam_an_salesmgr します。</span><span class="sxs-lookup"><span data-stu-id="e6173-115">For example if the view is SalesMgr, this will be BAM_AN_SalesMgr.</span></span>  
  
4.  <span data-ttu-id="e6173-116">パッケージ (たとえば、100%) のビューを拡大するズームを設定します。</span><span class="sxs-lookup"><span data-stu-id="e6173-116">Set the zoom to magnify the view of the package (e.g. 100%)</span></span>  
  
5.  <span data-ttu-id="e6173-117">照合に使用する場合は、SQL の接続を追加します。</span><span class="sxs-lookup"><span data-stu-id="e6173-117">Add a SQL connection that you will be using in the lookups.</span></span>  
  
6.  <span data-ttu-id="e6173-118">「クリーンアップ ステージング」ステップの後に、データ変換タスクを探します。</span><span class="sxs-lookup"><span data-stu-id="e6173-118">Locate the transform data task after the step "Cleanup Staging".</span></span> <span data-ttu-id="e6173-119">これは、データを移動する、PrimaryImport から StarSchema データベースにします。</span><span class="sxs-lookup"><span data-stu-id="e6173-119">This is where you move the data from the PrimaryImport to the StarSchema database.</span></span> <span data-ttu-id="e6173-120">このタスクの 2 つのインスタンスがある-完了したアクティビティと進行中にあるものの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="e6173-120">There are two instances of this task—one for the completed activities, and another for the one that is in progress.</span></span> <span data-ttu-id="e6173-121">両方のタスクには、すべての残りの手順を適用します。</span><span class="sxs-lookup"><span data-stu-id="e6173-121">Apply all the rest of the steps to both tasks.</span></span>  
  
7.  <span data-ttu-id="e6173-122">[変換] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6173-122">Click the transformation.</span></span>  
  
8.  <span data-ttu-id="e6173-123">検索を選択します。"lookupproductbyid"参照の接続を使用しての追加 (SQL オンライン ブックの参照を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e6173-123">Select Lookups; add your lookup "LookupProductByID" using the lookup connection (see SQL books online for lookups).</span></span> <span data-ttu-id="e6173-124">たとえば、参照には、単純なテーブル"LookupProduct"の場合、ProductID、ProductName の列を持つ検索のテキストになります。</span><span class="sxs-lookup"><span data-stu-id="e6173-124">If for example the lookup is a simple table "LookupProduct", the with columns ProductID and ProductName, the text of the lookup will be:</span></span>  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. <span data-ttu-id="e6173-125">[変換] タブをクリックします。既定のデータ変換"Transform"を削除し、代わりに ActiveX 変換を作成します。</span><span class="sxs-lookup"><span data-stu-id="e6173-125">Click the Transformations tab. Delete the default data transformation "Transform", and create ActiveX transformation instead.</span></span> <span data-ttu-id="e6173-126">ソース列 をクリックし、すべての列を追加します。</span><span class="sxs-lookup"><span data-stu-id="e6173-126">Click Source Columns and add all columns.</span></span> <span data-ttu-id="e6173-127">変換先列をクリックし、すべての列を追加します。</span><span class="sxs-lookup"><span data-stu-id="e6173-127">Click Destination Columns and add all columns.</span></span>  
  
10. <span data-ttu-id="e6173-128">[全般] タブ、および [プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6173-128">Click the General tab, and then Properties.</span></span> <span data-ttu-id="e6173-129">これは、結果に示すように自明なコピー変換を実行するスクリプトの自動生成。</span><span class="sxs-lookup"><span data-stu-id="e6173-129">This results in automatic generation of a script that performs the trivial copy transformation as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. <span data-ttu-id="e6173-130">示すように、参照を使用して、値を変更します。</span><span class="sxs-lookup"><span data-stu-id="e6173-130">Change the value by using the lookup as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. <span data-ttu-id="e6173-131">保存し、そのパッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6173-131">Save and then run the package.</span></span>  
  
13. <span data-ttu-id="e6173-132">正しいデータが OLAP キューブ終了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6173-132">Ensure that the correct data ends up in the OLAP cube.</span></span> <span data-ttu-id="e6173-133">BAM から自動生成されたステップだけでなくが、カスタム コードが含まれているために、VBScript または構造化ストレージ ファイルとしてパッケージを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6173-133">You should save the package as VBScript or a structured storage file, because it contains your custom code, not just the auto-generated steps from BAM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6173-134">検索は、DTS と OLAP を使用して実行するスケジュールされたレポートに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e6173-134">The lookup works only for the scheduled reports that you perform with DTS and OLAP.</span></span> <span data-ttu-id="e6173-135">リアルタイム集計で収集される情報とは異なるデータが必要な場合は、BAM API を呼び出す前に、データを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6173-135">If you need different data than what is collected in the real-time aggregation, then you must retrieve the data before calling the BAM API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6173-136">参照</span><span class="sxs-lookup"><span data-stu-id="e6173-136">See Also</span></span>  
 <span data-ttu-id="e6173-137">[ビジネス アクティビティの使用の監視](../core/using-business-activity-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="e6173-137">[Using Business Activity Monitoring](../core/using-business-activity-monitoring.md) </span></span>  
 [<span data-ttu-id="e6173-138">ローカライズされた BAM XML ファイルの展開</span><span class="sxs-lookup"><span data-stu-id="e6173-138">Deploying Localized BAM XML Files</span></span>](../core/deploying-localized-bam-xml-files.md)
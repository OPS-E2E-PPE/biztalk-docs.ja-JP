---
title: 参照を使用して BAM データを強化する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 43b42b42158bc3b3c179d624340a97a890072a17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253914"
---
# <a name="how-to-enrich-bam-data-using-lookups"></a><span data-ttu-id="7778a-102">照合を使用して BAM データを強化する方法</span><span class="sxs-lookup"><span data-stu-id="7778a-102">How to Enrich BAM Data Using Lookups</span></span>
<span data-ttu-id="7778a-103">操作時に使用できるデータに、レポート処理で必要となるデータがすべて含まれているとは限らない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7778a-103">There are cases in which the data that is available at operation time does not contain everything you need for reporting purposes.</span></span> <span data-ttu-id="7778a-104">たとえば、実行時に、ProductID があっても ProductName がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7778a-104">For example, you may have a ProductID but not a ProductName at runtime.</span></span> <span data-ttu-id="7778a-105">BAM アクティビティは実際のデータ収集方法に依存しない抽象概念を表すので、レポートに最終的に表示するデータとして "ProductName" という名前の項目を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7778a-105">Since the BAM Activity represents an abstraction independent of how the data is actually collected, it should contain an item named as the final data that you want to see in the report "ProductName".</span></span> <span data-ttu-id="7778a-106">この項目は、他の項目と同様に、マイルストーン グループ、期間、ディメンション、メジャーなどの解釈型の構成要素で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7778a-106">Just like any other item, you can use this in interpretive constructs such as milestone groups, durations, dimensions, and measures.</span></span> <span data-ttu-id="7778a-107">ProductName が実行時に使用できないので、ProductID など、照合の実行に必要な追加データを取得しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7778a-107">Since the ProductName is not available at runtime, you must get some additional data that is sufficient for performing a lookup, such as the ProductID.</span></span>  
  
 <span data-ttu-id="7778a-108">レポートに必要なデータに代わるデータを同じ列に収集します。</span><span class="sxs-lookup"><span data-stu-id="7778a-108">You should collect the data in the same column, instead of the data that you need for reports.</span></span> <span data-ttu-id="7778a-109">たとえば、実行時には ProductName ではなく ProductID を収集します。</span><span class="sxs-lookup"><span data-stu-id="7778a-109">For example, you should collect the ProductID instead of ProductName at runtime.</span></span> <span data-ttu-id="7778a-110">さらに多くの列が必要な場合は、アクティビティに多くの項目を作成することはできますが、これらをビューで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7778a-110">If more columns are required, you may create more items in the activity but not use them in any View.</span></span>  
  
### <a name="to-enrich-bam-data-via-lookups"></a><span data-ttu-id="7778a-111">照合によって BAM データを強化するには</span><span class="sxs-lookup"><span data-stu-id="7778a-111">To enrich BAM data via lookups</span></span>  
  
1.  <span data-ttu-id="7778a-112">BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="7778a-112">Deploy your BAM definition.</span></span>  
  
2.  <span data-ttu-id="7778a-113">SQL Server Management Studio で、必要なデータが入ったサーバーをリモート サーバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="7778a-113">In SQL Server Management Studio, add the server that contains the data of interest as a remote server.</span></span>  
  
3.  <span data-ttu-id="7778a-114">BAM_AN_`<View Name>` というデータ分析パッケージを探します。</span><span class="sxs-lookup"><span data-stu-id="7778a-114">Locate the data analysis package named BAM_AN_`<View Name>`.</span></span> <span data-ttu-id="7778a-115">たとえば、ビューが SalesMgr の場合は BAM_AN_SalesMgr を探します。</span><span class="sxs-lookup"><span data-stu-id="7778a-115">For example if the view is SalesMgr, this will be BAM_AN_SalesMgr.</span></span>  
  
4.  <span data-ttu-id="7778a-116">パッケージのビューを拡大表示するためにズーム (たとえば、100%) を設定します。</span><span class="sxs-lookup"><span data-stu-id="7778a-116">Set the zoom to magnify the view of the package (e.g. 100%)</span></span>  
  
5.  <span data-ttu-id="7778a-117">照合に使用する SQL 接続を追加します。</span><span class="sxs-lookup"><span data-stu-id="7778a-117">Add a SQL connection that you will be using in the lookups.</span></span>  
  
6.  <span data-ttu-id="7778a-118">"クリーンアップ ステージング" ステップの後にデータ変換タスクを配置します。</span><span class="sxs-lookup"><span data-stu-id="7778a-118">Locate the transform data task after the step "Cleanup Staging".</span></span> <span data-ttu-id="7778a-119">このタスクでは、PrimaryImport データベースから StarSchema データベースにデータを移動します。</span><span class="sxs-lookup"><span data-stu-id="7778a-119">This is where you move the data from the PrimaryImport to the StarSchema database.</span></span> <span data-ttu-id="7778a-120">このタスクの 2 つのインスタンス: 完了したアクティビティと、1 つの進行中の別のいずれか。</span><span class="sxs-lookup"><span data-stu-id="7778a-120">There are two instances of this task—one for the completed activities, and another for the one that is in progress.</span></span> <span data-ttu-id="7778a-121">両方のタスクに残りのすべてのステップを適用します。</span><span class="sxs-lookup"><span data-stu-id="7778a-121">Apply all the rest of the steps to both tasks.</span></span>  
  
7.  <span data-ttu-id="7778a-122">[変換] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7778a-122">Click the transformation.</span></span>  
  
8.  <span data-ttu-id="7778a-123">[照合] をクリックします。照合接続を使用して "LookupProductByID" という照合を追加します (照合については、SQL Server Books Online を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7778a-123">Select Lookups; add your lookup "LookupProductByID" using the lookup connection (see SQL books online for lookups).</span></span> <span data-ttu-id="7778a-124">たとえば、照合が ProductID 列と ProductName 列を含む単純なテーブル "LookupProduct" の場合、照合のテキストは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7778a-124">If for example the lookup is a simple table "LookupProduct", the with columns ProductID and ProductName, the text of the lookup will be:</span></span>  
  
    ```  
    SELECT ProductName  
    FROM   LookupProduct  
    WHERE ProductID=?  
    ```  
  
9. <span data-ttu-id="7778a-125">[変換] タブをクリックします。既定のデータ変換 "Transform" を削除し、代わりに ActiveX 変換を作成します。</span><span class="sxs-lookup"><span data-stu-id="7778a-125">Click the Transformations tab. Delete the default data transformation "Transform", and create ActiveX transformation instead.</span></span> <span data-ttu-id="7778a-126">変換元列をクリックしてすべての列を追加し、</span><span class="sxs-lookup"><span data-stu-id="7778a-126">Click Source Columns and add all columns.</span></span> <span data-ttu-id="7778a-127">変換先列をクリックしてすべての列を追加します。</span><span class="sxs-lookup"><span data-stu-id="7778a-127">Click Destination Columns and add all columns.</span></span>  
  
10. <span data-ttu-id="7778a-128">[全般] タブ、し、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7778a-128">Click the General tab, and then Properties.</span></span> <span data-ttu-id="7778a-129">この結果、次のような簡単なコピー変換を実行するスクリプトが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="7778a-129">This results in automatic generation of a script that performs the trivial copy transformation as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("ProductName") = DTSSource("ProductName")  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
11. <span data-ttu-id="7778a-130">次のように、照合を使用して値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7778a-130">Change the value by using the lookup as shown:</span></span>  
  
    ```  
    Function Main()  
       ...  
       DTSDestination("Product")= _  
                      DTSLookups( "LookupProductByID" ).Execute(  _                                  DTSSource("Product"))  
       ...  
       Main = DTSTransformStat_OK  
    End Function  
    ```  
  
12. <span data-ttu-id="7778a-131">パッケージを保存してから実行します。</span><span class="sxs-lookup"><span data-stu-id="7778a-131">Save and then run the package.</span></span>  
  
13. <span data-ttu-id="7778a-132">最終的に正しいデータが OLAP キューブに含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7778a-132">Ensure that the correct data ends up in the OLAP cube.</span></span> <span data-ttu-id="7778a-133">パッケージには、BAM から自動生成されたステップだけでなくカスタム コードが含まれているため、パッケージを VBScript または構造化ストレージ ファイルとして保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7778a-133">You should save the package as VBScript or a structured storage file, because it contains your custom code, not just the auto-generated steps from BAM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7778a-134">検索は、DTS と OLAP を使用して実行するスケジュールされたレポートに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7778a-134">The lookup works only for the scheduled reports that you perform with DTS and OLAP.</span></span> <span data-ttu-id="7778a-135">リアルタイム集計で収集したデータとは異なるデータが必要な場合は、BAM API を呼び出す前にデータを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7778a-135">If you need different data than what is collected in the real-time aggregation, then you must retrieve the data before calling the BAM API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7778a-136">参照</span><span class="sxs-lookup"><span data-stu-id="7778a-136">See Also</span></span>  
 <span data-ttu-id="7778a-137">[ビジネス アクティビティの使用の監視](../core/using-business-activity-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="7778a-137">[Using Business Activity Monitoring](../core/using-business-activity-monitoring.md) </span></span>  
 [<span data-ttu-id="7778a-138">ローカライズされた BAM XML ファイルの配置</span><span class="sxs-lookup"><span data-stu-id="7778a-138">Deploying Localized BAM XML Files</span></span>](../core/deploying-localized-bam-xml-files.md)
---
title: Excel でビジネス アクティビティとビューの定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating business activities
- monitoring business activities [BAM], creating business activities
ms.assetid: 000532f0-cb9a-40ac-a6c5-a8bd4e49f8d0
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61e9302d2f3178e457a5ed57353e77eac0909d32
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014139"
---
# <a name="defining-business-activities-and-views-in-excel"></a><span data-ttu-id="dd400-102">Excel でのビジネス アクティビティとビジネス ビューの定義</span><span class="sxs-lookup"><span data-stu-id="dd400-102">Defining Business Activities and Views in Excel</span></span>
<span data-ttu-id="dd400-103">BAM ソリューションを作成する場合は、まず関連データの種類とそのデータを解釈する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd400-103">Your first step in creating any BAM solution is to identify what data you're interested in and how that data should be interpreted.</span></span> <span data-ttu-id="dd400-104">これには、Excel 用の BAM アドインを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd400-104">To do this, you use the BAM Add-in for Excel.</span></span> <span data-ttu-id="dd400-105">このアドインを使用すると、ビジネス アクティビティを定義して、関連データの希望リストを定義できます。</span><span class="sxs-lookup"><span data-stu-id="dd400-105">The add-in allows you to define a wish-list of the data of interest by defining a business activity.</span></span> <span data-ttu-id="dd400-106">また、データを解釈する方法と、さまざまなカテゴリのビジネス ユーザーにデータを公開する方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="dd400-106">You can also define the way the data should be interpreted and shown to different categories of business users.</span></span>  
  
 <span data-ttu-id="dd400-107">BAM アドインでは、集計も定義できます。</span><span class="sxs-lookup"><span data-stu-id="dd400-107">The BAM Add-in also enables you to define aggregations.</span></span>  
  
 <span data-ttu-id="dd400-108">アクティビティ項目の名前の変更も可能です。たとえば、ユーザーにとって一般的な用語と、アクティビティの対応するデータ項目の名前が一致しない場合に名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="dd400-108">You can also rename activity items, for example, where the terminology some users are familiar with does not match the names of the corresponding data items in the activity.</span></span> <span data-ttu-id="dd400-109">たとえば、表示が別の言語になっている場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="dd400-109">One explanation for this is where the view is in a different language.</span></span>  
  
 <span data-ttu-id="dd400-110">アクティビティの定義が完了すると、必要なグラフおよびその他のプレゼンテーション手段の定義に使用できるランダムなプレビュー データが Excel で作成されます。</span><span class="sxs-lookup"><span data-stu-id="dd400-110">After you complete the activity definition, Excel generates random preview data that you can use to define the desired charts and other means of presentation.</span></span> <span data-ttu-id="dd400-111">プレビュー データの詳細については、[ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd400-111">For more information about preview data, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
 <span data-ttu-id="dd400-112">完成したアクティビティ定義では、ビジネス プロセスの実行時に収集する必要があるデータ ポイントとイベントが定義されています。</span><span class="sxs-lookup"><span data-stu-id="dd400-112">The completed activity definition defines the data points and events that you need collected when a business process is run.</span></span> <span data-ttu-id="dd400-113">BAM アドインは、さまざまな方法で入手できます。</span><span class="sxs-lookup"><span data-stu-id="dd400-113">You can get the BAM Add-in from a variety of sources.</span></span>  
  
 <span data-ttu-id="dd400-114">中に BAM アドイン XLA をインストールすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="dd400-114">You can install the BAM Add-in XLA during the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="dd400-115">詳細については、次を参照してください[BizTalk Server 2013 および 2013 R2 のインストールの概要。](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)</span><span class="sxs-lookup"><span data-stu-id="dd400-115">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)</span></span>  
  
 <span data-ttu-id="dd400-116">Bam の展開。XLA ファイルは、次の場所のいずれかでインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dd400-116">The BAM.XLA file is installed in one of the following locations:</span></span>  
  
- <span data-ttu-id="dd400-117">コンピューターで、Microsoft Office がインストールされていない場合、BAM.xla が BizTalk Server 20 \Program Files\Microsoft にインストールされている*xx*\ExcelDir\ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="dd400-117">If Microsoft Office is not installed on the computer, then the BAM.xla is installed to the \Program Files\Microsoft BizTalk Server 20*xx*\ExcelDir\ folder.</span></span>  
  
- <span data-ttu-id="dd400-118">Microsoft Office がインストールされている場合、BAM.xla は \Program Files\Microsoft Office\OFFICE にインストール*xx*\Library\ フォルダー。</span><span class="sxs-lookup"><span data-stu-id="dd400-118">If Microsoft Office is installed, the BAM.xla is installed in the \Program Files\Microsoft Office\OFFICE*xx*\Library\ folder.</span></span>  
  
  <span data-ttu-id="dd400-119">使用するコンピューターに、別のコンピューターの共有フォルダーから BAM.xla をコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dd400-119">You can also copy the BAM.xla to your computer from a shared folder on another computer.</span></span> <span data-ttu-id="dd400-120">コピーしたら、その場所で XLA を選択して XLA を登録できます。</span><span class="sxs-lookup"><span data-stu-id="dd400-120">You can then register the XLA by selecting it from the location to which you copied it.</span></span>  
  
  <span data-ttu-id="dd400-121">Excel メニュー バーで BAM アドインを有効にする をクリックして、**ファイル** メニューのをクリックし、**オプション**、順にクリックします**アドイン**します。選択**ビジネス アクティビティ監視**、順にクリックします**移動**、アドイン ウィンドウで、横にチェック ボックス**ビジネス アクティビティ監視**をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="dd400-121">To enable the BAM Add-in on the Excel menu toolbar, click the **File** menu, then click **Options**, and then click **Add-Ins**. Select **Business Activity Monitoring**, then click **GO**, In the Ad-ins window, select the check box next to **Business Activity Monitoring**, and then click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd400-122">BAM アドインの使用中、Excel では同じプロセスに 2 つのインスタンスを読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="dd400-122">Using the BAM Add-in precludes running Excel with two instances loaded into the same process.</span></span>  <span data-ttu-id="dd400-123">アドインの使用中に、同じプロセスへの複数インスタンスの読み込みが発生するのは次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="dd400-123">When using the add-in, multiple instances in the same process can occur in the following situations:</span></span>  
>   
>  <span data-ttu-id="dd400-124">BAM アドインを有効にした状態で Excel ワークシートを開き、さらに別の Excel ワークシートをダブルクリックした場合。この場合、Excel によってダブルクリックしたワークシートが実行中のインスタンスに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="dd400-124">When you have an Excel spreadsheet open with the BAM Add-in enabled, and you double-click a different Excel spreadsheet, Excel attempts to load the spreadsheet into the currently running instance.</span></span>  
>   
>  <span data-ttu-id="dd400-125">BAM アドインを有効にした状態で Excel ワークシートを開き、さらに [ファイル] メニューの [開く] を選択して他の Excel ワークシートを読み込んだ場合。</span><span class="sxs-lookup"><span data-stu-id="dd400-125">When you have an Excel spreadsheet open, with the BAM Add-in enabled, and you use the File/Open menu option to load another Excel spreadsheet.</span></span>  
  
 <span data-ttu-id="dd400-126">このような状況では、アドインを適切に使用できません。</span><span class="sxs-lookup"><span data-stu-id="dd400-126">You cannot use the add-in properly in such situations.</span></span> <span data-ttu-id="dd400-127">BAM アドインを有効にした状態で複数の Excel ワークシートを開くには、新しい Excel のウィンドウを開き、その Excel インスタンスにワークシートを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd400-127">To open multiple Excel spreadsheets when you have the BAM Add-in enabled, you must open a new copy of Excel and load the spreadsheet into that instance of Excel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd400-128">BAM.xla を Excel で使用するときにエラーが発生、「このブックは、VBA プロジェクト、ActiveX コントロールおよびその他のプログラミング関連の機能を紛失が」</span><span class="sxs-lookup"><span data-stu-id="dd400-128">When you use BAM.xla in Excel, you may get the error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span> <span data-ttu-id="dd400-129">エラーの詳細については、[BAM のトラブルシューティング](../core/troubleshooting-bam.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd400-129">For more information about the error, see [Troubleshooting BAM](../core/troubleshooting-bam.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd400-130">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dd400-130">In This Section</span></span>  
  
-   [<span data-ttu-id="dd400-131">ビジネス アクティビティを定義する方法</span><span class="sxs-lookup"><span data-stu-id="dd400-131">How to Define a Business Activity</span></span>](../core/how-to-define-a-business-activity.md)  
  
-   [<span data-ttu-id="dd400-132">BAM ビューの定義</span><span class="sxs-lookup"><span data-stu-id="dd400-132">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd400-133">参照</span><span class="sxs-lookup"><span data-stu-id="dd400-133">See Also</span></span>  
 [<span data-ttu-id="dd400-134">BAM によるビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="dd400-134">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)
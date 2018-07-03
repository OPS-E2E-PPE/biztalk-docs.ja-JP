---
title: EDI および AS2 状態レポートの構成 |Microsoft Docs
description: 作成、EDI または AS2 状態レポートのクエリ式、および BizTalk Server でのレポートに表示されているデータを選択
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6490864d-f1e6-4932-aefb-c332a595aad7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4981067305a6b1de57c393cea7d49323933a0ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972803"
---
# <a name="configure-an-edi-and-as2-status-report"></a><span data-ttu-id="37b79-103">EDI および AS2 状態レポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="37b79-103">Configure an EDI and AS2 Status Report</span></span>
<span data-ttu-id="37b79-104">EDI を有効にするか、状態レポートを表示するために AS2 状態レポートを後から必要な**EDI 状態レポート**または**EDIINT 状態レポート**のセクション、**グループ ハブ**タブ、**グループの概要**ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="37b79-104">After you have enabled EDI or AS2 status reports, you display the status report you want from the **EDI Status Reports** or **EDIINT Status Reports** section of the **Group Hub** tab of the **Group Overview** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="37b79-105">状態レポートを表示するときに、データの既定のセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37b79-105">When you display a status report, you will see a default set of data.</span></span> <span data-ttu-id="37b79-106">状態レポートの次の要素を構成できます。</span><span class="sxs-lookup"><span data-stu-id="37b79-106">You can configure the following aspects of the status reports:</span></span>  
  
- <span data-ttu-id="37b79-107">たとえば、日付の範囲、データの方向 (受信または送信)、状態の値 (受理、拒否、すべてなど) などの、状態レポートの対象となるデータの範囲を決定するために実行されるクエリ式。</span><span class="sxs-lookup"><span data-stu-id="37b79-107">The query expression that is run to determine the range of data that status is reported for, for example, the date range, the direction of the data (receive or send), or the status value (Accepted, Rejected, All, etc.)</span></span>  
  
- <span data-ttu-id="37b79-108">レポートのデータ列に基づいて決定される、状態レポート ペインに表示されるデータの種類。</span><span class="sxs-lookup"><span data-stu-id="37b79-108">The type of data displayed in the status report pane, as determined by the data columns in the report.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="37b79-109">状態レポートが有効になっている場合、常にすべての状態がストレージに保存されます。</span><span class="sxs-lookup"><span data-stu-id="37b79-109">Whenever status reporting is enabled, all status will be saved in storage.</span></span> <span data-ttu-id="37b79-110">クエリ式または状態列をカスタマイズすることで、表示する保存データを定義します。</span><span class="sxs-lookup"><span data-stu-id="37b79-110">By customizing the query expression or status columns, you are defining which saved data is displayed.</span></span>  
  
  <span data-ttu-id="37b79-111">5 つのさまざまな EDI および AS2 状態レポートが利用可能な (を参照してください[型の EDI および AS2 状態レポート](../core/types-of-edi-and-as2-status-reports.md))。</span><span class="sxs-lookup"><span data-stu-id="37b79-111">Five different EDI and AS2 status reports are available (see [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md)).</span></span> <span data-ttu-id="37b79-112">レポートのデータが異なっていても、レポートを構成する方法は同じです。</span><span class="sxs-lookup"><span data-stu-id="37b79-112">The way that you configure each report is the same, even though the data for each report is different.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="37b79-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="37b79-113">Prerequisites</span></span>  
 <span data-ttu-id="37b79-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="37b79-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="configure-the-status-report-query-expression"></a><span data-ttu-id="37b79-115">状態レポートのクエリ式を構成します。</span><span class="sxs-lookup"><span data-stu-id="37b79-115">Configure the status report query expression</span></span>  
  
1. <span data-ttu-id="37b79-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、 **BizTalk グループ**ノードを表示、**グループの概要**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="37b79-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node to see the **Group Overview** pane.</span></span>  
  
2. <span data-ttu-id="37b79-117">下部にある、**グループ ハブ** タブで、**グループの概要**ウィンドウで、状態レポートなど、構成する をクリックして**EDI インターチェンジと関連する ACK の状態**します。</span><span class="sxs-lookup"><span data-stu-id="37b79-117">At the bottom of the **Group Hub** tab in the **Group Overview** pane, click the status report that you want to configure, such as **EDI Interchange and Correlated ACK Status**.</span></span>  
  
3. <span data-ttu-id="37b79-118">**クエリ式**状態レポート ペインの領域では、クエリを定義するすべてのフィルター条件が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="37b79-118">In the **Query Expression** area of the status report pane, verify that all filter criteria that you want to define for the query are present.</span></span> <span data-ttu-id="37b79-119">そうでない場合に空の行で下矢印をクリックします。、**フィールド名**クエリ式、およびフィルター クエリ式に追加する条件をすべて選択 の下部にある列です。</span><span class="sxs-lookup"><span data-stu-id="37b79-119">If not, click the down arrow in the empty row in the **Field Name** column at the bottom of the query expression, and select any filter criteria that you want to add to the query expression.</span></span> <span data-ttu-id="37b79-120">フィルター条件の行を削除するには、行を選択し、クリックすると、**削除**キーボードのキー。</span><span class="sxs-lookup"><span data-stu-id="37b79-120">You can delete a filter criteria row by selecting the row and clicking the **Delete** button on the keyboard.</span></span>  
  
4. <span data-ttu-id="37b79-121">フィルタ式の値が適切かどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="37b79-121">Verify that the values for the filter expressions are as desired.</span></span> <span data-ttu-id="37b79-122">そうでない場合は、の下矢印をクリックして、**演算子**を、クエリ操作を選択し、適切な値を入力列、**値**列。</span><span class="sxs-lookup"><span data-stu-id="37b79-122">If not, click the down arrow for the **Operator** column to select a query operation, and enter the appropriate value in the **Value** column.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="37b79-123">演算子およびクエリ式でフィルター条件の使用可能な値については説明[型の EDI および AS2 状態レポート](../core/types-of-edi-and-as2-status-reports.md)と**EDI AS2 状態レポート UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="37b79-123">The operators and values available for filter criteria in the query expressions are described in [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md) and the **EDI-AS2 Status Reports UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
5. <span data-ttu-id="37b79-124">フィルターの条件に従った状態レポートを表示する、クエリを実行する をクリックして**クエリの実行**します。</span><span class="sxs-lookup"><span data-stu-id="37b79-124">To run the query, displaying the status report according to the filter criteria, click **Run Query**.</span></span>  
  
6. <span data-ttu-id="37b79-125">クエリ式を .btq ファイルとして保存する をクリックして**付けて**、フォルダーを指定し、ファイル名を入力して順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="37b79-125">To save a query expression as a .btq file, click **Save As**, specify the folder and enter a filename, and then click **Save**.</span></span>  
  
7. <span data-ttu-id="37b79-126">保存されている .btq ファイルを開くには、次のようにクリックします。**クエリを開く**します。</span><span class="sxs-lookup"><span data-stu-id="37b79-126">To open a saved .btq file, click **Open Query**.</span></span>  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a><span data-ttu-id="37b79-127">状態レポート ペインに表示されるデータの種類を構成します。</span><span class="sxs-lookup"><span data-stu-id="37b79-127">Configure the type of data displayed in the status report pane</span></span>  
  
1.  <span data-ttu-id="37b79-128">状態レポート ペインの状態の結果の領域を右クリックし、をクリックし、**列の追加/削除**します。</span><span class="sxs-lookup"><span data-stu-id="37b79-128">Right-click the status results area of the status report pane, and then click **Add/Remove Columns**.</span></span>  
  
2.  <span data-ttu-id="37b79-129">表示されている列の一覧には、状態のカテゴリを追加するで列をクリックします。、**使用可能な列**ボックスの一覧をクリック**追加**します。</span><span class="sxs-lookup"><span data-stu-id="37b79-129">To add a status category to the displayed columns list, click a column in the **Available columns** list, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="37b79-130">表示されている列の一覧から状態カテゴリを削除するで列をクリックします。、**表示されている列**ボックスの一覧をクリック**削除**します。</span><span class="sxs-lookup"><span data-stu-id="37b79-130">To remove a status category from the displayed columns list, click a column in the **Displayed columns** list, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b79-131">参照</span><span class="sxs-lookup"><span data-stu-id="37b79-131">See Also</span></span>  
 <span data-ttu-id="37b79-132">[EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="37b79-132">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="37b79-133">[EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="37b79-133">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="37b79-134">[EDI および AS2 状態レポートを有効にします。](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="37b79-134">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="37b79-135">EDI または AS2 状態レポートの表示</span><span class="sxs-lookup"><span data-stu-id="37b79-135">Displaying an EDI or AS2 Status Report</span></span>](../core/displaying-an-edi-or-as2-status-report.md)
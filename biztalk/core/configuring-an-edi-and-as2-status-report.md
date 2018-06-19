---
title: EDI および AS2 状態レポートの構成 |Microsoft ドキュメント
description: 作成、EDI または AS2 状態レポート クエリ式、および BizTalk Server でのレポートに表示されているデータを選択
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
ms.openlocfilehash: 833e3c6c26cdac57d7cc57d828b66a66b9eb37f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233682"
---
# <a name="configure-an-edi-and-as2-status-report"></a><span data-ttu-id="37e63-103">EDI および AS2 状態レポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="37e63-103">Configure an EDI and AS2 Status Report</span></span>
<span data-ttu-id="37e63-104">EDI を有効にするか、状態レポートを表示する AS2 状態レポートを後から、使用する、 **EDI 状態レポート**または**EDIINT 状態レポート**のセクションで、**グループ ハブ**タブ、**グループの概要** ページで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="37e63-104">After you have enabled EDI or AS2 status reports, you display the status report you want from the **EDI Status Reports** or **EDIINT Status Reports** section of the **Group Hub** tab of the **Group Overview** page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="37e63-105">状態レポートを表示するときに、データの既定のセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37e63-105">When you display a status report, you will see a default set of data.</span></span> <span data-ttu-id="37e63-106">状態レポートの次の要素を構成できます。</span><span class="sxs-lookup"><span data-stu-id="37e63-106">You can configure the following aspects of the status reports:</span></span>  
  
-   <span data-ttu-id="37e63-107">たとえば、日付の範囲、データの方向 (受信または送信)、状態の値 (受理、拒否、すべてなど) などの、状態レポートの対象となるデータの範囲を決定するために実行されるクエリ式。</span><span class="sxs-lookup"><span data-stu-id="37e63-107">The query expression that is run to determine the range of data that status is reported for, for example, the date range, the direction of the data (receive or send), or the status value (Accepted, Rejected, All, etc.)</span></span>  
  
-   <span data-ttu-id="37e63-108">レポートのデータ列に基づいて決定される、状態レポート ペインに表示されるデータの種類。</span><span class="sxs-lookup"><span data-stu-id="37e63-108">The type of data displayed in the status report pane, as determined by the data columns in the report.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37e63-109">状態レポートが有効になっている場合、常にすべての状態がストレージに保存されます。</span><span class="sxs-lookup"><span data-stu-id="37e63-109">Whenever status reporting is enabled, all status will be saved in storage.</span></span> <span data-ttu-id="37e63-110">クエリ式または状態列をカスタマイズすることで、表示する保存データを定義します。</span><span class="sxs-lookup"><span data-stu-id="37e63-110">By customizing the query expression or status columns, you are defining which saved data is displayed.</span></span>  
  
 <span data-ttu-id="37e63-111">5 つの異なる EDI および AS2 状態レポートを利用できます (を参照してください[型の EDI および AS2 状態レポート](../core/types-of-edi-and-as2-status-reports.md))。</span><span class="sxs-lookup"><span data-stu-id="37e63-111">Five different EDI and AS2 status reports are available (see [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md)).</span></span> <span data-ttu-id="37e63-112">レポートのデータが異なっていても、レポートを構成する方法は同じです。</span><span class="sxs-lookup"><span data-stu-id="37e63-112">The way that you configure each report is the same, even though the data for each report is different.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="37e63-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="37e63-113">Prerequisites</span></span>  
 <span data-ttu-id="37e63-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="37e63-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="configure-the-status-report-query-expression"></a><span data-ttu-id="37e63-115">ステータス レポートのクエリ式を構成します。</span><span class="sxs-lookup"><span data-stu-id="37e63-115">Configure the status report query expression</span></span>  
  
1.  <span data-ttu-id="37e63-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、 **BizTalk グループ**を表示するノード、**グループの概要**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="37e63-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **BizTalk Group** node to see the **Group Overview** pane.</span></span>  
  
2.  <span data-ttu-id="37e63-117">下部にある、**グループ ハブ** タブで、**グループの概要** ウィンドウで、状態レポートなど、構成する をクリックして**EDI インターチェンジと関連する ACK の状態**です。</span><span class="sxs-lookup"><span data-stu-id="37e63-117">At the bottom of the **Group Hub** tab in the **Group Overview** pane, click the status report that you want to configure, such as **EDI Interchange and Correlated ACK Status**.</span></span>  
  
3.  <span data-ttu-id="37e63-118">**クエリ式**状態レポート ペインの領域は、クエリを定義するすべてのフィルター条件が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="37e63-118">In the **Query Expression** area of the status report pane, verify that all filter criteria that you want to define for the query are present.</span></span> <span data-ttu-id="37e63-119">いない場合は、空の行で下矢印をクリックして、**フィールド名**フィルター条件をクエリ式を追加するをクリックし、クエリ式の下部にある列です。</span><span class="sxs-lookup"><span data-stu-id="37e63-119">If not, click the down arrow in the empty row in the **Field Name** column at the bottom of the query expression, and select any filter criteria that you want to add to the query expression.</span></span> <span data-ttu-id="37e63-120">フィルター条件の行を削除するには、行を選択しをクリックすると、**削除**キーボードのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="37e63-120">You can delete a filter criteria row by selecting the row and clicking the **Delete** button on the keyboard.</span></span>  
  
4.  <span data-ttu-id="37e63-121">フィルタ式の値が適切かどうか確認します。</span><span class="sxs-lookup"><span data-stu-id="37e63-121">Verify that the values for the filter expressions are as desired.</span></span> <span data-ttu-id="37e63-122">いない場合は、下矢印をクリックして、**演算子**をクエリ操作を選択し、適切な値を入力列、**値**列です。</span><span class="sxs-lookup"><span data-stu-id="37e63-122">If not, click the down arrow for the **Operator** column to select a query operation, and enter the appropriate value in the **Value** column.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37e63-123">演算子とのクエリ式のフィルタ条件として使用可能な値に記載されて[型の EDI および AS2 状態レポート](../core/types-of-edi-and-as2-status-reports.md)と**EDI AS2 状態レポート UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="37e63-123">The operators and values available for filter criteria in the query expressions are described in [Types of EDI and AS2 Status Reports](../core/types-of-edi-and-as2-status-reports.md) and the **EDI-AS2 Status Reports UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
5.  <span data-ttu-id="37e63-124">フィルター条件に従った状態レポートを表示する、クエリを実行する をクリックして**クエリの実行**です。</span><span class="sxs-lookup"><span data-stu-id="37e63-124">To run the query, displaying the status report according to the filter criteria, click **Run Query**.</span></span>  
  
6.  <span data-ttu-id="37e63-125">クエリ式を .btq ファイルとして保存する] をクリックして**名前を付けて保存**フォルダーを指定し、ファイル名を入力し、[クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="37e63-125">To save a query expression as a .btq file, click **Save As**, specify the folder and enter a filename, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="37e63-126">保存されている .btq ファイルを開くにはクリックして**クエリを開く**です。</span><span class="sxs-lookup"><span data-stu-id="37e63-126">To open a saved .btq file, click **Open Query**.</span></span>  
  
## <a name="configure-the-type-of-data-displayed-in-the-status-report-pane"></a><span data-ttu-id="37e63-127">状態レポート ペインに表示されるデータの種類を構成します。</span><span class="sxs-lookup"><span data-stu-id="37e63-127">Configure the type of data displayed in the status report pane</span></span>  
  
1.  <span data-ttu-id="37e63-128">状態レポート ペインの状態の結果領域を右クリックし、をクリックして**列の追加/削除**です。</span><span class="sxs-lookup"><span data-stu-id="37e63-128">Right-click the status results area of the status report pane, and then click **Add/Remove Columns**.</span></span>  
  
2.  <span data-ttu-id="37e63-129">表示されている列の一覧に状態カテゴリを追加するには、内の列をクリックして、**使用可能な列**一覧をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="37e63-129">To add a status category to the displayed columns list, click a column in the **Available columns** list, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="37e63-130">表示されている列の一覧から状態カテゴリを削除するには、内の列をクリックして、**表示されている列**一覧をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="37e63-130">To remove a status category from the displayed columns list, click a column in the **Displayed columns** list, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37e63-131">参照</span><span class="sxs-lookup"><span data-stu-id="37e63-131">See Also</span></span>  
 <span data-ttu-id="37e63-132">[EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="37e63-132">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="37e63-133">[EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md) </span><span class="sxs-lookup"><span data-stu-id="37e63-133">[EDI and AS2 Status Reporting](../core/edi-and-as2-status-reporting.md) </span></span>  
 <span data-ttu-id="37e63-134">[EDI および AS2 状態レポートを有効にします。](../core/enabling-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="37e63-134">[Enabling EDI and AS2 Status Reports](../core/enabling-edi-and-as2-status-reports.md) </span></span>  
 [<span data-ttu-id="37e63-135">EDI または AS2 状態レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="37e63-135">Displaying an EDI or AS2 Status Report</span></span>](../core/displaying-an-edi-or-as2-status-report.md)
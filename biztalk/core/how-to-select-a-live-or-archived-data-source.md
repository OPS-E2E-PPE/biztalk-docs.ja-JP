---
title: ライブまたはアーカイブ済みのデータ ソースを選択する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, archived data
- Management database, real-time data
- HAT, real-time data
- archived data, Management database
- HAT, archived data
- real-time data, HAT
- real-time data, Management database
- archived data, HAT
ms.assetid: e2325823-22e1-4a1a-865b-15757b215b29
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83f034a41fffa0c646b0173e8b889c20373760ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967155"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a><span data-ttu-id="d5de3-102">ライブ データまたはアーカイブ済みのデータのデータ ソースを選択する方法</span><span class="sxs-lookup"><span data-stu-id="d5de3-102">How to Select a Live or Archived Data Source</span></span>
<span data-ttu-id="d5de3-103">BizTalktracking では、アーカイブ済みのデータとライブ データの両方にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d5de3-103">BizTalktracking enables you to access both archived and live data.</span></span> <span data-ttu-id="d5de3-104">メインのライブまたはアーカイブ済みのデータ ソースを選択する**BizTalk Server 管理**BizTalk Server 管理コンソールのノード。</span><span class="sxs-lookup"><span data-stu-id="d5de3-104">You select a live or archived data source from the main **BizTalk Server Administration** node BizTalk Server Administration Console.</span></span>  <span data-ttu-id="d5de3-105">既定のソースは、BizTalk 管理サーバーから取得されるライブ データです。</span><span class="sxs-lookup"><span data-stu-id="d5de3-105">The default source is live data, retrieved from the BizTalk Management database.</span></span> <span data-ttu-id="d5de3-106">アーカイブ済みのデータを使用する場合は、使用する適切なサーバーとデータベースを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5de3-106">If you choose to work with archived data, you must select the appropriate server/s and database/s with which to work.</span></span>  

-   <span data-ttu-id="d5de3-107">アーカイブされたデータ: アーカイブされたデータを分析することができます、ビジネスと、システムの両方の傾向を調べます必要なだけさかのぼりためすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5de3-107">Archived data: Analyzing archived data enables you to examine trends both in your business and on your system, because you can look as far back as necessary.</span></span> <span data-ttu-id="d5de3-108">アーカイブ済みのデータを選択する場合、そのデータが格納された SQL Server および SQL データベースも選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5de3-108">If you select archived data, you must also select the appropriate SQL Servers and SQL databases that contain the archived data.</span></span>  

     <span data-ttu-id="d5de3-109">アーカイブ済みのデータが選択して指定**既存の追跡データベースに接続しています.**.</span><span class="sxs-lookup"><span data-stu-id="d5de3-109">Archived data is designated by selecting **Connect to an existing tracking database…**.</span></span>  

-   <span data-ttu-id="d5de3-110">ライブ データ: ライブ データを分析を識別し、開発環境またはステージング環境の問題を解決できるように、オーケストレーションとパイプラインを監視できます。</span><span class="sxs-lookup"><span data-stu-id="d5de3-110">Live data: Analyzing live data enables you to monitor orchestrations and pipelines, so that you can identify and fix problems in the development or staging environment.</span></span> <span data-ttu-id="d5de3-111">メッセージが保留されている原因など、システムの問題もライブ データを監視することで解決できます。</span><span class="sxs-lookup"><span data-stu-id="d5de3-111">Monitoring live data also enables you to correct problems in your system, such as why messages are being suspended.</span></span>  

     <span data-ttu-id="d5de3-112">ライブ データが選択して指定**既存のグループに接続しています.**.</span><span class="sxs-lookup"><span data-stu-id="d5de3-112">Live data is designated by selecting **Connect to an existing group…**.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="d5de3-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="d5de3-113">Prerequisites</span></span>  
 <span data-ttu-id="d5de3-114">この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5de3-114">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  

### <a name="to-select-live-data"></a><span data-ttu-id="d5de3-115">ライブ データを選択するには</span><span class="sxs-lookup"><span data-stu-id="d5de3-115">To select live data</span></span>  

1. <span data-ttu-id="d5de3-116">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="d5de3-116">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="d5de3-117">[メイン] をクリックして**BizTalk Server 管理**ノード。</span><span class="sxs-lookup"><span data-stu-id="d5de3-117">Click the main  **BizTalk Server Administration** node.</span></span>  

3. <span data-ttu-id="d5de3-118">クリックして**既存のグループに接続しています.**</span><span class="sxs-lookup"><span data-stu-id="d5de3-118">Click **Connect to an existing group…**</span></span>  

4. <span data-ttu-id="d5de3-119">**SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5de3-119">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  

5. <span data-ttu-id="d5de3-120">**データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**します。</span><span class="sxs-lookup"><span data-stu-id="d5de3-120">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  

6. <span data-ttu-id="d5de3-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5de3-121">Click **OK**.</span></span>  

### <a name="to-select-archived-data"></a><span data-ttu-id="d5de3-122">アーカイブ済みのデータを選択するには</span><span class="sxs-lookup"><span data-stu-id="d5de3-122">To select archived data</span></span>  

1. <span data-ttu-id="d5de3-123">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="d5de3-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="d5de3-124">[メイン] をクリックして**BizTalk Server 管理**ノード。</span><span class="sxs-lookup"><span data-stu-id="d5de3-124">Click the main  **BizTalk Server Administration** node.</span></span>  

3. <span data-ttu-id="d5de3-125">クリックして**既存の追跡データベースに接続しています.**</span><span class="sxs-lookup"><span data-stu-id="d5de3-125">Click **Connect to an existing tracking database…**</span></span>  

4. <span data-ttu-id="d5de3-126">**SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5de3-126">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  

5. <span data-ttu-id="d5de3-127">**データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**します。</span><span class="sxs-lookup"><span data-stu-id="d5de3-127">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  

6. <span data-ttu-id="d5de3-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5de3-128">Click **OK**.</span></span>

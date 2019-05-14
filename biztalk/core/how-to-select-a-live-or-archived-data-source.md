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
ms.openlocfilehash: e5917c4488e047a1956fde66a659754c659f23d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383958"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a><span data-ttu-id="f4531-102">ライブまたはアーカイブ済みのデータ ソースを選択する方法</span><span class="sxs-lookup"><span data-stu-id="f4531-102">How to Select a Live or Archived Data Source</span></span>
<span data-ttu-id="f4531-103">Biztalktracking ではアーカイブ済みとライブの両方のデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f4531-103">BizTalktracking enables you to access both archived and live data.</span></span> <span data-ttu-id="f4531-104">メインのライブまたはアーカイブ済みのデータ ソースを選択する**BizTalk Server 管理**BizTalk Server 管理コンソールのノード。</span><span class="sxs-lookup"><span data-stu-id="f4531-104">You select a live or archived data source from the main **BizTalk Server Administration** node BizTalk Server Administration Console.</span></span>  <span data-ttu-id="f4531-105">既定のソースは、ライブ データを BizTalk 管理データベースから取得します。</span><span class="sxs-lookup"><span data-stu-id="f4531-105">The default source is live data, retrieved from the BizTalk Management database.</span></span> <span data-ttu-id="f4531-106">アーカイブされたデータを操作する場合は、適切なサーバー/秒と動作するデータベース/秒を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4531-106">If you choose to work with archived data, you must select the appropriate server/s and database/s with which to work.</span></span>  

-   <span data-ttu-id="f4531-107">アーカイブされたデータ:アーカイブ済みのデータを分析することができます、ビジネスと、システムの両方の傾向を調べる必要なだけさかのぼりためすることができます。</span><span class="sxs-lookup"><span data-stu-id="f4531-107">Archived data: Analyzing archived data enables you to examine trends both in your business and on your system, because you can look as far back as necessary.</span></span> <span data-ttu-id="f4531-108">アーカイブ済みのデータを選択すると場合、は、適切な SQL サーバーと、アーカイブされたデータを含む SQL データベースも選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4531-108">If you select archived data, you must also select the appropriate SQL Servers and SQL databases that contain the archived data.</span></span>  

     <span data-ttu-id="f4531-109">アーカイブ済みのデータが選択して指定**既存の追跡データベースに接続しています.**.</span><span class="sxs-lookup"><span data-stu-id="f4531-109">Archived data is designated by selecting **Connect to an existing tracking database…**.</span></span>  

-   <span data-ttu-id="f4531-110">ライブ データ。ライブ データを分析するには、識別し、開発環境またはステージング環境の問題を解決できるようにオーケストレーションとパイプラインを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="f4531-110">Live data: Analyzing live data enables you to monitor orchestrations and pipelines, so that you can identify and fix problems in the development or staging environment.</span></span> <span data-ttu-id="f4531-111">ライブ データの監視ではメッセージが保留されている理由など、システムでの問題を修正することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4531-111">Monitoring live data also enables you to correct problems in your system, such as why messages are being suspended.</span></span>  

     <span data-ttu-id="f4531-112">ライブ データが選択して指定**既存のグループに接続しています.**.</span><span class="sxs-lookup"><span data-stu-id="f4531-112">Live data is designated by selecting **Connect to an existing group…**.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="f4531-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="f4531-113">Prerequisites</span></span>  
 <span data-ttu-id="f4531-114">この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4531-114">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  

### <a name="to-select-live-data"></a><span data-ttu-id="f4531-115">ライブ データを選択するには</span><span class="sxs-lookup"><span data-stu-id="f4531-115">To select live data</span></span>  

1. <span data-ttu-id="f4531-116">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f4531-116">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f4531-117">[メイン] をクリックして**BizTalk Server 管理**ノード。</span><span class="sxs-lookup"><span data-stu-id="f4531-117">Click the main  **BizTalk Server Administration** node.</span></span>  

3. <span data-ttu-id="f4531-118">クリックして**既存のグループに接続しています.**</span><span class="sxs-lookup"><span data-stu-id="f4531-118">Click **Connect to an existing group…**</span></span>  

4. <span data-ttu-id="f4531-119">**SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4531-119">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  

5. <span data-ttu-id="f4531-120">**データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**します。</span><span class="sxs-lookup"><span data-stu-id="f4531-120">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  

6. <span data-ttu-id="f4531-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4531-121">Click **OK**.</span></span>  

### <a name="to-select-archived-data"></a><span data-ttu-id="f4531-122">アーカイブされたデータを選択するには</span><span class="sxs-lookup"><span data-stu-id="f4531-122">To select archived data</span></span>  

1. <span data-ttu-id="f4531-123">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f4531-123">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f4531-124">[メイン] をクリックして**BizTalk Server 管理**ノード。</span><span class="sxs-lookup"><span data-stu-id="f4531-124">Click the main  **BizTalk Server Administration** node.</span></span>  

3. <span data-ttu-id="f4531-125">クリックして**既存の追跡データベースに接続しています.**</span><span class="sxs-lookup"><span data-stu-id="f4531-125">Click **Connect to an existing tracking database…**</span></span>  

4. <span data-ttu-id="f4531-126">**SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4531-126">In the **SQL Server name** box, type the name of the server that hosts the BizTalk Management database.</span></span>  

5. <span data-ttu-id="f4531-127">**データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**します。</span><span class="sxs-lookup"><span data-stu-id="f4531-127">In the **Database name** drop-down list box, select **BizTalkMgmtDb**.</span></span>  

6. <span data-ttu-id="f4531-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4531-128">Click **OK**.</span></span>

---
title: SAP のため、レポートの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0932ffc5-cde0-4d14-822f-713b760c3f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f43b35eacd264820afd07fce9d218a28e6b2e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372024"
---
# <a name="view-the-reports-for-sap"></a><span data-ttu-id="545db-102">SAP のため、レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="545db-102">View the Reports for SAP</span></span>
<span data-ttu-id="545db-103">表示できるレポートを作成した後 Visual Studio を使用するか、ネットワーク経由でインターネット インフォメーション サービス (IIS) とアクセス上のレポート サーバー上でホストします。</span><span class="sxs-lookup"><span data-stu-id="545db-103">After you have created the report, you can view it either using Visual Studio or host it on the Report Server on Internet Information Services (IIS) and access over the network.</span></span> <span data-ttu-id="545db-104">このトピックでは、Visual Studio と IIS を使用して両方でレポートを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="545db-104">This topic provides instructions on how to view reports both in Visual Studio and using IIS.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="545db-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="545db-105">Prerequisites</span></span>  
 <span data-ttu-id="545db-106">このトピックで説明する手順を実行する前にする必要がありますが生成したレポート」の説明に従って[Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="545db-106">Before performing the procedures provided in this topic, you must have generated a report as described in [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md).</span></span>  
  
### <a name="to-view-the-reports-in-visual-studio"></a><span data-ttu-id="545db-107">Visual Studio でレポートを表示するには</span><span class="sxs-lookup"><span data-stu-id="545db-107">To view the reports in Visual Studio</span></span>  
  
1. <span data-ttu-id="545db-108">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでプロジェクト名を右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="545db-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], right-click the project name in the Solution Explorer, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="545db-109">レポート プロパティ ページ ダイアログ ボックスで次のようにクリックします。 **Configuration Manager**、下のチェック ボックスをオフにし、**デプロイ**列。</span><span class="sxs-lookup"><span data-stu-id="545db-109">In the report property pages dialog box, click **Configuration Manager**, and clear the check box under the **Deploy** column.</span></span> <span data-ttu-id="545db-110">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="545db-110">Click **Close**.</span></span>  
  
3. <span data-ttu-id="545db-111">レポート プロパティ ページ ダイアログ ボックスの**startitem**プロパティが、レポートの名前を選択し、クリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="545db-111">In the report property pages dialog box, for the **StartItem** property, select the name of the report, and then click **OK**.</span></span>  
  
    <span data-ttu-id="545db-112">![レポート サーバー プロジェクトのプロパティを指定](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")</span><span class="sxs-lookup"><span data-stu-id="545db-112">![Specify properties for the Report Server project](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")</span></span>  
  
4. <span data-ttu-id="545db-113">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="545db-113">Right-click the project name in the Solution Explorer, and then click **Build**.</span></span>  
  
5. <span data-ttu-id="545db-114">キーを押して`F5`レポートを生成するプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="545db-114">Press `F5` to run the project to generate the report.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="545db-115">[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]、 をクリックして、レポートを表示できます、**プレビュー**タブ。このような場合は、[プレビュー] タブ内で以降のダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="545db-115">In [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], you can see the report by clicking the **Preview** tab. In such a case, the subsequent dialog boxes will open within the preview tab.</span></span>  
  
6. <span data-ttu-id="545db-116">レポートの指定した同じ名前のダイアログ ボックス開きます。</span><span class="sxs-lookup"><span data-stu-id="545db-116">A dialog box with the same name as you specified for the report opens up.</span></span> <span data-ttu-id="545db-117">選択した場合、データ ソースを作成するときに、**資格情報の入力を求める**オプションで、SAP システムのユーザー名とパスワードを入力します。 をクリック**レポートの表示**します。</span><span class="sxs-lookup"><span data-stu-id="545db-117">While creating the data source, if you chose the **Prompt for credentials** option, enter the user name and password for the SAP system, and then click **View Report**.</span></span>  
  
    <span data-ttu-id="545db-118">![レポートを生成する SAP 資格情報を指定](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")</span><span class="sxs-lookup"><span data-stu-id="545db-118">![Specify SAP credentials to generate a report](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")</span></span>  
  
7. <span data-ttu-id="545db-119">クエリを指定した場合、レポート サーバー プロジェクトを作成するには、パラメーターが必要です。 中にパラメーターの値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="545db-119">If the query you specified while creating the Report Server project requires a parameter, you must enter the value of the parameter.</span></span> <span data-ttu-id="545db-120">たとえばで指定したクエリの[Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)トピックでは、パラメーター、パラメーターの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="545db-120">For example, for the query you specified in the [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) topic, requires you to specify a value for the parameter, PARAM.</span></span>  
  
    <span data-ttu-id="545db-121">必要な場合に、パラメーターの値を指定し、クリックして**レポートの表示**します。</span><span class="sxs-lookup"><span data-stu-id="545db-121">Specify the value of the parameter, if required, and click **View Report**.</span></span>  
  
    <span data-ttu-id="545db-122">![レポートを生成するパラメーターを指定する](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")</span><span class="sxs-lookup"><span data-stu-id="545db-122">![Specify parameters to generate a report](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")</span></span>  
  
### <a name="to-host-the-reports-on-report-server"></a><span data-ttu-id="545db-123">レポート サーバーでレポートをホストするには</span><span class="sxs-lookup"><span data-stu-id="545db-123">To host the reports on Report Server</span></span>  
  
1. <span data-ttu-id="545db-124">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでプロジェクト名を右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="545db-124">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], right-click the project name in the Solution Explorer, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="545db-125">レポート プロパティ ページ ダイアログ ボックスで次のようにクリックします。 **Configuration Manager**、下のチェック ボックスを選択し、**デプロイ**列。</span><span class="sxs-lookup"><span data-stu-id="545db-125">In the report property pages dialog box, click **Configuration Manager**, and select the check box under the **Deploy** column.</span></span> <span data-ttu-id="545db-126">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="545db-126">Click **Close**.</span></span>  
  
3. <span data-ttu-id="545db-127">レポート プロパティ ページ ダイアログ ボックスの**StartItem**プロパティ、レポートの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="545db-127">In the report property pages dialog box, for the **StartItem** property, select the name of the report.</span></span>  
  
4. <span data-ttu-id="545db-128">レポート プロパティ ページ ダイアログ ボックスの**TargetServerURL**プロパティ、レポート サーバーの URL を指定し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="545db-128">In the report property pages dialog box, for the **TargetServerURL** property, specify a URL for the Report Server, and then click **OK**.</span></span> <span data-ttu-id="545db-129">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="545db-129">For example:</span></span>  
  
   ```  
   http://localhost/reportserver  
   ```  
  
    <span data-ttu-id="545db-130">![レポート サーバーの URL の指定](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")</span><span class="sxs-lookup"><span data-stu-id="545db-130">![Specify URL for the Report Server](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")</span></span>  
  
5. <span data-ttu-id="545db-131">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="545db-131">Right-click the project name in the Solution Explorer, and then click **Build**.</span></span>  
  
6. <span data-ttu-id="545db-132">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="545db-132">Right-click the project name in the Solution Explorer, and then click **Deploy**.</span></span>  
  
7. <span data-ttu-id="545db-133">IIS を起動します。</span><span class="sxs-lookup"><span data-stu-id="545db-133">Start IIS.</span></span> <span data-ttu-id="545db-134">クリックして**開始**、 をクリックして**実行**、型`inetmgr`、キーを押します`Enter`します。</span><span class="sxs-lookup"><span data-stu-id="545db-134">Click **Start**, click **Run**, type `inetmgr`, and press `Enter`.</span></span>  
  
8. <span data-ttu-id="545db-135">**インターネット インフォメーション サービス (IIS) マネージャー**スナップインで、コンピューター名を展開し、 **Websites**、展開**既定の Web サイト**、右クリック**ReportServer**、 をクリックし、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="545db-135">In the **Internet Information Services (IIS) Manager** snap-in, expand the computer name, expand **Web Sites**, expand **Default Web Site**, right-click **ReportServer**, and then click **Browse**.</span></span>  
  
9. <span data-ttu-id="545db-136">右側のウィンドウで、プロジェクトの名前をクリックし、レポートの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="545db-136">In the right pane, click the name of the project, and then click on the name of the report.</span></span>  
  
10. <span data-ttu-id="545db-137">選択した場合、データ ソースを作成するときに、**資格情報の入力を求める**オプション、SAP システムのユーザー名とパスワードを入力します をクリックして**レポートの表示**します。</span><span class="sxs-lookup"><span data-stu-id="545db-137">While creating the data source, if you chose the **Prompt for credentials** option, enter the user name and password for the SAP system and click **View Report**.</span></span>  
  
11. <span data-ttu-id="545db-138">クエリを指定した場合、レポート サーバー プロジェクトを作成するには、パラメーターが必要です。 中にパラメーターの値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="545db-138">If the query you specified while creating the Report Server project requires a parameter, you must enter the value of the parameter.</span></span> <span data-ttu-id="545db-139">たとえばで指定したクエリの[Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)トピックでは、パラメーター、パラメーターの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="545db-139">For example, for the query you specified in the [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) topic, requires you to specify a value for the parameter, PARAM.</span></span>  
  
     <span data-ttu-id="545db-140">必要な場合に、パラメーターの値を指定し、クリックして**レポートの表示**します。</span><span class="sxs-lookup"><span data-stu-id="545db-140">Specify the value of the parameter, if required, and click **View Report**.</span></span>  
  
     <span data-ttu-id="545db-141">![レポートを生成するパラメーターを指定する](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")</span><span class="sxs-lookup"><span data-stu-id="545db-141">![Specify parameters to generate a report](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="545db-142">レポートの URL を指定することにより、web ブラウザーから直接表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="545db-142">You can also view directly from the web browser by giving the URL for the report.</span></span> <span data-ttu-id="545db-143">レポートの一般的な URL`is http://localhohost/reportserver/<report_name>`します。</span><span class="sxs-lookup"><span data-stu-id="545db-143">A typical URL for the report `is http://localhohost/reportserver/<report_name>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="545db-144">参照</span><span class="sxs-lookup"><span data-stu-id="545db-144">See Also</span></span>  
 [<span data-ttu-id="545db-145">Data Provider for SAP を SSRS と一緒に使用する</span><span class="sxs-lookup"><span data-stu-id="545db-145">Use the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)
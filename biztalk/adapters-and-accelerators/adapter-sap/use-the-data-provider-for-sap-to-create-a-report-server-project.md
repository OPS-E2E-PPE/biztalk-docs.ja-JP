---
title: Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe985b5-ba67-4179-a31c-4f41106c32be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f57155b386af979f1da52d39d062aff171203b5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008211"
---
# <a name="use-the-data-provider-for-sap-to-create-a-report-server-project"></a><span data-ttu-id="ed06a-102">Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="ed06a-102">Use the Data Provider for SAP to Create a Report Server Project</span></span>
<span data-ttu-id="ed06a-103">レポート サーバーを作成する必要がありますを使用して、プロジェクト、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、SAP システムで使用可能なデータのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-103">You must create a Report Server project, using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], to generate reports for the data available in an SAP system.</span></span> <span data-ttu-id="ed06a-104">このトピックでは、レポート サーバー プロジェクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-104">This topic provides instructions on how to create a Report Server project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ed06a-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="ed06a-105">Prerequisites</span></span>  
 <span data-ttu-id="ed06a-106">このトピックで説明する手順を実行する前にインストールされていることを確認します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]のインストール中に、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="ed06a-106">Before performing the procedures provided in this topic, make sure you installed the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] while installing the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="ed06a-107">詳細については[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]のインストールで使用可能なインストール ガイドを参照してください\<*インストール ドライブ*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-107">For more information about [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, refer to the installation guide available at \<*installation drive*\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
### <a name="to-create-a-report-server-project"></a><span data-ttu-id="ed06a-108">レポート サーバー プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="ed06a-108">To create a Report Server project</span></span>  
  
1. <span data-ttu-id="ed06a-109">開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]レポート サーバー プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-109">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create a Report Server project.</span></span> <span data-ttu-id="ed06a-110">レポート サーバー プロジェクトを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed06a-110">To create a Report Server project, do the following:</span></span>  
  
   1.  <span data-ttu-id="ed06a-111">をクリックして、**ファイル** メニューのをクリックして**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-111">Click the **File** menu, click **New**, and then click **Project**.</span></span>  
  
   2.  <span data-ttu-id="ed06a-112">**新しいプロジェクト**] ダイアログ ボックスから、**プロジェクトの種類**一覧で、[**ビジネス インテリジェンス プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-112">In the **New Project** dialog box, from the **Project types** list, select **Business Intelligence Projects**.</span></span> <span data-ttu-id="ed06a-113">**Visual Studio にインストールされたテンプレート**一覧で、**レポート サーバー プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-113">From **the Visual Studio installed templates** list, select **Report Server Project**.</span></span>  
  
   3.  <span data-ttu-id="ed06a-114">プロジェクトの場所と名前を指定し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-114">Specify a name and location of the project and click **OK**.</span></span> <span data-ttu-id="ed06a-115">このトピックでは、プロジェクトの名前を指定`SAP_ Report`します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-115">For this topic, specify the name of the project as `SAP_ Report`.</span></span>  
  
2. <span data-ttu-id="ed06a-116">新しいデータ ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-116">Add a new data source:</span></span>  
  
   1. <span data-ttu-id="ed06a-117">ソリューション エクスプ ローラーで、右クリックして**共有データ ソース**、 をクリック**新しいデータ ソースの追加**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-117">From the Solution Explorer, right-click **Shared Data Sources**, and click **Add New Data Source**.</span></span>  
  
   2. <span data-ttu-id="ed06a-118">**共有データ ソース** ダイアログ ボックスで、**全般** タブで、データ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-118">In the **Shared Data Source** dialog box, in the **General** tab, specify a name for the data source.</span></span> <span data-ttu-id="ed06a-119">このトピックと名前を指定`SAPDataSource`します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-119">For this topic, specify the name as `SAPDataSource`.</span></span>  
  
   3. <span data-ttu-id="ed06a-120">**型**一覧で、 **Data Provider for SAP**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-120">From the **Type** list, select **Data Provider for SAP**.</span></span>  
  
   4. <span data-ttu-id="ed06a-121">**接続文字列**ボックスでの接続文字列を指定します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-121">In the **Connection String** box, specify the connection string for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="ed06a-122">については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]接続文字列を参照してください[SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-122">For information about the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
       <span data-ttu-id="ed06a-123">![データ ソースを作成する](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")</span><span class="sxs-lookup"><span data-stu-id="ed06a-123">![Create a data source](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="ed06a-124">接続文字列の一部として、資格情報を指定するか、次の手順」の説明に従って、それらを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ed06a-124">You can choose to specify the credentials as part of the connection string or specify them as described in the next step.</span></span>  
  
   5. <span data-ttu-id="ed06a-125">**資格情報**タブに、次のいずれかを選択してクリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="ed06a-125">In the **Credentials** tab, choose one of the following, and then click **OK**:</span></span>  
  
      |<span data-ttu-id="ed06a-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed06a-126">Use this</span></span>|<span data-ttu-id="ed06a-127">目的</span><span class="sxs-lookup"><span data-stu-id="ed06a-127">To do this</span></span>|  
      |--------------|----------------|  
      |<span data-ttu-id="ed06a-128">**[特定のユーザー名とパスワードを使用する]**</span><span class="sxs-lookup"><span data-stu-id="ed06a-128">**Use a specific user name and password**</span></span>|<span data-ttu-id="ed06a-129">ユーザー名と SAP システムに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-129">Specify a user name and password to connect to the SAP system.</span></span>|  
      |<span data-ttu-id="ed06a-130">**資格情報のプロンプト**</span><span class="sxs-lookup"><span data-stu-id="ed06a-130">**Prompt for credentials**</span></span>|<span data-ttu-id="ed06a-131">レポートの生成時に、SAP システムの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-131">Enter the credentials for the SAP system while the report is generated.</span></span> <span data-ttu-id="ed06a-132">**注:** の接続文字列の一部として、指定した場合、このオプションは、資格情報をオーバーライドを指定する資格情報。</span><span class="sxs-lookup"><span data-stu-id="ed06a-132">**Note:**  The credentials you specify for this option will override the credentials, if specified, as part of the connection string.</span></span>|  
      |<span data-ttu-id="ed06a-133">**資格情報なし**</span><span class="sxs-lookup"><span data-stu-id="ed06a-133">**No credentials**</span></span>|<span data-ttu-id="ed06a-134">接続文字列の一部として、ユーザー名とパスワードを指定する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-134">Choose this option if you are providing the user name and password as part of the connection string.</span></span>|  
  
      > [!NOTE]
      >  <span data-ttu-id="ed06a-135">レポート サーバー プロジェクトの Windows 認証モードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ed06a-135">The Windows Authentication mode is not supported for Report Server projects.</span></span>  
  
3. <span data-ttu-id="ed06a-136">新しいレポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-136">Add a new report:</span></span>  
  
   1. <span data-ttu-id="ed06a-137">ソリューション エクスプ ローラーで、右クリックして**レポート**、 をクリックし、**新しいレポートの追加**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-137">From the Solution Explorer, right-click **Reports**, and then click **Add New Report**.</span></span>  
  
       <span data-ttu-id="ed06a-138">これは、レポート ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-138">This starts the Report Wizard.</span></span>  
  
   2. <span data-ttu-id="ed06a-139">クリックして、ようこそ画面の情報を読み取る**次**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-139">Read the information on the welcome screen, and then click **Next**.</span></span>  
  
   3. <span data-ttu-id="ed06a-140">**データ ソースを選択** ダイアログ ボックスで、選択、**共有データ ソース**オプションで、選択、 **SAPDataSource**前の手順で作成し、 をクリックして**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-140">In the **Select the Data Source** dialog box, choose the **Shared data source** option, select the **SAPDataSource** you created in the previous step, and then click **Next**.</span></span>  
  
   4. <span data-ttu-id="ed06a-141">選択した場合、**資格情報の入力を求める**、データ ソースを作成するときにユーザーの資格情報を指定するオプション、**データ ソースの資格情報の入力** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed06a-141">If you chose the **Prompt for credentials** option to specify the user credentials while creating the data source, an **Enter Data Source Credentials** dialog box appears.</span></span> <span data-ttu-id="ed06a-142">ユーザー名と、SAP システムに接続し、をクリックし、パスワードを指定**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-142">Specify the user name and password to connect to the SAP system, and then click **OK**.</span></span>  
  
       <span data-ttu-id="ed06a-143">他の資格情報を指定するためのオプションを選択した場合、ウィザードは、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="ed06a-143">If you chose any other option for specifying credentials, the wizard proceeds to the next step.</span></span>  
  
   5. <span data-ttu-id="ed06a-144">**クエリをデザインする** ダイアログ ボックスで、レポートを生成するために使用するクエリ文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-144">In the **Design the Query** dialog box, specify a query string that is used to generate a report.</span></span> <span data-ttu-id="ed06a-145">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-145">For example:</span></span>  
  
      ```  
      SELECT TOP 2 KUNNR, NAME1 FROM KNA1 WHERE NAME1 LIKE @PARAM  
      ```  
  
       <span data-ttu-id="ed06a-146">このクエリでは、NAME1 はするが、レポートの生成中に指定する名前 KNA1 テーブルから上位 2 つのレコードが取得されます。</span><span class="sxs-lookup"><span data-stu-id="ed06a-146">This query will retrieve the top two records from the KNA1 table where the NAME1 is the name that you will specify while generating the report.</span></span>  
  
       <span data-ttu-id="ed06a-147">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed06a-147">Click **Next**.</span></span>  
  
   6. <span data-ttu-id="ed06a-148">以降のダイアログ ボックスでは、レポートを表示する形式を設計できます。</span><span class="sxs-lookup"><span data-stu-id="ed06a-148">In the subsequent dialog boxes you can design the format in which you want the report to appear.</span></span> <span data-ttu-id="ed06a-149">既定の形式を使用する場合をクリックして**完了 >>&#124;** に直接移動する、**完了** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ed06a-149">If you want to use the default format, click **Finish >>&#124;** to directly go to the **Finish** dialog box.</span></span>  
  
   7. <span data-ttu-id="ed06a-150">**ウィザードの完了**ダイアログ ボックスで、レポートの名前を指定の概要を確認 をクリックし、**完了**します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-150">In the **Completing the Wizard** dialog box, specify a name for the report, review the summary, and then click **Finish**.</span></span> <span data-ttu-id="ed06a-151">このトピックでは、レポートの名前を指定します`SAPReport`します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-151">For this topic, specify the name of the report as `SAPReport`.</span></span>  
  
      <span data-ttu-id="ed06a-152">レポートを表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ed06a-152">You can now view the report.</span></span> <span data-ttu-id="ed06a-153">レポートを表示する方法については、次を参照してください。 [SAP についてレポートを表示](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="ed06a-153">For instructions about how to view the report, see [view the Reports for SAP](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed06a-154">参照</span><span class="sxs-lookup"><span data-stu-id="ed06a-154">See Also</span></span>  
 [<span data-ttu-id="ed06a-155">Data Provider for SAP を SSRS と一緒に使用する</span><span class="sxs-lookup"><span data-stu-id="ed06a-155">Use the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)
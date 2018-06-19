---
title: SharePoint での Oracle データベース アダプターの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 254204e5-3b5d-4e70-97ab-817660d1206a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a5866344e666c9e9cb49af6c6d99211774a2758
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
ms.locfileid: "23450313"
---
# <a name="use-the-oracle-database-adapter-with-sharepoint"></a><span data-ttu-id="ad4eb-102">SharePoint での Oracle データベース アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-102">Use the Oracle Database Adapter with SharePoint</span></span>
<span data-ttu-id="ad4eb-103">WCF アダプター サービス開発ウィザード[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]Oracle データベースと、Microsoft BizTalk Adapter for Oracle E-business Suite は、Microsoft SharePoint の外部のデータ ソースと直接使用される Microsoft BizTalk Adapter を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-103">The WCF Adapter Service Development Wizard for [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] enables the Microsoft BizTalk Adapter for Oracle Database and the Microsoft BizTalk Adapter for Oracle E-Business Suite to be directly consumed as an external datasource in Microsoft SharePoint.</span></span> <span data-ttu-id="ad4eb-104">この機能をサポートする追加サービス開発ウィザードが起動し、 **WCF アダプタ サービス**、新しい Visual c# の Web サイトを作成するためのテンプレート[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-104">The Add Service Development Wizard that supports this feature is launched with the **WCF Adapter Service** template for creating a new Visual C# Web Sites in [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="ad4eb-105">テンプレートが付属して、[!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-105">The template is included with the [!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ad4eb-106">また、Microsoft Windows Communication Foundation (WCF) の基幹業務 (LOB) アダプター SDK をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-106">You must also install the Microsoft Windows Communication Foundation (WCF) Line of Business (LOB) Adapter SDK.</span></span>  
  
## <a name="sharepoint-operation-support"></a><span data-ttu-id="ad4eb-107">SharePoint の操作のサポート</span><span class="sxs-lookup"><span data-stu-id="ad4eb-107">SharePoint Operation Support</span></span>  
 <span data-ttu-id="ad4eb-108">アダプター サービス開発ウィザードでは、Microsoft SharePoint と互換性がある Oracle アダプターの特別なサービス コントラクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-108">The Adapter Service Development wizard generates a special service contract for the Oracle adapters that is compatible with Microsoft SharePoint.</span></span> <span data-ttu-id="ad4eb-109">ウィザードを Microsoft SharePoint と、アダプターを統合するため、次の操作を含むサービス コントラクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-109">The wizard will generate a service contract which includes the following operations for integrating the adapter with Microsoft SharePoint:</span></span>  
  
-   <span data-ttu-id="ad4eb-110">**作成します。** CreateItem_ 操作でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-110">**Create:** Supported by the CreateItem_ operation.</span></span>  
  
-   <span data-ttu-id="ad4eb-111">**お読みください:** ReadItem_ 操作でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-111">**Read:** Supported by the ReadItem_ operation.</span></span>  
  
-   <span data-ttu-id="ad4eb-112">**更新プログラム:** UpdateItem_ 操作でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-112">**Update:** Supported by the UpdateItem_ operation.</span></span>  
  
-   <span data-ttu-id="ad4eb-113">**削除:** DeleteItem_ 操作でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-113">**Delete:** Supported by the DeleteItem_ operation.</span></span>  
  
-   <span data-ttu-id="ad4eb-114">**クエリ:** ReadList 操作でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-114">**Query:** Supported by the ReadList operation.</span></span>  
  
-   <span data-ttu-id="ad4eb-115">**関連付け:** Associate_ 操作でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-115">**Associate:** Supported by the Associate_ operation.</span></span>  
  
 <span data-ttu-id="ad4eb-116">使用して、Microsoft BizTalk Adapter 用 Oracle データベースの例として次のサービス コントラクトが生成されました。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-116">The following service contract was generated using for the Microsoft BizTalk Adapter for Oracle Database as an example.</span></span> <span data-ttu-id="ad4eb-117">アダプターが、EMP テーブルへのアクセスを提供するよう構成します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-117">The adapter is configured to provide access to the EMP table</span></span>  
  
```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface ISCOTT_EMP {  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadList(System.Nullable<int> Limit);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void CreateItem(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void UpdateItem_EMPNO(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void DeleteItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] Associate_DEPTNO(System.Nullable<decimal> DEPTNO);  
}  
```  
  
## <a name="create-a-new-web-site-to-host-the-oracle-database-in-iis"></a><span data-ttu-id="ad4eb-118">IIS での Oracle データベースをホストする新しい Web サイトの作成します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-118">Create a New Web Site to Host the Oracle Database in IIS</span></span>  
 <span data-ttu-id="ad4eb-119">次の手順では、Oracle データベースをホストする Microsoft BizTalk Adapter 新しい WCF web サービスを作成する WCF アダプター サービス開発ウィザードを使用する例を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-119">These steps provide an example using the WCF Adapter Service Development Wizard, to create a new WCF web service hosting the Microsoft BizTalk Adapter for Oracle Database.</span></span> <span data-ttu-id="ad4eb-120">サービス コントラクトは、Sharepoint とは直接互換性操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-120">The service contract will include operations directly compatible with Sharepoint.</span></span> <span data-ttu-id="ad4eb-121">したがって、外部データ ソースとして it を直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-121">So that it can be directly consumed as an external datasource.</span></span> <span data-ttu-id="ad4eb-122">Oracle データベースを使用してでの認証に、アダプターが構成されている、 **SCOTT**アカウント。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-122">The adapter is configured to authenticate with the Oracle database using the **SCOTT** account.</span></span> <span data-ttu-id="ad4eb-123">場合、 **SCOTT**アカウントがロックされている、SYSDBA として SQL Plus にログインして、アカウントのロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-123">If the **SCOTT** account is locked, you can unlock the account by logging into SQL Plus as SYSDBA.</span></span>  
  
```  
<Oracle Installation Bin Directory>\Sqlplus.exe SYS AS SYSDBA  
```  
  
 <span data-ttu-id="ad4eb-124">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-124">Then run the following command.</span></span>  
  
```  
SQL> ALTER USER scott ACCOUNT UNLOCK;  
```  
  
#### <a name="create-the-new-web-site-project"></a><span data-ttu-id="ad4eb-125">新しい Web サイト プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-125">Create the New Web Site Project</span></span>  
  
1.  <span data-ttu-id="ad4eb-126">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-126">Open Visual Studio.</span></span>   
  
2.  <span data-ttu-id="ad4eb-127">Visual Studio での**ファイル**メニューの **新規**をクリックし、**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-127">In Visual Studio, on the **File** menu, select **New** and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="ad4eb-128">**新しいプロジェクト** ダイアログ ボックスで、展開**他の言語** をクリック**Visual c#** です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-128">In the **New Project** dialog box, expand **Other Languages** and click **Visual C#**.</span></span> <span data-ttu-id="ad4eb-129">検索、 **WCF アダプター サービス**テンプレートの一覧表示し、をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-129">Find the **WCF Adapter Service** in the template list and click it to select it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ad4eb-130">**WCF アダプタ サービス**テンプレートが利用できない場合、[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]がインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-130">The **WCF Adapter Service** template is not available if the [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)] is not installed.</span></span> <span data-ttu-id="ad4eb-131">X64 システムでは、インストールの x86 と x64 の両方のバージョン、[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-131">On x64 systems, install both the x86 and x64 versions of the [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)].</span></span>  
  
4.  <span data-ttu-id="ad4eb-132">指定**ScottEMP** をクリックし、名前の**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-132">Specify **ScottEMP** for the name, and then click **OK**.</span></span> <span data-ttu-id="ad4eb-133">**WCF アダプター サービス開発ウィザード**を開始します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-133">The **WCF Adapter Service Development Wizard** starts.</span></span>  
  
5.  <span data-ttu-id="ad4eb-134">**概要** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-134">On the **Introduction** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="ad4eb-135">**選択操作** ページで指定、 **oracleDBBinding**バインドします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-135">On the **Choose Operations** page, specify the **oracleDBBinding** binding.</span></span>  
  
7.  <span data-ttu-id="ad4eb-136">クリックして、**構成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-136">Click the **Configure** button.</span></span> <span data-ttu-id="ad4eb-137">**アダプターの構成**ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-137">The **Configure Adapter** dialog is displayed.</span></span>  
  
8.  <span data-ttu-id="ad4eb-138">**セキュリティ** タブで、 **Username**で、**クライアント資格情報の種類**ボックスの一覧。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-138">On the **Security** tab, select **Username** in the **Client credential type** dropdown list box.</span></span>  
  
9. <span data-ttu-id="ad4eb-139">入力**SCOTT**ユーザーの名前を指定し、SCOTT アカウントの正しいパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-139">Enter **SCOTT** for the User name and enter the correct password for the SCOTT account.</span></span> <span data-ttu-id="ad4eb-140">SCOTT アカウントの既定のパスワードは**tiger**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-140">The default password for the SCOTT account is **tiger**.</span></span>  
  
10. <span data-ttu-id="ad4eb-141">クリックして、 **URI プロパティ** タブに Oracle サーバーの IP アドレスまたはホスト名を入力、 **ServerAddress**ボックス。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-141">Click the **URI Properties** tab, enter the IP address or host name for your Oracle server in the **ServerAddress** box.</span></span>  
  
11. <span data-ttu-id="ad4eb-142">正しい Oracle データベース サービスで、インスタンス名を入力、 **ServiceName**ボックス。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-142">Enter the correct Oracle database service instance name in the **ServiceName** box.</span></span> <span data-ttu-id="ad4eb-143">インスタンス名の詳細については、Oracle Enterprise Manager からコピーできます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-143">You can copy the instance name information from Oracle Enterprise Manager.</span></span>  
  
12. <span data-ttu-id="ad4eb-144">キーを押して、 **OK**のボタンでは、**アダプターの構成**ダイアログ</span><span class="sxs-lookup"><span data-stu-id="ad4eb-144">Press the **OK** button on the **Configure Adapter** dialog</span></span>  
  
13. <span data-ttu-id="ad4eb-145">**選択操作**ページ、ウィザードのをクリックして、**接続**ボタンをクリックし、しばらくの Oracle データベースを構築するカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-145">On the **Choose Operations** page of the wizard, click the **Connect** button and wait a few moments for the categories to be built for the Oracle database.</span></span>  
  
14. <span data-ttu-id="ad4eb-146">カテゴリを追加した後、**カテゴリを選択**一覧で、下方向にスクロール**SCOTT**それを展開します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-146">Once the categories are added in the **Select a category** list, scroll down to **SCOTT** and expand it.</span></span> <span data-ttu-id="ad4eb-147">展開し、**テーブル** をクリックし、 **EMP**テーブル エントリ。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-147">Then expand **Table** and click the **EMP** table entry.</span></span>  
  
15. <span data-ttu-id="ad4eb-148">**利用可能なカテゴリと操作**一覧をリスト内のすべての操作を選択し、をクリックして、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-148">In the **Available categories and operations** list, select all the operations in the list and click the **Add** button.</span></span> <span data-ttu-id="ad4eb-149">すべての操作に追加されます、**カテゴリと操作を追加** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-149">All the operations are added to the **Added categories and operations** list.</span></span>  
  
16. <span data-ttu-id="ad4eb-150">**選択操作** ページで、をクリックして、**次**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-150">On the **Choose Operations** page, click the **Next** button.</span></span>  
  
17. <span data-ttu-id="ad4eb-151">**サービスの構成およびエンドポイント動作** ページで、設定、 **UseServiceCertificate**サービスの動作を**false**この例です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-151">On the **Configure Service and Endpoint Behaviors** page, set the **UseServiceCertificate** Service behavior to **false** for this example.</span></span> <span data-ttu-id="ad4eb-152">をクリックして、**次**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-152">Then click the **Next** button.</span></span>  
  
18. <span data-ttu-id="ad4eb-153">**を構成するサービス エンドポイントのバインドとアドレス** ページで、をクリックして、**適用**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-153">On the **Configure Service Endpoint Binding and Address** page, click the **Apply** button.</span></span> <span data-ttu-id="ad4eb-154">をクリックして、**次**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-154">Then click the **Next** button.</span></span>  
  
19. <span data-ttu-id="ad4eb-155">**概要** ページで、をクリックして、**完了**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-155">On the **Summary** page, click the **Finish** button.</span></span>  
  
20. <span data-ttu-id="ad4eb-156">クリックして、**ビルド**メニュー オプションをクリック**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-156">Click the **Build** menu option and then click **Build Solution**.</span></span> <span data-ttu-id="ad4eb-157">プロジェクトのビルドがエラーなしで成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-157">Verify the project build was successful with no errors.</span></span>  
  
## <a name="publish-the-new-service-to-iis"></a><span data-ttu-id="ad4eb-158">新しいサービスを IIS に発行します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-158">Publish the New Service to IIS</span></span>  
 <span data-ttu-id="ad4eb-159">この例では、ローカル IIS web サーバーに、アダプターのホスト サービスを発行します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-159">For this example you will publish the adapter host service to the local IIS web server.</span></span>  
  
1.  <span data-ttu-id="ad4eb-160">Visual Studio のソリューション エクスプ ローラーで右クリックし、 **ScottEmp**プロジェクトし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-160">In Solution Explorer for Visual Studio, right click the **ScottEmp** project and click **Properties**.</span></span> <span data-ttu-id="ad4eb-161">プロジェクト デザイナーのタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-161">The Project Designer tabs are displayed.</span></span>  
  
2.  <span data-ttu-id="ad4eb-162">クリックして、 **Web**  タブのをクリックして、**を使用してローカル IIS Web サーバー**オプション。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-162">Click the **Web** tab, then click the **Use Local IIS Web server** option.</span></span>  
  
3.  <span data-ttu-id="ad4eb-163">クリックして、**仮想ディレクトリの作成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-163">Click the **Create Virtual Directory** button.</span></span>  
  
4.  <span data-ttu-id="ad4eb-164">ブラウザーを開き、web サービス アドレスに**http://localhost/ScottEmp/ISCOTT_EMP.svc**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-164">Open a web browser to the service address **http://localhost/ScottEmp/ISCOTT_EMP.svc**.</span></span> <span data-ttu-id="ad4eb-165">「サービスを作成しました」というメッセージを受信する必要があります、アダプタを示すが IIS でホストされています。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-165">You should receive a message stating “You have created a service” indicating the adapter is hosted in IIS.</span></span>  
  
## <a name="add-the-external-data-source-to-a-sharepoint-site-using-sharepoint-designer"></a><span data-ttu-id="ad4eb-166">SharePoint Designer を使用して SharePoint サイトに外部データ ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-166">Add the External Data Source to a SharePoint Site using SharePoint Designer</span></span>  
 <span data-ttu-id="ad4eb-167">このセクションでは、外部データ ソースとして SharePoint Designer を使用して新しい Web サイトに、WCF サービスを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-167">This section describes how to add the WCF Service as an external data source to a new Web Site using SharePoint Designer.</span></span>  
  
  
1.  <span data-ttu-id="ad4eb-168">SharePoint デザイナーを開き、新しい Web サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-168">Open SharePoint Designer and create a new Web Site.</span></span>  
  
2.  <span data-ttu-id="ad4eb-169">SharePoint Designer の展開**ナビゲーション** をクリック**外部コンテンツ タイプ**で、**サイト オブジェクト** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-169">In SharePoint Designer, expand **Navigation** and click **External Content types** in the **Site Objects** list.</span></span>  
  
3.  <span data-ttu-id="ad4eb-170">クリックして、**外部コンテンツ タイプ**新しい外部コンテンツ タイプを作成するメニュー ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-170">Click the **External Content Type** menu button to create a new external content type.</span></span>  
  
4.  <span data-ttu-id="ad4eb-171">横にあるテキストをクリックして**名前**新しい外部コンテンツ タイプの名前を編集します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-171">Click the text beside **Name** to edit the name of the new external content type.</span></span> <span data-ttu-id="ad4eb-172">入力**OracleEMP**名。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-172">Enter **OracleEMP** for the name.</span></span>  
  
5.  <span data-ttu-id="ad4eb-173">横にあるテキスト リンクをクリックして**外部システム**見なします**ここをクリックして、外部データ ソースと操作を検出する。** です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-173">Click the text link beside **External System** which says **Click here to discover external data sources and operations.**.</span></span> <span data-ttu-id="ad4eb-174">OracleEMP 外部コンテンツ タイプの操作のデザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-174">This opens the Operation Designer for the OracleEMP external content type.</span></span>  
  
6.  <span data-ttu-id="ad4eb-175">クリックして、**接続の追加**[探索] 画面でボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-175">Click the **Add Connection** button on the discovery screen.</span></span>  
  
7.  <span data-ttu-id="ad4eb-176">外部データ ソースの種類の選択 ダイアログ ボックスで選択**WCF サービス** をクリックし、 **ok**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-176">In the External Data Source Type Selection dialog, choose **WCF Service** and click the **OK** button.</span></span>  
  
8.  <span data-ttu-id="ad4eb-177">WCF の接続 ダイアログ ボックスでの**サービス メタデータの URL**ボックスに「 **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**</span><span class="sxs-lookup"><span data-stu-id="ad4eb-177">In the WCF Connection dialog, in the **Service Metadata URL** box enter **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**</span></span>  
  
9. <span data-ttu-id="ad4eb-178">**サービス エンドポイントの URL**ボックスに「 **https://localhost/ScottEmp/ISCOTT_EMP.svc**</span><span class="sxs-lookup"><span data-stu-id="ad4eb-178">In the **Service Endpoint URL** box enter **https://localhost/ScottEmp/ISCOTT_EMP.svc**</span></span>  
  
10. <span data-ttu-id="ad4eb-179">をクリックして、 **OK**の WCF 接続ダイアログを閉じるボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-179">Click the **OK** button to close the WCF Connection dialog.</span></span>  
  
11. <span data-ttu-id="ad4eb-180">データ ソースの情報を設定した後に展開し、 **https://localhost/ScottEmp/ISCOTT_EMP.svc**データ ソースし、展開**Web メソッド**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-180">Once the Data Source information is populated, expand the **https://localhost/ScottEmp/ISCOTT_EMP.svc** data source and expand **Web Methods**.</span></span>  
  
12. <span data-ttu-id="ad4eb-181">右クリックして、 **ReadList**をクリックして、Web メソッドを**新しい読み取りリスト操作**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-181">Right click the **ReadList** Web Method and click **New Read List Operation**.</span></span> <span data-ttu-id="ad4eb-182">リストの読み取りの [構成] ダイアログ ボックスを起動します。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-182">The Read List configuration dialog is launched.</span></span>  
  
13. <span data-ttu-id="ad4eb-183">リストの読み取り ダイアログ ボックスをクリックして**戻り値のパラメーター**  をクリック**EMPNO**データのソース要素にします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-183">In the Read List dialog click **Return Parameters** and click **EMPNO** in the Data Source Elements.</span></span> <span data-ttu-id="ad4eb-184">クリックして、**識別子にマップ**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-184">Click the **Map to identifier**.</span></span>  
  
14. <span data-ttu-id="ad4eb-185">をクリックして**完了**リストの読み取り ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-185">Click **Finish** in the Read List dialog.</span></span>  
  
15. <span data-ttu-id="ad4eb-186">」と入力して、新しい外部データ ソースを保存**Ctrl + s**です。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-186">Save the new external data source by typing **Ctrl+s**.</span></span>  
  
#### <a name="test-the-external-data-source-connection"></a><span data-ttu-id="ad4eb-187">外部データ ソース接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-187">Test the External Data Source Connection</span></span>  
  
1.  <span data-ttu-id="ad4eb-188">新しい web サイト をクリックして、**リストの作成とフォーム**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-188">In the new web site, click the **Create Lists and Forms** button.</span></span> <span data-ttu-id="ad4eb-189">リストの作成および OracleEMP ダイアログ フォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-189">The Create List and Form for OracleEMP dialog appears.</span></span>  
  
2.  <span data-ttu-id="ad4eb-190">入力**OracleEMP_List**のリストの名前とクリック、 **[ok]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-190">Enter **OracleEMP_List** for the List Name and click the **OK** button.</span></span>  
  
3.  <span data-ttu-id="ad4eb-191">一覧を作成すると、クリックして、**の概要 ビュー**ボタン、メニューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-191">Once the list is create, click the **Summary View** button on the menu.</span></span>  
  
4.  <span data-ttu-id="ad4eb-192">をクリックして**OracleEMP_List**外部リストの下。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-192">Click **OracleEMP_List** under External Lists.</span></span>  
  
5.  <span data-ttu-id="ad4eb-193">クリックして、**ブラウザーでプレビュー** アダプターの ReadList 操作をテストするメニュー ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-193">Click the **Preview in Browser** button on the menu to test the ReadList operation of the adapter.</span></span>  
  
## <a name="troubleshoot"></a><span data-ttu-id="ad4eb-194">[トラブルシューティング]</span><span class="sxs-lookup"><span data-stu-id="ad4eb-194">Troubleshoot</span></span>
  
-   <span data-ttu-id="ad4eb-195">64 ビット コンピューターでは 32 ビットの Oracle クライアント コンポーネントもインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-195">On 64-bit machines you must make sure that 32-bit Oracle client components are also installed.</span></span> <span data-ttu-id="ad4eb-196">Visual Studio とウィザードの開発時に 32 ビット コンポーネントへのアクセスを必要とする 32 ビット プロセスとして実行するためです。</span><span class="sxs-lookup"><span data-stu-id="ad4eb-196">This is because Visual Studio and it’s wizards will be running as a 32-bit process requiring access to 32-bit components during development.</span></span>
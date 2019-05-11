---
title: 'チュートリアル: データベースおよび .NET のファクトを使用して |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 676d6e46-d9f8-477e-979e-1ac051ad4451
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 453d7e657c2e2a416729a68700098be9b69a3a86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395956"
---
# <a name="walkthrough-using-database-and-net-facts"></a><span data-ttu-id="4acd8-102">チュートリアル: データベースおよび .NET のファクトの使用</span><span class="sxs-lookup"><span data-stu-id="4acd8-102">Walkthrough: Using Database and .NET Facts</span></span>
<span data-ttu-id="4acd8-103">ここでは、ビジネス ルール作成ツールを使用して、データベースおよび .NET のファクトを使用するポリシーを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-103">This walkthrough provides step-by-step procedures for using the Business Rule Composer to create a policy that uses database and .NET facts.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="4acd8-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="4acd8-104">Prerequisites</span></span>  
 <span data-ttu-id="4acd8-105">値を設定する必要があります、 **StaticSupport**を 1 または 2 のチュートリアルを実行する前にレジストリ キー。</span><span class="sxs-lookup"><span data-stu-id="4acd8-105">You must set the value of the **StaticSupport** registry key to 1 or 2 before performing the walkthrough.</span></span> <span data-ttu-id="4acd8-106">これによって、クライアントにクラスのインスタンスをアサートするように要求しなくても、ポリシーで .NET クラスの静的メソッドを呼び出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4acd8-106">This allows the policy to invoke the static methods of a .NET class without requiring the client to assert an instance of the class.</span></span> <span data-ttu-id="4acd8-107">詳細については、次を参照してください。[クラスの静的メンバーを呼び出す](../core/invoking-static-members-of-a-class.md)します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-107">For more information, see [Invoking Static Members of a Class](../core/invoking-static-members-of-a-class.md).</span></span>  

## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="4acd8-108">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="4acd8-108">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="4acd8-109">次の表に示すように、このチュートリアルには 5 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4acd8-109">This walkthrough contains five procedures, as described in the following table.</span></span>  

|<span data-ttu-id="4acd8-110">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="4acd8-110">Procedure title</span></span>|<span data-ttu-id="4acd8-111">手順の説明</span><span class="sxs-lookup"><span data-stu-id="4acd8-111">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="4acd8-112">TestDB データベースと PO テーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="4acd8-112">To create the TestDB database and the PO table</span></span>|<span data-ttu-id="4acd8-113">作成するための手順について説明します、 **TestDB**データベースおよび**PO**テーブル。</span><span class="sxs-lookup"><span data-stu-id="4acd8-113">Provides step-by-step instructions for creating the **TestDB** database and the **PO** table.</span></span>|  
|<span data-ttu-id="4acd8-114">POUtility コンポーネントを作成するには</span><span class="sxs-lookup"><span data-stu-id="4acd8-114">To create the POUtility component</span></span>|<span data-ttu-id="4acd8-115">作成するための手順について説明します、 **POUtility**コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="4acd8-115">Provides step-by-step instructions for creating the **POUtility** component.</span></span>|  
|<span data-ttu-id="4acd8-116">ProcessPurchaseOrderDbNet ビジネス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4acd8-116">To create the ProcessPurchaseOrderDbNet business policy</span></span>|<span data-ttu-id="4acd8-117">作成するための手順について説明します、 **ProcessPurchaseOrderDbNet**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="4acd8-117">Provides step-by-step instructions for creating the **ProcessPurchaseOrderDbNet** policy.</span></span>|  
|<span data-ttu-id="4acd8-118">ビジネス ルール作成ツールを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="4acd8-118">To test the ProcessPurchaseOrderDbNet policy by using the Business Rule Composer</span></span>|<span data-ttu-id="4acd8-119">ビジネス ルール作成ツールを使用してテストする手順について説明します、 **ProcessPurchaseOrderDbNet**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="4acd8-119">Provides step-by-step instructions for using the Business Rule Composer to test the **ProcessPurchaseOrderDbNet** policy.</span></span>|  
|<span data-ttu-id="4acd8-120">Policy.Execute メソッドを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="4acd8-120">To test the ProcessPurchaseOrderDbNet policy by using the Policy.Execute method</span></span>|<span data-ttu-id="4acd8-121">テストするための手順について説明します、 **ProcessPurchaseOrderDbNet**ポリシーを使用して、 **Policy.Execute**メソッド。</span><span class="sxs-lookup"><span data-stu-id="4acd8-121">Provides step-by-step instructions for testing the **ProcessPurchaseOrderDbNet** policy by using the **Policy.Execute** method.</span></span>|  

### <a name="to-create-the-testdb-database-and-the-po-table"></a><span data-ttu-id="4acd8-122">TestDB データベースと PO テーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="4acd8-122">To create the TestDB database and the PO table</span></span>  

1.  <span data-ttu-id="4acd8-123">**SQL Server Management Studio** を開きます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-123">Open **SQL Server Management Studio**.</span></span>  

2.  <span data-ttu-id="4acd8-124">サーバー名と認証を確認し、順にクリックします**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-124">Verify the server name and authentication, and then click **Connect**.</span></span>  

3.  <span data-ttu-id="4acd8-125">左側の [オブジェクト エクスプ ローラー] ウィンドウで、コンピューター名を右クリックし、**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-125">In the Object Explorer window on the left, right-click the computer name, and then click **New Query**.</span></span>  

4.  <span data-ttu-id="4acd8-126">次の SQL ステートメントをクエリ ウィンドウにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-126">Copy the following SQL statements to the query window:</span></span>  

    ```  
    CREATE DATABASE [TestDB]  
    GO  

    Use TestDB  
    CREATE TABLE [dbo].[PO]([PONumber] [nvarchar](50) NOT NULL,  
    [Quantity] [int] NOT NULL,  
    [Status] [nchar](10) NULL  
    CONSTRAINT [PK_PO] PRIMARY KEY CLUSTERED ([PONumber] ASC))   
    GO  

    INSERT INTO PO VALUES ('PO1', 400, NULL)  
    INSERT INTO PO VALUES ('PO2', 700, NULL)  
    GO  
    ```  

5.  <span data-ttu-id="4acd8-127">F5 キーを押して、SQL クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-127">Press F5 to execute the SQL query.</span></span>  

6.  <span data-ttu-id="4acd8-128">オブジェクト エクスプ ローラー ウィンドウで、コンピューター名を展開し、**データベース**、ことを確認および**TestDB**存在します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-128">In the Object Explorer window, expand the computer name, expand **Databases**, and then verify that **TestDB** exists.</span></span>  

7.  <span data-ttu-id="4acd8-129">展開**TestDB**、展開**テーブル**、ことを確認および**dbo します。PO**存在します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-129">Expand **TestDB**, expand **Tables**, and then verify that **dbo.PO** exists.</span></span>  

8.  <span data-ttu-id="4acd8-130">右クリックして**dbo します。PO**、 をクリックし、**テーブルを開く**次のデータがテーブルに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-130">Right-click **dbo.PO**, and then click **Open Table** to verify that the following data exists in the table.</span></span>  

    |<span data-ttu-id="4acd8-131">PONumber</span><span class="sxs-lookup"><span data-stu-id="4acd8-131">PONumber</span></span>|<span data-ttu-id="4acd8-132">Quantity</span><span class="sxs-lookup"><span data-stu-id="4acd8-132">Quantity</span></span>|<span data-ttu-id="4acd8-133">状態</span><span class="sxs-lookup"><span data-stu-id="4acd8-133">Status</span></span>|  
    |--------------|--------------|------------|  
    |<span data-ttu-id="4acd8-134">PO1</span><span class="sxs-lookup"><span data-stu-id="4acd8-134">PO1</span></span>|<span data-ttu-id="4acd8-135">400</span><span class="sxs-lookup"><span data-stu-id="4acd8-135">400</span></span>|<span data-ttu-id="4acd8-136">NULL</span><span class="sxs-lookup"><span data-stu-id="4acd8-136">NULL</span></span>|  
    |<span data-ttu-id="4acd8-137">PO2</span><span class="sxs-lookup"><span data-stu-id="4acd8-137">PO2</span></span>|<span data-ttu-id="4acd8-138">700</span><span class="sxs-lookup"><span data-stu-id="4acd8-138">700</span></span>|<span data-ttu-id="4acd8-139">NULL</span><span class="sxs-lookup"><span data-stu-id="4acd8-139">NULL</span></span>|  

### <a name="to-create-the-poutility-component"></a><span data-ttu-id="4acd8-140">POUtility コンポーネントを作成するには</span><span class="sxs-lookup"><span data-stu-id="4acd8-140">To create the POUtility component</span></span>  

1. <span data-ttu-id="4acd8-141">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-141">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="4acd8-142">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-142">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="4acd8-143">**新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4acd8-143">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="4acd8-144">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4acd8-144">Use this</span></span>              |                             <span data-ttu-id="4acd8-145">目的</span><span class="sxs-lookup"><span data-stu-id="4acd8-145">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="4acd8-146">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="4acd8-146">**Project types**</span></span>         |                        <span data-ttu-id="4acd8-147">クリックして**Visual c#** します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-147">Click **Visual C#**.</span></span>                         |
   |           <span data-ttu-id="4acd8-148">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="4acd8-148">**Templates**</span></span>           |                      <span data-ttu-id="4acd8-149">クリックして**クラス ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-149">Click **Class Library**.</span></span>                       |
   |             <span data-ttu-id="4acd8-150">**名前**</span><span class="sxs-lookup"><span data-stu-id="4acd8-150">**Name**</span></span>              |                       <span data-ttu-id="4acd8-151">型**POUtilityLib**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-151">Type **POUtilityLib**.</span></span>                        |
   |           <span data-ttu-id="4acd8-152">**場所**</span><span class="sxs-lookup"><span data-stu-id="4acd8-152">**Location**</span></span>            |          <span data-ttu-id="4acd8-153">指定**C:\BRE-Walkthroughs**場所として。</span><span class="sxs-lookup"><span data-stu-id="4acd8-153">Specify **C:\BRE-Walkthroughs** as the location.</span></span>           |
   |         <span data-ttu-id="4acd8-154">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="4acd8-154">**Solution Name**</span></span>         |                       <span data-ttu-id="4acd8-155">型**POUtilitySol**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-155">Type **POUtilitySol**.</span></span>                        |
   | <span data-ttu-id="4acd8-156">**ソリューションのディレクトリを作成します。**</span><span class="sxs-lookup"><span data-stu-id="4acd8-156">**Create directory for solution**</span></span> | <span data-ttu-id="4acd8-157">ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-157">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="4acd8-158">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-158">Click **OK**.</span></span> <span data-ttu-id="4acd8-159">**POUtilityLib**プロジェクトがソリューション エクスプ ローラーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-159">The **POUtilityLib** project should appear in Solution Explorer.</span></span> <span data-ttu-id="4acd8-160">ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="4acd8-160">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="4acd8-161">[プロパティ] ウィンドウで、ファイルの名前を変更する**Class1.cs**を**POUtility.cs**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-161">In the Properties window, change the name of the file, **Class1.cs**, to **POUtility.cs**.</span></span>  

6. <span data-ttu-id="4acd8-162">次のコードに示すように、パブリック コンストラクターをクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-162">Add a public constructor to the class as shown in the following code:</span></span>  

   ```  
   public POUtility()  
   {  
   }  
   ```  

7. <span data-ttu-id="4acd8-163">という名前の静的メソッドを追加**GetMaxAllowed**を**POUtility**クラスの次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-163">Add a static method named **GetMaxAllowed** to the **POUtility** class as shown in the following code:</span></span>  

   ```  
   public static int GetMaxAllowed()  
   {  
   return 500;  
   }   
   ```  

8. <span data-ttu-id="4acd8-164">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-164">Start **Visual Studio Command Prompt**.</span></span>  

9. <span data-ttu-id="4acd8-165">ディレクトリに移動します**C:\BRE-Walkthroughs\POUtilitySol**、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-165">Change the directory to **C:\BRE-Walkthroughs\POUtilitySol**, and then execute the following command:</span></span>  

     <span data-ttu-id="4acd8-166">**Sn -k POUtility.snk**</span><span class="sxs-lookup"><span data-stu-id="4acd8-166">**Sn -k POUtility.snk**</span></span>  

10. <span data-ttu-id="4acd8-167">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、**プロパティ**、し、ダブルクリック**AssemblyInfo.cs**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-167">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, expand **Properties**, and then double-click **AssemblyInfo.cs**.</span></span>  

11. <span data-ttu-id="4acd8-168">次のステートメントを追加、 **AssemblyInfo.cs**最後にファイル。</span><span class="sxs-lookup"><span data-stu-id="4acd8-168">Add the following statement to the **AssemblyInfo.cs** file at the end:</span></span>  

    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POUtilitySol\POUtility.snk")]  
    ```  

12. <span data-ttu-id="4acd8-169">ソリューション エクスプ ローラー ウィンドウで右クリック**POUtilityLib**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-169">In the Solution Explorer window, right-click **POUtilityLib**, and then click **Build**.</span></span>  

13. <span data-ttu-id="4acd8-170">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動します**C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**、しを GAC (グローバル POUtility コンポーネントを登録するには、次のコマンドを実行アセンブリ キャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="4acd8-170">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt, change the directory to **C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**, and then execute the following command to register the POUtility component with the GAC (global assembly cache).</span></span> <span data-ttu-id="4acd8-171">場合は、コマンド プロンプトを開き、次の手順 8 に開くことはありません。</span><span class="sxs-lookup"><span data-stu-id="4acd8-171">If you do not have the command prompt open, follow step 8 to open it.</span></span>  

     <span data-ttu-id="4acd8-172">**Gacutil-i POUtilityLib.dll**</span><span class="sxs-lookup"><span data-stu-id="4acd8-172">**Gacutil -i POUtilityLib.dll**</span></span>  

### <a name="to-create-the-processpurchaseorderdbnet-business-policy"></a><span data-ttu-id="4acd8-173">ProcessPurchaseOrderDbNet ビジネス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4acd8-173">To create the ProcessPurchaseOrderDbNet business policy</span></span>  

1.  <span data-ttu-id="4acd8-174">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-174">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="4acd8-175">ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-175">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="4acd8-176">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4acd8-176">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="4acd8-177">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-177">To do this, right-click the application, and then select **Run as administrator**.</span></span>  

2.  <span data-ttu-id="4acd8-178">[ファクト エクスプ ローラー] ウィンドウ**データベース**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-178">In the Facts Explorer window, click **Databases**.</span></span>  

3.  <span data-ttu-id="4acd8-179">右クリック**サーバー**、 をクリックし、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-179">Right-click **Servers**, and then click **Browse**.</span></span>  

4.  <span data-ttu-id="4acd8-180">サーバーとの認証情報を確認し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-180">Verify the server and authentication information, and then click **OK**.</span></span>  

5.  <span data-ttu-id="4acd8-181">展開**TestDB**、順に展開**PO**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-181">Expand **TestDB**, and then expand **PO**.</span></span>  

6.  <span data-ttu-id="4acd8-182">[ファクト エクスプ ローラー] ウィンドウ **.NET クラス**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-182">In the Facts Explorer window, click **.NET Classes**.</span></span>  

7.  <span data-ttu-id="4acd8-183">右クリックして**します。NETAssemblies**、 をクリックし、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-183">Right-click **.NETAssemblies**, and then click **Browse**.</span></span>  

8.  <span data-ttu-id="4acd8-184">選択**POUtility**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="4acd8-184">Select **POUtility**, and then click **OK**.</span></span>  

9. <span data-ttu-id="4acd8-185">展開**Class1**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-185">Expand **Class1**.</span></span>  

10. <span data-ttu-id="4acd8-186">ポリシー エクスプ ローラー ウィンドウで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-186">In the Policy Explorer window, right-click **Policies**, and then click **Add New Policy**.</span></span>  

11. <span data-ttu-id="4acd8-187">ポリシーの名前を変更**Policy1**に**ProcessPurchaseOrderDbNet**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-187">Change the name of the policy from **Policy1** to **ProcessPurchaseOrderDbNet** and then press ENTER.</span></span> <span data-ttu-id="4acd8-188">ポリシーの名前は [プロパティ] ウィンドウで変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-188">You can also change the name of the policy in the Properties window.</span></span>  

12. <span data-ttu-id="4acd8-189">右クリックして**バージョン 1.0**、 をクリックし、**新しいルールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-189">Right-click **Version 1.0**, and then click **AddNewRule**.</span></span>  

13. <span data-ttu-id="4acd8-190">ルールの名前を変更**Rule1**に**ApprovalRule**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-190">Change the name of the rule from **Rule1** to **ApprovalRule** and then press ENTER.</span></span> <span data-ttu-id="4acd8-191">ルールの名前は [プロパティ] ウィンドウで変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-191">You can also change the name of the rule in the Properties window.</span></span>  

14. <span data-ttu-id="4acd8-192">右側の場合にペイン (上部)、右クリック**条件**、 をクリックして**述語**、 をクリックし、 **以下**。</span><span class="sxs-lookup"><span data-stu-id="4acd8-192">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **LessThanEqual**.</span></span>  

15. <span data-ttu-id="4acd8-193">[ファクト エクスプ ローラー] ウィンドウ**データベース**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-193">In the Facts Explorer window, click **Databases**.</span></span>  

16. <span data-ttu-id="4acd8-194">ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**引数 1** IF ペインでします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-194">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  

17. <span data-ttu-id="4acd8-195">[ファクト エクスプ ローラー] ウィンドウ **.NET クラス**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-195">In the Facts Explorer window, click **.NET Classes**.</span></span>  

18. <span data-ttu-id="4acd8-196">ドラッグ**GetMaxAllowed**ノードを ファクト エクスプ ローラー ウィンドウから**引数 2** IF ペインでします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-196">Drag **GetMaxAllowed** node from the Facts Explorer window to **argument2** in the IF pane.</span></span>  

19. <span data-ttu-id="4acd8-197">[ファクト エクスプ ローラー] ウィンドウ**データベース**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-197">In the Facts Explorer window, click **Databases**.</span></span>  

20. <span data-ttu-id="4acd8-198">ドラッグ、**状態**ノードをファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの右下にある THEN ペインにします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-198">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom right of the Business Rule Composer.</span></span>  

21. <span data-ttu-id="4acd8-199">[THEN] ペインで、次のようにクリックします。 **\<値を入力します\>** し、入力**Approved**。</span><span class="sxs-lookup"><span data-stu-id="4acd8-199">In the THEN pane, click **\<Enter a value\>** and then type **Approved**.</span></span>  

22. <span data-ttu-id="4acd8-200">ファクト エクスプ ローラー ウィンドウで、右クリック**バージョン 1.0**で**ProcessPurchaseOrderDbNet**、 をクリックし、**新しいルールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-200">In the Facts Explorer window, right-click **Version 1.0** in **ProcessPurchaseOrderDbNet**, and then click **AddNewRule**.</span></span>  

23. <span data-ttu-id="4acd8-201">ルールの名前を変更**Rule1**に**DeniedRule**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-201">Change the name of the rule from **Rule1** to **DeniedRule** and then press ENTER.</span></span> <span data-ttu-id="4acd8-202">ルールの名前は [プロパティ] ウィンドウで変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-202">You can also change the name of the rule in the Properties window.</span></span>  

24. <span data-ttu-id="4acd8-203">右側の場合にペイン (上部)、右クリック**条件**、 をクリックして**述語**、 をクリックし、 **GreaterThan**。</span><span class="sxs-lookup"><span data-stu-id="4acd8-203">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **GreaterThan**.</span></span>  

25. <span data-ttu-id="4acd8-204">[ファクト エクスプ ローラー] ウィンドウ**データベース**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-204">In the Facts Explorer window, click **Databases**.</span></span>  

26. <span data-ttu-id="4acd8-205">ドラッグ、**数量**ノードを ファクト エクスプ ローラー ウィンドウから**引数 1** IF ペインでします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-205">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  

27. <span data-ttu-id="4acd8-206">[ファクト エクスプ ローラー] ウィンドウ **.NET クラス**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-206">In the Facts Explorer window, click **.NET Classes**.</span></span>  

28. <span data-ttu-id="4acd8-207">ドラッグ、 **GetMaxAllowed**ノードを ファクト エクスプ ローラー ウィンドウから**引数 2** IF ペインでします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-207">Drag the **GetMaxAllowed** node from the Facts Explorer window to **argument2** in the IF pane.</span></span>  

29. <span data-ttu-id="4acd8-208">[ファクト エクスプ ローラー] ウィンドウ**データベース**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-208">In the Facts Explorer window, click **Databases**.</span></span>  

30. <span data-ttu-id="4acd8-209">ドラッグ、**状態**ノードをファクト エクスプ ローラー ウィンドウからビジネス ルール作成ツールの右下にある THEN ペインにします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-209">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom right of the Business Rule Composer.</span></span>  

31. <span data-ttu-id="4acd8-210">THEN ペインで次のようにクリックします。 **\<値を入力します\>** し、入力**Denied**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-210">In the THEN pane, click **\<Enter a value\>** and then type **Denied**.</span></span>  

32. <span data-ttu-id="4acd8-211">ポリシー エクスプ ローラー ウィンドウで右クリック**バージョン 1.0 (未保存)**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-211">In the Policy Explorer window, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  

### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-business-rule-composer"></a><span data-ttu-id="4acd8-212">ビジネス ルール作成ツールを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="4acd8-212">To test the ProcessPurchaseOrderDbNet policy by using the Business Rule Composer</span></span>  

1.  <span data-ttu-id="4acd8-213">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-213">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="4acd8-214">ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-214">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  

2.  <span data-ttu-id="4acd8-215">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrderDbNet**、右クリック**バージョン 1.0**、 をクリックし、**ポリシーのテスト**.</span><span class="sxs-lookup"><span data-stu-id="4acd8-215">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrderDbNet**, right-click **Version 1.0**, and then click **Test Policy**.</span></span>  

3.  <span data-ttu-id="4acd8-216">クリックして**TestDB:PO (Data Connection)**、 をクリックし、**インスタンスの追加**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-216">Click **TestDB:PO (Data Connection)**, and then click **Add Instance**.</span></span>  

4.  <span data-ttu-id="4acd8-217">**SQL サーバーへの接続**ダイアログ ボックスで、サーバー名と認証情報を確認し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-217">In the **Connect to SQL Server** dialog box, verify the server name and authentication information, and then click **OK**.</span></span>  

5.  <span data-ttu-id="4acd8-218">**バインドの選択** ダイアログ ボックスで、展開**TestDB**、 をクリックして**PO**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-218">In the **Select Binding** dialog box, expand **TestDB**, click **PO**, and then click **OK**.</span></span>  

6.  <span data-ttu-id="4acd8-219">クリックして**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-219">Click **Test**.</span></span>  

7.  <span data-ttu-id="4acd8-220">[出力] ウィンドウであることを確認両方、 **ApprovalRule**と**DeniedRule**が発生します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-220">In the Output window, verify that both the **ApprovalRule** and the **DeniedRule** are fired.</span></span>  

8.  <span data-ttu-id="4acd8-221">SQL Server Management studio で右クリックして**dbo します。PO**、 をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-221">In SQL Server Management Studio, right-click **dbo.PO**, and then click **Open Table**.</span></span>  

9. <span data-ttu-id="4acd8-222">いることを確認の値、**状態**にフィールドが設定されている**Approved**最初のレコード。</span><span class="sxs-lookup"><span data-stu-id="4acd8-222">Verify that the value of the **Status** field is set to **Approved** for the first record.</span></span>  

10. <span data-ttu-id="4acd8-223">いることを確認の値、**状態**にフィールドが設定されている**が拒否されました**2 番目のレコード。</span><span class="sxs-lookup"><span data-stu-id="4acd8-223">Verify that the value of the **Status** field is set to **Denied** for the second record.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="4acd8-224">値が引き続き表示される場合、**状態**NULL としてフィールドをデータを含むリストを右クリックし、をクリックし、 **SQL 実行**ビューが更新されます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-224">If you still see the value of the **Status** field as NULL, right-click the list containing the data, and then click **Execute SQL**, which refreshes the view.</span></span>  

11. <span data-ttu-id="4acd8-225">SQL Server Management Studio は開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-225">Keep SQL Server Management Studio open.</span></span>  

### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-policyexecute-method"></a><span data-ttu-id="4acd8-226">Policy.Execute メソッドを使用して ProcessPurchaseOrderDbNet ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="4acd8-226">To test the ProcessPurchaseOrderDbNet policy by using the Policy.Execute method</span></span>  

1. <span data-ttu-id="4acd8-227">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-227">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="4acd8-228">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-228">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="4acd8-229">**新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4acd8-229">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="4acd8-230">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4acd8-230">Use this</span></span>              |                             <span data-ttu-id="4acd8-231">目的</span><span class="sxs-lookup"><span data-stu-id="4acd8-231">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="4acd8-232">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="4acd8-232">**Project types**</span></span>         |                        <span data-ttu-id="4acd8-233">クリックして**Visual c#** します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-233">Click **Visual C#**.</span></span>                         |
   |           <span data-ttu-id="4acd8-234">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="4acd8-234">**Templates**</span></span>           |                   <span data-ttu-id="4acd8-235">クリックして**コンソール アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-235">Click **Console Application**.</span></span>                    |
   |             <span data-ttu-id="4acd8-236">**名前**</span><span class="sxs-lookup"><span data-stu-id="4acd8-236">**Name**</span></span>              |                    <span data-ttu-id="4acd8-237">型**TestProcessPODbNet**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-237">Type **TestProcessPODbNet**.</span></span>                     |
   |           <span data-ttu-id="4acd8-238">**場所**</span><span class="sxs-lookup"><span data-stu-id="4acd8-238">**Location**</span></span>            |          <span data-ttu-id="4acd8-239">指定**C:\BRE-Walkthroughs**場所として。</span><span class="sxs-lookup"><span data-stu-id="4acd8-239">Specify **C:\BRE-Walkthroughs** as the location.</span></span>           |
   |         <span data-ttu-id="4acd8-240">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="4acd8-240">**Solution Name**</span></span>         |                   <span data-ttu-id="4acd8-241">型**TestProcessPODbNetSol**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-241">Type **TestProcessPODbNetSol**.</span></span>                   |
   | <span data-ttu-id="4acd8-242">**ソリューションのディレクトリを作成します。**</span><span class="sxs-lookup"><span data-stu-id="4acd8-242">**Create directory for solution**</span></span> | <span data-ttu-id="4acd8-243">ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-243">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="4acd8-244">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-244">Click **OK**.</span></span> <span data-ttu-id="4acd8-245">**TestProcessPODbNet**プロジェクトがソリューション エクスプ ローラーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-245">The **TestProcessPODbNet** project should appear in Solution Explorer.</span></span> <span data-ttu-id="4acd8-246">ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="4acd8-246">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="4acd8-247">ソリューション エクスプ ローラーで右クリックして**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-247">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  

6. <span data-ttu-id="4acd8-248">をクリックして**参照**を参照**\Program Files\Common files \microsoft BizTalk**、し、ダブルクリック **[microsoft.ruleengine.dll]** します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-248">Click **Browse**, browse to **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  

7. <span data-ttu-id="4acd8-249">先頭に次のコードを追加、 **Program.cs**既存の後にファイルを`using`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="4acd8-249">Add the following code to the top of the **Program.cs** file after the existing `using` statements:</span></span>  

   ```  
   //To use the SQLConnection class  
   using System.Data.SqlClient;  

   //To use the Policy and DataConnection classes  
   using Microsoft.RuleEngine;  
   ```  

8. <span data-ttu-id="4acd8-250">次のコードを追加、 **Main**関数を作成して開く、 **SQLConnection**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4acd8-250">Add the following code to the **Main** function to create and open a **SQLConnection** object:</span></span>  

   ```  
   SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
   cn.Open();  
   ```  

9. <span data-ttu-id="4acd8-251">次のコードを追加、 **Main**関数の末尾を作成する、 **DataConnection**オブジェクトに基づいて、 **SQLConnection**前の手順で作成したオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-251">Add the following code to the **Main** function at the end to create a **DataConnection** object based on the **SQLConnection** object you created in the previous step:</span></span>  

    ```  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    ```  

10. <span data-ttu-id="4acd8-252">次のコードを追加、 **Main**関数の末尾を作成する、**ポリシー**オブジェクトし、ポリシーの実行します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-252">Add the following code to the **Main** function at the end to create a **Policy** object and execute the policy:</span></span>  

    ```  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    ```  

11. <span data-ttu-id="4acd8-253">次のコードを追加、 **Main**関数の末尾にデータベースを更新します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-253">Add the following code to the **Main** function at the end to update the database:</span></span>  

    ```  
    dc.Update();  
    ```  

12. <span data-ttu-id="4acd8-254">次のコードを追加、 **Main**関数の末尾をデータベースへの接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-254">Add the following code to the **Main** function at the end to close the connection to the database:</span></span>  

    ```  
    cn.Close();  
    ```  

13. <span data-ttu-id="4acd8-255">生成された例外をキャッチする try/catch ブロックを追加、 **Main**メソッド。</span><span class="sxs-lookup"><span data-stu-id="4acd8-255">Add a try-catch block to catch any exception generated in the **Main** method.</span></span>  

14. <span data-ttu-id="4acd8-256">いることを確認の完全なコード、 **Main**関数は、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-256">Verify that the complete code for the **Main** function is as shown in the following code:</span></span>  

    ```  
    try  
    {  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    dc.Update();  
    cn.Close();  
    }  
    catch (Exception ex)  
    {  
    Console.WriteLine(ex.Message);  
    }  
    ```  

15. <span data-ttu-id="4acd8-257">**ビルド** メニューのをクリックして**ビルド TestProcessPODbNet**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-257">On the **Build** menu, click **Build TestProcessPODbNet**.</span></span>  

16. <span data-ttu-id="4acd8-258">ビジネス ルール作成ツールで、展開**ポリシー**、展開**ProcessPurchaseOrderDbNet**、右クリック**バージョン 1.0**、順にクリックします**発行**.</span><span class="sxs-lookup"><span data-stu-id="4acd8-258">In the Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrderDbNet**, right-click **Version 1.0**, and then click **Publish**.</span></span>  

17. <span data-ttu-id="4acd8-259">右クリック**バージョン 1.0 - 公開済み**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-259">Right-click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  

18. <span data-ttu-id="4acd8-260">SQL Server Management studio での値を設定、**状態**フィールドを**NULL**の両方の PO レコード。</span><span class="sxs-lookup"><span data-stu-id="4acd8-260">In SQL Server Management Studio, set the value of the **Status** field to **NULL** for both the PO records.</span></span>  

19. <span data-ttu-id="4acd8-261">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を実行するには、CTRL + F5 キーを押して、 **TestProcessPODbNet**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="4acd8-261">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], Press CTRL+F5 to execute the **TestProcessPODbNet** application.</span></span>  

20. <span data-ttu-id="4acd8-262">任意のキーを押してコマンド プロンプト ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4acd8-262">Press any key to close the command prompt window.</span></span>  

21. <span data-ttu-id="4acd8-263">SQL Server Management studio で、PO レコードのテーブルを右クリックし、 **SQL 実行**します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-263">In SQL Server Management Studio, right-click the table with PO records, and then click **Execute SQL**.</span></span>  

22. <span data-ttu-id="4acd8-264">いることを確認の値、**状態**にフィールドが設定されている**Approved**最初のレコード。</span><span class="sxs-lookup"><span data-stu-id="4acd8-264">Verify that the value of the **Status** field is set to **Approved** for the first record.</span></span>  

23. <span data-ttu-id="4acd8-265">いることを確認の値、**状態**にフィールドが設定されている**が拒否されました**2 番目のレコード。</span><span class="sxs-lookup"><span data-stu-id="4acd8-265">Verify that the value of the **Status** field is set to **Denied** for the second record.</span></span>  

## <a name="comments"></a><span data-ttu-id="4acd8-266">コメント</span><span class="sxs-lookup"><span data-stu-id="4acd8-266">Comments</span></span>  

-   <span data-ttu-id="4acd8-267">ポリシーで .NET クラスの非静的メソッドを使用する場合は、ポリシーをビジネス ルール作成ツールでテストするために .NET クラスのインスタンスをアサートするファクト作成コンポーネントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4acd8-267">If a policy uses the non-static methods of a .NET class, you need to use a fact creator component that asserts an instance of the .NET class to test the policy by using the Business Rule Composer.</span></span>  

-   <span data-ttu-id="4acd8-268">ビジネス ルール作成ツールがのインスタンスを作成することに注意してくださいに非常に重要ですが、 **DataConnection**オブジェクトし、するルール エンジンの作業メモリに自動的にアサートが。</span><span class="sxs-lookup"><span data-stu-id="4acd8-268">It is very important to remember that the Business Rule Composer creates an instance of the **DataConnection** object and asserts it into the working memory of the rule engine automatically for you.</span></span> <span data-ttu-id="4acd8-269">ただし、クライアント (BizTalk または BizTalk 以外) アプリケーションからポリシーを呼び出すと、 **DataConnection**のオブジェクトが自動的に作成されません。</span><span class="sxs-lookup"><span data-stu-id="4acd8-269">However, when you invoke the policy from a client (BizTalk or non-BizTalk) application, the **DataConnection** object is not created automatically for you.</span></span> <span data-ttu-id="4acd8-270">クライアントを作成する必要があります、 **DataConnection**オブジェクトし、パラメーターまたはファクトとしてポリシーを実行するルール エンジンに渡します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-270">The client should create a **DataConnection** object and pass it as a parameter or fact to the rule engine to execute the policy.</span></span>  

-   <span data-ttu-id="4acd8-271">使用することができます、 **DebugTrackingInterceptor**ポリシー実行の詳細を追跡するクラス。</span><span class="sxs-lookup"><span data-stu-id="4acd8-271">You can use the **DebugTrackingInterceptor** class to track the policy execution details.</span></span> <span data-ttu-id="4acd8-272">次のサンプル コードのインスタンスを作成する方法を示しています、 **DebugTrackingInterceptor**クラスし、ポリシーの実行時に使用します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-272">The following sample code shows how to create an instance of the **DebugTrackingInterceptor** class, and use it when executing the policy:</span></span>  

    ```  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    ```  

-   <span data-ttu-id="4acd8-273">使用することができます、 **SqlTransaction**からデータベースを更新するクラス、 **ProcessPODbNet**をトランザクションでのポリシー。</span><span class="sxs-lookup"><span data-stu-id="4acd8-273">You can use the **SqlTransaction** class to update the database from the **ProcessPODbNet** policy in a transactional manner.</span></span> <span data-ttu-id="4acd8-274">次のコードは、トランザクションを開始するには、トランザクションをパラメーターとして渡す方法を示しています、 **DataConnection**オブジェクト、およびデータベースの変更をコミットします。</span><span class="sxs-lookup"><span data-stu-id="4acd8-274">The following code shows how to begin a transaction, pass the transaction as a parameter to the **DataConnection** object, and commit the database changes.</span></span> <span data-ttu-id="4acd8-275">詳細については、次を参照してください。[トランザクション サポート](../core/transaction-support.md)します。</span><span class="sxs-lookup"><span data-stu-id="4acd8-275">For more information, see [Transaction Support](../core/transaction-support.md).</span></span>  

    ```  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    //Begin the transaction  
    SqlTransaction  tn = cn.BeginTransaction();  
    //Pass the transaction object to the DataConnection constructor  
    DataConnection dc = new DataConnection("TestDB", "PO", cn, tn);  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    dc.Update();  
    //Commit the database transaction  
    tn.Commit();  
    cn.Close();  
    ```  

## <a name="see-also"></a><span data-ttu-id="4acd8-276">参照</span><span class="sxs-lookup"><span data-stu-id="4acd8-276">See Also</span></span>  
 [<span data-ttu-id="4acd8-277">ファクトの選択</span><span class="sxs-lookup"><span data-stu-id="4acd8-277">Selecting Facts</span></span>](../core/selecting-facts.md)
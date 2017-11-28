---
title: "手順 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fde018d8-9d9a-42ea-8ee9-e3632450b9d7
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d27a186cffc86a79f0a40f73cc6a0c1791c3b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-the-request-message-for-insert-operation-on-purchaseorder-table"></a><span data-ttu-id="e75ae-102">手順 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-102">Step 1: Create the Request Message for Insert Operation on Purchase_Order Table</span></span>
<span data-ttu-id="e75ae-103">![4 のステップ 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="e75ae-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="e75ae-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="e75ae-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="e75ae-105">**目標:** c# クラス ライブラリ プロジェクトをソリューションでは、追加します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-105">**Objective:** In this step, you add a C# class library project to your solution.</span></span> <span data-ttu-id="e75ae-106">このライブラリに挿入操作のため、メモリ内の要求メッセージを作成する、 **Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="e75ae-106">This library creates an in-memory request message for the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="e75ae-107">以降のステップでは、オーケストレーションは、テーブルにレコードを挿入する SQL Server にこのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-107">In later steps, the orchestration sends this message to SQL Server to insert records in the table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e75ae-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="e75ae-108">Prerequisites</span></span>  
 <span data-ttu-id="e75ae-109">内の手順を完了する必要があります[レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行して](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-109">You must have completed the steps in [Lesson 3: Execute a Stored Procedure to Select New Employees Added](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md).</span></span>  
  
### <a name="to-create-a-request-message-for-insert-operation"></a><span data-ttu-id="e75ae-110">挿入操作の要求メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="e75ae-110">To create a request message for Insert operation</span></span>  
  
1.  <span data-ttu-id="e75ae-111">Visual c# クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-111">Add a Visual C# class library project to your solution.</span></span> <span data-ttu-id="e75ae-112">プロジェクトの名前を入力`UpdatePOMessageCreator`です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-112">For the name of the project, type `UpdatePOMessageCreator`.</span></span>  
  
2.  <span data-ttu-id="e75ae-113">名前を変更**Class1.cs**に**UpdatePOMessageCreator.cs**です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-113">Rename **Class1.cs** to **UpdatePOMessageCreator.cs**.</span></span>  
  
3.  <span data-ttu-id="e75ae-114">.Cs ファイルに次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e75ae-114">Copy the following code to the .cs file:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdatePOMessageCreator  
    {  
        public class UpdatePOMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreatePOMessage";  
                try  
                {  
                    ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                    Console.WriteLine("EXCEPTION: " + ex.ToString());  
                    throw ex;  
                }  
  
                //Create Message From XML  
                Message = new XmlDocument();  
  
                Message.PreserveWhitespace = true;  
  
                Message.Load(ResponseDoc);  
  
                return Message;  
            }  
        }  
    }  
  
    ```  
  
     <span data-ttu-id="e75ae-115">このコード スニペットの挿入操作の要求メッセージが必要ですが、 **Purchase_Order** C:\TestLocation\CreatePOMessage に存在するテーブル。</span><span class="sxs-lookup"><span data-stu-id="e75ae-115">This code snippet expects a request message for the Insert operation on the **Purchase_Order** table to be present at C:\TestLocation\CreatePOMessage.</span></span> <span data-ttu-id="e75ae-116">コードでは、要求メッセージを使用して、実行時に、同様の要求メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-116">The code uses the request message to create a similar request message at run time.</span></span>  
  
4.  <span data-ttu-id="e75ae-117">厳密な名前キー ファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-117">Add a strong-name key file to the project.</span></span> <span data-ttu-id="e75ae-118">厳密な名前キー ファイルを作成する方法の詳細については、次を参照してください。 [SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-118">For instructions on creating a strong-name key file, see [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span></span>  
  
    1.  <span data-ttu-id="e75ae-119">ソリューション エクスプ ローラーで右クリックし、 **UpdatePOMessageCreator**プロジェクトし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-119">In the Solution Explorer, right-click the **UpdatePOMessageCreator** project and click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="e75ae-120">**プロパティ**ウィンドウで、をクリックして**署名**です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-120">In the **Property** window, click **Signing**.</span></span>  
  
    3.  <span data-ttu-id="e75ae-121">**署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="e75ae-121">In the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
    4.  <span data-ttu-id="e75ae-122">**厳密な名前キー ファイルを選択して**一覧で、クリックして**\<参照 >**です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-122">From the **Choose a strong-name key file** list, click **\<Browse>**.</span></span>  
  
    5.  <span data-ttu-id="e75ae-123">厳密な名前のキー ファイルを作成したフォルダーに移動し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-123">Navigate to the folder where you created the strong-name key file, and then click **Open**.</span></span>  
  
    6.  <span data-ttu-id="e75ae-124">をクリックして**保存**上、**標準**メニュー バーです。</span><span class="sxs-lookup"><span data-stu-id="e75ae-124">Click **Save** on the **Standard** menu bar.</span></span> <span data-ttu-id="e75ae-125">閉じる、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e75ae-125">Close the **Property** window.</span></span>  
  
5.  <span data-ttu-id="e75ae-126">プロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="e75ae-126">Build the project.</span></span> <span data-ttu-id="e75ae-127">プロジェクトを右クリックし、をクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-127">Right-click the project and click **Build**.</span></span>  
  
6.  <span data-ttu-id="e75ae-128">このプロジェクトの参照をソリューション内の BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-128">Add a reference of this project to the BizTalk project in the solution.</span></span>  
  
    1.  <span data-ttu-id="e75ae-129">ソリューション エクスプ ローラーで、BizTalk プロジェクトを展開しを右クリックして**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-129">In the Solution Explorer, expand the BizTalk project, right-click **References**, and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="e75ae-130">**参照の追加**ダイアログ ボックスで、をクリックして、**プロジェクト**タブです。</span><span class="sxs-lookup"><span data-stu-id="e75ae-130">In the **Add Reference** dialog box, click the **Projects** tab.</span></span>  
  
    3.  <span data-ttu-id="e75ae-131">、プロジェクト名の一覧から選択**UpdatePOMessageCreator**、 をクリックして**追加**、をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="e75ae-131">From the list of project names, select **UpdatePOMessageCreator**, click **Add**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="e75ae-132">プロジェクトをビルドすると、プロジェクトの \bin\Debug フォルダーの下アセンブリ DLL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e75ae-132">Building the project creates the assembly DLL under \bin\Debug folder of the project.</span></span> <span data-ttu-id="e75ae-133">この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e75ae-133">You must add this DLL to the Global Assembly Cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="e75ae-134">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-134">Start a Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="e75ae-135">コマンド プロンプトからの \bin\Debug\ フォルダーに移動、 **UpdatePOMessageCreator**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="e75ae-135">From the command prompt, navigate to the \bin\Debug\ folder of the **UpdatePOMessageCreator** project.</span></span>  
  
    3.  <span data-ttu-id="e75ae-136">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-136">Run the following command on the command prompt:</span></span>  
  
        ```  
        gacutil /i UpdatePOMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="e75ae-137">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="e75ae-137">What did I just do?</span></span>  
 <span data-ttu-id="e75ae-138">このステップでは、実行時に要求メッセージを作成する UpdatePOMessageCreator クラス ライブラリ プロジェクトを追加しました。</span><span class="sxs-lookup"><span data-stu-id="e75ae-138">In this step, you added an UpdatePOMessageCreator class library project that creates request message at run-time.</span></span> <span data-ttu-id="e75ae-139">BizTalk プロジェクトでこのプロジェクトへの参照を追加しても、GAC にアセンブリ DLL を追加します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-139">You added the reference to this project in the BizTalk project and also added the assembly DLL to the GAC.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e75ae-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="e75ae-140">Next Steps</span></span>  
 <span data-ttu-id="e75ae-141">挿入操作の要求メッセージに UPDATE_EMPLOYEE ストアド プロシージャの応答メッセージをマップする**Purchaser_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="e75ae-141">You map the response message for the UPDATE_EMPLOYEE stored procedure to the request message for the Insert operation on **Purchaser_Order** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75ae-142">参照</span><span class="sxs-lookup"><span data-stu-id="e75ae-142">See Also</span></span>  
 <span data-ttu-id="e75ae-143">[手順 2: マップ操作の要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span><span class="sxs-lookup"><span data-stu-id="e75ae-143">[Step 2: Map the UPDATE_EMPLOYEE Response Message to Insert Operation Request Message](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md) </span></span>  
 [<span data-ttu-id="e75ae-144">レッスン 4: Purchase Order テーブルで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e75ae-144">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)
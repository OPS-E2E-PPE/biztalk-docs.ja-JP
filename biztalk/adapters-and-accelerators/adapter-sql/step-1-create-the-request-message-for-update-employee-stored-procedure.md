---
title: '手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dd975d9-4b38-46e0-a926-4b325b0d7b5e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e30225b79b14ffc237798ddde6f3fe40fb4aea9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965992"
---
# <a name="step-1-create-the-request-message-for-updateemployee-stored-procedure"></a><span data-ttu-id="d55c1-102">手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d55c1-102">Step 1: Create the Request Message for UPDATE_EMPLOYEE Stored Procedure</span></span>
<span data-ttu-id="d55c1-103">![2 の手順 1.](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="d55c1-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="d55c1-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="d55c1-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="d55c1-105">**目標:** c# クラス ライブラリ プロジェクトをソリューションでは、追加します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-105">**Objective:** In this step, you add a C# class library project to your solution.</span></span> <span data-ttu-id="d55c1-106">このライブラリのメモリ内の要求メッセージを作成する、 **UPDATE_EMPLOYEE**ストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="d55c1-106">This library creates an in-memory request message for the **UPDATE_EMPLOYEE** stored procedure.</span></span> <span data-ttu-id="d55c1-107">以降のステップでは、オーケストレーションは、ストアド プロシージャを実行する SQL Server にこのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-107">In later steps, the orchestration sends this message to SQL Server to execute the stored procedure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d55c1-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="d55c1-108">Prerequisites</span></span>  
 <span data-ttu-id="d55c1-109">内の手順を完了する必要があります[レッスン 2: 受信とフィルター通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-109">You must have completed the steps in [Lesson 2: Receive and Filter Notifications](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span></span>  
  
### <a name="to-create-a-request-message-for-updateemployee-stored-procedure"></a><span data-ttu-id="d55c1-110">UPDATE_EMPLOYEE の要求メッセージを作成するには、ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d55c1-110">To create a request message for UPDATE_EMPLOYEE stored procedure</span></span>  
  
1.  <span data-ttu-id="d55c1-111">Visual c# クラス ライブラリ プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-111">Add a Visual C# class library project to your solution.</span></span> <span data-ttu-id="d55c1-112">プロジェクトの名前を入力`UpdateEmployeeMessageCreator`です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-112">For the name of the project, type `UpdateEmployeeMessageCreator`.</span></span>  
  
2.  <span data-ttu-id="d55c1-113">名前を変更**Class1.cs**に**UpdateEmployeeMessageCreator.cs**です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-113">Rename **Class1.cs** to **UpdateEmployeeMessageCreator.cs**.</span></span>  
  
3.  <span data-ttu-id="d55c1-114">.Cs ファイルに次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d55c1-114">Copy the following code to the .cs file:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdateEmployeeMessageCreator  
    {  
        public class UpdateEmployeeMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreateEmployeeMessage";  
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
  
     <span data-ttu-id="d55c1-115">このコード スニペットの要求メッセージが必要ですが、 **UPDATE_EMPLOYEE**ストアド プロシージャを C:\TestLocation\CreateEmployeeMessage に存在します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-115">This code snippet expects a request message for the **UPDATE_EMPLOYEE** stored procedure to be present at C:\TestLocation\CreateEmployeeMessage.</span></span> <span data-ttu-id="d55c1-116">コードでは、要求メッセージを使用して、実行時に、同様の要求メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-116">The code uses the request message to create a similar request message at run time.</span></span>  
  
4.  <span data-ttu-id="d55c1-117">厳密な名前キー ファイルをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-117">Add a strong-name key file to the project.</span></span> <span data-ttu-id="d55c1-118">参照してください[SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-118">See [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md).</span></span>  
  
    1.  <span data-ttu-id="d55c1-119">ソリューション エクスプ ローラーで右クリックし、 **UpdateEmployeeMessageCreator**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-119">In the Solution Explorer, right-click the **UpdateEmployeeMessageCreator** project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="d55c1-120">**プロパティ**ウィンドウで、をクリックして**署名**です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-120">In the **Property** window, click **Signing**.</span></span>  
  
    3.  <span data-ttu-id="d55c1-121">**署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="d55c1-121">In the **Signing** tab, select the **Sign the assembly** check box.</span></span>  
  
    4.  <span data-ttu-id="d55c1-122">**厳密な名前キー ファイルを選択して**一覧で、クリックして**\<参照\>** です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-122">From the **Choose a strong-name key file** list, click **\<Browse\>**.</span></span>  
  
    5.  <span data-ttu-id="d55c1-123">厳密な名前のキー ファイルを作成したフォルダーに移動し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-123">Navigate to the folder where you created the strong-name key file, and then click **Open**.</span></span>  
  
    6.  <span data-ttu-id="d55c1-124">をクリックして**保存**標準メニュー バーでします。</span><span class="sxs-lookup"><span data-stu-id="d55c1-124">Click **Save** on the Standard menu bar.</span></span> <span data-ttu-id="d55c1-125">閉じる、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="d55c1-125">Close the **Property** window.</span></span>  
  
5.  <span data-ttu-id="d55c1-126">プロジェクトをビルドする。</span><span class="sxs-lookup"><span data-stu-id="d55c1-126">Build the project.</span></span> <span data-ttu-id="d55c1-127">プロジェクトを右クリックし、をクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-127">Right-click the project, and then click **Build**.</span></span>  
  
6.  <span data-ttu-id="d55c1-128">このプロジェクトの参照をソリューション内の BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-128">Add a reference of this project to the BizTalk project in the solution.</span></span>  
  
    1.  <span data-ttu-id="d55c1-129">ソリューション エクスプ ローラーで、BizTalk プロジェクトを展開しを右クリックして**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-129">In the Solution Explorer, expand the BizTalk project, right-click **References**, and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="d55c1-130">**参照の追加**ダイアログ ボックスで、をクリックして、**プロジェクト**タブです。</span><span class="sxs-lookup"><span data-stu-id="d55c1-130">In the **Add Reference** dialog box, click the **Projects** tab.</span></span>  
  
    3.  <span data-ttu-id="d55c1-131">、プロジェクト名の一覧から選択**UpdateEmployeeMessageCreator**、 をクリックして**追加**、をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-131">From the list of project names, select **UpdateEmployeeMessageCreator**, click **Add**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="d55c1-132">プロジェクトをビルドすると、プロジェクトの \bin\Debug フォルダーの下アセンブリ DLL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d55c1-132">Building the project creates the assembly DLL under \bin\Debug folder of the project.</span></span> <span data-ttu-id="d55c1-133">この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d55c1-133">You must add this DLL to the Global Assembly Cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="d55c1-134">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-134">Start a Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="d55c1-135">コマンド プロンプトからの \bin\Debug\ フォルダーに移動、 **UpdateEmployeeMessageCreator**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="d55c1-135">From the command prompt, navigate to the \bin\Debug\ folder of the **UpdateEmployeeMessageCreator** project.</span></span>  
  
    3.  <span data-ttu-id="d55c1-136">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-136">Run the following command on the command prompt:</span></span>  
  
        ```  
        gacutil /i UpdateEmployeeMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="d55c1-137">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="d55c1-137">What did I just do?</span></span>  
 <span data-ttu-id="d55c1-138">このステップでは、実行時に要求メッセージを作成する UpdateEmployeeMessageCreator クラス ライブラリ プロジェクトを追加しました。</span><span class="sxs-lookup"><span data-stu-id="d55c1-138">In this step, you added an UpdateEmployeeMessageCreator class library project that creates request message at run-time.</span></span> <span data-ttu-id="d55c1-139">BizTalk プロジェクトでこのプロジェクトへの参照を追加しても、GAC にアセンブリ DLL を追加します。</span><span class="sxs-lookup"><span data-stu-id="d55c1-139">You added the reference to this project in the BizTalk project and also added the assembly DLL to the GAC.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d55c1-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="d55c1-140">Next Steps</span></span>  
 <span data-ttu-id="d55c1-141">SQL Server に要求メッセージを送信し、」の説明に従って、応答を受信する[手順 2: SQL Server と応答の受信要求メッセージを送信](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)です。</span><span class="sxs-lookup"><span data-stu-id="d55c1-141">You send the request message to SQL Server and receive the response, as described in [Step 2: Send the Request Message to SQL Server and Receive Response](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55c1-142">参照</span><span class="sxs-lookup"><span data-stu-id="d55c1-142">See Also</span></span>  
 [<span data-ttu-id="d55c1-143">レッスン 3: ストアド プロシージャを実行して、追加された新しい従業員を選択する</span><span class="sxs-lookup"><span data-stu-id="d55c1-143">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)
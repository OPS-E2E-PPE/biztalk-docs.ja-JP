---
title: 'チュートリアル: ファクト作成コンポーネントの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041c8f73-c72e-43fd-8446-144cecdc95ef
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a1c91417cb58eb53e35c724513d4f955e4e6b6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290306"
---
# <a name="walkthrough-creating-a-fact-creator"></a><span data-ttu-id="f138b-102">チュートリアル: ファクト作成コンポーネントの作成</span><span class="sxs-lookup"><span data-stu-id="f138b-102">Walkthrough: Creating a Fact Creator</span></span>
<span data-ttu-id="f138b-103">このチュートリアルは、ファクト作成コンポーネントを作成する手順を示します**POFactCreator**、テストに使用できる、 **ProcessPurchaseOrder**以前で作成したポリシーチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="f138b-103">This walkthrough provides step-by-step procedures for creating a fact creator component, **POFactCreator**, which you can use to test the **ProcessPurchaseOrder** policy you created in earlier walkthroughs.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f138b-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="f138b-104">Prerequisites</span></span>  
 <span data-ttu-id="f138b-105">完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのこのチュートリアルを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="f138b-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="f138b-106">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="f138b-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="f138b-107">次の表に示すように、このチュートリアルには 2 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f138b-107">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="f138b-108">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="f138b-108">Procedure title</span></span>|<span data-ttu-id="f138b-109">手順の説明</span><span class="sxs-lookup"><span data-stu-id="f138b-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="f138b-110">POFactCreator コンポーネントを作成するには</span><span class="sxs-lookup"><span data-stu-id="f138b-110">To create the POFactCreator component</span></span>|<span data-ttu-id="f138b-111">ファクト作成コンポーネントを作成するための手順をわかりやすく説明**POFactCreator**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-111">Provides step-by-step instructions for creating a fact creator component, **POFactCreator**.</span></span>|  
|<span data-ttu-id="f138b-112">POFactCreator を使用して、ProcessPurchaseOrder ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="f138b-112">To test the ProcessPurchaseOrder policy using POFactCreator</span></span>|<span data-ttu-id="f138b-113">ビジネス ルール作成ツールを使用してテストするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーを使用して、 **POFactCreator**コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f138b-113">Provides step-by-step instructions for using the Business Rule Composer tool to test the **ProcessPurchaseOrder** policy by using the **POFactCreator** component.</span></span>|  
  
### <a name="to-create-the-pofactcreator-component"></a><span data-ttu-id="f138b-114">POFactCreator コンポーネントを作成するには</span><span class="sxs-lookup"><span data-stu-id="f138b-114">To create the POFactCreator component</span></span>  
  
1.  <span data-ttu-id="f138b-115">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-115">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="f138b-116">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-116">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="f138b-117">**新しいプロジェクト** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f138b-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f138b-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f138b-118">Use this</span></span>|<span data-ttu-id="f138b-119">目的</span><span class="sxs-lookup"><span data-stu-id="f138b-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f138b-120">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="f138b-120">**Project types**</span></span>|<span data-ttu-id="f138b-121">をクリックして**Visual c#** です。</span><span class="sxs-lookup"><span data-stu-id="f138b-121">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="f138b-122">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="f138b-122">**Templates**</span></span>|<span data-ttu-id="f138b-123">をクリックして**クラス ライブラリ**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-123">Click **Class Library**.</span></span>|  
    |<span data-ttu-id="f138b-124">**名前**</span><span class="sxs-lookup"><span data-stu-id="f138b-124">**Name**</span></span>|<span data-ttu-id="f138b-125">型**POFactCreatorLib**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-125">Type **POFactCreatorLib**.</span></span>|  
    |<span data-ttu-id="f138b-126">**場所**</span><span class="sxs-lookup"><span data-stu-id="f138b-126">**Location**</span></span>|<span data-ttu-id="f138b-127">指定**C:\BRE-Walkthroughs**場所として。</span><span class="sxs-lookup"><span data-stu-id="f138b-127">Specify **C:\BRE-Walkthroughs** as the location.</span></span>|  
    |<span data-ttu-id="f138b-128">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="f138b-128">**Solution Name**</span></span>|<span data-ttu-id="f138b-129">型**POFactCreatorSol**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-129">Type **POFactCreatorSol**.</span></span>|  
    |<span data-ttu-id="f138b-130">**ソリューションのディレクトリを作成します。**</span><span class="sxs-lookup"><span data-stu-id="f138b-130">**Create directory for solution**</span></span>|<span data-ttu-id="f138b-131">ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f138b-131">Select this check box to create a directory for the solution files.</span></span>|  
  
4.  <span data-ttu-id="f138b-132">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f138b-132">Click **OK**.</span></span> <span data-ttu-id="f138b-133">**POFactCreatorLib**プロジェクトがソリューション エクスプ ローラーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="f138b-133">The **POFactCreatorLib** project should appear in Solution Explorer.</span></span> <span data-ttu-id="f138b-134">ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="f138b-134">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="f138b-135">[プロパティ] ウィンドウで、ファイルの名前変更**Class1.cs**を**POFactCreator.cs**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-135">In the Properties window, change the name of the file, **Class1.cs**, to **POFactCreator.cs**.</span></span>  
  
6.  <span data-ttu-id="f138b-136">ソリューション エクスプ ローラー ウィンドウで右クリック**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-136">In the Solution Explorer window, right-click **References**, and then click **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="f138b-137">をクリックして**参照**に移動**C:\Program files \common files \microsoft BizTalk**、順にダブルクリック **[microsoft.ruleengine.dll]** です。</span><span class="sxs-lookup"><span data-stu-id="f138b-137">Click **Browse**, navigate to **C:\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  
  
8.  <span data-ttu-id="f138b-138">先頭に次の行を追加、 **POFactCreator.cs**後、既存のファイル`using`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="f138b-138">Add the following lines to the top of the **POFactCreator.cs** file after the existing `using` statements:</span></span>  
  
    ```  
    //To use the XmlDocument class  
    using System.Xml;  
    //To use the TypedXmlDocument and Policy classes  
    using Microsoft.RuleEngine;   
    ```  
  
9. <span data-ttu-id="f138b-139">変更、 **POFactCreator**から派生するクラス、 **IFactCreator**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f138b-139">Modify the **POFactCreator** class to derive from the **IFactCreator** interface:</span></span>  
  
    ```  
    public class POFactCreator : IFactCreator  
    {  
    }  
    ```  
  
10. <span data-ttu-id="f138b-140">右クリック**IFactCreator**、をポイント**インターフェイスの実装**、クリックして**インターフェイスの実装**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-140">Right-click **IFactCreator**, point to **Implement Interface**, and then click **Implement Interface**.</span></span>  
  
     <span data-ttu-id="f138b-141">![BRE &#45;チュートリアル &#45; ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")</span><span class="sxs-lookup"><span data-stu-id="f138b-141">![BRE&#45;Walkthrough&#45;ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")</span></span>  
  
11. <span data-ttu-id="f138b-142">Public コンス トラクターを追加、 **POFactCreator**クラスの次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f138b-142">Add a public constructor to the **POFactCreator** class as shown below:</span></span>  
  
    ```  
    public POFactCreator()  
    {  
    }  
    ```  
  
12. <span data-ttu-id="f138b-143">唯一のステートメントを削除、 **CreateFacts**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f138b-143">Remove the lone statement in the **CreateFacts** method.</span></span>  
  
13. <span data-ttu-id="f138b-144">次のコードを追加、 **CreateFacts**メソッドを作成、 **TypedXmlDocument**オブジェクトに基づいて、 **SamplePO.xml**ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="f138b-144">Add the following code to the **CreateFacts** method to create a **TypedXmlDocument** object based on the **SamplePO.xml** document:</span></span>  
  
    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  
  
14. <span data-ttu-id="f138b-145">ファクトの配列を作成する次のコードを追加、 **TypedXmlDocument**オブジェクトのみのファクトとして。</span><span class="sxs-lookup"><span data-stu-id="f138b-145">Add the following code to create an array of facts with the **TypedXmlDocument** object as the only fact:</span></span>  
  
    ```  
    object[] facts = new object[1];  
    facts[0] = txd;   
    ```  
  
15. <span data-ttu-id="f138b-146">ファクトの配列からの戻り値、 **CreateFacts**メソッド。</span><span class="sxs-lookup"><span data-stu-id="f138b-146">Return the facts array from the **CreateFacts** method:</span></span>  
  
    ```  
    return facts;  
    ```  
  
16. <span data-ttu-id="f138b-147">いることを確認で完全なコード、 **CreateFacts**メソッドは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f138b-147">Verify that the complete code in the **CreateFacts** method looks like the following:</span></span>  
  
    ```  
    public object[] CreateFacts(RuleSetInfo ruleSetInfo)  
    {  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
  
    object[] facts = new object[1];  
    facts[0] = txd;  
    return facts;  
    }  
    ```  
  
17. <span data-ttu-id="f138b-148">唯一のステートメントを削除、 **GetFactTypes**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f138b-148">Remove the lone statement in the **GetFactTypes** method.</span></span>  
  
18. <span data-ttu-id="f138b-149">次のコードを追加、 **GetFactTypes**の型を含む型の配列を返すメソッドを**TypedXmlDocument**クラス。</span><span class="sxs-lookup"><span data-stu-id="f138b-149">Add the following code to the **GetFactTypes** method to return an array of types containing the type of the **TypedXmlDocument** class:</span></span>  
  
    ```  
    Type[] t = new Type[1];  
    t[0] = typeof(TypedXmlDocument);  
    return t;  
    ```  
  
19. <span data-ttu-id="f138b-150">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-150">Start **Visual Studio Command Prompt**.</span></span>  
  
20. <span data-ttu-id="f138b-151">ディレクトリに移動**C:\BRE-Walkthroughs\POFactCreatorSol**、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f138b-151">Change the directory to **C:\BRE-Walkthroughs\POFactCreatorSol**, and then execute the following command:</span></span>  
  
     <span data-ttu-id="f138b-152">**Sn-k POFactCreator.snk**</span><span class="sxs-lookup"><span data-stu-id="f138b-152">**Sn -k POFactCreator.snk**</span></span>  
  
21. <span data-ttu-id="f138b-153">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、**プロパティ**、順にダブルクリック**AssemblyInfo.cs**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-153">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, expand **Properties**, and then double-click **AssemblyInfo.cs**.</span></span>  
  
22. <span data-ttu-id="f138b-154">次のステートメントを追加、 **AssemblyInfo.cs**最後のファイル。</span><span class="sxs-lookup"><span data-stu-id="f138b-154">Add the following statement to the **AssemblyInfo.cs** file at the end:</span></span>  
  
    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreator.snk")]  
    ```  
  
23. <span data-ttu-id="f138b-155">ソリューション エクスプ ローラー ウィンドウで右クリック**POFactCreatorLib**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-155">In the Solution Explorer window, right-click **POFactCreatorLib**, and then click **Build**.</span></span>  
  
24. <span data-ttu-id="f138b-156">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動**C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**、登録するには、次のコマンドを実行し、 **POFactCreator**コンポーネントを GAC (グローバル アセンブリ キャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="f138b-156">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt, change the directory to **C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**, and then execute the following command to register the **POFactCreator** component with the GAC (global assembly cache).</span></span> <span data-ttu-id="f138b-157">コマンド プロンプトが開いていない場合は、手順 19. に従って開きます。</span><span class="sxs-lookup"><span data-stu-id="f138b-157">If you do not have the command prompt open, follow step 19 to open it.</span></span>  
  
     <span data-ttu-id="f138b-158">**Gacutil-i POFactCreatorLib.dll**</span><span class="sxs-lookup"><span data-stu-id="f138b-158">**Gacutil -i POFactCreatorLib.dll**</span></span>  
  
### <a name="to-test-the-processpurchaseorder-policy-using-pofactcreator"></a><span data-ttu-id="f138b-159">POFactCreator を使用して、ProcessPurchaseOrder ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="f138b-159">To test the ProcessPurchaseOrder policy using POFactCreator</span></span>  
  
1.  <span data-ttu-id="f138b-160">**開始**メニューのをポイント**すべてのプログラム**、をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、クリックして**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rule Composer**.</span></span> <span data-ttu-id="f138b-161">ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="f138b-161">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f138b-162">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f138b-162">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="f138b-163">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-163">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="f138b-164">ポリシー エクスプ ローラー] ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**最新バージョンを右クリックし、[クリックして**テスト ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-164">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click the latest version, and then click **Test Policy**.</span></span>  
  
     <span data-ttu-id="f138b-165">![ビジネス ルール作成ツール &#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")</span><span class="sxs-lookup"><span data-stu-id="f138b-165">![Business Rule Composer&#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")</span></span>  
  
3.  <span data-ttu-id="f138b-166">ダイアログ ボックスの下部には、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-166">At the bottom of the dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="f138b-167">**.NET アセンブリ**ダイアログ ボックスで、 **POFactCreatorLib**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-167">In the **.NET Assemblies** dialog box, select **POFactCreatorLib**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="f138b-168">**バインドの選択**ダイアログ ボックスで、をクリックして**POFactCreator**で**POFactCreatorLib、10.0.0**、クリックして **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="f138b-168">In the **Select Binding** dialog box, click **POFactCreator** in **POFactCreatorLib, 10.0.0**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="f138b-169">をクリックして**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="f138b-169">Click **Test**.</span></span>  
  
7.  <span data-ttu-id="f138b-170">いることを確認、 **ApprovalRule**出力ウィンドウには、発生します。</span><span class="sxs-lookup"><span data-stu-id="f138b-170">Verify that the **ApprovalRule** is fired in the Output window.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="f138b-171">コメント</span><span class="sxs-lookup"><span data-stu-id="f138b-171">Comments</span></span>  
  
-   <span data-ttu-id="f138b-172">.NET クラスの非静的メソッドを使用するポリシーをビジネス ルール作成ツールでテストするには、ファクト作成コンポーネントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f138b-172">To test a policy that uses non-static methods of a .NET class by using the Business Rule Composer, you must create a fact creator component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f138b-173">参照</span><span class="sxs-lookup"><span data-stu-id="f138b-173">See Also</span></span>  
 [<span data-ttu-id="f138b-174">ファクト取得コンポーネントを作成する方法</span><span class="sxs-lookup"><span data-stu-id="f138b-174">How to Create a Fact Retriever</span></span>](../core/how-to-create-a-fact-retriever.md)
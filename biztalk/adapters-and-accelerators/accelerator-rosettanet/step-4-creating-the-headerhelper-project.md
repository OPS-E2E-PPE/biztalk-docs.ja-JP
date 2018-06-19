---
title: '手順 4: HeaderHelper プロジェクトの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, helper projects
- private process tutorial, creating helper projects
ms.assetid: 82413537-032a-4368-8d77-d024a7c83b0b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2525e0e87106e2eeb82fb05b52b3ec69d4be876d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965528"
---
# <a name="step-4-creating-the-headerhelper-project"></a><span data-ttu-id="e9a80-102">手順 4: HeaderHelper プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="e9a80-102">Step 4: Creating the HeaderHelper Project</span></span>
<span data-ttu-id="e9a80-103">ここでは、[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] クラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9a80-103">In this step, you create a [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] class library.</span></span> <span data-ttu-id="e9a80-104">プライベート プロセス オーケストレーションが受信メッセージを受信すると、HeaderHelper ライブラリは、ドキュメントの変換が必要かどうかを判断し、変換が必要な場合は変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9a80-104">When a private process orchestration receives an incoming message, the HeaderHelper library determines whether a document conversion is required and if it is required, performs that conversion.</span></span> <span data-ttu-id="e9a80-105">これにより、オーケストレーションは別のバージョンの RNIF (RosettaNet Implementation Framework) ドキュメントでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9a80-105">This lets your orchestration work with different versions of RosettaNet Implementation Framework (RNIF) documents.</span></span> <span data-ttu-id="e9a80-106">また、3A2 応答メッセージを送信する際には、HeaderHelper ライブラリはメッセージを送信する前に追加のドキュメント変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9a80-106">Additionally, when a 3A2 response message is sent, the HeaderHelper library performs an additional document conversion before transmitting the message.</span></span>  
  
### <a name="to-create-the-headerhelper-project"></a><span data-ttu-id="e9a80-107">HeaderHelper プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="e9a80-107">To create the HeaderHelper project</span></span>  
  
1.  <span data-ttu-id="e9a80-108">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、Contoso ソリューションを右クリックし、順にポイント**追加**、クリックして**新しいプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="e9a80-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the Contoso solution, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="e9a80-109">新しいプロジェクトの追加 ダイアログ ボックスで、プロジェクトの種類 ペインで、次のように選択します。 **Visual c#** です。</span><span class="sxs-lookup"><span data-stu-id="e9a80-109">In the Add New Project dialog box, in the Project Types pane, select **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="e9a80-110">[テンプレート] ペインで、選択、**クラス ライブラリ**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="e9a80-110">In the Templates pane, select the **Class Library** template.</span></span>  
  
4.  <span data-ttu-id="e9a80-111">**名**ボックスに、入力**HeaderHelper**、クリックして **[ok]** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9a80-111">In the **Name** box, type **HeaderHelper**, and then click **OK** to create the project.</span></span>  
  
5.  <span data-ttu-id="e9a80-112">ソリューション エクスプ ローラーで右クリックし、 **Class1.cs**ファイルで、 **HeaderHelper**プロジェクトで、をクリックして**の名前を変更**、型**HeaderHelper.cs**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e9a80-112">In Solution Explorer, right click the **Class1.cs** file in the **HeaderHelper** project, click **Rename**, type **HeaderHelper.cs**, and then press **Enter**.</span></span>  
  
### <a name="to-create-the-helper-class"></a><span data-ttu-id="e9a80-113">ヘルパー クラスを作成するには</span><span class="sxs-lookup"><span data-stu-id="e9a80-113">To create the Helper class</span></span>  
  
1.  <span data-ttu-id="e9a80-114">ソリューション エクスプ ローラーで、展開、 **HeaderHelper**プロジェクト、し、ダブルクリック、 **HeaderHelper.cs**ノード HeaderHelper ソース ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e9a80-114">In Solution Explorer, expand the **HeaderHelper** project, and then double-click the **HeaderHelper.cs** node to open the HeaderHelper source file.</span></span>  
  
2.  <span data-ttu-id="e9a80-115">ソース ファイルに次のコードを入力し、既存のすべてのコードを上書きします。</span><span class="sxs-lookup"><span data-stu-id="e9a80-115">Type the following code into the source file, overwriting all the existing code:</span></span>  
  
    ```  
    using System;  
    using System.Xml;  
  
    namespace ContosoPriceAndAvailability  
    {  
        public class Helper  
        {  
            static public XmlDocument NormalizeHeader( XmlDocument curPip )  
            {  
                string strInput = curPip.OuterXml;  
                try  
                {  
                    XmlDocument xDoc = new XmlDocument();  
  
                    strInput = strInput.Replace("<!DOCTYPE Pip3A2PriceAndAvailabilityQuery SYSTEM \"3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\"[]>",String.Empty);  
                    strInput = strInput.Replace("<Pip3A2PriceAndAvailabilityQuery>","<Pip3A2PriceAndAvailabilityQuery xmlns=\"http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\">");  
                    strInput = strInput.Replace("xml:",String.Empty);  
                    strInput = strInput.Replace("b:",String.Empty);  
                    strInput = strInput.Replace("lang:",String.Empty);  
                    strInput = strInput.Replace("ns1:",String.Empty);  
  
                    xDoc.LoadXml(strInput);  
  
                    return xDoc;  
                }  
                catch(Exception ex)  
                {  
                    System.Diagnostics.Debug.Write( ex.Message );  
                    throw ex;  
                }  
            }  
  
            static public string ReturnSCWithDocType( XmlDocument xmlDoc )  
            {  
                try  
                {  
                    string sResponse = xmlDoc.InnerXml;  
                    sResponse=sResponse.Replace("ns0:",String.Empty);  
                    xmlDoc.LoadXml(sResponse);  
                    xmlDoc.DocumentElement.RemoveAllAttributes();  
                    sResponse = xmlDoc.InnerXml;  
  
                    sResponse = sResponse.Insert(0,"<!DOCTYPE Pip3A2PriceAndAvailabilityResponse SYSTEM \"3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.dtd\">");  
                    sResponse = sResponse.Replace("ns0:",String.Empty);  
                    sResponse = sResponse.Replace("b:",String.Empty);  
                    sResponse = sResponse.Replace("lang:",String.Empty);  
                    sResponse = sResponse.Replace("ns1:",String.Empty);  
  
                    return sResponse;  
                }  
                catch(Exception ex)  
                {  
                    throw ex;  
                }  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="e9a80-116">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9a80-116">On the **File** menu, click **Save All**.</span></span>  
  
### <a name="to-create-a-strong-named-assembly-for-the-headerhelper-project"></a><span data-ttu-id="e9a80-117">HeaderHelper プロジェクトの厳密な名前のアセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="e9a80-117">To create a strong named assembly for the HeaderHelper project</span></span>  
  
1.  <span data-ttu-id="e9a80-118">ソリューション エクスプ ローラーで右クリックし、 **HeaderHelper**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e9a80-118">In Solution Explorer, right-click the **HeaderHelper** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e9a80-119">HeaderHelper のプロパティ ページ] ダイアログ ボックスで、[**署名**HeaderHelp プロパティ ペインの左ペインでします。</span><span class="sxs-lookup"><span data-stu-id="e9a80-119">In the HeaderHelper Property Pages dialog box, select **Signing** in the left pane of the HeaderHelp properties pane.</span></span>  
  
3.  <span data-ttu-id="e9a80-120">右側のウィンドウでをクリックして**アセンブリに署名**です。</span><span class="sxs-lookup"><span data-stu-id="e9a80-120">In the right pane, click **Sign the Assembly**.</span></span>  
  
4.  <span data-ttu-id="e9a80-121">をクリックして、**厳密な名前キー ファイルを選択して**テキスト ボックス、および選択**\<参照\>** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="e9a80-121">Click the **Choose a strong name key file** text box, and then select **\<Browse\>** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="e9a80-122">ファイルの選択 ダイアログ ボックスで、Contoso アセンブリの場所に移動し、ダブルクリック**FabConPriceAvail.snk**です。</span><span class="sxs-lookup"><span data-stu-id="e9a80-122">In the Select File dialog box, move to the location of your Contoso assembly, and double-click **FabConPriceAvail.snk**.</span></span>  
  
6.  <span data-ttu-id="e9a80-123">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9a80-123">On the **File** menu, click **Save All**.</span></span>  
  
7.  <span data-ttu-id="e9a80-124">ソリューション エクスプ ローラーで、展開、 **HeaderHelper**プロジェクトで、展開、**プロパティ**ノードを展開し、ダブルクリック、 **AssemblyInfo.cs**ノードを開くには、AssemblyInfo.csソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e9a80-124">In Solution Explorer, expand the **HeaderHelper** project, expand the **Properties** node, and then double-click the **AssemblyInfo.cs** node to open the AssemblyInfo.cs source file.</span></span>  
  
8.  <span data-ttu-id="e9a80-125">AssemblyInfo.cs ソース ファイルの AssemblyCulture 属性の後の行に、次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e9a80-125">In the AssemblyInfo.cs source file, type the following code on the line after the AssemblyCulture attribute:</span></span>  
  
    ```  
    [assembly: AssemblyKeyFile("../../../FabConPriceAvail.snk")]  
    ```  
  
9. <span data-ttu-id="e9a80-126">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9a80-126">On the **File** menu, click **Save All**.</span></span>  
  
### <a name="to-build-and-deploy-the-headerhelper-project"></a><span data-ttu-id="e9a80-127">HeaderHelper プロジェクトを構築および展開するには</span><span class="sxs-lookup"><span data-stu-id="e9a80-127">To build and deploy the HeaderHelper project</span></span>  
  
1.  <span data-ttu-id="e9a80-128">ソリューション エクスプ ローラーで右クリックし、 **HeaderHelper**プロジェクトをクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="e9a80-128">In Solution Explorer, right-click the **HeaderHelper** project, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="e9a80-129">開始**Visual Studio 2012 コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="e9a80-129">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
3.  <span data-ttu-id="e9a80-130">コマンド プロンプトでの場所に移動、 **HeaderHelper**プロジェクト出力ディレクトリ (\Bin\Debug フォルダ)。</span><span class="sxs-lookup"><span data-stu-id="e9a80-130">At the command prompt, move to the location of the **HeaderHelper** project output directory (the \Bin\Debug folder).</span></span>  
  
4.  <span data-ttu-id="e9a80-131">コマンド プロンプトで次のように入力します**gacutil/if HeaderHelper.dll**とキーを押します**Enter**をインストールする、 **HeaderHelper**にアセンブリを、**グローバル アセンブリ キャッシュ**。</span><span class="sxs-lookup"><span data-stu-id="e9a80-131">At the command prompt, type **gacutil /if HeaderHelper.dll** and press **Enter** to install the **HeaderHelper** assembly into the **Global Assembly Cache**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a80-132">参照</span><span class="sxs-lookup"><span data-stu-id="e9a80-132">See Also</span></span>  
 [<span data-ttu-id="e9a80-133">手順 5: Contoso プライベート プロセス オーケストレーションの変更</span><span class="sxs-lookup"><span data-stu-id="e9a80-133">Step 5: Modifying the Contoso Private Process Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)
---
title: "WCF LOB Adapter SDK と WSDL の生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f701d78d-b3ad-4f75-b814-e5b1f1319fb9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1075bbe59e15e3eeabde6c1d5c954460d1cb570
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="5b1cb-102">WCF LOB Adapter SDK と WSDL を生成します。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-102">Generate WSDL with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="5b1cb-103">アダプター、または LOB システムの変更から返されるメタデータは多くの場合、操作のメタデータが生成されることを確認するアダプターから返される Web サービス記述言語 (WSDL) を表示すると便利開発時に正しくです。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-103">During development of an adapter, or when the metadata that is returned from the LOB system changes, it is often useful to view the Web Services Description Language (WSDL) that is returned from the adapter to verify that the metadata for your operations is generated correctly.</span></span> <span data-ttu-id="5b1cb-104">WSDL を生成するいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-104">There are several methods to generate the WSDL.</span></span> <span data-ttu-id="5b1cb-105">このトピックでは、svcutil.exe とメタデータ検索参照コントロールの使用に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-105">This topic provides information about using svcutil.exe and the Metadata Search Browse control.</span></span>  

  
## <a name="use-svcutilexe"></a><span data-ttu-id="5b1cb-106">Svcutil.exe を使用してください。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-106">Use svcutil.exe</span></span>  
 <span data-ttu-id="5b1cb-107">Svcutil.exe は、URL と省略可能なスイッチを受け取り、WSDL を返す Windows SDK に付属してコマンド ライン ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-107">Svcutil.exe is a command-line utility shipped with the Windows SDK that accepts a URL and optional switches, and returns WSDL.</span></span> <span data-ttu-id="5b1cb-108">Svcutil.exe を使用してエコー アダプターの WSDL を取得する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-108">The following is an example of using svcutil.exe to return the WSDL of the Echo Adapter:</span></span>  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 <span data-ttu-id="5b1cb-109">これにより、メタデータが Microsoft.Adapters.Samples.Echov2.wsdl として保存します。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-109">This saves the metadata as Microsoft.Adapters.Samples.Echov2.wsdl.</span></span> <span data-ttu-id="5b1cb-110">場合は、アダプターは、多くの操作を使用して、目的の操作だけを返すことができます ' op OperationName =' URI の一部として。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-110">If your adapter has many operations, you can choose to return only the desired operations by using ‘op=OperationName’ as part of the URI.</span></span> <span data-ttu-id="5b1cb-111">これを使用して EchoStrings 情報のみを返す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-111">The following is an example of using this to return only the EchoStrings information:</span></span>  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a><span data-ttu-id="5b1cb-112">メタデータの検索の参照機能付きコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-112">Use the Metadata Search Browse Control</span></span>  
 <span data-ttu-id="5b1cb-113">メタデータ検索参照コントロールに含まれるウィザードで使用されている Windows コントロール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-113">The Metadata Search Browse control is a Windows control that is used in the wizards included in [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="5b1cb-114">Visual Studio で、任意の Windows フォーム プロジェクトにこのコントロールを追加し、アダプターでは、目的の操作を選択して、WSDL を生成できます。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-114">You can add this control to any Windows Forms project in Visual Studio, and use it to select your adapter, the desired operations, and then generate the WSDL.</span></span>  
  
1.  <span data-ttu-id="5b1cb-115">開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-115">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="5b1cb-116">**ファイル**メニューの **新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-116">On the **File** menu, select **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="5b1cb-117">**新しいプロジェクト**ダイアログ ボックスで、 **Windows アプリケーション**から**テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-117">In the **New Project** dialog box, select **Windows Application** from **Templates**.</span></span> <span data-ttu-id="5b1cb-118">プロジェクト名を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-118">Enter a project name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="5b1cb-119">開く、**ツールボックス**、展開**コモン コントロール**を右クリックし、**ツールボックス**、順にクリック**アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-119">Open the **Toolbox**, expand **Common Controls**, right-click the **Toolbox**, and then click **Choose Items**.</span></span>  
  
5.  <span data-ttu-id="5b1cb-120">**ツールボックス アイテムの選択**ダイアログ ボックスで、検索**MetadataUserControl**上、**の .NET Framework コンポーネント** タブで、この項目の横にあるチェック ボックスをオンにし、 をクリックして**Ok**です。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-120">In the **Choose Toolbox Items** dialog box, find **MetadataUserControl** on the **.NET Framework Components** tab, select the check box beside this item, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="5b1cb-121">[ツールボックス] から、MetadataUserControl を Form1 にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-121">From the Toolbox, drag the MetadataUserControl to Form1.</span></span> <span data-ttu-id="5b1cb-122">コントロール全体を表示するフォームのサイズを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-122">You may need to resize the form to see the entire control.</span></span> <span data-ttu-id="5b1cb-123">できます、プロジェクトを今すぐ実行し、コントロールが、機能していることを確認するアダプターと操作を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-123">You should be able to run the project now and verify that the control is functional, allowing you to select an adapter and operations.</span></span>  
  
7.  <span data-ttu-id="5b1cb-124">このコントロールを使用して WSDL を生成するを呼び出して、フォームにコードを追加する必要があります、 **GetWsdl**このコントロールのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-124">To generate WSDL by using this control, you must add code to your form to call the **GetWsdl** method of this control.</span></span> <span data-ttu-id="5b1cb-125">次の例を呼び出す方法**GetWsdl**ファイルにデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-125">The following example demonstrates how to call **GetWsdl** and save the data to file:</span></span>  
  
    ```csharp  
    private void button1_Click(object sender, EventArgs e)  
    {  
       ServiceDescription sd = mdUserControl.GetWsdl();  
       FileStream myFileStream = new FileStream(tbWsdlFileName.Text, FileMode.OpenOrCreate, FileAccess.Write);  
       StreamWriter myStreamWriter = new StreamWriter(myFileStream);  
       sd.Write(myStreamWriter);  
       myStreamWriter.Flush();  
       myStreamWriter.Close();  
       MessageBox.Show("WSDL file " + tbWsdlFileName.Text + " is created.");  
    }  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5b1cb-126">参照</span><span class="sxs-lookup"><span data-stu-id="5b1cb-126">See Also</span></span>  
 [<span data-ttu-id="5b1cb-127">WCF LOB Adapter SDK を使用して作成されたアダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="5b1cb-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)
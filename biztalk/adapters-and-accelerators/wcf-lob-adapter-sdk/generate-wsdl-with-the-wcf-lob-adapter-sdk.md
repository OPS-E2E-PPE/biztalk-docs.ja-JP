---
title: WCF LOB Adapter SDK と WSDL の生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f701d78d-b3ad-4f75-b814-e5b1f1319fb9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaf5ed992864c11d360baa30f35983f0082213b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971075"
---
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="a8311-102">WCF LOB Adapter SDK と WSDL を生成します。</span><span class="sxs-lookup"><span data-stu-id="a8311-102">Generate WSDL with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="a8311-103">アダプター、または LOB システムの変更から返されるメタデータは多くの場合、操作のメタデータが生成されることを確認するアダプターから返される Web サービス記述言語 (WSDL) を確認するために、開発中に正しくします。</span><span class="sxs-lookup"><span data-stu-id="a8311-103">During development of an adapter, or when the metadata that is returned from the LOB system changes, it is often useful to view the Web Services Description Language (WSDL) that is returned from the adapter to verify that the metadata for your operations is generated correctly.</span></span> <span data-ttu-id="a8311-104">WSDL を生成するいくつかの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="a8311-104">There are several methods to generate the WSDL.</span></span> <span data-ttu-id="a8311-105">このトピックでは、svcutil.exe とメタデータの検索参照コントロールの使用に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8311-105">This topic provides information about using svcutil.exe and the Metadata Search Browse control.</span></span>  

  
## <a name="use-svcutilexe"></a><span data-ttu-id="a8311-106">Svcutil.exe を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a8311-106">Use svcutil.exe</span></span>  
 <span data-ttu-id="a8311-107">Svcutil.exe は、URL と省略可能なスイッチを受け入れ、WSDL を返します Windows SDK に付属のコマンド ライン ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="a8311-107">Svcutil.exe is a command-line utility shipped with the Windows SDK that accepts a URL and optional switches, and returns WSDL.</span></span> <span data-ttu-id="a8311-108">Svcutil.exe を使用してエコー アダプターの WSDL を取得する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a8311-108">The following is an example of using svcutil.exe to return the WSDL of the Echo Adapter:</span></span>  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 <span data-ttu-id="a8311-109">これにより、メタデータが Microsoft.Adapters.Samples.Echov2.wsdl として保存します。</span><span class="sxs-lookup"><span data-stu-id="a8311-109">This saves the metadata as Microsoft.Adapters.Samples.Echov2.wsdl.</span></span> <span data-ttu-id="a8311-110">アダプターに多くの操作がある場合を使用して、目的の操作のみを返すことができます ' op OperationName =' の URI の一部として。</span><span class="sxs-lookup"><span data-stu-id="a8311-110">If your adapter has many operations, you can choose to return only the desired operations by using ‘op=OperationName’ as part of the URI.</span></span> <span data-ttu-id="a8311-111">EchoStrings 情報のみを返すこれを使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a8311-111">The following is an example of using this to return only the EchoStrings information:</span></span>  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a><span data-ttu-id="a8311-112">メタデータの検索の閲覧コントロールを使用して、</span><span class="sxs-lookup"><span data-stu-id="a8311-112">Use the Metadata Search Browse Control</span></span>  
 <span data-ttu-id="a8311-113">メタデータの検索参照コントロールに含まれているウィザードで使用されている Windows コントロール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a8311-113">The Metadata Search Browse control is a Windows control that is used in the wizards included in [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="a8311-114">Visual Studio で、任意の Windows フォーム プロジェクトにこのコントロールを追加し、アダプターでは、目的の操作を選択して WSDL を生成できます。</span><span class="sxs-lookup"><span data-stu-id="a8311-114">You can add this control to any Windows Forms project in Visual Studio, and use it to select your adapter, the desired operations, and then generate the WSDL.</span></span>  
  
1. <span data-ttu-id="a8311-115">開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプト。</span><span class="sxs-lookup"><span data-stu-id="a8311-115">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2. <span data-ttu-id="a8311-116">**ファイル**メニューの [**新規**、] をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="a8311-116">On the **File** menu, select **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="a8311-117">**新しいプロジェクト**ダイアログ ボックスで、 **Windows アプリケーション**から**テンプレート**します。</span><span class="sxs-lookup"><span data-stu-id="a8311-117">In the **New Project** dialog box, select **Windows Application** from **Templates**.</span></span> <span data-ttu-id="a8311-118">プロジェクト名を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a8311-118">Enter a project name, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="a8311-119">開く、**ツールボックス**、展開**コモン コントロール**を右クリックし、**ツールボックス**、順にクリックします**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="a8311-119">Open the **Toolbox**, expand **Common Controls**, right-click the **Toolbox**, and then click **Choose Items**.</span></span>  
  
5. <span data-ttu-id="a8311-120">**ツールボックス アイテムの選択**ダイアログ ボックスで、検索**MetadataUserControl**上、**の .NET Framework コンポーネント**タブに、この項目の横にあるチェック ボックスをオンにしてをクリックして **[Ok]** します。</span><span class="sxs-lookup"><span data-stu-id="a8311-120">In the **Choose Toolbox Items** dialog box, find **MetadataUserControl** on the **.NET Framework Components** tab, select the check box beside this item, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="a8311-121">ツールボックスから、MetadataUserControl を Form1 にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a8311-121">From the Toolbox, drag the MetadataUserControl to Form1.</span></span> <span data-ttu-id="a8311-122">コントロール全体を表示するフォームのサイズを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8311-122">You may need to resize the form to see the entire control.</span></span> <span data-ttu-id="a8311-123">はずプロジェクトを今すぐ実行して、コントロールが機能することを確認するアダプターと操作を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="a8311-123">You should be able to run the project now and verify that the control is functional, allowing you to select an adapter and operations.</span></span>  
  
7. <span data-ttu-id="a8311-124">このコントロールを使用して WSDL を生成するには、呼び出すように、フォームにコードを追加する必要があります、 **GetWsdl**このコントロールのメソッド。</span><span class="sxs-lookup"><span data-stu-id="a8311-124">To generate WSDL by using this control, you must add code to your form to call the **GetWsdl** method of this control.</span></span> <span data-ttu-id="a8311-125">次の例を呼び出す方法を示します**GetWsdl**ファイルにデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="a8311-125">The following example demonstrates how to call **GetWsdl** and save the data to file:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8311-126">参照</span><span class="sxs-lookup"><span data-stu-id="a8311-126">See Also</span></span>  
 [<span data-ttu-id="a8311-127">WCF LOB Adapter SDK を使用して作成されたアダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="a8311-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)
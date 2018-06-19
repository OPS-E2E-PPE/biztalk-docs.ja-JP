---
title: BAM インターセプタ動作を Machine.config ファイルに追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ea09925-264f-4976-8e34-f63bad70f886
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abc8845333389c95ea52d440437935d4c4867dc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248826"
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a><span data-ttu-id="b41f1-102">BAM インターセプタ動作を Machine.config ファイルに追加する方法</span><span class="sxs-lookup"><span data-stu-id="b41f1-102">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>
<span data-ttu-id="b41f1-103">BAM でデータを受信するには、BAM インターセプタ動作を Microsoft .NET machine.config ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b41f1-103">To intercept data in BAM, you must add the BAM interceptor behavior to the Microsoft .NET machine.config file.</span></span> <span data-ttu-id="b41f1-104">これは次の 2 つの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b41f1-104">You can do this in two ways:</span></span>  
  
-   <span data-ttu-id="b41f1-105">machine.config ファイルを手動で編集して動作を追加する。</span><span class="sxs-lookup"><span data-stu-id="b41f1-105">Manually edit the machine.config file to include the behavior.</span></span>  
  
-   <span data-ttu-id="b41f1-106">サービス構成エディタを使用して動作を追加する。</span><span class="sxs-lookup"><span data-stu-id="b41f1-106">Use the Service Configuration Editor to include the behavior.</span></span>  
  
### <a name="to-manually-edit-the-machineconfig-file"></a><span data-ttu-id="b41f1-107">machine.config ファイルを手動で編集するには</span><span class="sxs-lookup"><span data-stu-id="b41f1-107">To manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="b41f1-108">Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-108">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="b41f1-109">これを行うには、をクリックして**開始**、 をクリックして**実行**notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config」を入力して、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b41f1-109">To do this, click **Start**, click **Run**, type notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b41f1-110">次の動作拡張機能を追加して machine.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-110">Update the machine.config file with the following behavior extensions.</span></span>  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="b41f1-111">machine.config ファイルを閉じて保存します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-111">Close and save the machine.config file.</span></span>  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="b41f1-112">サービス構成エディタを使用して machine.config ファイルを編集するには</span><span class="sxs-lookup"><span data-stu-id="b41f1-112">To edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="b41f1-113">サービス構成エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="b41f1-113">Open the Service Configuration Editor.</span></span> <span data-ttu-id="b41f1-114">サービス構成エディターの使用方法の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557)です。</span><span class="sxs-lookup"><span data-stu-id="b41f1-114">For information about using the Service Configuration Editor, see [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557).</span></span>  
  
2.  <span data-ttu-id="b41f1-115">ツリー ビュー ウィンドウ (ラベルの付いた**構成**)、ノード ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-115">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="b41f1-116">をクリックして、 **[詳細設定]** フォルダー、をクリックして、**拡張機能**フォルダーをクリックし、**動作要素拡張**要素。</span><span class="sxs-lookup"><span data-stu-id="b41f1-116">Click the **Advanced** folder, click the **Extensions** folder, and then select the **behavior element extensions** element.</span></span>  
  
3.  <span data-ttu-id="b41f1-117">新しい動作要素の拡張機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-117">Create a new behavior element extension.</span></span> <span data-ttu-id="b41f1-118">クリックして、**新規**Extension 構成要素エディタ ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="b41f1-118">Click the **New** button to open the Extension Configuration Element Editor dialog box.</span></span> <span data-ttu-id="b41f1-119">**構成名**動作、BAMEndPointBehaviorExtension などの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-119">In **Configuration Name** enter a unique name for the behavior, for example BAMEndPointBehaviorExtension.</span></span>  
  
     <span data-ttu-id="b41f1-120">![Extension 構成要素エディタ](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span><span class="sxs-lookup"><span data-stu-id="b41f1-120">![Extension Configuration Element Editor](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span></span>  
  
4.  <span data-ttu-id="b41f1-121">クリックして、**型**フィールドに、省略記号ボタンをクリックして (**.**) 動作拡張型ブラウザ ダイアログ ボックスを開くボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b41f1-121">Click the **Type** field, and then click the ellipsis button (**...**) button to open the Behavior Extension Type Browser dialog box.</span></span>  
  
5.  <span data-ttu-id="b41f1-122">グローバル アセンブリ キャッシュ (GAC) アイコンをクリックして、GAC の DLL を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-122">Click the global assembly cache (GAC) icon to list the DLLs in GAC.</span></span>  
  
6.  <span data-ttu-id="b41f1-123">Microsoft.BizTalk.Bam.Interceptors アセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-123">Select the Microsoft.BizTalk.Bam.Interceptors assembly.</span></span>  
  
7.  <span data-ttu-id="b41f1-124">クリックして、**開く**アセンブリを選択するボタンをクリックし、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b41f1-124">Click the **Open** button to select the assembly, and then close the dialog box.</span></span>  
  
     <span data-ttu-id="b41f1-125">![動作拡張型ブラウザー](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span><span class="sxs-lookup"><span data-stu-id="b41f1-125">![Bejavopr Extension Type Browser](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span></span>  
  
8.  <span data-ttu-id="b41f1-126">動作拡張型ブラウザ ダイアログ ボックスの型名ペインで、Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior 型をダブルクリックします (次の画面の強調表示されている部分を参照)。</span><span class="sxs-lookup"><span data-stu-id="b41f1-126">In the Type Name pane of the Behavior Extension Type Browser dialog box, double-click the Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior type (as highlighted in the following screen).</span></span>  
  
     <span data-ttu-id="b41f1-127">![動作拡張型ブラウザー](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span><span class="sxs-lookup"><span data-stu-id="b41f1-127">![Bejavopr Extension Type Browser](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span></span>  
  
     <span data-ttu-id="b41f1-128">これにより、Extension 構成要素エディタが開きます。</span><span class="sxs-lookup"><span data-stu-id="b41f1-128">This opens the Extension Configuration Element Editor.</span></span>  
  
9. <span data-ttu-id="b41f1-129">をクリックして**OK** Extension 構成要素エディタ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b41f1-129">Click **OK** to close the Extension Configuration Element Editor dialog box.</span></span>  
  
10. <span data-ttu-id="b41f1-130">サービス構成エディタの詳細ペインで、BAMEndPointBehaviorExtension が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b41f1-130">In the details pane of the Service Configuration Editor, verify that the BAMEndPointBehaviorExtension appears.</span></span>  
  
11. <span data-ttu-id="b41f1-131">サービス構成エディタを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b41f1-131">Close the Service Configuration Editor.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b41f1-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="b41f1-132">Next Steps</span></span>  
 [<span data-ttu-id="b41f1-133">BAM WCF インターセプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b41f1-133">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a><span data-ttu-id="b41f1-134">参照</span><span class="sxs-lookup"><span data-stu-id="b41f1-134">See Also</span></span>  
 [<span data-ttu-id="b41f1-135">BAM データを受信する WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="b41f1-135">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)
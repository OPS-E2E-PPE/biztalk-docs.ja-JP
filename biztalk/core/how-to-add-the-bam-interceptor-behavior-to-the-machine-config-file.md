---
title: BAM インターセプタ動作を Machine.config ファイルに追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 20ef2ac191a50929be06fb5093d93382b63d2959
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387300"
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a><span data-ttu-id="0e46f-102">BAM インターセプタ動作を Machine.config ファイルに追加する方法</span><span class="sxs-lookup"><span data-stu-id="0e46f-102">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>
<span data-ttu-id="0e46f-103">Bam データをインターセプトするには、Microsoft .NET machine.config ファイルに、BAM インターセプタ動作を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e46f-103">To intercept data in BAM, you must add the BAM interceptor behavior to the Microsoft .NET machine.config file.</span></span> <span data-ttu-id="0e46f-104">これは、2 つの方法で行います。</span><span class="sxs-lookup"><span data-stu-id="0e46f-104">You can do this in two ways:</span></span>  
  
-   <span data-ttu-id="0e46f-105">動作を追加する、machine.config ファイルを手動で編集します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-105">Manually edit the machine.config file to include the behavior.</span></span>  
  
-   <span data-ttu-id="0e46f-106">動作を追加するのにには、サービス構成エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-106">Use the Service Configuration Editor to include the behavior.</span></span>  
  
### <a name="to-manually-edit-the-machineconfig-file"></a><span data-ttu-id="0e46f-107">Machine.config ファイルを手動で編集するには</span><span class="sxs-lookup"><span data-stu-id="0e46f-107">To manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="0e46f-108">Microsoft .NET の構成フォルダーにある machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-108">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="0e46f-109">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、メモ帳の c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config を入力し、クリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-109">To do this, click **Start**, click **Run**, type notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="0e46f-110">次の動作拡張機能では、machine.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-110">Update the machine.config file with the following behavior extensions.</span></span>  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="0e46f-111">Machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="0e46f-111">Close and save the machine.config file.</span></span>  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="0e46f-112">サービス構成エディターを使用して machine.config ファイルを編集するには</span><span class="sxs-lookup"><span data-stu-id="0e46f-112">To edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="0e46f-113">サービス構成エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e46f-113">Open the Service Configuration Editor.</span></span> <span data-ttu-id="0e46f-114">サービス構成エディターの使用方法の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557)します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-114">For information about using the Service Configuration Editor, see [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557).</span></span>  
  
2.  <span data-ttu-id="0e46f-115">ツリー ビュー ペインで (というラベルの付いた**構成**)、ノード ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-115">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="0e46f-116">をクリックして、 **詳細設定**フォルダー、 をクリックして、**拡張**フォルダー、および選択し、**動作要素拡張**要素。</span><span class="sxs-lookup"><span data-stu-id="0e46f-116">Click the **Advanced** folder, click the **Extensions** folder, and then select the **behavior element extensions** element.</span></span>  
  
3.  <span data-ttu-id="0e46f-117">新しい動作要素拡張を作成します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-117">Create a new behavior element extension.</span></span> <span data-ttu-id="0e46f-118">をクリックして、**新規**ボタン Extension 構成要素エディタ ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e46f-118">Click the **New** button to open the Extension Configuration Element Editor dialog box.</span></span> <span data-ttu-id="0e46f-119">**構成名**動作、BAMEndPointBehaviorExtension などの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-119">In **Configuration Name** enter a unique name for the behavior, for example BAMEndPointBehaviorExtension.</span></span>  
  
     <span data-ttu-id="0e46f-120">![Extension 構成要素エディタ](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span><span class="sxs-lookup"><span data-stu-id="0e46f-120">![Extension Configuration Element Editor](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span></span>  
  
4.  <span data-ttu-id="0e46f-121">をクリックして、**型**フィールドし、省略記号ボタンをクリックして (**.**)、動作拡張型ブラウザ ダイアログ ボックスを開くボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e46f-121">Click the **Type** field, and then click the ellipsis button (**...**) button to open the Behavior Extension Type Browser dialog box.</span></span>  
  
5.  <span data-ttu-id="0e46f-122">GAC の Dll を一覧表示する、グローバル アセンブリ キャッシュ (GAC) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e46f-122">Click the global assembly cache (GAC) icon to list the DLLs in GAC.</span></span>  
  
6.  <span data-ttu-id="0e46f-123">Microsoft.BizTalk.Bam.Interceptors アセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-123">Select the Microsoft.BizTalk.Bam.Interceptors assembly.</span></span>  
  
7.  <span data-ttu-id="0e46f-124">をクリックして、**オープン**アセンブリを選択するボタンをクリックし、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0e46f-124">Click the **Open** button to select the assembly, and then close the dialog box.</span></span>  
  
     <span data-ttu-id="0e46f-125">![動作拡張型ブラウザー](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span><span class="sxs-lookup"><span data-stu-id="0e46f-125">![Bejavopr Extension Type Browser](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span></span>  
  
8.  <span data-ttu-id="0e46f-126">動作拡張型ブラウザ ダイアログ ボックスの [型名] ウィンドウで、Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior 型 (として、次の画面で強調表示されている) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e46f-126">In the Type Name pane of the Behavior Extension Type Browser dialog box, double-click the Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior type (as highlighted in the following screen).</span></span>  
  
     <span data-ttu-id="0e46f-127">![動作拡張型ブラウザー](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span><span class="sxs-lookup"><span data-stu-id="0e46f-127">![Bejavopr Extension Type Browser](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span></span>  
  
     <span data-ttu-id="0e46f-128">拡張機能の構成要素エディタが開きます。</span><span class="sxs-lookup"><span data-stu-id="0e46f-128">This opens the Extension Configuration Element Editor.</span></span>  
  
9. <span data-ttu-id="0e46f-129">クリックして**OK** Extension 構成要素エディタ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0e46f-129">Click **OK** to close the Extension Configuration Element Editor dialog box.</span></span>  
  
10. <span data-ttu-id="0e46f-130">サービス構成エディターの詳細ウィンドウで、BAMEndPointBehaviorExtension が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e46f-130">In the details pane of the Service Configuration Editor, verify that the BAMEndPointBehaviorExtension appears.</span></span>  
  
11. <span data-ttu-id="0e46f-131">サービス構成エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0e46f-131">Close the Service Configuration Editor.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0e46f-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="0e46f-132">Next Steps</span></span>  
 [<span data-ttu-id="0e46f-133">BAM WCF インターセプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="0e46f-133">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e46f-134">参照</span><span class="sxs-lookup"><span data-stu-id="0e46f-134">See Also</span></span>  
 [<span data-ttu-id="0e46f-135">BAM データを受信するための WCF アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="0e46f-135">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)
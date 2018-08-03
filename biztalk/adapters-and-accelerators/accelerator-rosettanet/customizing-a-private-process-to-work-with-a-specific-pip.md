---
title: 特定の PIP に使用するプライベート プロセスのカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, PIPs
- private processes, customizing
- developing, private processes
- PIPs, private processes
- customizing private processes
ms.assetid: 88494e87-25a0-4c94-9396-61a0e07964aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77abdf870f0813bb5b9e1dd7a039b99ef0726c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001507"
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="6b132-102">特定の PIP に使用するプライベート プロセスのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6b132-102">Customizing a Private Process to Work with a Specific PIP</span></span>
<span data-ttu-id="6b132-103">応答側のプライベートプロセス オーケストレーションが特定の Partner Interface Process (PIP) のインスタンスを処理するかどうかを指定するフィルター式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6b132-103">You can create a filter expression that will cause a responder private-process orchestration to process or not process instances of a specific Partner Interface Process (PIP).</span></span> <span data-ttu-id="6b132-104">これにより、特定の PIP インスタンスを受信して処理するためのカスタム プライベート プロセスを作成し、その他の PIP インスタンスには既定のプライベート プロセスを使用する柔軟性が備わります。</span><span class="sxs-lookup"><span data-stu-id="6b132-104">This gives you the flexibility of creating a custom private process to receive and process some PIP instances, and using the default private process to process all other PIP instances.</span></span>  
  
 <span data-ttu-id="6b132-105">特定の PIP で使用するカスタム プライベート プロセスを作成するには、プライベートプロセス オーケストレーションの受信図形のフィルタ式を作成します。</span><span class="sxs-lookup"><span data-stu-id="6b132-105">To create a custom private process to work with a specific PIP or multiple specific PIPs, you create a filter expression for the receive shape of the private-process orchestration.</span></span> <span data-ttu-id="6b132-106">例としては、Microsoft® で PIP3A4PrivateResponder.odx オーケストレーション[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK。</span><span class="sxs-lookup"><span data-stu-id="6b132-106">An example is the PIP3A4PrivateResponder.odx orchestration in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="6b132-107">場所は\<*ドライブ*\>: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pip3a4process を使用して Business rules \pip3a4privateresponder にあります。</span><span class="sxs-lookup"><span data-stu-id="6b132-107">It is located at \<*drive*\>:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PIP3A4Process Using Business Rules\PIP3A4PrivateResponder.</span></span>  
  
 <span data-ttu-id="6b132-108">特定の PIP のインスタンスのみを処理するプライベート プロセスを作成するだけでなく、既定の BTARN プライベート プロセスをカスタマイズして、その PIP のインスタンスを処理しないように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b132-108">Besides creating a private process that process only instances of a specific PIP, you must customize the default BTARN private process so that it will not process instances for that PIP.</span></span>  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="6b132-109">特定の PIP で使用する応答側プライベート プロセスをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="6b132-109">To customize a responder private process to work with a specific PIP</span></span>  
  
1. <span data-ttu-id="6b132-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で、特定の PIP で使用する応答側プライベートプロセス オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b132-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], create a custom responder private-process orchestration for working with a specific PIP.</span></span> <span data-ttu-id="6b132-111">既定の BTARN 応答側プライベートプロセスのオーケストレーションを基盤にできます。</span><span class="sxs-lookup"><span data-stu-id="6b132-111">You can base the orchestration on the default BTARN responder private-process orchestration.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6b132-112">PrivateResponder.odx という名前の既定の応答側プライベートプロセス オーケストレーションは BTARN SDK にあります。</span><span class="sxs-lookup"><span data-stu-id="6b132-112">You can find the default responder private-process orchestration, named PrivateResponder.odx, in the BTARN SDK.</span></span> <span data-ttu-id="6b132-113">場所は*\<ドライブ\>*: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\privateresponder です。</span><span class="sxs-lookup"><span data-stu-id="6b132-113">It is located at *\<drive\>*:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
2. <span data-ttu-id="6b132-114">カスタム オーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="6b132-114">Add the custom orchestration to your BizTalk project.</span></span> <span data-ttu-id="6b132-115">プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの参照があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6b132-115">Make sure that your project has a reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
3. <span data-ttu-id="6b132-116">オーケストレーション デザイナでカスタム オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="6b132-116">Open the custom orchestration in Orchestration Designer.</span></span>  
  
4. <span data-ttu-id="6b132-117">1 つ目を右クリックして**受信**図形をオーケストレーションをアクティブ化し、をクリックし、**フィルター式の編集**します。</span><span class="sxs-lookup"><span data-stu-id="6b132-117">Right-click the first **Receive** shape that activates the orchestration, and then click **Edit Filter Expression**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6b132-118">既定の BTARN 応答側プライベートプロセス オーケストレーションの受信図形には、Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" または Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction" という 2 つのフィルター条件があります。</span><span class="sxs-lookup"><span data-stu-id="6b132-118">The receive shape for the default BTARN responder private-process orchestration has two filter conditions: Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" or Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction".</span></span> <span data-ttu-id="6b132-119">この式は、オーケストレーションが RosettaNet メッセージを処理することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b132-119">This expression makes sure that the orchestration processes RosettaNet messages.</span></span> <span data-ttu-id="6b132-120">カスタム オーケストレーションにこのフィルター式を維持してください。</span><span class="sxs-lookup"><span data-stu-id="6b132-120">Retain this filter expression in your custom orchestration.</span></span>  
  
5. <span data-ttu-id="6b132-121">**フィルター式**ダイアログ ボックスで、最初の開いている行のプロパティの列で選択**microsoft.solutions.btarn.globalschemas.scpipcode** 演算子 列で、ドロップダウン リストから選択**==** 値 列に入力 3 桁の PIP コードの例では、型のボックスの一覧から**3A4**します。</span><span class="sxs-lookup"><span data-stu-id="6b132-121">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list, in the Operator column, select **==** from the drop-down list, in the Value column, type the three-digit PIP code, for example, type **3A4**.</span></span>  
  
6. <span data-ttu-id="6b132-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b132-122">Click **OK**.</span></span>  
  
7. <span data-ttu-id="6b132-123">オーケストレーション デザイナーで既定の応答側プライベートプロセス オーケストレーション プロジェクト (PrivateResponder.btproj) を開きます。</span><span class="sxs-lookup"><span data-stu-id="6b132-123">Open the default responder private-process orchestration project (PrivateResponder.btproj) in Orchestration Designer.</span></span> <span data-ttu-id="6b132-124">プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの実際の参照があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6b132-124">Make sure that the project has a working reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
8. <span data-ttu-id="6b132-125">ダブルクリック**PrivateResponder.odx**します。</span><span class="sxs-lookup"><span data-stu-id="6b132-125">Double-click **PrivateResponder.odx**.</span></span>  
  
9. <span data-ttu-id="6b132-126">右クリックし、 **[receivefrompublicprocessresponder]** 受信図形をクリックして**フィルター式の編集**します。</span><span class="sxs-lookup"><span data-stu-id="6b132-126">Right-click the **ReceiveFromPublicProcessResponder** receive shape, and then click **Edit Filter Expression**.</span></span>  
  
10. <span data-ttu-id="6b132-127">**フィルター式**ダイアログ ボックスで、最初の開いている行のプロパティの列で選択 **[microsoft.solutions.btarn.globalschemas.scpipcode]** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="6b132-127">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span> <span data-ttu-id="6b132-128">[演算子] 列で選択 **! =** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="6b132-128">In the Operator column, select **!=** from the drop-down list.</span></span> <span data-ttu-id="6b132-129">[値] 列で、入力 3 桁の PIP コードの例では、型の"**3A4"** します。</span><span class="sxs-lookup"><span data-stu-id="6b132-129">In the Value column, type the three-digit PIP code, for example, type "**3A4"**.</span></span>  
  
11. <span data-ttu-id="6b132-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b132-130">Click **OK**.</span></span>  
  
12. <span data-ttu-id="6b132-131">ソリューション エクスプ ローラーでオーケストレーションを含むプロジェクトを右クリックし、クリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="6b132-131">In Solution Explorer, right-click the project that contains the orchestration and then click **Build**.</span></span>  
  
13. <span data-ttu-id="6b132-132">プロジェクトがビルドされたら、プロジェクトを右クリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="6b132-132">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
14. <span data-ttu-id="6b132-133">**ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。</span><span class="sxs-lookup"><span data-stu-id="6b132-133">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="6b132-134">移動\<*ドライブ*\>: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\privateresponder には、選択**PrivateResponder.odx**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="6b132-134">Move to \<*drive*\>:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder, select **PrivateResponder.odx**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="6b132-135">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b132-135">In Solution Explorer, right-click the project, and then click **Build**.</span></span>  
  
17. <span data-ttu-id="6b132-136">プロジェクトがビルドされたら、プロジェクトを右クリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="6b132-136">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b132-137">参照</span><span class="sxs-lookup"><span data-stu-id="6b132-137">See Also</span></span>  
 [<span data-ttu-id="6b132-138">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6b132-138">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)
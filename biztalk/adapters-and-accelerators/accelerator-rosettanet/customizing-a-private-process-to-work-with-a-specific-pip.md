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
ms.openlocfilehash: c2a9bac75fd3cb71210fdfff99978d973f28c142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284072"
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="93f31-102">特定の PIP に使用するプライベート プロセスのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="93f31-102">Customizing a Private Process to Work with a Specific PIP</span></span>
<span data-ttu-id="93f31-103">処理するプライベート プロセス オーケストレーションまたはプロセスのインスタンスの特定のプロセス PIP (Partner Interface) いない応答側が発生するフィルター式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="93f31-103">You can create a filter expression that will cause a responder private-process orchestration to process or not process instances of a specific Partner Interface Process (PIP).</span></span> <span data-ttu-id="93f31-104">これは、受信および特定の PIP インスタンスを処理するカスタム プライベート プロセスを作成して、プロセスを使用して既定のプライベート プロセスにその他のすべての PIP インスタンスの柔軟性をによりします。</span><span class="sxs-lookup"><span data-stu-id="93f31-104">This gives you the flexibility of creating a custom private process to receive and process some PIP instances, and using the default private process to process all other PIP instances.</span></span>  
  
 <span data-ttu-id="93f31-105">PIP または複数の特定の Pip の特定の作業のカスタム プライベート プロセスを作成するには、プライベート プロセス オーケストレーションの受信図形のフィルター式を作成します。</span><span class="sxs-lookup"><span data-stu-id="93f31-105">To create a custom private process to work with a specific PIP or multiple specific PIPs, you create a filter expression for the receive shape of the private-process orchestration.</span></span> <span data-ttu-id="93f31-106">例としては、Microsoft® で PIP3A4PrivateResponder.odx オーケストレーション[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK。</span><span class="sxs-lookup"><span data-stu-id="93f31-106">An example is the PIP3A4PrivateResponder.odx orchestration in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="93f31-107">場所は\<*ドライブ*\>: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pip3a4process を使用して Business rules \pip3a4privateresponder にあります。</span><span class="sxs-lookup"><span data-stu-id="93f31-107">It is located at \<*drive*\>:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PIP3A4Process Using Business Rules\PIP3A4PrivateResponder.</span></span>  
  
 <span data-ttu-id="93f31-108">だけでなく、特定の PIP のインスタンスのみを処理するプライベート プロセスを作成するには、その PIP のインスタンスを処理しないように、既定の BTARN プライベート プロセスをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93f31-108">Besides creating a private process that process only instances of a specific PIP, you must customize the default BTARN private process so that it will not process instances for that PIP.</span></span>  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="93f31-109">特定の PIP を使用する応答側プライベート プロセスをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="93f31-109">To customize a responder private process to work with a specific PIP</span></span>  
  
1. <span data-ttu-id="93f31-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の PIP を操作するためのカスタム応答側プライベート プロセス オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="93f31-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], create a custom responder private-process orchestration for working with a specific PIP.</span></span> <span data-ttu-id="93f31-111">既定の BTARN 応答側プライベート プロセス オーケストレーションのオーケストレーションを基にすることができます。</span><span class="sxs-lookup"><span data-stu-id="93f31-111">You can base the orchestration on the default BTARN responder private-process orchestration.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="93f31-112">既定値を検索する応答側プライベート プロセス オーケストレーション、BTARN SDK PrivateResponder.odx という名前です。</span><span class="sxs-lookup"><span data-stu-id="93f31-112">You can find the default responder private-process orchestration, named PrivateResponder.odx, in the BTARN SDK.</span></span> <span data-ttu-id="93f31-113">場所は*\<ドライブ\>*: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\privateresponder です。</span><span class="sxs-lookup"><span data-stu-id="93f31-113">It is located at *\<drive\>*:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
2. <span data-ttu-id="93f31-114">カスタム オーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="93f31-114">Add the custom orchestration to your BizTalk project.</span></span> <span data-ttu-id="93f31-115">プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの参照があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="93f31-115">Make sure that your project has a reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
3. <span data-ttu-id="93f31-116">オーケストレーション デザイナーでカスタム オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="93f31-116">Open the custom orchestration in Orchestration Designer.</span></span>  
  
4. <span data-ttu-id="93f31-117">1 つ目を右クリックして**受信**図形をオーケストレーションをアクティブ化し、をクリックし、**フィルター式の編集**します。</span><span class="sxs-lookup"><span data-stu-id="93f31-117">Right-click the first **Receive** shape that activates the orchestration, and then click **Edit Filter Expression**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="93f31-118">既定の BTARN 応答側プライベート プロセス オーケストレーションの受信図形には、2 つのフィルター条件があります。Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory = ="AsyncAction"または Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory ="SyncAction"です。</span><span class="sxs-lookup"><span data-stu-id="93f31-118">The receive shape for the default BTARN responder private-process orchestration has two filter conditions: Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" or Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction".</span></span> <span data-ttu-id="93f31-119">この式は、オーケストレーションが RosettaNet メッセージを処理することを確認します。</span><span class="sxs-lookup"><span data-stu-id="93f31-119">This expression makes sure that the orchestration processes RosettaNet messages.</span></span> <span data-ttu-id="93f31-120">カスタム オーケストレーションには、このフィルター式を保持します。</span><span class="sxs-lookup"><span data-stu-id="93f31-120">Retain this filter expression in your custom orchestration.</span></span>  
  
5. <span data-ttu-id="93f31-121">**フィルター式**ダイアログ ボックスで、最初の開いている行のプロパティの列で選択**microsoft.solutions.btarn.globalschemas.scpipcode** 演算子 列で、ドロップダウン リストから選択**==** 値 列に入力 3 桁の PIP コードの例では、型のボックスの一覧から**3A4**します。</span><span class="sxs-lookup"><span data-stu-id="93f31-121">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list, in the Operator column, select **==** from the drop-down list, in the Value column, type the three-digit PIP code, for example, type **3A4**.</span></span>  
  
6. <span data-ttu-id="93f31-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93f31-122">Click **OK**.</span></span>  
  
7. <span data-ttu-id="93f31-123">オーケストレーション デザイナーでは、既定の応答側プライベート プロセス オーケストレーション プロジェクト (PrivateResponder.btproj) を開きます。</span><span class="sxs-lookup"><span data-stu-id="93f31-123">Open the default responder private-process orchestration project (PrivateResponder.btproj) in Orchestration Designer.</span></span> <span data-ttu-id="93f31-124">プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの参照が含まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="93f31-124">Make sure that the project has a working reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
8. <span data-ttu-id="93f31-125">ダブルクリック**PrivateResponder.odx**します。</span><span class="sxs-lookup"><span data-stu-id="93f31-125">Double-click **PrivateResponder.odx**.</span></span>  
  
9. <span data-ttu-id="93f31-126">右クリックし、 **[receivefrompublicprocessresponder]** 受信図形をクリックして**フィルター式の編集**します。</span><span class="sxs-lookup"><span data-stu-id="93f31-126">Right-click the **ReceiveFromPublicProcessResponder** receive shape, and then click **Edit Filter Expression**.</span></span>  
  
10. <span data-ttu-id="93f31-127">**フィルター式**ダイアログ ボックスで、最初の開いている行のプロパティの列で選択 **[microsoft.solutions.btarn.globalschemas.scpipcode]** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="93f31-127">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span> <span data-ttu-id="93f31-128">[演算子] 列で選択 **! =** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="93f31-128">In the Operator column, select **!=** from the drop-down list.</span></span> <span data-ttu-id="93f31-129">[値] 列で、入力 3 桁の PIP コードの例では、型の"**3A4"** します。</span><span class="sxs-lookup"><span data-stu-id="93f31-129">In the Value column, type the three-digit PIP code, for example, type "**3A4"**.</span></span>  
  
11. <span data-ttu-id="93f31-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93f31-130">Click **OK**.</span></span>  
  
12. <span data-ttu-id="93f31-131">ソリューション エクスプ ローラーでオーケストレーションを含むプロジェクトを右クリックし、クリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="93f31-131">In Solution Explorer, right-click the project that contains the orchestration and then click **Build**.</span></span>  
  
13. <span data-ttu-id="93f31-132">プロジェクトがビルドされたら、プロジェクトを右クリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="93f31-132">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
14. <span data-ttu-id="93f31-133">**ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。</span><span class="sxs-lookup"><span data-stu-id="93f31-133">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="93f31-134">移動\<*ドライブ*\>: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\privateresponder には、選択**PrivateResponder.odx**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="93f31-134">Move to \<*drive*\>:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder, select **PrivateResponder.odx**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="93f31-135">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93f31-135">In Solution Explorer, right-click the project, and then click **Build**.</span></span>  
  
17. <span data-ttu-id="93f31-136">プロジェクトがビルドされたら、プロジェクトを右クリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="93f31-136">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f31-137">参照</span><span class="sxs-lookup"><span data-stu-id="93f31-137">See Also</span></span>  
 [<span data-ttu-id="93f31-138">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="93f31-138">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)
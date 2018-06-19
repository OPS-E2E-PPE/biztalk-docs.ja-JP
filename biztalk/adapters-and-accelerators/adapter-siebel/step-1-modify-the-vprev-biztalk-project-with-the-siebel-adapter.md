---
title: '手順 1: 変更の Siebel アダプターと BizTalk プロジェクト vPrev |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd95e2-bd51-420f-8156-6f17cc0e91d6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5465a80fd7b75dcbf7ec864b196d2fd5033cb003
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224066"
---
# <a name="step-1-modify-the-vprev-biztalk-project-with-the-siebel-adapter"></a><span data-ttu-id="5af1b-102">手順 1: Siebel アダプターと vPrev BizTalk プロジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-102">Step 1: Modify the vPrev BizTalk Project with the Siebel adapter</span></span>
<span data-ttu-id="5af1b-103">![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="5af1b-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="5af1b-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="5af1b-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="5af1b-105">**目標:** このステップで、次を変更する既存の vPrev BizTalk プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="5af1b-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
-   <span data-ttu-id="5af1b-106">WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-106">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="5af1b-107">WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev Siebel アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-107">Map the request message for performing an Insert operation using the vPrev Siebel adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="5af1b-108">WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]vPrev Siebel アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="5af1b-108">Map the response message received using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the response message for the vPrev Siebel adapter.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="5af1b-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="5af1b-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="5af1b-110">Siebel システムでアカウント ビジネス コンポーネントには挿入操作を実行する vPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-110">You must have a vPrev BizTalk project to perform an Insert operation on the Account business component in the Siebel system.</span></span>  
  
### <a name="to-modify-the-vprev-biztalk-project"></a><span data-ttu-id="5af1b-111">VPrev BizTalk プロジェクトを変更するには</span><span class="sxs-lookup"><span data-stu-id="5af1b-111">To modify the vPrev BizTalk project</span></span>  
  
1.  <span data-ttu-id="5af1b-112">WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-112">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="5af1b-113">使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
     <span data-ttu-id="5af1b-114">メタデータを生成する方法については、次を参照してください。 [Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-114">For instructions on how to generate metadata, see [Get Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span></span> <span data-ttu-id="5af1b-115">スキーマを生成すると後のような名前のファイルが*SiebelBindingSchema.xsd*が BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-115">After the schema is generated, a file with the name similar to *SiebelBindingSchema.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="5af1b-116">このファイルには、WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作を実行するメッセージを送信するためのスキーマが含まれています。[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-116">This file contains the schema for sending a message to perform the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="5af1b-117">挿入操作のメタデータを生成すると、ポートのバインド ファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="5af1b-117">Generating the metadata for the Insert operation also creates a port binding file.</span></span> <span data-ttu-id="5af1b-118">次の手順で Siebel システムへのメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5af1b-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the Siebel system.</span></span> <span data-ttu-id="5af1b-119">操作の SOAP アクションは、メタデータを生成する操作にも設定されます。</span><span class="sxs-lookup"><span data-stu-id="5af1b-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="5af1b-120">たとえば、挿入操作のメタデータを生成する場合、送信ポートでの SOAP アクションで、操作名されます"Insert"。</span><span class="sxs-lookup"><span data-stu-id="5af1b-120">For example, if you generate metadata for the Insert operation, the operation name in the SOAP action on the send port will be “Insert”.</span></span> <span data-ttu-id="5af1b-121">ただし、操作の名前、オーケストレーションの一部異なる場合があります、たとえばなどを作成する論理送信ポートで"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="5af1b-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="5af1b-122">結果として、送信ポートを使用して、Siebel システムにメッセージを送信するときに、エラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-122">As a result, when you send messages to the Siebel system using the send port, you get an error.</span></span> <span data-ttu-id="5af1b-123">これを防ぐためには、確認の論理送信ポート、オーケストレーションでは、メタデータの生成対象の操作名と同じ操作名。</span><span class="sxs-lookup"><span data-stu-id="5af1b-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
     <span data-ttu-id="5af1b-124">そのため、このチュートリアルが発生した場合、挿入操作のメタデータを生成するための名前を変更"Insert"への論理送信ポート操作します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-124">So, in case of this tutorial, because you generate metadata for the Insert operation, change the name of the logical send port operation to “Insert”.</span></span>  
  
3.  <span data-ttu-id="5af1b-125">要求メッセージの WCF ベースを使用して生成されたスキーマに vPrev Siebel アダプターを使用して生成されたスキーマにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-125">For the request message, map the schema generated using vPrev Siebel adapter to the schema generated using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="5af1b-126">BizTalk マッパーは、BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-126">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="5af1b-127">BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-127">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
         <span data-ttu-id="5af1b-128">**新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="5af1b-129">右側のウィンドウから次のように選択します。**マップ**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="5af1b-130">など、マップの名前を指定**RequestMap.btm**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="5af1b-131">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5af1b-131">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="5af1b-132">送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
    3.  <span data-ttu-id="5af1b-133">**BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev Siebel アダプターの要求メッセージのスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the vPrev Siebel adapter.</span></span> <span data-ttu-id="5af1b-134">このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.AccountService_Account_x5d*です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-134">For this tutorial, select *Siebel_BussComp_Migration.AccountService_Account_x5d*.</span></span> <span data-ttu-id="5af1b-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5af1b-135">Click **OK**.</span></span>  
  
    4.  <span data-ttu-id="5af1b-136">**送信元スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリック**OK**。</span><span class="sxs-lookup"><span data-stu-id="5af1b-136">In the **Root Node for Source Schema** dialog box, select *Insert*, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="5af1b-137">送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-137">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
    6.  <span data-ttu-id="5af1b-138">**BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-138">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="5af1b-139">このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.SiebelDBBindingSchema*、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-139">For this tutorial, select *Siebel_BussComp_Migration.SiebelDBBindingSchema*, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="5af1b-140">**ターゲット スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-140">In the **Root Node for Target Schema** dialog box, select *Insert*, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="5af1b-141">両方のスキーマで、次の要素をマップ: **Currency_Code**、 **Current_Volume**、 **Customer_Account_Group**、**場所**、**Main_Phone_Number**、**名前**、 **Party_Name**、 **Primary_Address_Id**、</span><span class="sxs-lookup"><span data-stu-id="5af1b-141">Map the following elements in both the schemas: **Currency_Code**, **Current_Volume**, **Customer_Account_Group**, **Location**, **Main_Phone_Number**, **Name**, **Party_Name**, **Primary_Address_Id**,</span></span>  
  
    9. <span data-ttu-id="5af1b-142">マップを保存します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-142">Save the map.</span></span>  
  
4.  <span data-ttu-id="5af1b-143">応答メッセージの vPrev Siebel アダプターは WCF ベースを使用して生成されたスキーマを使用して生成されたスキーマにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-143">For the response message, map the schema generated using the vPrev Siebel adapter to the schema generated using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="5af1b-144">BizTalk マッパーは、BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-144">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="5af1b-145">BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-145">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
         <span data-ttu-id="5af1b-146">[新しい項目の追加] ダイアログ ボックスの左側のペインで選択**マップ ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-146">In the Add New Item dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="5af1b-147">右側のウィンドウから次のように選択します。**マップ**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-147">From the right pane, select **Map**.</span></span> <span data-ttu-id="5af1b-148">など、マップの名前を指定**ResponseMap.btm**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-148">Specify a name for the map, such as **ResponseMap.btm**.</span></span> <span data-ttu-id="5af1b-149">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5af1b-149">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="5af1b-150">送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-150">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
    3.  <span data-ttu-id="5af1b-151">**BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-151">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="5af1b-152">このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.SiebelDBBindingSchema*です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-152">For this tutorial, select *Siebel_BussComp_Migration.SiebelDBBindingSchema*.</span></span> <span data-ttu-id="5af1b-153">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5af1b-153">Click **OK**.</span></span>  
  
    4.  <span data-ttu-id="5af1b-154">**送信元スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-154">In the **Root Node for Source Schema** dialog box, select *InsertResponse* and click **OK**.</span></span>  
  
    5.  <span data-ttu-id="5af1b-155">送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-155">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
    6.  <span data-ttu-id="5af1b-156">**BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev Siebel アダプターの応答メッセージのスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-156">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the vPrev Siebel adapter.</span></span> <span data-ttu-id="5af1b-157">このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.AccountService_Account_x5d*です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-157">For this tutorial, select *Siebel_BussComp_Migration.AccountService_Account_x5d*.</span></span> <span data-ttu-id="5af1b-158">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5af1b-158">Click **OK**.</span></span>  
  
    7.  <span data-ttu-id="5af1b-159">**ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-159">In the **Root Node for Target Schema** dialog box, select *InsertResponse* and click **OK**.</span></span>  
  
    8.  <span data-ttu-id="5af1b-160">マップ、 **: 文字列の配列**送信元スキーマ内の要素、**公開: 文字列**に次の図に示すように、送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="5af1b-160">Map the **array:string** element in the source schema to the **exposed:string** element in the destination schema, as illustrated in the following figure.</span></span>  
  
         <span data-ttu-id="5af1b-161">![アダプター バージョン間の応答メッセージをマップ](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")</span><span class="sxs-lookup"><span data-stu-id="5af1b-161">![Map the response messages between adapter versions](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")</span></span>  
  
    9. <span data-ttu-id="5af1b-162">マップを保存します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-162">Save the map.</span></span>  
  
5.  <span data-ttu-id="5af1b-163">保存し、BizTalk ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="5af1b-163">Save and build the BizTalk solution.</span></span> <span data-ttu-id="5af1b-164">ソリューションを右クリックし、をクリックして**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-164">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6.  <span data-ttu-id="5af1b-165">ソリューションを展開する。</span><span class="sxs-lookup"><span data-stu-id="5af1b-165">Deploy the solution.</span></span> <span data-ttu-id="5af1b-166">ソリューションを右クリックし、をクリックして**ソリューションの配置**です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-166">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5af1b-167">次の手順</span><span class="sxs-lookup"><span data-stu-id="5af1b-167">Next Steps</span></span>  
 <span data-ttu-id="5af1b-168">Wcf-custom 送信ポートを作成および構成」の説明に従って、この手順で作成したマップを使用するように[手順 2: Oracle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成する](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)です。</span><span class="sxs-lookup"><span data-stu-id="5af1b-168">Create a WCF-custom send port and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af1b-169">参照</span><span class="sxs-lookup"><span data-stu-id="5af1b-169">See Also</span></span>  
 [<span data-ttu-id="5af1b-170">チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="5af1b-170">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)
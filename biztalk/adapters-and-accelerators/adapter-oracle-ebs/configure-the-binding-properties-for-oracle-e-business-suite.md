---
title: Oracle E-business Suite のバインド プロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfdca8c8-4434-4a9f-8e2a-970988c2f685
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb6250a5305e6b2cb65a9b6075f1a9e906a4663
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375685"
---
# <a name="configure-the-binding-properties-for-oracle-e-business-suite"></a><span data-ttu-id="380ee-102">Oracle E-business Suite のバインド プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="380ee-102">Configure the binding properties for Oracle E-Business Suite</span></span>
<span data-ttu-id="380ee-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="380ee-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="380ee-104">このセクションでは、バインドのプロパティを設定する方法についての情報を提供します。[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との間、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="380ee-104">This section provides information about setting the binding properties from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="380ee-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の操作のスキーマの生成中にバインディング プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380ee-105">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the binding properties while generating schema for specific operations.</span></span> <span data-ttu-id="380ee-106">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信の一環としてのバインドのプロパティを指定するか、受信ポートを送信または Oracle E-business Suite からメッセージを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380ee-106">From [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must specify the binding properties as part of the send or receive port for sending or receiving messages from Oracle E-Business Suite.</span></span>  

 <span data-ttu-id="380ee-107">バインドのプロパティについては、バインドのプロパティの一覧を含む、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="380ee-107">For information about the binding properties, including a list of binding properties for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  

## <a name="specifying-binding-properties-from-visual-studio"></a><span data-ttu-id="380ee-108">Visual Studio からバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="380ee-108">Specifying Binding Properties from Visual Studio</span></span>  
 <span data-ttu-id="380ee-109">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用してバインドのプロパティを指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="380ee-109">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="380ee-110">Consume Adapter Service アドインを使用してバインドのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="380ee-110">To specify binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="380ee-111">BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-111">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="380ee-112">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="380ee-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="380ee-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="380ee-113">Use this</span></span>|<span data-ttu-id="380ee-114">目的</span><span class="sxs-lookup"><span data-stu-id="380ee-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="380ee-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="380ee-115">**Categories**</span></span>|<span data-ttu-id="380ee-116">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="380ee-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="380ee-117">**Templates**</span></span>|<span data-ttu-id="380ee-118">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="380ee-119">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="380ee-120">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**oracleEBSBinding**、順にクリックします**構成**.</span><span class="sxs-lookup"><span data-stu-id="380ee-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list, select **oracleEBSBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="380ee-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインド プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="380ee-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  

6.  <span data-ttu-id="380ee-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="380ee-122">Click **OK**.</span></span>  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="380ee-123">アダプター メタデータの追加ウィザードを使用してバインドのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="380ee-123">To specify binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="380ee-124">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-124">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="380ee-125">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="380ee-125">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="380ee-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="380ee-126">Use this</span></span>    |           <span data-ttu-id="380ee-127">目的</span><span class="sxs-lookup"><span data-stu-id="380ee-127">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="380ee-128">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="380ee-128">**Categories**</span></span> |     <span data-ttu-id="380ee-129">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-129">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="380ee-130">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="380ee-130">**Templates**</span></span>  | <span data-ttu-id="380ee-131">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-131">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="380ee-132">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="380ee-132">Click **Add**.</span></span> <span data-ttu-id="380ee-133">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="380ee-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="380ee-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 **Wcf-oracleebs**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-134">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleEBS**.</span></span> <span data-ttu-id="380ee-135">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="380ee-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="380ee-136">BizTalk で構成された Wcf-oracleebs ポート既にある場合は、ポートの一覧から、ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="380ee-136">If you already have a WCF-OracleEBS port configured in BizTalk, select the port from the Port list.</span></span>  

5. <span data-ttu-id="380ee-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="380ee-137">Click **Next**.</span></span>  

6. <span data-ttu-id="380ee-138">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、順にクリックします**構成**.</span><span class="sxs-lookup"><span data-stu-id="380ee-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleEBSBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="380ee-139">をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。</span><span class="sxs-lookup"><span data-stu-id="380ee-139">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="380ee-140">バインド プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="380ee-140">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="380ee-141">既存を選択した場合は、Wcf-oracleebs 送信ポート、バインディングのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380ee-141">If you selected an existing WCF-OracleEBS send port, you need not specify the binding properties.</span></span> <span data-ttu-id="380ee-142">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="380ee-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="380ee-143">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="380ee-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="380ee-144">このような場合は、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="380ee-144">In such a case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="380ee-145">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="380ee-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="380ee-146">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="380ee-146">Click **OK**.</span></span>  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="380ee-147">BizTalk Server 管理コンソールからバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="380ee-147">Specifying Binding Properties from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="380ee-148">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部としてのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380ee-148">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the binding properties as part of the WCF-Custom or WCF-OracleEBS port configuration.</span></span>  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="380ee-149">WCF カスタム ポートのバインドのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="380ee-149">To specify binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="380ee-150">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="380ee-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="380ee-151">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="380ee-152">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="380ee-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="380ee-153">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="380ee-154">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="380ee-155">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="380ee-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="380ee-156">**バインドの種類**一覧で、 **oracleEBSBinding**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-156">From the **Binding Type** list, select **oracleEBSBinding**.</span></span>  

6. <span data-ttu-id="380ee-157">**構成**ボックスに、さまざまなバインドのプロパティの値を指定してクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="380ee-157">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  

#### <a name="to-specify-binding-properties-for-the-wcf-oracleebs-port"></a><span data-ttu-id="380ee-158">Wcf-oracleebs ポートのバインドのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="380ee-158">To specify binding properties for the WCF-OracleEBS port</span></span>  

1. <span data-ttu-id="380ee-159">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="380ee-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="380ee-160">Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="380ee-160">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="380ee-161">手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="380ee-161">For instructions, see [Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="380ee-162">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="380ee-163">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="380ee-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="380ee-164">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した Wcf-oracleebs アダプターを選択してをクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleEBS adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="380ee-165">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="380ee-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="380ee-166">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="380ee-166">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="380ee-167">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="380ee-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="380ee-168">たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。</span><span class="sxs-lookup"><span data-stu-id="380ee-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  

## <a name="see-also"></a><span data-ttu-id="380ee-169">参照</span><span class="sxs-lookup"><span data-stu-id="380ee-169">See Also</span></span>  
 [<span data-ttu-id="380ee-170">Oracle E-business Suite のアプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="380ee-170">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)
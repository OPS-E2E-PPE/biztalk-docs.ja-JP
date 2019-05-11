---
title: Siebel のバインド プロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
- how to, specify binding properties at design time
- how to, specify binding properties at run time
ms.assetid: 063e9507-8172-4fb0-8b9f-2f95e8a82f21
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99d34f37573714f0b61bd4bf19aa788dba6742b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371898"
---
# <a name="configure-the-binding-properties-for-siebel"></a><span data-ttu-id="b5dbd-102">Siebel のバインド プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-102">Configure the binding properties for Siebel</span></span>
<span data-ttu-id="b5dbd-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="b5dbd-104">このセクションでは、および Visual Studio (デザイン時) からバインドのプロパティを設定する方法についての情報を提供します。、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを (実行時)。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console (run time).</span></span> <span data-ttu-id="b5dbd-105">デザイン時に、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="b5dbd-106">実行時に、Siebel システムへのメッセージを送信するための送信ポートの一部としてのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-106">At run time, you must specify the binding properties as part of the send port for sending messages to the Siebel system.</span></span>  

 <span data-ttu-id="b5dbd-107">バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

## <a name="enter-the-binding-properties-at-design-time"></a><span data-ttu-id="b5dbd-108">デザイン時のバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-108">Enter the binding properties at design time</span></span>  
 <span data-ttu-id="b5dbd-109">デザイン時からのバインドのプロパティを指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-109">For design time, you must specify the binding properties from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] dialog box.</span></span>  

#### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="b5dbd-110">Consume Adapter Service アドインを使用してバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="b5dbd-111">BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-111">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="b5dbd-112">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="b5dbd-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b5dbd-113">Use this</span></span>|<span data-ttu-id="b5dbd-114">目的</span><span class="sxs-lookup"><span data-stu-id="b5dbd-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b5dbd-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="b5dbd-115">**Categories**</span></span>|<span data-ttu-id="b5dbd-116">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="b5dbd-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="b5dbd-117">**Templates**</span></span>|<span data-ttu-id="b5dbd-118">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="b5dbd-119">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="b5dbd-120">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="b5dbd-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  

5.  <span data-ttu-id="b5dbd-121">**アダプターの構成**ダイアログ ボックスで、 をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="b5dbd-122">バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-122">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

6.  <span data-ttu-id="b5dbd-123">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-123">Click **OK**.</span></span>  

#### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="b5dbd-124">アダプター メタデータの追加ウィザードを使用してバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-124">Enter binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="b5dbd-125">BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-125">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="b5dbd-126">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-126">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="b5dbd-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b5dbd-127">Use this</span></span>    |           <span data-ttu-id="b5dbd-128">目的</span><span class="sxs-lookup"><span data-stu-id="b5dbd-128">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="b5dbd-129">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="b5dbd-129">**Categories**</span></span> |     <span data-ttu-id="b5dbd-130">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-130">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="b5dbd-131">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="b5dbd-131">**Templates**</span></span>  | <span data-ttu-id="b5dbd-132">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-132">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="b5dbd-133">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-133">Click **Add**.</span></span> <span data-ttu-id="b5dbd-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="b5dbd-135">アダプターの追加ウィザードで選択**Wcf-siebel**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-135">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="b5dbd-136">コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-136">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="b5dbd-137">BizTalk で構成された Wcf-siebel ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-137">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="b5dbd-138">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-138">Click **Next**.</span></span>  

6. <span data-ttu-id="b5dbd-139">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="b5dbd-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="b5dbd-140">**アダプターの構成**ダイアログ ボックスで、 をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-140">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="b5dbd-141">バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-141">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="b5dbd-142">既存の WCF Siebel 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-142">If you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="b5dbd-143">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="b5dbd-144">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="b5dbd-145">このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="b5dbd-146">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="b5dbd-147">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-147">Click **OK**.</span></span>  

## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="b5dbd-148">実行時のバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-148">Enter binding properties at run time</span></span>  
 <span data-ttu-id="b5dbd-149">実行時に、Wcf-custom またはで Wcf-siebel ポートの構成の一部としてのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-149">For run time, you must specify the binding properties as part of the WCF-Custom or the WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

#### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="b5dbd-150">WCF カスタム ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-150">Enter binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="b5dbd-151">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="b5dbd-152">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し**送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="b5dbd-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="b5dbd-153">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="b5dbd-154">**ポートのプロパティ** ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="b5dbd-155">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="b5dbd-156">**バインドの種類**ドロップダウン リストで、 **siebelBinding**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-156">From the **Binding Type** drop-down list, select **siebelBinding**.</span></span>  

6. <span data-ttu-id="b5dbd-157">**構成**ボックスでのさまざまなバインドのプロパティの値を指定し、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-157">In the **Configuration** box, specify the values for the different binding properties and click **OK**.</span></span>  

#### <a name="enter-binding-properties-for-the-wcf-siebel-port"></a><span data-ttu-id="b5dbd-158">Wcf-siebel ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-158">Enter binding properties for the WCF-Siebel port</span></span>  

1. <span data-ttu-id="b5dbd-159">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="b5dbd-160">Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-160">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b5dbd-161">手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-161">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="b5dbd-162">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し**送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="b5dbd-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="b5dbd-163">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="b5dbd-164">**ポートのプロパティ** ダイアログ ボックスから、**型**ボックスの一覧は、先ほど追加した Wcf-siebel ポートを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-164">In the **Port Properties** dialog box, from the **Type** drop-down list, select the WCF-Siebel port you added earlier, and then click **Configure**.</span></span>  

5. <span data-ttu-id="b5dbd-165">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-165">In the transport properties dialog box, click the **Binding** tab and specify values for the binding properties.</span></span>  

6. <span data-ttu-id="b5dbd-166">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5dbd-166">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b5dbd-167">参照</span><span class="sxs-lookup"><span data-stu-id="b5dbd-167">See Also</span></span>  
[<span data-ttu-id="b5dbd-168">Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="b5dbd-168">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)
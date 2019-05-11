---
title: アダプター メタデータのウィザードを追加する Visual Studio を使用して SAP への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a442837b-e7d8-4edb-9c5e-5603d4c58fe5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd2c7eecc6bf7edaaf51faea7962bd8a32785caf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373606"
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="6d6b0-102">アダプター メタデータのウィザードを追加する Visual Studio を使用して、SAP に接続します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-102">Connecting to SAP in Visual Studio Using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="6d6b0-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BizTalk アダプターとしても公開されると、そのため、使用することができます、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプターを使用して SAP システムで実行する操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is also exposed as a BizTalk adapter and hence, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on an SAP system using the adapter.</span></span>  

## <a name="connecting-to-an-sap-system-using-add-adapter-metadata-wizard"></a><span data-ttu-id="6d6b0-104">接続するのには、SAP システムを使用してアダプター メタデータのウィザードを追加</span><span class="sxs-lookup"><span data-stu-id="6d6b0-104">Connecting to an SAP System Using Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="6d6b0-105">SAP システムを使用して接続するには、次の手順を実行、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-105">Perform the following steps to connect to an SAP system using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-connect-to-an-sap-system"></a><span data-ttu-id="6d6b0-106">SAP システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="6d6b0-106">To connect to an SAP system</span></span>  

1. <span data-ttu-id="6d6b0-107">使用して接続する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="6d6b0-108">使用して BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-108">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="6d6b0-109">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-109">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="6d6b0-110">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-110">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="6d6b0-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6d6b0-111">Use this</span></span>    |           <span data-ttu-id="6d6b0-112">目的</span><span class="sxs-lookup"><span data-stu-id="6d6b0-112">To do this</span></span>            |
      |----------------|---------------------------------|
      | <span data-ttu-id="6d6b0-113">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="6d6b0-113">**Categories**</span></span> |     <span data-ttu-id="6d6b0-114">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-114">Click **Add Adapter**.</span></span>      |
      | <span data-ttu-id="6d6b0-115">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="6d6b0-115">**Templates**</span></span>  | <span data-ttu-id="6d6b0-116">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-116">Click **Add Adapter Metadata**.</span></span> |


   4. <span data-ttu-id="6d6b0-117">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-117">Click **Add**.</span></span> <span data-ttu-id="6d6b0-118">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

   5. <span data-ttu-id="6d6b0-119">アダプターの追加ウィザードで選択**WCF-SAP**します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-119">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="6d6b0-120">コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

      > [!IMPORTANT]
      >  <span data-ttu-id="6d6b0-121">BizTalk で構成されている WCF SAP ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-121">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  

   6. <span data-ttu-id="6d6b0-122">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-122">Click **Next**.</span></span>  

2. <span data-ttu-id="6d6b0-123">**バインディングを選択**ドロップダウン リスト、選択**sapBinding**  をクリック**構成**します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-123">From the **Select a binding** drop-down list, select **sapBinding** and click **Configure**.</span></span>  

3. <span data-ttu-id="6d6b0-124">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="6d6b0-125">SAP システムに接続する SAP セキュリティで保護されたネットワーク接続 (SNC) ライブラリを使用する場合は、ユーザー名とパスワードを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-125">If you are using the SAP Secure Network Connection (SNC) library to connect to an SAP system, do not specify a username and password.</span></span>  

4. <span data-ttu-id="6d6b0-126">をクリックして、 **URI プロパティ**タブし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-126">Click the **URI Properties** tab and specify values for the connection parameters.</span></span> <span data-ttu-id="6d6b0-127">接続 URI の詳細についてはの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-127">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="6d6b0-128">SAP システムに接続する SAP SNC ライブラリを使用する場合は、設定、 **UseSnc**接続プロパティを**True**します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-128">If you are using the SAP SNC library to connect to an SAP system, set the **UseSnc** connection property to **True**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6d6b0-129">接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-129">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="6d6b0-130">ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-130">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  

5. <span data-ttu-id="6d6b0-131">をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-131">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="6d6b0-132">たとえば、ReceiveIdoc 操作の対象とする場合は、する必要があります設定する、 **ReceiveIdocFormat**プロパティを文字列にバインドします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-132">For example, if you want to target a ReceiveIdoc operation you must set the **ReceiveIdocFormat** binding property to String.</span></span> <span data-ttu-id="6d6b0-133">バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-133">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="6d6b0-134">使用してメタデータを生成している場合[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]と既存の SAP では WCF 送信ポートを選択した、バインドのプロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-134">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="6d6b0-135">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-135">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="6d6b0-136">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-136">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="6d6b0-137">このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-137">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="6d6b0-138">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-138">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="6d6b0-139">SAP システムに接続する SAP SNC ライブラリを使用する場合は、設定、 **SncLibrary**と**SncPartnerName**適切な値にします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-139">If you are using the SAP SNC library to connect to an SAP system, set the **SncLibrary** and **SncPartnerName** to appropriate values.</span></span>  
   > 
   >  <span data-ttu-id="6d6b0-140">**SncLibrary**パスと SNC を使用して SAP システムに接続するために必要な Dll のファイル名は、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-140">The **SncLibrary** binding property takes the path and the filename of the DLLs required for using SNC to connect to an SAP system.</span></span> <span data-ttu-id="6d6b0-141">これらの Dll、SAP クライアントを使用してコンピューター上に存在する必要がありますと[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-141">These DLLs must be present on the computer with the SAP client and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] installed.</span></span> <span data-ttu-id="6d6b0-142">詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドで使用可能な\<インストール ガイド\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-142">For more information see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide available at \<installation guide\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
   > 
   >  <span data-ttu-id="6d6b0-143">**SncPartnerName**通信パートナーの SNC 名を受け取るプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-143">The **SncPartnerName** binding property takes the SNC name of the communication partner.</span></span>  

6. <span data-ttu-id="6d6b0-144">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-144">Click **OK**.</span></span>  

7. <span data-ttu-id="6d6b0-145">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-145">Click **Connect**.</span></span> <span data-ttu-id="6d6b0-146">接続が確立されると、接続の状態が表示として**接続**します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-146">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="6d6b0-147">次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-147">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="6d6b0-148">グラフィカル ユーザー インターフェイスは変わりません、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-148">The graphical user interface is same for the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

    <span data-ttu-id="6d6b0-149">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span><span class="sxs-lookup"><span data-stu-id="6d6b0-149">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span></span>  

    <span data-ttu-id="6d6b0-150">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SAP システムで呼び出すことができるさまざまな成果物を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-150">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various artifacts that can be invoked in an SAP system.</span></span> <span data-ttu-id="6d6b0-151">たとえば、 **RFC**ノードに接続されている SAP システムで使用可能なすべての Rfc が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-151">For example, the **RFC** node contains all the RFCs available in the SAP system you connected to.</span></span> <span data-ttu-id="6d6b0-152">これらのノードの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)します。</span><span class="sxs-lookup"><span data-stu-id="6d6b0-152">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="6d6b0-153">参照</span><span class="sxs-lookup"><span data-stu-id="6d6b0-153">See Also</span></span>  
 [<span data-ttu-id="6d6b0-154">Visual Studio で SAP システムに接続する</span><span class="sxs-lookup"><span data-stu-id="6d6b0-154">Connect to the SAP System in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)
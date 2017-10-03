---
title: "アダプターを使用する Visual Studio を使用して、SAP に接続する追加のサービスの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4f7d57a-fd88-4420-b893-49f42b449597
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736d9a668bba50a04e4316db40026379e47209a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connecting-to-sap-in-visual-studio-using-consume-adapter-service-add-in"></a><span data-ttu-id="5c471-102">アダプターを使用する Visual Studio を使用して、SAP に接続する追加のサービス</span><span class="sxs-lookup"><span data-stu-id="5c471-102">Connecting to SAP in Visual Studio Using Consume Adapter Service Add-in</span></span>
<span data-ttu-id="5c471-103">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] WCF LOB Adapter SDK をインストールするときにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="5c471-103">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] is installed when you install WCF LOB Adapter SDK.</span></span> <span data-ttu-id="5c471-104">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]コンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="5c471-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="5c471-105">WCF ベースを使用して SAP システムへの接続に[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]BizTalk プロジェクトで使用する必要があります、 **sapbinding**です。</span><span class="sxs-lookup"><span data-stu-id="5c471-105">To connect to SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in a BizTalk project, you must use the **sapbinding**.</span></span>  
  
 <span data-ttu-id="5c471-106">このトピックでは、使用する方法の説明、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5c471-106">This topic provides instructions on how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
## <a name="connecting-to-an-sap-system-using-consume-adapter-service-add-in"></a><span data-ttu-id="5c471-107">接続するには、SAP システムを使用してアダプターを使用アドインでは、サービス</span><span class="sxs-lookup"><span data-stu-id="5c471-107">Connecting to an SAP System Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="5c471-108">使用して SAP システムへの接続には、次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5c471-108">Perform the following steps to connect to an SAP system using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-an-sap-system"></a><span data-ttu-id="5c471-109">SAP システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="5c471-109">To connect to an SAP system</span></span>  
  
1.  <span data-ttu-id="5c471-110">使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="5c471-110">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="5c471-111">使用して BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5c471-111">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="5c471-112">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="5c471-112">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    3.  <span data-ttu-id="5c471-113">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5c471-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="5c471-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5c471-114">Use this</span></span>|<span data-ttu-id="5c471-115">目的</span><span class="sxs-lookup"><span data-stu-id="5c471-115">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="5c471-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="5c471-116">**Categories**</span></span>|<span data-ttu-id="5c471-117">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="5c471-117">Click **Consume Adapter Service**.</span></span>|  
        |<span data-ttu-id="5c471-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="5c471-118">**Templates**</span></span>|<span data-ttu-id="5c471-119">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="5c471-119">Click **Consume Adapter Service**.</span></span>|  
  
    4.  <span data-ttu-id="5c471-120">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c471-120">Click **Add**.</span></span> <span data-ttu-id="5c471-121">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c471-121">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="5c471-122">**バインディングを選択**ドロップダウン リスト、選択**sapBinding**  をクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="5c471-122">From the **Select a binding** drop-down list, select **sapBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="5c471-123">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c471-123">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5c471-124">SAP システムへの接続に SAP セキュリティで保護されたネットワーク接続 (SNC) ライブラリを使用する場合を指定しないユーザー名とパスワード。</span><span class="sxs-lookup"><span data-stu-id="5c471-124">If you are using the SAP Secure Network Connection (SNC) library to connect to an SAP system, do not specify a username and password.</span></span>  
  
4.  <span data-ttu-id="5c471-125">クリックして、 **URI プロパティ**タブし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c471-125">Click the **URI Properties** tab and specify values for the connection parameters.</span></span> <span data-ttu-id="5c471-126">詳細については、接続 URI の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="5c471-126">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5c471-127">SAP システムへの接続に SAP SNC ライブラリを使用する場合は、設定、 **UseSnc**接続プロパティを**True**です。</span><span class="sxs-lookup"><span data-stu-id="5c471-127">If you are using the SAP SNC library to connect to an SAP system, set the **UseSnc** connection property to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c471-128">接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="5c471-128">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="5c471-129">ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c471-129">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
5.  <span data-ttu-id="5c471-130">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c471-130">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="5c471-131">たとえば場合 ReceiveIdoc 操作の対象にする必要があります設定する、 **ReceiveIdocFormat**文字列にプロパティを連結します。</span><span class="sxs-lookup"><span data-stu-id="5c471-131">For example, if you want to target a ReceiveIdoc operation you must set the **ReceiveIdocFormat** binding property to String.</span></span> <span data-ttu-id="5c471-132">バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="5c471-132">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5c471-133">SAP システムへの接続に SAP SNC ライブラリを使用する場合は、設定、 **SncLibrary**と**SncPartnerName**を適切な値です。</span><span class="sxs-lookup"><span data-stu-id="5c471-133">If you are using the SAP SNC library to connect to an SAP system, set the **SncLibrary** and **SncPartnerName** to appropriate values.</span></span>  
    >   
    >  <span data-ttu-id="5c471-134">**SncLibrary**パスと SNC を使用して SAP システムに接続するために必要な Dll のファイル名は、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5c471-134">The **SncLibrary** binding property takes the path and the filename of the DLLs required for using SNC to connect to an SAP system.</span></span> <span data-ttu-id="5c471-135">これらの Dll は、SAP クライアントを使用してコンピューター上に存在する必要がありますと[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="5c471-135">These DLLs must be present on the computer with the SAP client and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] installed.</span></span> <span data-ttu-id="5c471-136">詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドで使用可能な\<インストール ガイド >: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。</span><span class="sxs-lookup"><span data-stu-id="5c471-136">For more information see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide available at \<installation guide>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
    >   
    >  <span data-ttu-id="5c471-137">**SncPartnerName**通信パートナーの SNC 名を取得するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5c471-137">The **SncPartnerName** binding property takes the SNC name of the communication partner.</span></span>  
  
6.  <span data-ttu-id="5c471-138">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c471-138">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="5c471-139">**[接続]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c471-139">Click **Connect**.</span></span> <span data-ttu-id="5c471-140">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="5c471-140">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="5c471-141">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="5c471-141">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="5c471-142">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span><span class="sxs-lookup"><span data-stu-id="5c471-142">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span></span>  
  
     <span data-ttu-id="5c471-143">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SAP システムで呼び出すことのできる各種の成果物を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c471-143">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various artifacts that can be invoked in an SAP system.</span></span> <span data-ttu-id="5c471-144">たとえば、 **RFC**ノードに接続されている SAP システムで使用できるすべての Rfc に含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c471-144">For example, the **RFC** node contains all the RFCs available in the SAP system you connected to.</span></span> <span data-ttu-id="5c471-145">これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。</span><span class="sxs-lookup"><span data-stu-id="5c471-145">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c471-146">参照</span><span class="sxs-lookup"><span data-stu-id="5c471-146">See Also</span></span>  
 [<span data-ttu-id="5c471-147">Visual Studio での SAP システムへの接続します。</span><span class="sxs-lookup"><span data-stu-id="5c471-147">Connect to the SAP System in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)
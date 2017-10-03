---
title: "アダプター サービス参照のプラグインを追加する Visual Studio を使用して SAP への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05116c2f-08a4-495b-a031-d377e7ca33e0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19dd824322906bdd148b96eb305e88fc35847947
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connecting-to-sap-in-visual-studio-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="3963a-102">アダプター サービス参照のプラグインを追加する Visual Studio を使用して SAP への接続</span><span class="sxs-lookup"><span data-stu-id="3963a-102">Connecting to SAP in Visual Studio Using Add Adapter Service Reference Plug-in</span></span>
<span data-ttu-id="3963a-103">使用して SAP システムへの接続に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] .NET プログラミング ソリューションで使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3963a-103">To connect to an SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="3963a-104">このトピックでは、使用する方法の説明、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3963a-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connecting-to-an-sap-system-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="3963a-105">接続を SAP システムを使用してアダプター サービス参照のプラグインを追加</span><span class="sxs-lookup"><span data-stu-id="3963a-105">Connecting to an SAP System Using Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="3963a-106">使用して SAP システムへの接続には、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3963a-106">Perform the following steps to connect to an SAP system using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-an-sap-system"></a><span data-ttu-id="3963a-107">SAP システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="3963a-107">To connect to an SAP system</span></span>  
  
1.  <span data-ttu-id="3963a-108">使用して接続する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="3963a-108">To connect using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="3963a-109">プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3963a-109">Create a project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="3963a-110">ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="3963a-110">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="3963a-111">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3963a-111">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="3963a-112">**バインディングを選択**ドロップダウン リスト、選択**sapBinding**  をクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="3963a-112">From the **Select a binding** drop-down list, select **sapBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="3963a-113">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="3963a-113">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3963a-114">SAP システムへの接続に SAP セキュリティで保護されたネットワーク接続 (SNC) ライブラリを使用する場合を指定しないユーザー名とパスワード。</span><span class="sxs-lookup"><span data-stu-id="3963a-114">If you are using the SAP Secure Network Connection (SNC) library to connect to an SAP system, do not specify a username and password.</span></span>  
  
4.  <span data-ttu-id="3963a-115">クリックして、 **URI プロパティ**タブし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3963a-115">Click the **URI Properties** tab and specify values for the connection parameters.</span></span> <span data-ttu-id="3963a-116">詳細については、接続 URI の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="3963a-116">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3963a-117">SAP システムへの接続に SAP SNC ライブラリを使用する場合は、設定、 **UseSnc**接続プロパティを**True**です。</span><span class="sxs-lookup"><span data-stu-id="3963a-117">If you are using the SAP SNC library to connect to an SAP system, set the **UseSnc** connection property to **True**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3963a-118">接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="3963a-118">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="3963a-119">ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3963a-119">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
5.  <span data-ttu-id="3963a-120">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3963a-120">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="3963a-121">たとえば場合 ReceiveIdoc 操作の対象にする必要があります設定する、 **ReceiveIdocFormat**文字列にプロパティを連結します。</span><span class="sxs-lookup"><span data-stu-id="3963a-121">For example, if you want to target a ReceiveIdoc operation you must set the **ReceiveIdocFormat** binding property to String.</span></span> <span data-ttu-id="3963a-122">バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="3963a-122">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3963a-123">SAP システムへの接続に SAP SNC ライブラリを使用する場合は、設定、 **SncLibrary**と**SncPartnerName**を適切な値です。</span><span class="sxs-lookup"><span data-stu-id="3963a-123">If you are using the SAP SNC library to connect to an SAP system, set the **SncLibrary** and **SncPartnerName** to appropriate values.</span></span>  
    >   
    >  <span data-ttu-id="3963a-124">**SncLibrary**パスと SNC を使用して SAP システムに接続するために必要な Dll のファイル名は、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="3963a-124">The **SncLibrary** binding property takes the path and the filename of the DLLs required for using SNC to connect to an SAP system.</span></span> <span data-ttu-id="3963a-125">これらの Dll は、SAP クライアントを使用してコンピューター上に存在する必要がありますと[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="3963a-125">These DLLs must be present on the computer with the SAP client and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] installed.</span></span> <span data-ttu-id="3963a-126">詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドで使用可能な\<インストール ガイド >: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。</span><span class="sxs-lookup"><span data-stu-id="3963a-126">For more information see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide available at \<installation guide>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
    >   
    >  <span data-ttu-id="3963a-127">**SncPartnerName**通信パートナーの SNC 名を取得するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="3963a-127">The **SncPartnerName** binding property takes the SNC name of the communication partner.</span></span>  
  
6.  <span data-ttu-id="3963a-128">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3963a-128">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="3963a-129">**[接続]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3963a-129">Click **Connect**.</span></span> <span data-ttu-id="3963a-130">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="3963a-130">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="3963a-131">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="3963a-131">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="3963a-132">グラフィカル ユーザー インターフェイスが同じ、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3963a-132">The graphical user interface is same for the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
     <span data-ttu-id="3963a-133">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span><span class="sxs-lookup"><span data-stu-id="3963a-133">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-sap/media/00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0.gif "00eb7c9c-3af3-4dad-8c97-2e6ae211b8f0")</span></span>  
  
     <span data-ttu-id="3963a-134">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] SAP システムで呼び出すことのできる各種の成果物を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3963a-134">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] displays different nodes containing various artifacts that can be invoked in an SAP system.</span></span> <span data-ttu-id="3963a-135">たとえば、 **RFC**ノードに接続されている SAP システムで使用できるすべての Rfc に含まれます。</span><span class="sxs-lookup"><span data-stu-id="3963a-135">For example, the **RFC** node contains all the RFCs available in the SAP system you connected to.</span></span> <span data-ttu-id="3963a-136">これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。</span><span class="sxs-lookup"><span data-stu-id="3963a-136">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3963a-137">参照</span><span class="sxs-lookup"><span data-stu-id="3963a-137">See Also</span></span>  
 [<span data-ttu-id="3963a-138">Visual Studio での SAP システムへの接続します。</span><span class="sxs-lookup"><span data-stu-id="3963a-138">Connect to the SAP System in Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)
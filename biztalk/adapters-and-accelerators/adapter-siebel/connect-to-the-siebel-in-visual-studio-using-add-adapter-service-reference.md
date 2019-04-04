---
title: ビジュアルで Siebel システムへの接続 Studio を使用してアダプター サービス参照のプラグインの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d27121be-6407-4bb6-acb5-37dc8a3785c0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdf3ea907ba5905965188d17b3a7493788ef123e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991347"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="e0ce3-102">ビジュアルで Siebel システムへの接続 Studio を使用して、アダプター サービス参照のプラグインを追加</span><span class="sxs-lookup"><span data-stu-id="e0ce3-102">Connect to the Siebel System in Visual Studio Using Add Adapter Service Reference Plug-in</span></span>
<span data-ttu-id="e0ce3-103">使用して Siebel システムへの接続に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] .NET プログラミング ソリューションでは、使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-103">To connect to a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="e0ce3-104">このトピックでは、手順を使用する方法には、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="e0ce3-105">アダプター サービス参照のプラグインの追加を使用して Siebel システムへの接続</span><span class="sxs-lookup"><span data-stu-id="e0ce3-105">Connecting to a Siebel System Using Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="e0ce3-106">使用して Siebel システムへの接続には、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-106">Perform the following steps to connect to a Siebel system using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="e0ce3-107">Siebel システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="e0ce3-107">To connect to a Siebel system</span></span>  
  
1. <span data-ttu-id="e0ce3-108">使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-108">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  
  
   1. <span data-ttu-id="e0ce3-109">使用して BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-109">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="e0ce3-110">ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**アダプター サービス参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-110">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="e0ce3-111">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-111">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] opens.</span></span>  
  
2. <span data-ttu-id="e0ce3-112">**バインディングを選択**ドロップダウン リスト、選択**siebelBinding**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-112">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  
  
3. <span data-ttu-id="e0ce3-113">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**.</span><span class="sxs-lookup"><span data-stu-id="e0ce3-113">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  
  
4. <span data-ttu-id="e0ce3-114">ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-114">Specify the user name and password to connect to the Siebel system.</span></span>  
  
5. <span data-ttu-id="e0ce3-115">をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-115">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="e0ce3-116">接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-116">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e0ce3-117">接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-117">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="e0ce3-118">ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-118">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
6. <span data-ttu-id="e0ce3-119">をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-119">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="e0ce3-120">バインド プロパティの詳細については、[for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-120">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
7. <span data-ttu-id="e0ce3-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-121">Click **OK**.</span></span>  
  
8. <span data-ttu-id="e0ce3-122">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-122">Click **Connect**.</span></span> <span data-ttu-id="e0ce3-123">として、接続の状態が示すように、接続が確立されると、**接続**します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-123">Once the connection is established, the connection status is shown as **Connected**.</span></span>  
  
    <span data-ttu-id="e0ce3-124">次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-124">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="e0ce3-125">グラフィカル ユーザー インターフェイスは変わりません、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-125">The graphical user interface is same for the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    <span data-ttu-id="e0ce3-126">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="e0ce3-126">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  
  
    <span data-ttu-id="e0ce3-127">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Siebel システムで実行できるさまざまな操作を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-127">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="e0ce3-128">たとえば、**ビジネス オブジェクト**ノードには、すべてのビジネス オブジェクトと Siebel システムで呼び出すことができるビジネス コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-128">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="e0ce3-129">同様に、**ビジネス サービス**ノードには、すべてのビジネス サービスに接続されている Siebel システムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-129">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="e0ce3-130">これらのノードの詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ce3-130">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>
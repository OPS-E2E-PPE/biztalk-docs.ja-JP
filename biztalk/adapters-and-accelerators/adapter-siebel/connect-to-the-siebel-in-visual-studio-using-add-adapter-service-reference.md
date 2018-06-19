---
title: ビジュアルの Siebel システムへの接続 Studio を使用してアダプター サービス参照のプラグインを追加 |Microsoft ドキュメント
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
ms.openlocfilehash: 696e91d689bfc7bc058ce0c512e8fa09b91b18a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222090"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="ea491-102">ビジュアルの Siebel システムへの接続 Studio を使用してアダプター サービス参照のプラグインを追加</span><span class="sxs-lookup"><span data-stu-id="ea491-102">Connect to the Siebel System in Visual Studio Using Add Adapter Service Reference Plug-in</span></span>
<span data-ttu-id="ea491-103">使用して Siebel システムへの接続に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] .NET プログラミング ソリューションで使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea491-103">To connect to a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="ea491-104">このトピックでは、使用する方法の説明、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea491-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="ea491-105">プラグイン アダプター サービス参照の追加を使用する Siebel システムへの接続</span><span class="sxs-lookup"><span data-stu-id="ea491-105">Connecting to a Siebel System Using Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="ea491-106">使用して Siebel システムへの接続には、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea491-106">Perform the following steps to connect to a Siebel system using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="ea491-107">Siebel システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="ea491-107">To connect to a Siebel system</span></span>  
  
1.  <span data-ttu-id="ea491-108">使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="ea491-108">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="ea491-109">使用して BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea491-109">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="ea491-110">ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="ea491-110">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="ea491-111">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea491-111">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="ea491-112">**バインディングを選択**ドロップダウン リスト、選択**siebelBinding**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ea491-112">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="ea491-113">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**.</span><span class="sxs-lookup"><span data-stu-id="ea491-113">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  
  
4.  <span data-ttu-id="ea491-114">ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea491-114">Specify the user name and password to connect to the Siebel system.</span></span>  
  
5.  <span data-ttu-id="ea491-115">クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea491-115">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="ea491-116">詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea491-116">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea491-117">接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="ea491-117">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="ea491-118">ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea491-118">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
6.  <span data-ttu-id="ea491-119">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea491-119">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="ea491-120">バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea491-120">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
7.  <span data-ttu-id="ea491-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea491-121">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="ea491-122">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea491-122">Click **Connect**.</span></span> <span data-ttu-id="ea491-123">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="ea491-123">Once the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="ea491-124">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="ea491-124">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="ea491-125">グラフィカル ユーザー インターフェイスが同じ、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea491-125">The graphical user interface is same for the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
     <span data-ttu-id="ea491-126">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="ea491-126">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  
  
     <span data-ttu-id="ea491-127">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Siebel システムで実行できるさまざまな操作を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea491-127">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="ea491-128">たとえば、**ビジネス オブジェクト**ノードには、すべてのビジネス オブジェクトと Siebel システムで呼び出すことができるビジネス コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea491-128">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="ea491-129">同様に、**ビジネス サービス**ノードには、すべてのビジネス サービスに接続されている Siebel システムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea491-129">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="ea491-130">これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea491-130">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>
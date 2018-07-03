---
title: ビジュアルで Siebel システムに接続するアダプターを使用して Studio を使用して追加のサービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2baaa361-1b14-4d00-bcef-f68bc3fa7139
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9916dc1328412428e4f21858905a005e35d9d1d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013819"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-consume-adapter-service-add-in"></a><span data-ttu-id="87559-102">ビジュアルで Siebel システムに接続するアダプターを使用して Studio を使用して追加のサービス</span><span class="sxs-lookup"><span data-stu-id="87559-102">Connect to the Siebel System in Visual Studio Using Consume Adapter Service Add-in</span></span>
<span data-ttu-id="87559-103">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]をインストールするときにインストールされている[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="87559-103">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is installed when you install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="87559-104">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]コンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="87559-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="87559-105">WCF ベースを使用して Siebel システムへの接続に[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]BizTalk プロジェクトで使用する必要があります、 **siebelBinding**します。</span><span class="sxs-lookup"><span data-stu-id="87559-105">To connect to a Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in a BizTalk project, you must use the **siebelBinding**.</span></span>  

## <a name="connecting-to-a-siebel-system-using-consume-adapter-service-add-in"></a><span data-ttu-id="87559-106">アダプターを使用してを使用して Siebel システムへの接続では、追加のサービス</span><span class="sxs-lookup"><span data-stu-id="87559-106">Connecting to a Siebel System Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="87559-107">使用して Siebel システムへの接続には、次の手順を実行、[!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="87559-107">Perform the following steps to connect to a Siebel system using the [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)].</span></span>  

#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="87559-108">Siebel システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="87559-108">To connect to a Siebel system</span></span>  

1. <span data-ttu-id="87559-109">使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="87559-109">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="87559-110">使用して BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="87559-110">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="87559-111">ソリューション エクスプ ローラーでプロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="87559-111">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="87559-112">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87559-112">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="87559-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="87559-113">Use this</span></span>    |             <span data-ttu-id="87559-114">目的</span><span class="sxs-lookup"><span data-stu-id="87559-114">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="87559-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="87559-115">**Categories**</span></span> | <span data-ttu-id="87559-116">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="87559-116">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="87559-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="87559-117">**Templates**</span></span>  | <span data-ttu-id="87559-118">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="87559-118">Click **Consume Adapter Service**.</span></span> |


   4. <span data-ttu-id="87559-119">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87559-119">Click **Add**.</span></span> <span data-ttu-id="87559-120">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="87559-120">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="87559-121">**バインディングを選択**ドロップダウン リスト、選択**siebelBinding**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="87559-121">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  

3. <span data-ttu-id="87559-122">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**.</span><span class="sxs-lookup"><span data-stu-id="87559-122">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  

4. <span data-ttu-id="87559-123">ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="87559-123">Specify the user name and password to connect to the Siebel system.</span></span>  

5. <span data-ttu-id="87559-124">をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="87559-124">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="87559-125">接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="87559-125">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="87559-126">接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="87559-126">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="87559-127">ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87559-127">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  

6. <span data-ttu-id="87559-128">をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="87559-128">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="87559-129">バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="87559-129">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

7. <span data-ttu-id="87559-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87559-130">Click **OK**.</span></span>  

8. <span data-ttu-id="87559-131">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87559-131">Click **Connect**.</span></span> <span data-ttu-id="87559-132">として、接続の状態が示すように、接続が確立されると、**接続**します。</span><span class="sxs-lookup"><span data-stu-id="87559-132">Once the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="87559-133">次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。</span><span class="sxs-lookup"><span data-stu-id="87559-133">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="87559-134">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="87559-134">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  

    <span data-ttu-id="87559-135">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Siebel システムで実行できるさまざまな操作を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87559-135">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="87559-136">たとえば、**ビジネス オブジェクト**ノードには、すべてのビジネス オブジェクトと Siebel システムで呼び出すことができるビジネス コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87559-136">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="87559-137">同様に、**ビジネス サービス**ノードには、すべてのビジネス サービスに接続されている Siebel システムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87559-137">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="87559-138">これらのノードの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)します。</span><span class="sxs-lookup"><span data-stu-id="87559-138">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>
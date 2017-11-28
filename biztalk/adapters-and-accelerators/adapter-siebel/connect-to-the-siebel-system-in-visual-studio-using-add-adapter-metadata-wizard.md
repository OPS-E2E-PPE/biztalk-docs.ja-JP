---
title: "ビジュアルの Siebel システムへの接続 Studio を使用して、アダプター メタデータのウィザードを追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0a82fcc-b3ac-4936-9210-03c99d3741d7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9fc38299ffdce6cf6227cacb7de0cae84b22091
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="b0ebd-102">ビジュアルの Siebel システムへの接続 Studio を使用して、アダプター メタデータのウィザードを追加</span><span class="sxs-lookup"><span data-stu-id="b0ebd-102">Connect to the Siebel System in Visual Studio Using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="b0ebd-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]は BizTalk アダプターとしても公開し、そのため、使用することができます、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプターを使用して、Siebel システムに対して実行する操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is also exposed as a BizTalk adapter and hence, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on the Siebel system using the adapter.</span></span>  
  
## <a name="connecting-to-a-siebel-system-using-add-adapter-metadata-wizard"></a><span data-ttu-id="b0ebd-104">アダプター メタデータのウィザードの追加を使用する Siebel システムへの接続</span><span class="sxs-lookup"><span data-stu-id="b0ebd-104">Connecting to a Siebel System Using Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="b0ebd-105">使用して Siebel システムへの接続には、次の手順を実行、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-105">Perform the following steps to connect to a Siebel system using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="b0ebd-106">Siebel システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="b0ebd-106">To connect to a Siebel system</span></span>  
  
1.  <span data-ttu-id="b0ebd-107">使用して接続する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="b0ebd-108">使用して BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-108">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="b0ebd-109">ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-109">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    3.  <span data-ttu-id="b0ebd-110">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="b0ebd-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b0ebd-111">Use this</span></span>|<span data-ttu-id="b0ebd-112">目的</span><span class="sxs-lookup"><span data-stu-id="b0ebd-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="b0ebd-113">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="b0ebd-113">**Categories**</span></span>|<span data-ttu-id="b0ebd-114">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-114">Click **Consume Adapter Service**.</span></span>|  
        |<span data-ttu-id="b0ebd-115">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="b0ebd-115">**Templates**</span></span>|<span data-ttu-id="b0ebd-116">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-116">Click **Consume Adapter Service**.</span></span>|  
  
    4.  <span data-ttu-id="b0ebd-117">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-117">Click **Add**.</span></span> <span data-ttu-id="b0ebd-118">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
    5.  <span data-ttu-id="b0ebd-119">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、WCF Siebel を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-119">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select WCF-Siebel.</span></span> <span data-ttu-id="b0ebd-120">コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="b0ebd-121">既に存在する場合、 **Wcf-siebel**で構成されている BizTalk のポートからポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-121">If you already have a **WCF-Siebel** port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
    6.  <span data-ttu-id="b0ebd-122">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-122">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="b0ebd-123">**バインディングを選択**ドロップダウン リスト、選択**siebelBinding**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-123">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="b0ebd-124">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**.</span><span class="sxs-lookup"><span data-stu-id="b0ebd-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  
  
4.  <span data-ttu-id="b0ebd-125">ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-125">Specify the user name and password to connect to the Siebel system.</span></span>  
  
5.  <span data-ttu-id="b0ebd-126">クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-126">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="b0ebd-127">詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-127">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0ebd-128">接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-128">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="b0ebd-129">ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-129">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
6.  <span data-ttu-id="b0ebd-130">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-130">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="b0ebd-131">バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-131">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0ebd-132">使用してメタデータを生成する場合[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]と既存の WCF Siebel 送信ポートを選択して、バインドのプロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-132">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="b0ebd-133">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-133">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="b0ebd-134">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-134">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="b0ebd-135">このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-135">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="b0ebd-136">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-136">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
7.  <span data-ttu-id="b0ebd-137">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="b0ebd-138">**[接続]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-138">Click **Connect**.</span></span> <span data-ttu-id="b0ebd-139">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-139">Once the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="b0ebd-140">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-140">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="b0ebd-141">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="b0ebd-141">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  
  
     <span data-ttu-id="b0ebd-142">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Siebel システムで実行できるさまざまな操作を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-142">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="b0ebd-143">たとえば、**ビジネス オブジェクト**ノードには、すべてのビジネス オブジェクトと Siebel システムで呼び出すことができるビジネス コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-143">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="b0ebd-144">同様に、**ビジネス サービス**ノードには、すべてのビジネス サービスに接続されている Siebel システムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-144">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="b0ebd-145">これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0ebd-145">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>
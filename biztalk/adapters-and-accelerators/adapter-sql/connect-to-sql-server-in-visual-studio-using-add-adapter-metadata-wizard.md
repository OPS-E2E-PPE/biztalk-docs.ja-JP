---
title: "SQL への接続で Visual Studio を使用してサーバー メタデータの追加アダプター ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2169722d-beba-4d96-a54b-54986ece9bf8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ffe323321db217fdc81b288cee9029161841fa1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="ab3b8-102">SQL への接続で Visual Studio を使用してサーバー メタデータの追加アダプター ウィザード</span><span class="sxs-lookup"><span data-stu-id="ab3b8-102">Connect to SQL Server in Visual Studio Using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="ab3b8-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] BizTalk アダプターとしても公開されると、そのため、使用することができます、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプターを使用して SQL Server で実行する操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is also exposed as a BizTalk adapter and, therefore, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on SQL Server using the adapter.</span></span>  
  
## <a name="connecting-to-sql-server-using-add-adapter-metadata-wizard"></a><span data-ttu-id="ab3b8-104">SQL への接続を使用してサーバー メタデータの追加アダプター ウィザード</span><span class="sxs-lookup"><span data-stu-id="ab3b8-104">Connecting to SQL Server Using Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="ab3b8-105">使用して SQL サーバーへの接続には、次の手順を実行、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-105">Perform the following steps to connect to SQL Server using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-connect-to-sql-server"></a><span data-ttu-id="ab3b8-106">SQL Server に接続するには</span><span class="sxs-lookup"><span data-stu-id="ab3b8-106">To connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="ab3b8-107">使用して接続する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-107">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="ab3b8-108">使用して BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-108">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="ab3b8-109">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-109">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    3.  <span data-ttu-id="ab3b8-110">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="ab3b8-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ab3b8-111">Use this</span></span>|<span data-ttu-id="ab3b8-112">目的</span><span class="sxs-lookup"><span data-stu-id="ab3b8-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="ab3b8-113">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="ab3b8-113">**Categories**</span></span>|<span data-ttu-id="ab3b8-114">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-114">Click **Add Adapter**.</span></span>|  
        |<span data-ttu-id="ab3b8-115">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="ab3b8-115">**Templates**</span></span>|<span data-ttu-id="ab3b8-116">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-116">Click **Add Adapter Metadata**.</span></span>|  
  
    4.  <span data-ttu-id="ab3b8-117">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-117">Click **Add**.</span></span> <span data-ttu-id="ab3b8-118">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
    5.  <span data-ttu-id="ab3b8-119">アダプターの追加ウィザードで選択**WCF-SQL**です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-119">In the Add Adapter Wizard, select **WCF-SQL**.</span></span> <span data-ttu-id="ab3b8-120">コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-120">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="ab3b8-121">BizTalk で構成されている WCF SQL ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-121">If you already have a WCF-SQL port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
    6.  <span data-ttu-id="ab3b8-122">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-122">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="ab3b8-123">**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-123">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="ab3b8-124">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リストで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab3b8-125">SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[SQL アダプターと Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-125">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="ab3b8-126">このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-126">Click this</span></span>|<span data-ttu-id="ab3b8-127">目的</span><span class="sxs-lookup"><span data-stu-id="ab3b8-127">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="ab3b8-128">**なし**</span><span class="sxs-lookup"><span data-stu-id="ab3b8-128">**None**</span></span>|<span data-ttu-id="ab3b8-129">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-129">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="ab3b8-130">**Windows**</span><span class="sxs-lookup"><span data-stu-id="ab3b8-130">**Windows**</span></span>|<span data-ttu-id="ab3b8-131">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-131">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="ab3b8-132">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="ab3b8-132">**Username**</span></span>|<span data-ttu-id="ab3b8-133">ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-133">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="ab3b8-134">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-134">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="ab3b8-135">**注:**のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-135">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
4.  <span data-ttu-id="ab3b8-136">クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-136">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="ab3b8-137">詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-137">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab3b8-138">接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-138">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="ab3b8-139">ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-139">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab3b8-140">[URI のプロパティ] タブで値を指定しないと、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] により URI が `mssql://.//` になります。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-140">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="ab3b8-141">このような場合、アダプターは既定のデータベースと、ローカル コンピューター上の既定のデータベース インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-141">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  
  
5.  <span data-ttu-id="ab3b8-142">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-142">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="ab3b8-143">バインディングのプロパティ」を参照しての詳細については[SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-143">For more information about binding properties see, [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab3b8-144">使用してメタデータを生成する場合[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]と既存の WCF-SQL 送信ポートを選択して、バインドのプロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-144">If you are generating metadata using [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] and you selected an existing WCF-SQL send port, you need not specify the binding properties.</span></span> <span data-ttu-id="ab3b8-145">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-145">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="ab3b8-146">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-146">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="ab3b8-147">このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-147">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="ab3b8-148">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-148">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
6.  <span data-ttu-id="ab3b8-149">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-149">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="ab3b8-150">**[接続]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-150">Click **Connect**.</span></span> <span data-ttu-id="ab3b8-151">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-151">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="ab3b8-152">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-152">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="ab3b8-153">グラフィカル ユーザー インターフェイスが同じ、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-153">The graphical user interface is same for the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
     <span data-ttu-id="ab3b8-154">![SQL Server に接続](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span><span class="sxs-lookup"><span data-stu-id="ab3b8-154">![Connect to SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span></span>  
  
     <span data-ttu-id="ab3b8-155">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SQL Server で実行できるさまざまな操作を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-155">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on SQL Server.</span></span> <span data-ttu-id="ab3b8-156">たとえば、**プロシージャ**ノードに接続されているデータベースに使用できるすべてのプロシージャが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-156">For example, the **Procedures** node contains all the procedures available for the database you connected to.</span></span> <span data-ttu-id="ab3b8-157">同様に、**テーブル**ノードに接続して、データベースとテーブルで実行できる操作のすべてのテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-157">Similarly, the **Tables** node contains all the tables in the database you connected to, and the operations that can be performed on a table.</span></span> <span data-ttu-id="ab3b8-158">これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)です。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-158">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3b8-159">参照</span><span class="sxs-lookup"><span data-stu-id="ab3b8-159">See Also</span></span>  
 [<span data-ttu-id="ab3b8-160">アダプター サービスのアドインを使用して Visual Studio での SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="ab3b8-160">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)
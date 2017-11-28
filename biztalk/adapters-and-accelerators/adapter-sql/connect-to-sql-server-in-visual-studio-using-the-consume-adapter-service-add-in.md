---
title: "アダプター サービスのアドインを使用して Visual Studio での SQL Server に接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d4fa2bd-ac9e-41b1-8fea-e6a41cbfd1a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69ccf497c9546f0695565e3e9f46ec2536b42ef8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in"></a><span data-ttu-id="d600f-102">アダプター サービスのアドインを使用して Visual Studio での SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="d600f-102">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>
<span data-ttu-id="d600f-103">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]をインストールするときにインストールされている[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d600f-103">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is installed when you install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="d600f-104">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]コンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d600f-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="d600f-105">WCF ベースを使用して SQL Server に接続する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]BizTalk プロジェクトで使用する必要があります、 **sqlbinding**です。</span><span class="sxs-lookup"><span data-stu-id="d600f-105">To connect to SQL Server using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a BizTalk project, you must use the **sqlbinding**.</span></span>  
  
 <span data-ttu-id="d600f-106">このトピックでは、使用する方法の説明、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d600f-106">This topic provides instructions on how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
## <a name="connecting-to-sql-server-using-consume-adapter-service-add-in"></a><span data-ttu-id="d600f-107">SQL に接続するアダプターを使用するサーバーを使用してアドインでは、サービス</span><span class="sxs-lookup"><span data-stu-id="d600f-107">Connecting to SQL Server Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="d600f-108">使用して SQL サーバーへの接続には、次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d600f-108">Perform the following steps to connect to SQL Server using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-sql-server"></a><span data-ttu-id="d600f-109">SQL Server に接続するには</span><span class="sxs-lookup"><span data-stu-id="d600f-109">To connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="d600f-110">使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="d600f-110">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="d600f-111">使用して BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d600f-111">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="d600f-112">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="d600f-112">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    3.  <span data-ttu-id="d600f-113">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="d600f-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="d600f-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d600f-114">Use this</span></span>|<span data-ttu-id="d600f-115">目的</span><span class="sxs-lookup"><span data-stu-id="d600f-115">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="d600f-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="d600f-116">**Categories**</span></span>|<span data-ttu-id="d600f-117">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="d600f-117">Click **Consume Adapter Service**.</span></span>|  
        |<span data-ttu-id="d600f-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="d600f-118">**Templates**</span></span>|<span data-ttu-id="d600f-119">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="d600f-119">Click **Consume Adapter Service**.</span></span>|  
  
    4.  <span data-ttu-id="d600f-120">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d600f-120">Click **Add**.</span></span> <span data-ttu-id="d600f-121">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d600f-121">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="d600f-122">**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="d600f-122">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="d600f-123">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リストで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d600f-123">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d600f-124">SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[SQL アダプターと Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="d600f-124">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="d600f-125">このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d600f-125">Click this</span></span>|<span data-ttu-id="d600f-126">目的</span><span class="sxs-lookup"><span data-stu-id="d600f-126">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="d600f-127">**なし**</span><span class="sxs-lookup"><span data-stu-id="d600f-127">**None**</span></span>|<span data-ttu-id="d600f-128">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="d600f-128">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="d600f-129">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d600f-129">**Windows**</span></span>|<span data-ttu-id="d600f-130">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="d600f-130">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="d600f-131">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="d600f-131">**Username**</span></span>|<span data-ttu-id="d600f-132">ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="d600f-132">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="d600f-133">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d600f-133">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="d600f-134">**注:**のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="d600f-134">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
4.  <span data-ttu-id="d600f-135">クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d600f-135">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="d600f-136">詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="d600f-136">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d600f-137">接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="d600f-137">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="d600f-138">ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d600f-138">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d600f-139">[URI のプロパティ] タブで値を指定しないと、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] により URI が `mssql://.//` になります。</span><span class="sxs-lookup"><span data-stu-id="d600f-139">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="d600f-140">このような場合、アダプターは既定のデータベースと、ローカル コンピューター上の既定のデータベース インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="d600f-140">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  
  
5.  <span data-ttu-id="d600f-141">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d600f-141">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span>  
  
6.  <span data-ttu-id="d600f-142">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d600f-142">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="d600f-143">**[接続]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d600f-143">Click **Connect**.</span></span> <span data-ttu-id="d600f-144">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="d600f-144">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="d600f-145">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="d600f-145">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="d600f-146">![SQL Server に接続](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span><span class="sxs-lookup"><span data-stu-id="d600f-146">![Connect to SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span></span>  
  
     <span data-ttu-id="d600f-147">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SQL Server で実行できるさまざまな操作を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d600f-147">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on SQL Server.</span></span> <span data-ttu-id="d600f-148">たとえば、**プロシージャ**ノードに接続されているデータベースに使用できるすべてのプロシージャが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d600f-148">For example, the **Procedures** node contains all the procedures available for the database you connected to.</span></span> <span data-ttu-id="d600f-149">同様に、**テーブル**ノードに接続して、データベースとテーブルで実行できる操作のすべてのテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d600f-149">Similarly, the **Tables** node contains all the tables in the database you connected to, and the operations that can be performed on a table.</span></span> <span data-ttu-id="d600f-150">これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)です。</span><span class="sxs-lookup"><span data-stu-id="d600f-150">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d600f-151">参照</span><span class="sxs-lookup"><span data-stu-id="d600f-151">See Also</span></span>  
 [<span data-ttu-id="d600f-152">アダプター サービスのアドインを使用して Visual Studio での SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="d600f-152">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)
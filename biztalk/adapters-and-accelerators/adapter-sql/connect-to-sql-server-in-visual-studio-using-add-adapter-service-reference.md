---
title: "SQL への接続で Visual Studio を使用して Server プラグインのアダプター サービス参照の追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fc3b824-d20b-4531-81f3-89b4a1ff3216
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506d0cc1d4f4fca94b71aef3e6d4855a2afb845b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-sql-server-in-visual-studio-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="70c68-102">SQL への接続で Visual Studio を使用して Server プラグインのアダプター サービス参照の追加</span><span class="sxs-lookup"><span data-stu-id="70c68-102">Connect to SQL Server in Visual Studio Using Add Adapter Service Reference Plug-in</span></span>
<span data-ttu-id="70c68-103">使用して SQL サーバーに接続する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] .NET プログラミング ソリューションで使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="70c68-103">To connect to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="70c68-104">このトピックでは、使用する方法の説明、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="70c68-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connecting-to-sql-server-using-add-adapter-service-reference-plug-in"></a><span data-ttu-id="70c68-105">SQL に接続するサーバーを使用してアダプター サービス参照のプラグインを追加</span><span class="sxs-lookup"><span data-stu-id="70c68-105">Connecting to SQL Server Using Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="70c68-106">使用して SQL サーバーへの接続には、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="70c68-106">Perform the following steps to connect to SQL Server using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
#### <a name="to-connect-to-sql-server"></a><span data-ttu-id="70c68-107">SQL Server に接続するには</span><span class="sxs-lookup"><span data-stu-id="70c68-107">To connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="70c68-108">使用して接続する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]プログラミング ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="70c68-108">To connect using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] in a programming solution:</span></span>  
  
    1.  <span data-ttu-id="70c68-109">プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="70c68-109">Create a project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="70c68-110">ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="70c68-110">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="70c68-111">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70c68-111">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="70c68-112">**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="70c68-112">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="70c68-113">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リストで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="70c68-113">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70c68-114">SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[SQL アダプターと Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="70c68-114">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="70c68-115">このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="70c68-115">Click this</span></span>|<span data-ttu-id="70c68-116">目的</span><span class="sxs-lookup"><span data-stu-id="70c68-116">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="70c68-117">**なし**</span><span class="sxs-lookup"><span data-stu-id="70c68-117">**None**</span></span>|<span data-ttu-id="70c68-118">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="70c68-118">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="70c68-119">**Windows**</span><span class="sxs-lookup"><span data-stu-id="70c68-119">**Windows**</span></span>|<span data-ttu-id="70c68-120">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="70c68-120">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="70c68-121">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="70c68-121">**Username**</span></span>|<span data-ttu-id="70c68-122">ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="70c68-122">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="70c68-123">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="70c68-123">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="70c68-124">**注:**のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="70c68-124">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
4.  <span data-ttu-id="70c68-125">クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="70c68-125">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="70c68-126">詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="70c68-126">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70c68-127">接続パラメーターに予約済みの文字が含まれている場合、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="70c68-127">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="70c68-128">ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70c68-128">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70c68-129">[URI のプロパティ] タブで値を指定しないと、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] により URI が `mssql://.//` になります。</span><span class="sxs-lookup"><span data-stu-id="70c68-129">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="70c68-130">このような場合、アダプターは既定のデータベースと、ローカル コンピューター上の既定のデータベース インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="70c68-130">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  
  
5.  <span data-ttu-id="70c68-131">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="70c68-131">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span>  
  
6.  <span data-ttu-id="70c68-132">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70c68-132">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="70c68-133">**[接続]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70c68-133">Click **Connect**.</span></span> <span data-ttu-id="70c68-134">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="70c68-134">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="70c68-135">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="70c68-135">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span> <span data-ttu-id="70c68-136">グラフィカル ユーザー インターフェイスが同じ、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="70c68-136">The graphical user interface is same for the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
     <span data-ttu-id="70c68-137">![SQL Server に接続](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span><span class="sxs-lookup"><span data-stu-id="70c68-137">![Connect to SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span></span>  
  
     <span data-ttu-id="70c68-138">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] SQL Server で実行できるさまざまな操作を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70c68-138">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] displays different nodes containing various operations that can be performed on SQL Server.</span></span> <span data-ttu-id="70c68-139">たとえば、**プロシージャ**ノードに接続されているデータベースに使用できるすべてのプロシージャが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70c68-139">For example, the **Procedures** node contains all the procedures available for the database you connected to.</span></span> <span data-ttu-id="70c68-140">同様に、**テーブル**ノードに接続して、データベースとテーブルで実行できる操作のすべてのテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70c68-140">Similarly, the **Tables** node contains all the tables in the database you connected to, and the operations that can be performed on a table.</span></span> <span data-ttu-id="70c68-141">これらのノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)です。</span><span class="sxs-lookup"><span data-stu-id="70c68-141">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c68-142">参照</span><span class="sxs-lookup"><span data-stu-id="70c68-142">See Also</span></span>  
 [<span data-ttu-id="70c68-143">アダプター サービスのアドインを使用して Visual Studio での SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="70c68-143">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)
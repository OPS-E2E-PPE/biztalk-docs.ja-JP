---
title: Consume Adapter Service アドインを使用して Visual Studio での SQL Server への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4fa2bd-ac9e-41b1-8fea-e6a41cbfd1a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25ea1988f95042ad83cc210355b4dc8838d1e116
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008779"
---
# <a name="connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in"></a><span data-ttu-id="9fc46-102">Consume Adapter Service アドインを使用して Visual Studio での SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-102">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>
<span data-ttu-id="9fc46-103">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]をインストールするときにインストールされている[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-103">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is installed when you install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="9fc46-104">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]コンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="9fc46-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="9fc46-105">WCF ベースを使用して SQL Server に接続する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]BizTalk プロジェクトで使用する必要があります、 **sqlbinding**します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-105">To connect to SQL Server using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in a BizTalk project, you must use the **sqlbinding**.</span></span>  

 <span data-ttu-id="9fc46-106">このトピックでは、手順を使用する方法には、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-106">This topic provides instructions on how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  

## <a name="connecting-to-sql-server-using-consume-adapter-service-add-in"></a><span data-ttu-id="9fc46-107">SQL に接続するアダプターを使用してサーバーを使用して追加のサービス</span><span class="sxs-lookup"><span data-stu-id="9fc46-107">Connecting to SQL Server Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="9fc46-108">SQL Server に接続するのには、次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-108">Perform the following steps to connect to SQL Server using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  

#### <a name="to-connect-to-sql-server"></a><span data-ttu-id="9fc46-109">SQL Server に接続するには</span><span class="sxs-lookup"><span data-stu-id="9fc46-109">To connect to SQL Server</span></span>  

1. <span data-ttu-id="9fc46-110">使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="9fc46-110">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="9fc46-111">使用して BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-111">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="9fc46-112">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-112">Right-click the project name in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="9fc46-113">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9fc46-113">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="9fc46-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9fc46-114">Use this</span></span>    |             <span data-ttu-id="9fc46-115">目的</span><span class="sxs-lookup"><span data-stu-id="9fc46-115">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="9fc46-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="9fc46-116">**Categories**</span></span> | <span data-ttu-id="9fc46-117">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-117">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="9fc46-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="9fc46-118">**Templates**</span></span>  | <span data-ttu-id="9fc46-119">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-119">Click **Consume Adapter Service**.</span></span> |


   4. <span data-ttu-id="9fc46-120">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fc46-120">Click **Add**.</span></span> <span data-ttu-id="9fc46-121">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc46-121">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="9fc46-122">**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-122">From the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  

3. <span data-ttu-id="9fc46-123">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リストで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9fc46-123">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential  type** drop-down list, do one of the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9fc46-124">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要があります Windows 認証を使用して SQL Server に接続する場合[SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-124">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   |  <span data-ttu-id="9fc46-125">このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fc46-125">Click this</span></span>  |                                                                                                                                                               <span data-ttu-id="9fc46-126">目的</span><span class="sxs-lookup"><span data-stu-id="9fc46-126">To do this</span></span>                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   <span data-ttu-id="9fc46-127">**なし**</span><span class="sxs-lookup"><span data-stu-id="9fc46-127">**None**</span></span>   |                                                                                                                                         <span data-ttu-id="9fc46-128">Windows 認証を使用して、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-128">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="9fc46-129">**Windows**</span><span class="sxs-lookup"><span data-stu-id="9fc46-129">**Windows**</span></span>  |                                                                                                                                         <span data-ttu-id="9fc46-130">Windows 認証を使用して、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-130">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="9fc46-131">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="9fc46-131">**Username**</span></span> | <span data-ttu-id="9fc46-132">ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-132">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="9fc46-133">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9fc46-133">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="9fc46-134">**注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白、アダプターが Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-134">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span> |


4. <span data-ttu-id="9fc46-135">をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-135">Click the **URI Properties** tab, and then specify values for the connection parameters.</span></span> <span data-ttu-id="9fc46-136">接続 URI の詳細についてはの[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="9fc46-136">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9fc46-137">接続パラメーターに予約済みの文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="9fc46-137">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="9fc46-138">ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc46-138">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="9fc46-139">[URI のプロパティ] タブで値を指定しないと、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] により URI が `mssql://.//` になります。</span><span class="sxs-lookup"><span data-stu-id="9fc46-139">If you do not specify any values in the URI property tab, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puts the URI as `mssql://.//`.</span></span> <span data-ttu-id="9fc46-140">このような場合、アダプターは既定のデータベースと、ローカル コンピューター上の既定のデータベース インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-140">In such a case, the adapter connects to the default database and the default database instance on the local computer.</span></span>  

5. <span data-ttu-id="9fc46-141">をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-141">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span>  

6. <span data-ttu-id="9fc46-142">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fc46-142">Click **OK**.</span></span>  

7. <span data-ttu-id="9fc46-143">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fc46-143">Click **Connect**.</span></span> <span data-ttu-id="9fc46-144">接続が確立されると、接続の状態が表示として**接続**します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-144">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="9fc46-145">次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。</span><span class="sxs-lookup"><span data-stu-id="9fc46-145">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="9fc46-146">![SQL Server に接続](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span><span class="sxs-lookup"><span data-stu-id="9fc46-146">![Connect to SQL Server](../../adapters-and-accelerators/adapter-sql/media/661adb8a-5050-44d5-8db8-fdf0fe530b40.gif "661adb8a-5050-44d5-8db8-fdf0fe530b40")</span></span>  

    <span data-ttu-id="9fc46-147">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SQL Server で実行できるさまざまな操作を含む別のノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc46-147">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on SQL Server.</span></span> <span data-ttu-id="9fc46-148">たとえば、**プロシージャ**ノードに接続されているデータベースに使用できるすべてのプロシージャが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9fc46-148">For example, the **Procedures** node contains all the procedures available for the database you connected to.</span></span> <span data-ttu-id="9fc46-149">同様に、**テーブル**ノードに接続して、データベースとテーブルで実行できる操作のすべてのテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9fc46-149">Similarly, the **Tables** node contains all the tables in the database you connected to, and the operations that can be performed on a table.</span></span> <span data-ttu-id="9fc46-150">これらのノードの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-150">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="9fc46-151">参照</span><span class="sxs-lookup"><span data-stu-id="9fc46-151">See Also</span></span>  
 [<span data-ttu-id="9fc46-152">Consume Adapter Service アドインを使用して Visual Studio での SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="9fc46-152">Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in</span></span>](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)
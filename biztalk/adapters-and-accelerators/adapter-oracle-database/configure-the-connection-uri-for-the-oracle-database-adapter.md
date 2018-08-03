---
title: Oracle データベース アダプターの接続 URI の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at design time
- connection URI, specifying at run time
ms.assetid: 9f302b67-0bcc-44d1-9517-10d402873540
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 849adf16faa96726fb3d182930be8f4965eb180d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007211"
---
# <a name="configure-the-connection-uri-for-the-oracle-database-adapter"></a><span data-ttu-id="d8c01-102">Oracle データベース アダプターの接続 URI の構成します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-102">Configure the connection URI for the Oracle Database adapter</span></span>
<span data-ttu-id="d8c01-103">接続 URI は、Oracle データベースへの接続に必要なパラメーターを含む接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="d8c01-103">A connection URI is a connection string that contains parameters required to connect to the Oracle database.</span></span> <span data-ttu-id="d8c01-104">使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]で[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する Oracle データベースに接続する URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c01-104">While using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the URI to connect to the Oracle database to generate the metadata.</span></span> <span data-ttu-id="d8c01-105">使用して、オーケストレーションを構成するときに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、操作を実行する Oracle データベースに接続する URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c01-105">While configuring an orchestration using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the URI to connect to the Oracle database to perform operations.</span></span>  

## <a name="specifying-the-connection-uri-from-visual-studio"></a><span data-ttu-id="d8c01-106">接続を Visual Studio から URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-106">Specifying the Connection URI from Visual Studio</span></span>  
 <span data-ttu-id="d8c01-107">Visual studio を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-107">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-specify-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="d8c01-108">Consume Adapter Service アドインを使用して接続 URI を指定するには</span><span class="sxs-lookup"><span data-stu-id="d8c01-108">To specify the Connection URI using Consume Adapter Service Add-in</span></span>  

1. <span data-ttu-id="d8c01-109">BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-109">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="d8c01-110">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d8c01-110">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="d8c01-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8c01-111">Use this</span></span>    |             <span data-ttu-id="d8c01-112">目的</span><span class="sxs-lookup"><span data-stu-id="d8c01-112">To do this</span></span>             |
   |----------------|------------------------------------|
   | <span data-ttu-id="d8c01-113">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="d8c01-113">**Categories**</span></span> | <span data-ttu-id="d8c01-114">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-114">Click **Consume Adapter Service**.</span></span> |
   | <span data-ttu-id="d8c01-115">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="d8c01-115">**Templates**</span></span>  | <span data-ttu-id="d8c01-116">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-116">Click **Consume Adapter Service**.</span></span> |


3. <span data-ttu-id="d8c01-117">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-117">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4. <span data-ttu-id="d8c01-118">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleDBBinding**、 をクリック**構成**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-118">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and click **Configure**.</span></span>  

5. <span data-ttu-id="d8c01-119">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-119">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  

   -   <span data-ttu-id="d8c01-120">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-120">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

   -   <span data-ttu-id="d8c01-121">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-121">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

6. <span data-ttu-id="d8c01-122">をクリックして、 **URI プロパティ**タブをクリックし、さまざまなパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-122">Click the **URI Properties** tab, and specify values for different parameters.</span></span> <span data-ttu-id="d8c01-123">接続 URI の詳細についてはの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="d8c01-123">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  

7. <span data-ttu-id="d8c01-124">をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。</span><span class="sxs-lookup"><span data-stu-id="d8c01-124">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="d8c01-125">バインド プロパティの詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-125">For more information about binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  

8. <span data-ttu-id="d8c01-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8c01-126">Click **OK**.</span></span>  

#### <a name="to-specify-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="d8c01-127">アダプター メタデータの追加ウィザードを使用して接続 URI を指定するには</span><span class="sxs-lookup"><span data-stu-id="d8c01-127">To specify the Connection URI using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="d8c01-128">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-128">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="d8c01-129">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d8c01-129">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="d8c01-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8c01-130">Use this</span></span>    |           <span data-ttu-id="d8c01-131">目的</span><span class="sxs-lookup"><span data-stu-id="d8c01-131">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="d8c01-132">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="d8c01-132">**Categories**</span></span> |     <span data-ttu-id="d8c01-133">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-133">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="d8c01-134">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="d8c01-134">**Templates**</span></span>  | <span data-ttu-id="d8c01-135">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-135">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="d8c01-136">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8c01-136">Click **Add**.</span></span> <span data-ttu-id="d8c01-137">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8c01-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="d8c01-138">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、 **Wcf-oracledb**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-138">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleDB**.</span></span> <span data-ttu-id="d8c01-139">コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="d8c01-139">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="d8c01-140">BizTalk で構成された Wcf-oracledb ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="d8c01-140">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="d8c01-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8c01-141">Click **Next**.</span></span>  

6. <span data-ttu-id="d8c01-142">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleDBBinding**、順にクリックします**構成**.</span><span class="sxs-lookup"><span data-stu-id="d8c01-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="d8c01-143">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**] タブとの間、**クライアント資格情報の種類**一覧で、[**ユーザー名**とユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-143">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  

   -   <span data-ttu-id="d8c01-144">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-144">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

   -   <span data-ttu-id="d8c01-145">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-145">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

8. <span data-ttu-id="d8c01-146">をクリックして、 **URI プロパティ**タブをクリックし、さまざまなパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-146">Click the **URI Properties** tab, and specify values for different parameters.</span></span> <span data-ttu-id="d8c01-147">接続 URI の詳細についてはの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="d8c01-147">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  

9. <span data-ttu-id="d8c01-148">をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。</span><span class="sxs-lookup"><span data-stu-id="d8c01-148">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="d8c01-149">バインド プロパティの詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-149">For more information about binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  

10. <span data-ttu-id="d8c01-150">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8c01-150">Click **OK**.</span></span>  

## <a name="specifying-the-connection-uri-from-the-biztalk-server-administration-console"></a><span data-ttu-id="d8c01-151">接続を BizTalk Server 管理コンソールから URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-151">Specifying the Connection URI from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="d8c01-152">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracledb ポートの構成の一部として、資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c01-152">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the credentials as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  

#### <a name="to-specify-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="d8c01-153">WCF カスタム ポートの接続 URI を指定するには</span><span class="sxs-lookup"><span data-stu-id="d8c01-153">To specify the Connection URI for the WCF-Custom Port</span></span>  

1. <span data-ttu-id="d8c01-154">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d8c01-154">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="d8c01-155">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-155">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="d8c01-156">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8c01-156">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="d8c01-157">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-157">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="d8c01-158">送信ポートので、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、 をクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d8c01-158">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="d8c01-159">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-159">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  

       -   <span data-ttu-id="d8c01-160">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-160">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

       -   <span data-ttu-id="d8c01-161">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-161">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

   -   <span data-ttu-id="d8c01-162">選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-162">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

5. <span data-ttu-id="d8c01-163">受信ポートので、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他** タブで、次のいずれかを実行し、。</span><span class="sxs-lookup"><span data-stu-id="d8c01-163">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="d8c01-164">選択**ユーザー アカウント**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-164">Select **User account** option, and specify the user name and password to connect to an Oracle database.</span></span>  

       -   <span data-ttu-id="d8c01-165">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-165">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

       -   <span data-ttu-id="d8c01-166">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-166">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

   -   <span data-ttu-id="d8c01-167">選択**関連アプリケーションから資格情報を Get**オプション、および関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-167">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  

6. <span data-ttu-id="d8c01-168">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8c01-168">Click **OK**.</span></span>  

#### <a name="to-specify-the-connection-uri-for-the-wcf-oracledb-port"></a><span data-ttu-id="d8c01-169">Wcf-oracledb ポートの接続 URI を指定するには</span><span class="sxs-lookup"><span data-stu-id="d8c01-169">To specify the Connection URI for the WCF-OracleDB port</span></span>  

1. <span data-ttu-id="d8c01-170">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d8c01-170">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="d8c01-171">Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d8c01-171">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d8c01-172">手順については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-172">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="d8c01-173">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-173">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="d8c01-174">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8c01-174">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="d8c01-175">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-oracledb**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-175">In the port properties dialog box, from the **Type** drop-down list, select **WCF-OracleDB**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d8c01-176">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-176">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="d8c01-177">ポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブ。**バインドの種類**ドロップダウン リストで、 **oracleDBBinding**します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-177">In the port properties dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  

6. <span data-ttu-id="d8c01-178">トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合は、クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d8c01-178">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="d8c01-179">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-179">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the Oracle database.</span></span>  

       -   <span data-ttu-id="d8c01-180">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-180">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

       -   <span data-ttu-id="d8c01-181">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-181">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

   -   <span data-ttu-id="d8c01-182">選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-182">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

7. <span data-ttu-id="d8c01-183">トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d8c01-183">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="d8c01-184">選択**ユーザー アカウント**オプション、およびユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-184">Select **User account** option, and specify the user name and password to connect to the Oracle database.</span></span>  

       -   <span data-ttu-id="d8c01-185">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-185">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  

       -   <span data-ttu-id="d8c01-186">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="d8c01-186">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

   -   <span data-ttu-id="d8c01-187">選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-187">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

8. <span data-ttu-id="d8c01-188">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8c01-188">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d8c01-189">参照</span><span class="sxs-lookup"><span data-stu-id="d8c01-189">See Also</span></span>  
<span data-ttu-id="d8c01-190">[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="d8c01-190">[Building Blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span></span>  
 [<span data-ttu-id="d8c01-191">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="d8c01-191">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)
---
title: "アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle データベースへの接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 726b3f82-887c-407a-bb9f-dcb9443155b0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbf023a306e7caabeb3e207f90831167f46e8009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-database-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="5f17d-102">アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-102">Connect to Oracle Database in Visual Studio using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="5f17d-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] BizTalk アダプターとしても公開されると、そのため、使用することができます、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプターを使用して Oracle データベースに対して実行する操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is also exposed as a BizTalk adapter and, therefore, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on the Oracle database using the adapter.</span></span>  
  
 <span data-ttu-id="5f17d-104">このトピックでは、使用する方法の説明、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-104">This topic provides instructions on how to use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
## <a name="connecting-to-an-oracle-database-using-the-add-adapter-metadata-wizard"></a><span data-ttu-id="5f17d-105">Oracle に接続するデータベースを使用して、アダプター メタデータのウィザードの追加</span><span class="sxs-lookup"><span data-stu-id="5f17d-105">Connecting to an Oracle Database Using the Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="5f17d-106">使用して Oracle データベースへの接続には、次の手順を実行、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-106">Perform the following steps to connect to an Oracle database using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-connect-to-an-oracle-database"></a><span data-ttu-id="5f17d-107">Oracle データベースに接続するには</span><span class="sxs-lookup"><span data-stu-id="5f17d-107">To connect to an Oracle database</span></span>  
  
1.  <span data-ttu-id="5f17d-108">使用して接続する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="5f17d-108">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="5f17d-109">ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-109">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    2.  <span data-ttu-id="5f17d-110">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-110">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="5f17d-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5f17d-111">Use this</span></span>|<span data-ttu-id="5f17d-112">目的</span><span class="sxs-lookup"><span data-stu-id="5f17d-112">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="5f17d-113">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="5f17d-113">**Categories**</span></span>|<span data-ttu-id="5f17d-114">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-114">Click **Add Adapter**.</span></span>|  
        |<span data-ttu-id="5f17d-115">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="5f17d-115">**Templates**</span></span>|<span data-ttu-id="5f17d-116">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-116">Click **Add Adapter Metadata**.</span></span>|  
  
    3.  <span data-ttu-id="5f17d-117">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f17d-117">Click **Add**.</span></span> <span data-ttu-id="5f17d-118">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f17d-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
    4.  <span data-ttu-id="5f17d-119">アダプター メタデータの追加ウィザードで選択**Wcf-oracledb**です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-119">In the Add Adapter Metadata Wizard, select **WCF-OracleDB**.</span></span> <span data-ttu-id="5f17d-120">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="5f17d-120">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="5f17d-121">BizTalk で構成された Wcf-oracledb ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-121">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
    5.  <span data-ttu-id="5f17d-122">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f17d-122">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="5f17d-123">**バインディングを選択**ドロップダウン リスト、選択**oracleDBBinding**  をクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-123">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="5f17d-124">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  
  
    1.  <span data-ttu-id="5f17d-125">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="5f17d-125">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="5f17d-126">ユーザー名と Oracle データベースへの接続にパスワードを指定するときに、次の考慮事項に従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-126">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  
  
        -   <span data-ttu-id="5f17d-127">**ユーザー名**です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-127">**User name**.</span></span> <span data-ttu-id="5f17d-128">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときに、ユーザー名を入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="5f17d-129">Oracle データベースでユーザー名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-129">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="5f17d-130">Oracle ユーザー名を指定することを確認する必要があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。</span><span class="sxs-lookup"><span data-stu-id="5f17d-130">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="5f17d-131">通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります:"SCOTT"です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-131">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  
  
        -   <span data-ttu-id="5f17d-132">**パスワード**です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-132">**Password**.</span></span> <span data-ttu-id="5f17d-133">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-133">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="5f17d-134">リリース 10 g、前の Oracle システム上のパスワードは大文字小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="5f17d-134">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  
  
    2.  <span data-ttu-id="5f17d-135">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-135">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
4.  <span data-ttu-id="5f17d-136">クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-136">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="5f17d-137">詳細については、接続 URI の[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI を作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-137">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
5.  <span data-ttu-id="5f17d-138">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-138">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="5f17d-139">たとえば、POLLINGSTMT 操作の対象とする場合は、設定する必要あります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5f17d-139">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="5f17d-140">バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-140">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="5f17d-141">アダプター メタデータの追加ウィザードを使用してメタデータを生成して、選択した場合は、既存の Wcf-oracledb 送信ポートをバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f17d-141">If you are generating metadata using Add Adapter Metadata Wizard and you selected an existing WCF-OracleDB send port, you need not specify the binding properties.</span></span> <span data-ttu-id="5f17d-142">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="5f17d-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="5f17d-143">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f17d-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="5f17d-144">このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f17d-144">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="5f17d-145">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="5f17d-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
6.  <span data-ttu-id="5f17d-146">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f17d-146">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="5f17d-147">**[接続]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f17d-147">Click **Connect**.</span></span> <span data-ttu-id="5f17d-148">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="5f17d-148">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="5f17d-149">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="5f17d-149">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="5f17d-150">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="5f17d-150">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f17d-151">参照</span><span class="sxs-lookup"><span data-stu-id="5f17d-151">See Also</span></span>  
 <span data-ttu-id="5f17d-152">[アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span><span class="sxs-lookup"><span data-stu-id="5f17d-152">[Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span></span>  
 [<span data-ttu-id="5f17d-153">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="5f17d-153">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)
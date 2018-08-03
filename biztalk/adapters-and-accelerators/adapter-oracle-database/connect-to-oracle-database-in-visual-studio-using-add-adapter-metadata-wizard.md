---
title: アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle データベースへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 726b3f82-887c-407a-bb9f-dcb9443155b0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe5ebb085055307730f65cd36fea29f68deeccf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996539"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-add-adapter-metadata-wizard"></a><span data-ttu-id="5ce24-102">アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-102">Connect to Oracle Database in Visual Studio using Add Adapter Metadata Wizard</span></span>
<span data-ttu-id="5ce24-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] BizTalk アダプターとしても公開されると、そのため、使用することができます、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプターを使用して Oracle データベースで実行する操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is also exposed as a BizTalk adapter and, therefore, you can use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate schema for the operations you want to perform on the Oracle database using the adapter.</span></span>  

 <span data-ttu-id="5ce24-104">このトピックでは、手順を使用する方法には、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-104">This topic provides instructions on how to use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

## <a name="connecting-to-an-oracle-database-using-the-add-adapter-metadata-wizard"></a><span data-ttu-id="5ce24-105">Oracle に接続するデータベースを使用して、アダプター メタデータのウィザードの追加</span><span class="sxs-lookup"><span data-stu-id="5ce24-105">Connecting to an Oracle Database Using the Add Adapter Metadata Wizard</span></span>  
 <span data-ttu-id="5ce24-106">使用して Oracle データベースに接続するには、次の手順を実行、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-106">Perform the following steps to connect to an Oracle database using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-connect-to-an-oracle-database"></a><span data-ttu-id="5ce24-107">Oracle データベースに接続するには</span><span class="sxs-lookup"><span data-stu-id="5ce24-107">To connect to an Oracle database</span></span>  

1. <span data-ttu-id="5ce24-108">使用して接続する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="5ce24-108">To connect using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="5ce24-109">ソリューション エクスプ ローラーでプロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-109">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   2. <span data-ttu-id="5ce24-110">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5ce24-110">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="5ce24-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5ce24-111">Use this</span></span>    |           <span data-ttu-id="5ce24-112">目的</span><span class="sxs-lookup"><span data-stu-id="5ce24-112">To do this</span></span>            |
      |----------------|---------------------------------|
      | <span data-ttu-id="5ce24-113">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="5ce24-113">**Categories**</span></span> |     <span data-ttu-id="5ce24-114">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-114">Click **Add Adapter**.</span></span>      |
      | <span data-ttu-id="5ce24-115">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="5ce24-115">**Templates**</span></span>  | <span data-ttu-id="5ce24-116">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-116">Click **Add Adapter Metadata**.</span></span> |


   3. <span data-ttu-id="5ce24-117">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce24-117">Click **Add**.</span></span> <span data-ttu-id="5ce24-118">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ce24-118">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

   4. <span data-ttu-id="5ce24-119">アダプター メタデータの追加ウィザードで選択**Wcf-oracledb**します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-119">In the Add Adapter Metadata Wizard, select **WCF-OracleDB**.</span></span> <span data-ttu-id="5ce24-120">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="5ce24-120">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

      > [!IMPORTANT]
      >  <span data-ttu-id="5ce24-121">BizTalk で構成された Wcf-oracledb ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="5ce24-121">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  

   5. <span data-ttu-id="5ce24-122">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce24-122">Click **Next**.</span></span>  

2. <span data-ttu-id="5ce24-123">**バインディングを選択**ドロップダウン リスト、選択**oracleDBBinding**  をクリック**構成**します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-123">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  

3. <span data-ttu-id="5ce24-124">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-124">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  

   1. <span data-ttu-id="5ce24-125">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="5ce24-125">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="5ce24-126">ユーザー名と Oracle データベースに接続するためのパスワードを指定するときに、次の考慮事項に従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-126">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  

      - <span data-ttu-id="5ce24-127">**ユーザー名**します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-127">**User name**.</span></span> <span data-ttu-id="5ce24-128">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにユーザー名を入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="5ce24-129">Oracle データベースでのユーザー名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-129">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="5ce24-130">Oracle ユーザー名を指定することを確認してください、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。</span><span class="sxs-lookup"><span data-stu-id="5ce24-130">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="5ce24-131">通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります。"SCOTT"。</span><span class="sxs-lookup"><span data-stu-id="5ce24-131">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  

      - <span data-ttu-id="5ce24-132">**パスワード**します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-132">**Password**.</span></span> <span data-ttu-id="5ce24-133">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-133">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="5ce24-134">リリース 10 g、前の Oracle システム上のパスワードは大文字小文字を区別しない.</span><span class="sxs-lookup"><span data-stu-id="5ce24-134">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  

   2. <span data-ttu-id="5ce24-135">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="5ce24-135">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

4. <span data-ttu-id="5ce24-136">をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-136">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="5ce24-137">接続 URI の詳細についてはの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="5ce24-137">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  

5. <span data-ttu-id="5ce24-138">をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-138">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="5ce24-139">たとえば、POLLINGSTMT 操作の対象とする場合は、する必要があります設定、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5ce24-139">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="5ce24-140">バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-140">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>

   > [!NOTE]
   >  <span data-ttu-id="5ce24-141">アダプター メタデータの追加ウィザードを使用してメタデータを生成して、選択した場合は、既存の Wcf-oracledb 送信ポート、バインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ce24-141">If you are generating metadata using Add Adapter Metadata Wizard and you selected an existing WCF-OracleDB send port, you need not specify the binding properties.</span></span> <span data-ttu-id="5ce24-142">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="5ce24-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="5ce24-143">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5ce24-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="5ce24-144">このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ce24-144">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="5ce24-145">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="5ce24-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

6. <span data-ttu-id="5ce24-146">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce24-146">Click **OK**.</span></span>  

7. <span data-ttu-id="5ce24-147">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ce24-147">Click **Connect**.</span></span> <span data-ttu-id="5ce24-148">接続が確立されると、接続の状態が表示として**接続**します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-148">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="5ce24-149">次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。</span><span class="sxs-lookup"><span data-stu-id="5ce24-149">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="5ce24-150">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="5ce24-150">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  

## <a name="see-also"></a><span data-ttu-id="5ce24-151">参照</span><span class="sxs-lookup"><span data-stu-id="5ce24-151">See Also</span></span>  
 <span data-ttu-id="5ce24-152">[アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span><span class="sxs-lookup"><span data-stu-id="5ce24-152">[Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span></span>  
 [<span data-ttu-id="5ce24-153">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="5ce24-153">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)
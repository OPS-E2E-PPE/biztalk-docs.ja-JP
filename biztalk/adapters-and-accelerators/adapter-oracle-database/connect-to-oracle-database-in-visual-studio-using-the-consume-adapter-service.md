---
title: アダプター サービスを使用して Visual Studio での Oracle データベースへの接続 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting, to the Oracle database
- connection, to the Oracle database
ms.assetid: db2789d0-2d61-472b-ad0c-4ef0707e9c64
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9ecd6867776b8adf918f901369f526bc0479bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215106"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service"></a><span data-ttu-id="f1154-102">アダプター サービスを使用して Visual Studio での Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="f1154-102">Connect to Oracle Database in Visual Studio using the Consume Adapter Service</span></span>
<span data-ttu-id="f1154-103">アダプター サービスのアドインがインストールされている WCF LOB Adapter SDK をインストールするときにします。</span><span class="sxs-lookup"><span data-stu-id="f1154-103">The Consume Adapter Service Add-in is installed when you install WCF LOB Adapter SDK.</span></span> <span data-ttu-id="f1154-104">アダプター サービスの追加のコンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f1154-104">The Consume Adapter Service Add-in loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="f1154-105">WCF ベースを使用して Oracle データベースへの接続に[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]BizTalk プロジェクトで使用する必要があります、 **oracleDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="f1154-105">To connect to the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in a BizTalk project, you must use the **oracleDBBinding**.</span></span>  
  
 <span data-ttu-id="f1154-106">このトピックでは、アダプター サービスの追加で使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1154-106">This topic provides instructions on how to use the Consume Adapter Service Add-in.</span></span>  
  
## <a name="connecting-to-an-oracle-database-using-the-consume-adapter-service-add-in"></a><span data-ttu-id="f1154-107">Oracle に接続するデータベースを使用して、アダプターを使用する追加のサービスの</span><span class="sxs-lookup"><span data-stu-id="f1154-107">Connecting to an Oracle Database Using the Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="f1154-108">使用して Oracle データベースへの接続には、次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f1154-108">Perform the following steps to connect to an Oracle database using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="f1154-109">使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="f1154-109">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  
  
    1.  <span data-ttu-id="f1154-110">ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="f1154-110">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
    2.  <span data-ttu-id="f1154-111">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f1154-111">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="f1154-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1154-112">Use this</span></span>|<span data-ttu-id="f1154-113">目的</span><span class="sxs-lookup"><span data-stu-id="f1154-113">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="f1154-114">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="f1154-114">**Categories**</span></span>|<span data-ttu-id="f1154-115">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="f1154-115">Click **Consume Adapter Service**.</span></span>|  
        |<span data-ttu-id="f1154-116">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="f1154-116">**Templates**</span></span>|<span data-ttu-id="f1154-117">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="f1154-117">Click **Consume Adapter Service**.</span></span>|  
  
    3.  <span data-ttu-id="f1154-118">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1154-118">Click **Add**.</span></span> <span data-ttu-id="f1154-119">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1154-119">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  
  
2.  <span data-ttu-id="f1154-120">**バインディングを選択**ドロップダウン リスト、選択**oracleDBBinding**  をクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f1154-120">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="f1154-121">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1154-121">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  
  
    1.  <span data-ttu-id="f1154-122">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="f1154-122">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="f1154-123">ユーザー名と Oracle データベースへの接続にパスワードを指定するときに、次の考慮事項に従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1154-123">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  
  
        -   <span data-ttu-id="f1154-124">**ユーザー名**です。</span><span class="sxs-lookup"><span data-stu-id="f1154-124">**User name**.</span></span> <span data-ttu-id="f1154-125">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときに、ユーザー名を入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="f1154-125">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="f1154-126">Oracle データベースでユーザー名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="f1154-126">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="f1154-127">Oracle ユーザー名を指定することを確認する必要があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。</span><span class="sxs-lookup"><span data-stu-id="f1154-127">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="f1154-128">通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります:"SCOTT"です。</span><span class="sxs-lookup"><span data-stu-id="f1154-128">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  
  
        -   <span data-ttu-id="f1154-129">**パスワード**です。</span><span class="sxs-lookup"><span data-stu-id="f1154-129">**Password**.</span></span> <span data-ttu-id="f1154-130">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]が Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="f1154-130">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="f1154-131">リリース 10 g、前の Oracle システム上のパスワードは大文字小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="f1154-131">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  
  
    2.  <span data-ttu-id="f1154-132">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="f1154-132">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
4.  <span data-ttu-id="f1154-133">クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1154-133">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="f1154-134">詳細については、接続 URI の[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI を作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1154-134">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
5.  <span data-ttu-id="f1154-135">クリックして、**バインド プロパティ**タブをクリックし、対象となる操作で、必要な場合、バインド プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1154-135">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="f1154-136">たとえば、POLLINGSTMT 操作の対象とする場合は、設定する必要あります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="f1154-136">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="f1154-137">バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1154-137">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
6.  <span data-ttu-id="f1154-138">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1154-138">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="f1154-139">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1154-139">Click **Connect**.</span></span> <span data-ttu-id="f1154-140">接続が確立されると、接続状態は表示**接続**です。</span><span class="sxs-lookup"><span data-stu-id="f1154-140">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="f1154-141">次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後にすぐにします。</span><span class="sxs-lookup"><span data-stu-id="f1154-141">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="f1154-142">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="f1154-142">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1154-143">参照</span><span class="sxs-lookup"><span data-stu-id="f1154-143">See Also</span></span>  
 <span data-ttu-id="f1154-144">[アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span><span class="sxs-lookup"><span data-stu-id="f1154-144">[Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span></span>  
 [<span data-ttu-id="f1154-145">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="f1154-145">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)
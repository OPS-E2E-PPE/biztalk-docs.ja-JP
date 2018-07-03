---
title: Consume Adapter Service を使用して Visual Studio での Oracle データベースへの接続 |Microsoft Docs
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
ms.openlocfilehash: 19e83b518e188528b357e52f6397045baeb3ed76
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010481"
---
# <a name="connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service"></a><span data-ttu-id="8be6d-102">Consume Adapter Service を使用して Visual Studio での Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-102">Connect to Oracle Database in Visual Studio using the Consume Adapter Service</span></span>
<span data-ttu-id="8be6d-103">Consume Adapter Service アドインがインストールされている WCF LOB Adapter SDK をインストールするときにします。</span><span class="sxs-lookup"><span data-stu-id="8be6d-103">The Consume Adapter Service Add-in is installed when you install WCF LOB Adapter SDK.</span></span> <span data-ttu-id="8be6d-104">Consume Adapter Service アドインをコンピューターにインストールされているすべての WCF カスタム バインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8be6d-104">The Consume Adapter Service Add-in loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="8be6d-105">WCF ベースを使用して Oracle データベースへの接続に[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]BizTalk プロジェクトで使用する必要があります、 **oracleDBBinding**します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-105">To connect to the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in a BizTalk project, you must use the **oracleDBBinding**.</span></span>  

 <span data-ttu-id="8be6d-106">このトピックでは、Consume Adapter Service アドインを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-106">This topic provides instructions on how to use the Consume Adapter Service Add-in.</span></span>  

## <a name="connecting-to-an-oracle-database-using-the-consume-adapter-service-add-in"></a><span data-ttu-id="8be6d-107">Oracle への接続を使用してデータベース、アダプターを使用する追加のサービス</span><span class="sxs-lookup"><span data-stu-id="8be6d-107">Connecting to an Oracle Database Using the Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="8be6d-108">使用して Oracle データベースに接続するには、次の手順を実行、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-108">Perform the following steps to connect to an Oracle database using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  

1. <span data-ttu-id="8be6d-109">使用して接続する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションで。</span><span class="sxs-lookup"><span data-stu-id="8be6d-109">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="8be6d-110">ソリューション エクスプ ローラーでプロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-110">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   2. <span data-ttu-id="8be6d-111">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8be6d-111">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="8be6d-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8be6d-112">Use this</span></span>    |             <span data-ttu-id="8be6d-113">目的</span><span class="sxs-lookup"><span data-stu-id="8be6d-113">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="8be6d-114">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="8be6d-114">**Categories**</span></span> | <span data-ttu-id="8be6d-115">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-115">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="8be6d-116">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="8be6d-116">**Templates**</span></span>  | <span data-ttu-id="8be6d-117">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-117">Click **Consume Adapter Service**.</span></span> |


   3. <span data-ttu-id="8be6d-118">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8be6d-118">Click **Add**.</span></span> <span data-ttu-id="8be6d-119">[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8be6d-119">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="8be6d-120">**バインディングを選択**ドロップダウン リスト、選択**oracleDBBinding**  をクリック**構成**します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-120">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  

3. <span data-ttu-id="8be6d-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-121">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  

   1. <span data-ttu-id="8be6d-122">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="8be6d-122">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="8be6d-123">ユーザー名と Oracle データベースに接続するためのパスワードを指定するときに、次の考慮事項に従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-123">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  

      - <span data-ttu-id="8be6d-124">**ユーザー名**します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-124">**User name**.</span></span> <span data-ttu-id="8be6d-125">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにユーザー名を入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-125">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="8be6d-126">Oracle データベースでのユーザー名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-126">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="8be6d-127">Oracle ユーザー名を指定することを確認してください、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。</span><span class="sxs-lookup"><span data-stu-id="8be6d-127">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="8be6d-128">通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります。"SCOTT"。</span><span class="sxs-lookup"><span data-stu-id="8be6d-128">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  

      - <span data-ttu-id="8be6d-129">**パスワード**します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-129">**Password**.</span></span> <span data-ttu-id="8be6d-130">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-130">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="8be6d-131">リリース 10 g、前の Oracle システム上のパスワードは大文字小文字を区別しない.</span><span class="sxs-lookup"><span data-stu-id="8be6d-131">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  

   2. <span data-ttu-id="8be6d-132">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="8be6d-132">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  

4. <span data-ttu-id="8be6d-133">をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-133">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="8be6d-134">接続 URI の詳細についてはの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="8be6d-134">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  

5. <span data-ttu-id="8be6d-135">をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-135">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="8be6d-136">たとえば、POLLINGSTMT 操作の対象とする場合は、する必要があります設定、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="8be6d-136">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="8be6d-137">バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-137">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  

6. <span data-ttu-id="8be6d-138">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8be6d-138">Click **OK**.</span></span>  

7. <span data-ttu-id="8be6d-139">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8be6d-139">Click **Connect**.</span></span> <span data-ttu-id="8be6d-140">接続が確立されると、接続の状態が表示として**接続**します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-140">After the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="8be6d-141">次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。</span><span class="sxs-lookup"><span data-stu-id="8be6d-141">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="8be6d-142">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="8be6d-142">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  

## <a name="see-also"></a><span data-ttu-id="8be6d-143">参照</span><span class="sxs-lookup"><span data-stu-id="8be6d-143">See Also</span></span>  
 <span data-ttu-id="8be6d-144">[アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span><span class="sxs-lookup"><span data-stu-id="8be6d-144">[Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-db-in-visual-studio-using-the-add-adapter-service.md) </span></span>  
 [<span data-ttu-id="8be6d-145">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="8be6d-145">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)
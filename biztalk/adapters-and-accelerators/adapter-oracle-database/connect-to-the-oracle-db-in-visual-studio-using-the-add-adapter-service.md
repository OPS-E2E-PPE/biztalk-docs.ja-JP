---
title: アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93e56c1f-adee-4976-bc39-bb9b8102145e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06ae5d68ea1dcaced65d57b0f1a832588b5aeb11
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994147"
---
# <a name="connect-to-the-oracle-database-in-visual-studio-using-the-add-adapter-service-reference"></a><span data-ttu-id="678b8-102">アダプター サービス参照の追加を使用して Visual Studio での Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="678b8-102">Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference</span></span>
<span data-ttu-id="678b8-103">使用して Oracle データベースに接続するため、 [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] .NET プログラミング ソリューションでは、使用する必要があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="678b8-103">To connect to the Oracle database using the [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="678b8-104">このトピックでは、手順を使用する方法には、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="678b8-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connect-using-the-add-adapter-service-reference-plug-in"></a><span data-ttu-id="678b8-105">Add Adapter Service Reference プラグインを使用して接続します。</span><span class="sxs-lookup"><span data-stu-id="678b8-105">Connect using the Add Adapter Service Reference Plug-in</span></span>  
<span data-ttu-id="678b8-106">使用して Oracle データベースに接続するには、次の手順を完了、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="678b8-106">Complete the following steps to connect to an Oracle database using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>   

  
1. <span data-ttu-id="678b8-107">使用して接続する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]プログラミング ソリューション。</span><span class="sxs-lookup"><span data-stu-id="678b8-107">To connect using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] in a programming solution:</span></span>  
  
   1.  <span data-ttu-id="678b8-108">Visual Studio を使用してプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="678b8-108">Create a project using Visual Studio.</span></span>  
  
   2.  <span data-ttu-id="678b8-109">ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**アダプター サービス参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="678b8-109">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="678b8-110">Add Adapter Service Reference プラグインを開きます。</span><span class="sxs-lookup"><span data-stu-id="678b8-110">The Add Adapter Service Reference Plug-in opens.</span></span>  
  
2. <span data-ttu-id="678b8-111">**バインディングを選択**ドロップダウン リスト、選択**oracleDBBinding**  をクリック**構成**します。</span><span class="sxs-lookup"><span data-stu-id="678b8-111">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  
  
3. <span data-ttu-id="678b8-112">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Oracle データベースに接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="678b8-112">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  
  
   1. <span data-ttu-id="678b8-113">Oracle データベースの資格情報を使用して接続するでデータベースの資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="678b8-113">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="678b8-114">ユーザー名と Oracle データベースに接続するためのパスワードを指定するときに、次の考慮事項に従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="678b8-114">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  
  
      - <span data-ttu-id="678b8-115">**ユーザー名**します。</span><span class="sxs-lookup"><span data-stu-id="678b8-115">**User name**.</span></span> <span data-ttu-id="678b8-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにユーザー名を入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="678b8-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="678b8-117">Oracle データベースでのユーザー名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="678b8-117">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="678b8-118">Oracle ユーザー名を指定することを確認してください、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで想定されている場合。</span><span class="sxs-lookup"><span data-stu-id="678b8-118">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="678b8-119">通常、これは SCOTT/TIGER 資格情報にユーザー名は大文字である必要があります。"SCOTT"。</span><span class="sxs-lookup"><span data-stu-id="678b8-119">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  
  
      - <span data-ttu-id="678b8-120">**パスワード**します。</span><span class="sxs-lookup"><span data-stu-id="678b8-120">**Password**.</span></span> <span data-ttu-id="678b8-121">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースでの接続を開くときにパスワードを入力する値の大文字小文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="678b8-121">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="678b8-122">リリース 10 g、前の Oracle システム上のパスワードは大文字小文字を区別しない.</span><span class="sxs-lookup"><span data-stu-id="678b8-122">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  
  
   2. <span data-ttu-id="678b8-123">Windows 認証を使用して接続するには、入力**/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**空白テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="678b8-123">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
4. <span data-ttu-id="678b8-124">をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="678b8-124">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="678b8-125">接続 URI の詳細についてはの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="678b8-125">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
5. <span data-ttu-id="678b8-126">をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="678b8-126">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="678b8-127">たとえば、POLLINGSTMT 操作の対象とする場合は、する必要があります設定、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="678b8-127">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="678b8-128">バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="678b8-128">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
6. <span data-ttu-id="678b8-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="678b8-129">Click **OK**.</span></span>  
  
7. <span data-ttu-id="678b8-130">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="678b8-130">Click **Connect**.</span></span> <span data-ttu-id="678b8-131">接続が確立されると、接続の状態が表示として**接続**します。</span><span class="sxs-lookup"><span data-stu-id="678b8-131">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
    <span data-ttu-id="678b8-132">次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続が確立された後すぐにします。</span><span class="sxs-lookup"><span data-stu-id="678b8-132">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
    <span data-ttu-id="678b8-133">![アダプター サービスの使用 ダイアログ ボックスの接続](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="678b8-133">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678b8-134">参照</span><span class="sxs-lookup"><span data-stu-id="678b8-134">See Also</span></span>  
 <span data-ttu-id="678b8-135">[Visual Studio での Oracle データベースへの接続します。](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="678b8-135">[Connect to Oracle Database in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) </span></span>  
 [<span data-ttu-id="678b8-136">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="678b8-136">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)
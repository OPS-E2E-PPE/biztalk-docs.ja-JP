---
title: BizTalk の Wcf-oracledb アダプターを使用してポートを構成する |Microsoft ドキュメント
description: Wcf-oracledb 送信を作成し、BizTalk Server で Oracle DB アダプターを使用する受信ポート
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9eafefb-9b30-4801-9be9-6034ae0d3b7d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1e910d3a4d76444495de5ee4e20ada352a7a42b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215874"
---
# <a name="configure-a-port-using-the-wcf-oracledb-adapter"></a><span data-ttu-id="53fc7-103">Wcf-oracledb アダプターを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-103">Configure a port using the WCF-OracleDB adapter</span></span>
<span data-ttu-id="53fc7-104">Wcf-oracledb を構成する方法は、送信し、受信ポートを使用して Oracle データベースの送信および受信操作を実行する、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-104">How to configure WCF-OracleDB send and receive ports to perform outbound and inbound operations on the Oracle database using the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="53fc7-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="53fc7-105">Prerequisites</span></span>  
<span data-ttu-id="53fc7-106">メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="53fc7-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="53fc7-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span> 
  
## <a name="deploy-adapters-to-send-messages-to-oracle-database"></a><span data-ttu-id="53fc7-108">Oracle データベースにメッセージを送信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-108">Deploy adapters to send messages to Oracle Database</span></span>  
  
1.  <span data-ttu-id="53fc7-109">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="53fc7-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="53fc7-110">Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="53fc7-110">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="53fc7-111">手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-111">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="53fc7-112">コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-112">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="53fc7-113">展開するアプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-113">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
5.  <span data-ttu-id="53fc7-114">右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle データベース。</span><span class="sxs-lookup"><span data-stu-id="53fc7-114">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the Oracle database.</span></span>  
  
6.  <span data-ttu-id="53fc7-115">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-115">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7.  <span data-ttu-id="53fc7-116">**型**ドロップダウン リストが Wcf-oracledb を選択し、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-116">From the **Type** drop-down list, select WCF-OracleDB, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="53fc7-117">トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="53fc7-117">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="53fc7-118">をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-118">Click the **General** tab, click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="53fc7-119">接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-119">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="53fc7-120">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-120">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="53fc7-121">参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)各操作のアクションの一覧についてはします。</span><span class="sxs-lookup"><span data-stu-id="53fc7-121">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) for a list of actions for each operation.</span></span> <span data-ttu-id="53fc7-122">たとえば、Oracle データベースで HR スキーマ EMPLOYEE テーブルの挿入操作を呼び出すアクションは。</span><span class="sxs-lookup"><span data-stu-id="53fc7-122">For example, the action to invoke the Insert operation an EMPLOYEE table under the HR schema in an Oracle database is:</span></span>  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/HR/Table/EMPLOYEE/Select  
        ```  
  
    3.  <span data-ttu-id="53fc7-123">クリックして、**バインディング**タブによって公開されているバインドのプロパティを指定して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-123">Click the **Binding** tab and specify values for the binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="53fc7-124">バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-124">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
        > [!NOTE]
        >  <span data-ttu-id="53fc7-125">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53fc7-125">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="53fc7-126">たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="53fc7-126">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
    4.  <span data-ttu-id="53fc7-127">クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="53fc7-127">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
        -   <span data-ttu-id="53fc7-128">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-128">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
            -   <span data-ttu-id="53fc7-129">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="53fc7-129">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
            -   <span data-ttu-id="53fc7-130">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-130">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
        -   <span data-ttu-id="53fc7-131">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-131">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
    5.  <span data-ttu-id="53fc7-132">戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-132">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="53fc7-133">**送信ハンドラー**一覧で、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-133">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="53fc7-134">選択した場合**静的な一方向送信ポート**手順 5 で、送信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-134">If you chose **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="53fc7-135">**送信パイプライン**一覧で、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-135">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="53fc7-136">選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="53fc7-136">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="53fc7-137">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-137">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="53fc7-138">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-138">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
12. <span data-ttu-id="53fc7-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53fc7-139">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-oracle-database"></a><span data-ttu-id="53fc7-140">Oracle データベースからメッセージを受信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-140">Deploy adapters to receive messages from Oracle Database</span></span>  
  
1.  <span data-ttu-id="53fc7-141">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="53fc7-141">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="53fc7-142">Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="53fc7-142">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="53fc7-143">手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-143">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="53fc7-144">コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-144">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="53fc7-145">展開するアプリケーションを展開し、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-145">Expand the application under which you want to deploy the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
5.  <span data-ttu-id="53fc7-146">右クリック**受信ポート**、指す**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と Oracle データベース。</span><span class="sxs-lookup"><span data-stu-id="53fc7-146">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the Oracle database.</span></span>  
  
6.  <span data-ttu-id="53fc7-147">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-147">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7.  <span data-ttu-id="53fc7-148">**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-148">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="53fc7-149">**受信場所のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53fc7-149">The **Receive Location Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="53fc7-150">**受信場所のプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-150">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="53fc7-151">受信場所の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-151">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="53fc7-152">**型**ドロップダウン リストが Wcf-oracledb を選択し、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-152">From the **Type** drop-down list, select WCF-OracleDB, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="53fc7-153">トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="53fc7-153">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="53fc7-154">をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-154">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="53fc7-155">接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-155">For more information about the connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="53fc7-156">クリックして、**バインディング**タブによって公開されるプロパティのバインドを指定して、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-156">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="53fc7-157">バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-157">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
        > [!NOTE]
        >  <span data-ttu-id="53fc7-158">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53fc7-158">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="53fc7-159">たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="53fc7-159">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
    3.  <span data-ttu-id="53fc7-160">クリックして、**動作**タブは、トランザクション分離レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-160">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="53fc7-161">トランザクション分離レベルの設定の詳細については、次を参照してください。[トランザクション分離レベルとトランザクションのタイムアウト構成](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-161">For more information about setting transaction isolation level, see [Configure transaction isolation level and transaction timeout](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).</span></span>  
  
    4.  <span data-ttu-id="53fc7-162">クリックして、**他**タブをクリックし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-162">Click the **Others** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="53fc7-163">選択**ユーザー アカウント**オプション、およびユーザー名と、Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-163">Select **User account** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
            -   <span data-ttu-id="53fc7-164">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="53fc7-164">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
            -   <span data-ttu-id="53fc7-165">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-165">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
        -   <span data-ttu-id="53fc7-166">選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-166">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
    5.  <span data-ttu-id="53fc7-167">戻るには、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-167">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="53fc7-168">**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-168">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="53fc7-169">選択した場合**一方向の受信ポート**手順 5 で、受信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-169">If you chose **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="53fc7-170">**受信パイプライン**一覧で、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-170">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="53fc7-171">選択した場合**要求-応答受信ポート**手順 5 で、指定の送信および受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="53fc7-171">If you chose **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="53fc7-172">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-172">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="53fc7-173">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-173">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="53fc7-174">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-174">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="53fc7-175">**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="53fc7-175">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53fc7-176">参照</span><span class="sxs-lookup"><span data-stu-id="53fc7-176">See Also</span></span>  
   [<span data-ttu-id="53fc7-177">Oracle データベース アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-177">Manually configure a physical port binding to the Oracle Database Adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)
 
 [<span data-ttu-id="53fc7-178">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="53fc7-178">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)
---
title: "Biztalk WCF SQL アダプタを使用してポートを構成する |Microsoft ドキュメント"
description: "WCF-SQL 送信を作成し、BizTalk Server で SQL Server のアダプターを使用する受信ポート"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8cdc032-3160-43de-9510-7ca69506083e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a2ca9bda40aa016efba95b89948f1d12bc49f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-port-using-the-wcf-sql-adapter"></a><span data-ttu-id="e7377-103">WCF-SQL アダプターを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e7377-103">Configure a port using the WCF-SQL adapter</span></span>
<span data-ttu-id="e7377-104">このトピックでは、WCF SQL を構成する方法については送受信ポートを使用して SQL サーバーに送信および受信操作を実行する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e7377-104">This topic provides instructions on how to configure WCF-SQL send and receive ports to perform outbound and inbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e7377-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="e7377-105">Prerequisites</span></span>  
<span data-ttu-id="e7377-106">メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="e7377-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="e7377-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a><span data-ttu-id="e7377-108">SQL Server にメッセージを送信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="e7377-108">Deploy adapters to send messages to SQL Server</span></span>  
 <span data-ttu-id="e7377-109">使用して SQL サーバーにメッセージを送信するための WCF-SQL 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e7377-109">Perform the following steps to configure a WCF-SQL send port for sending messages to SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="e7377-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e7377-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="e7377-111">WCF-SQL アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e7377-111">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="e7377-112">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-112">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="e7377-113">コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="e7377-114">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e7377-114">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
5.  <span data-ttu-id="e7377-115">右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="e7377-115">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
6.  <span data-ttu-id="e7377-116">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7377-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7.  <span data-ttu-id="e7377-117">**型**ドロップダウン リストは、前に追加する WCF-SQL アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-117">From the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="e7377-118">トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7377-118">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="e7377-119">をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-119">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="e7377-120">詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-120">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="e7377-121">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="e7377-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="e7377-122">参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)各操作のアクションの一覧についてはします。</span><span class="sxs-lookup"><span data-stu-id="e7377-122">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) for a list of actions for each operation.</span></span> <span data-ttu-id="e7377-123">たとえば、SQL Server データベース内のテーブルに対する挿入操作を呼び出すアクションは。</span><span class="sxs-lookup"><span data-stu-id="e7377-123">For example, the action to invoke the Insert operation on a table in a SQL Server database is:</span></span>  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="e7377-124">従業員は、SQL Server データベース内のテーブルの名前です。</span><span class="sxs-lookup"><span data-stu-id="e7377-124">Employee is the name of a table in SQL Server database.</span></span>  
  
    3.  <span data-ttu-id="e7377-125">クリックして、**バインディング**タブによって公開されるプロパティのバインドを指定して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e7377-125">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="e7377-126">バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-126">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e7377-127">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7377-127">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="e7377-128">たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="e7377-128">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
    4.  <span data-ttu-id="e7377-129">クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7377-129">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
        -   <span data-ttu-id="e7377-130">選択、**シングル サインオンを使用しない**オプション、およびユーザー名を指定とパスワードを SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="e7377-130">Select the **Do not use Single Sign-On** option, and the specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="e7377-131">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7377-131">Note that the user name and password are case-sensitive.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="e7377-132">Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-132">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="e7377-133">SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-133">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
        -   <span data-ttu-id="e7377-134">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-134">Select the **Use Single Sign-On** option, and then specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
             <span data-ttu-id="e7377-135">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-135">For more information about security with respect to BizTalk Server, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="e7377-136">戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-136">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="e7377-137">**送信ハンドラー**一覧で、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-137">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="e7377-138">作成する場合は**静的な一方向送信ポート**手順 5 で、送信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-138">If you chose to create **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="e7377-139">**送信パイプライン**一覧で、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7377-139">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="e7377-140">作成する場合は**静的な送信請求-応答ポート**手順 5 で、指定の送信および受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="e7377-140">If you chose to create **Static Solicit-Response Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="e7377-141">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7377-141">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="e7377-142">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7377-142">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
12. <span data-ttu-id="e7377-143">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7377-143">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a><span data-ttu-id="e7377-144">SQL Server からメッセージを受信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="e7377-144">Deploy adapters to receive messages from SQL Server</span></span>  
 <span data-ttu-id="e7377-145">次の実行 WCF SQL を構成する手順を使用して SQL サーバーからメッセージを受信するためのポートの受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e7377-145">Perform the following steps to configure a WCF-SQL receive port for receiving messages from SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1.  <span data-ttu-id="e7377-146">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e7377-146">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="e7377-147">WCF-SQL アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e7377-147">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="e7377-148">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-148">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="e7377-149">コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-149">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4.  <span data-ttu-id="e7377-150">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e7377-150">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
5.  <span data-ttu-id="e7377-151">右クリック**受信ポート**、指す**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="e7377-151">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
6.  <span data-ttu-id="e7377-152">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7377-152">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7.  <span data-ttu-id="e7377-153">**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-153">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="e7377-154">**受信場所のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7377-154">The **Receive Location Properties** dialog box appears.</span></span>  
  
8.  <span data-ttu-id="e7377-155">**受信場所のプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e7377-155">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="e7377-156">受信場所の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-156">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="e7377-157">**型**ドロップダウン リストは、前に追加する WCF-SQL アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-157">From the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="e7377-158">トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7377-158">In the transport properties dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="e7377-159">をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-159">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="e7377-160">詳細については、接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI を作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-160">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="e7377-161">クリックして、**バインディング**タブによって公開されるプロパティのバインドを指定して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e7377-161">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="e7377-162">バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-162">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e7377-163">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7377-163">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="e7377-164">たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="e7377-164">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
    3.  <span data-ttu-id="e7377-165">クリックして、**動作**タブは、トランザクション分離レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-165">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="e7377-166">トランザクション分離レベルの設定の詳細については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-166">For more information about setting transaction isolation level, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
    4.  <span data-ttu-id="e7377-167">クリックして、**他**タブをクリックし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="e7377-167">Click the **Other** tab, and do one of the following:</span></span>  
  
        -   <span data-ttu-id="e7377-168">選択**ユーザー アカウント**ユーザー名と SQL Server に接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-168">Select **User account**, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="e7377-169">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7377-169">Note that the user name and password are case-sensitive.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="e7377-170">Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-170">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="e7377-171">SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-171">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
        -   <span data-ttu-id="e7377-172">選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-172">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
             <span data-ttu-id="e7377-173">関連するセキュリティの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7377-173">For more information about security with respect to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="e7377-174">戻るには、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-174">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="e7377-175">**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-175">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="e7377-176">作成する場合は**一方向の受信ポート**手順 5 で、受信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="e7377-176">If you chose to create **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="e7377-177">**受信パイプライン**一覧で、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7377-177">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="e7377-178">作成する場合は**要求-応答受信ポート**手順 5 で、指定の送信および受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="e7377-178">If you chose to create **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="e7377-179">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7377-179">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="e7377-180">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7377-180">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="e7377-181">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-181">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="e7377-182">**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e7377-182">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7377-183">参照</span><span class="sxs-lookup"><span data-stu-id="e7377-183">See Also</span></span>  
[<span data-ttu-id="e7377-184">SQL アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="e7377-184">Manually configure a physical port binding to the SQL adapter </span></span>](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)
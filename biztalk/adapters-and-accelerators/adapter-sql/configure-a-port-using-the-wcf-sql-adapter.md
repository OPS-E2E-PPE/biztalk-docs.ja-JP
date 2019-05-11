---
title: WCF-SQL アダプターを使用して biztalk ポートの構成 |Microsoft Docs
description: 作成 WCF-SQL 送信ポートと受信ポートを BizTalk Server で SQL Server のアダプターを使用するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8cdc032-3160-43de-9510-7ca69506083e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbccab308521ca6c3bb429da3ba13078258ba2dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370003"
---
# <a name="configure-a-port-using-the-wcf-sql-adapter"></a><span data-ttu-id="a1f2d-103">WCF-SQL アダプターを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-103">Configure a port using the WCF-SQL adapter</span></span>
<span data-ttu-id="a1f2d-104">このトピックでは WCF SQL を構成する方法については送受信ポートを使用して SQL サーバーの送信および受信操作を実行する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-104">This topic provides instructions on how to configure WCF-SQL send and receive ports to perform outbound and inbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1f2d-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="a1f2d-105">Prerequisites</span></span>  
<span data-ttu-id="a1f2d-106">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="a1f2d-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a><span data-ttu-id="a1f2d-108">SQL Server にメッセージを送信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-108">Deploy adapters to send messages to SQL Server</span></span>  
 <span data-ttu-id="a1f2d-109">使用して SQL Server にメッセージを送信するための WCF-SQL 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-109">Perform the following steps to configure a WCF-SQL send port for sending messages to SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="a1f2d-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="a1f2d-111">WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-111">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a1f2d-112">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-112">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="a1f2d-113">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-113">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4. <span data-ttu-id="a1f2d-114">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-114">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
5. <span data-ttu-id="a1f2d-115">右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-115">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
6. <span data-ttu-id="a1f2d-116">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-116">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
7. <span data-ttu-id="a1f2d-117">**型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-117">From the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="a1f2d-118">トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-118">In the transport properties dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="a1f2d-119">をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-119">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="a1f2d-120">接続 URI の詳細についてはの[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-120">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="a1f2d-121">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-121">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="a1f2d-122">参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)の各操作のアクションの一覧。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-122">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) for a list of actions for each operation.</span></span> <span data-ttu-id="a1f2d-123">たとえば、SQL Server データベース内のテーブルに対する挿入操作を呼び出すアクションは。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-123">For example, the action to invoke the Insert operation on a table in a SQL Server database is:</span></span>  
  
      ```  
      TableOp/Insert/dbo/Employee  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="a1f2d-124">従業員は、SQL Server データベース内のテーブルの名前です。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-124">Employee is the name of a table in SQL Server database.</span></span>  
  
   3. <span data-ttu-id="a1f2d-125">をクリックして、**バインド** タブでバインドによって公開されるプロパティの値を指定し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-125">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="a1f2d-126">バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-126">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="a1f2d-127">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-127">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="a1f2d-128">たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-128">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
   4. <span data-ttu-id="a1f2d-129">をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-129">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
      -   <span data-ttu-id="a1f2d-130">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名の指定とパスワードを SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-130">Select the **Do not use Single Sign-On** option, and the specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="a1f2d-131">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-131">Note that the user name and password are case-sensitive.</span></span>  
  
          > [!NOTE]
          >  <span data-ttu-id="a1f2d-132">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-132">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="a1f2d-133">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-133">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
      -   <span data-ttu-id="a1f2d-134">選択、**使用してシングル サインオン**オプション、し、関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-134">Select the **Use Single Sign-On** option, and then specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
           <span data-ttu-id="a1f2d-135">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-135">For more information about security with respect to BizTalk Server, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
   5. <span data-ttu-id="a1f2d-136">戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-136">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="a1f2d-137">**送信ハンドラー**一覧で、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-137">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="a1f2d-138">作成した場合**静的な一方向送信ポート**手順 5 で、送信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-138">If you chose to create **Static One-Way Send Port** in step 5, specify a send pipeline.</span></span> <span data-ttu-id="a1f2d-139">**送信パイプライン**一覧で [xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-139">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
11. <span data-ttu-id="a1f2d-140">作成した場合**静的な送信請求-応答ポート**手順 5 で、指定の送信および受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-140">If you chose to create **Static Solicit-Response Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="a1f2d-141">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-141">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="a1f2d-142">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-142">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
12. <span data-ttu-id="a1f2d-143">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-143">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a><span data-ttu-id="a1f2d-144">SQL Server からメッセージを受信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-144">Deploy adapters to receive messages from SQL Server</span></span>  
 <span data-ttu-id="a1f2d-145">以下を実行する WCF SQL を構成する手順を使用して SQL Server からメッセージを受信するためのポートの受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-145">Perform the following steps to configure a WCF-SQL receive port for receiving messages from SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="a1f2d-146">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-146">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="a1f2d-147">WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-147">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a1f2d-148">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-148">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="a1f2d-149">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-149">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
4. <span data-ttu-id="a1f2d-150">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-150">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
5. <span data-ttu-id="a1f2d-151">右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-151">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
6. <span data-ttu-id="a1f2d-152">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-152">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
7. <span data-ttu-id="a1f2d-153">**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-153">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="a1f2d-154">**受信場所のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-154">The **Receive Location Properties** dialog box appears.</span></span>  
  
8. <span data-ttu-id="a1f2d-155">**受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-155">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="a1f2d-156">受信場所の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-156">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="a1f2d-157">**型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-157">From the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
9. <span data-ttu-id="a1f2d-158">トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-158">In the transport properties dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="a1f2d-159">をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-159">Click the **General** tab, click the **Configure** button, and provide values for the connection parameters.</span></span> <span data-ttu-id="a1f2d-160">接続 URI の詳細についてはの[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-160">For more information about the connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="a1f2d-161">をクリックして、**バインド** タブでバインドによって公開されるプロパティの値を指定し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-161">Click the **Binding** tab and specify values for binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="a1f2d-162">バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-162">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="a1f2d-163">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-163">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="a1f2d-164">たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-164">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
   3. <span data-ttu-id="a1f2d-165">をクリックして、**動作** タブ、トランザクション分離レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-165">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="a1f2d-166">トランザクション分離レベルを設定する方法についての詳細については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクション タイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-166">For more information about setting transaction isolation level, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
   4. <span data-ttu-id="a1f2d-167">をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-167">Click the **Other** tab, and do one of the following:</span></span>  
  
      - <span data-ttu-id="a1f2d-168">選択**ユーザー アカウント**ユーザー名と SQL Server に接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-168">Select **User account**, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="a1f2d-169">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-169">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a1f2d-170">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-170">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="a1f2d-171">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-171">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
      - <span data-ttu-id="a1f2d-172">選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-172">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
         <span data-ttu-id="a1f2d-173">セキュリティの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-173">For more information about security with respect to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
   5. <span data-ttu-id="a1f2d-174">戻ります、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-174">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="a1f2d-175">**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-175">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
11. <span data-ttu-id="a1f2d-176">作成した場合**一方向の受信ポート**手順 5 で、受信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-176">If you chose to create **One-way Receive Port** in step 5, specify a receive pipeline.</span></span> <span data-ttu-id="a1f2d-177">**受信パイプライン**一覧で [xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-177">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
12. <span data-ttu-id="a1f2d-178">作成した場合**要求-応答受信ポート**手順 5 で、指定の送信および受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-178">If you chose to create **Request Response Receive Port** in step 5, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="a1f2d-179">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-179">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="a1f2d-180">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-180">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
13. <span data-ttu-id="a1f2d-181">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-181">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="a1f2d-182">**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a1f2d-182">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f2d-183">参照</span><span class="sxs-lookup"><span data-stu-id="a1f2d-183">See Also</span></span>  
[<span data-ttu-id="a1f2d-184">SQL アダプターを物理ポートのバインドを手動で構成します。 </span><span class="sxs-lookup"><span data-stu-id="a1f2d-184">Manually configure a physical port binding to the SQL adapter </span></span>](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)
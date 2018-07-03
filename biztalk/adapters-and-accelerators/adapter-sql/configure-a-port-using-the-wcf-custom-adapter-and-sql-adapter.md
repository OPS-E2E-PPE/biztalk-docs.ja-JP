---
title: Biztalk WCF カスタム アダプターと SQL アダプタを使用してポートの構成 |Microsoft Docs
description: 作成 wcf-custom 送信ポートと受信ポートを BizTalk Server で SQL Server のアダプターを使用するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d44d9932-0a5e-4072-a480-2f8dc544ca79
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eafde28037b3c38dd36ec03907544a5ec23560f5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012611"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter"></a><span data-ttu-id="931d5-103">Wcf-custom アダプタと SQL アダプタを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="931d5-103">Configure a port using the WCF-custom adapter and SQL adapter</span></span>
<span data-ttu-id="931d5-104">Wcf-custom 送信を構成し、受信ポートを使用して SQL Server で送信および受信の操作を実行する手順、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="931d5-104">Steps to configure WCF-Custom send and receive ports to perform outbound and inbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="931d5-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="931d5-105">Prerequisites</span></span>  
<span data-ttu-id="931d5-106">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="931d5-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="931d5-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="931d5-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span> 
  
## <a name="deploy-adapters-to-send-messages-to-sql-server"></a><span data-ttu-id="931d5-108">SQL Server にメッセージを送信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="931d5-108">Deploy adapters to send messages to SQL Server</span></span>  
 <span data-ttu-id="931d5-109">使用して SQL Server にメッセージを送信するための Wcf-custom 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="931d5-109">Perform the following steps to configure a WCF-Custom send port for sending messages to SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>    
 
1. <span data-ttu-id="931d5-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="931d5-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="931d5-111">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="931d5-112">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="931d5-112">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4. <span data-ttu-id="931d5-113">右クリック**送信ポート**、 をポイント**新規**との間の通信モードによって構成するポートの種類 をポイントし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="931d5-113">Right-click **Send Ports**, point to **New**, and then point to the type of port you want to configure depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
5. <span data-ttu-id="931d5-114">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="931d5-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="931d5-115">**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7. <span data-ttu-id="931d5-116">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="931d5-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="931d5-117">をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for SQL Server.</span></span> <span data-ttu-id="931d5-118">接続 URI の詳細については、次を参照してください。 [SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="931d5-118">For more information about the connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="931d5-119">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="931d5-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="931d5-120">参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)の各操作のアクションの一覧。</span><span class="sxs-lookup"><span data-stu-id="931d5-120">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) for a list of actions for each operation.</span></span> <span data-ttu-id="931d5-121">たとえば、SQL Server データベース内のテーブルに対する挿入操作を呼び出すアクションは。</span><span class="sxs-lookup"><span data-stu-id="931d5-121">For example, the action to invoke the Insert operation on a table in a SQL Server database is:</span></span>  
  
      ```  
      TableOp/Insert/dbo/Employee  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="931d5-122">従業員は、SQL Server データベース内のテーブルの名前です。</span><span class="sxs-lookup"><span data-stu-id="931d5-122">Employee is the name of a table in SQL Server database.</span></span>  
  
   3. <span data-ttu-id="931d5-123">をクリックして、**バインド**] タブとの間、**バインドの種類**一覧で、[ **sqlBinding**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-123">Click the **Binding** tab, and from the **Binding Type** list, select **sqlBinding**.</span></span> <span data-ttu-id="931d5-124">によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="931d5-124">You can specify the different binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="931d5-125">バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="931d5-125">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
   4. <span data-ttu-id="931d5-126">をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="931d5-126">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
      -   <span data-ttu-id="931d5-127">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名の指定とパスワードを SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="931d5-127">Select the **Do not use Single Sign-On** option, and the specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="931d5-128">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="931d5-128">Note that the user name and password are case-sensitive.</span></span>  
  
          > [!NOTE]
          >  <span data-ttu-id="931d5-129">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-129">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="931d5-130">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="931d5-130">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
      -   <span data-ttu-id="931d5-131">選択、**使用してシングル サインオン**オプション、し、関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-131">Select the **Use Single Sign-On** option, and then specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
           <span data-ttu-id="931d5-132">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="931d5-132">For more information about security with respect to BizTalk Server, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
   5. <span data-ttu-id="931d5-133">戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="931d5-133">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8. <span data-ttu-id="931d5-134">**送信ハンドラー**一覧で、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-134">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="931d5-135">選択した場合**静的な一方向送信ポート**手順 4 で、送信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-135">If you chose **Static One-Way Send Port** in step 4, specify a send pipeline.</span></span> <span data-ttu-id="931d5-136">**送信パイプライン**一覧で [xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="931d5-136">From the **Send pipeline** list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="931d5-137">選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="931d5-137">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="931d5-138">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="931d5-138">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="931d5-139">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="931d5-139">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
11. <span data-ttu-id="931d5-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="931d5-140">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sql-server"></a><span data-ttu-id="931d5-141">SQL Server からメッセージを受信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="931d5-141">Deploy adapters to receive messages from SQL Server</span></span>
 <span data-ttu-id="931d5-142">以下を実行するカスタム WCF を構成する手順を使用して SQL Server からメッセージを受信するためのポートの受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="931d5-142">Perform the following steps to configure a WCF-Custom receive port for receiving messages from SQL Server using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="931d5-143">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="931d5-143">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="931d5-144">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-144">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="931d5-145">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="931d5-145">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4. <span data-ttu-id="931d5-146">右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、間の通信モード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と SQL Server。</span><span class="sxs-lookup"><span data-stu-id="931d5-146">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port**, depending on the mode of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and SQL Server.</span></span>  
  
5. <span data-ttu-id="931d5-147">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="931d5-147">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6. <span data-ttu-id="931d5-148">**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-148">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="931d5-149">**受信場所のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="931d5-149">The **Receive Location Properties** dialog box appears.</span></span>  
  
7. <span data-ttu-id="931d5-150">**受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="931d5-150">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="931d5-151">受信場所の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-151">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="931d5-152">**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-152">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="931d5-153">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="931d5-153">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="931d5-154">をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-154">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for SQL Server.</span></span> <span data-ttu-id="931d5-155">接続 URI の詳細については、次を参照してください。 [SQL Server 接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="931d5-155">For more information about the connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="931d5-156">をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sqlBinding**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-156">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sqlBinding**.</span></span> <span data-ttu-id="931d5-157">によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="931d5-157">You can specify the different binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="931d5-158">バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="931d5-158">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
   3. <span data-ttu-id="931d5-159">をクリックして、**動作** タブ、トランザクション分離レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-159">Click the **Behavior** tab to set the transaction isolation level.</span></span> <span data-ttu-id="931d5-160">トランザクション分離レベルを設定する方法についての詳細については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクション タイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="931d5-160">For more information about setting transaction isolation level, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
   4. <span data-ttu-id="931d5-161">をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="931d5-161">Click the **Other** tab, and do one of the following:</span></span>  
  
      - <span data-ttu-id="931d5-162">選択**ユーザー アカウント**ユーザー名と SQL Server に接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-162">Select **User account**, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="931d5-163">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="931d5-163">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="931d5-164">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-164">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="931d5-165">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[SQL アダプターを使用した Windows 認証を使用して SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="931d5-165">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
      - <span data-ttu-id="931d5-166">選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-166">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
         <span data-ttu-id="931d5-167">セキュリティの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="931d5-167">For more information about security with respect to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>  
  
   5. <span data-ttu-id="931d5-168">戻ります、**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="931d5-168">To return to the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="931d5-169">**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-169">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="931d5-170">選択した場合**一方向の受信ポート**手順 4 で、受信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="931d5-170">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="931d5-171">**受信パイプライン**一覧で [xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="931d5-171">From the **Receive pipeline** list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="931d5-172">選択した場合**要求-応答受信ポート**手順 4 で、指定の送信および受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="931d5-172">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="931d5-173">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="931d5-173">From the **Receive pipeline** drop-down list, select the pipeline that corresponds to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="931d5-174">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="931d5-174">From the **Send pipeline** drop-down list, select the pipeline that corresponds to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="931d5-175">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-175">In the **Receive Location Properties** dialog box, click **OK**.</span></span>  
  
13. <span data-ttu-id="931d5-176">**受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="931d5-176">In the **Receive Port Properties** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931d5-177">参照</span><span class="sxs-lookup"><span data-stu-id="931d5-177">See Also</span></span>  
[<span data-ttu-id="931d5-178">SQL アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="931d5-178">Manually configure a physical port binding to the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)
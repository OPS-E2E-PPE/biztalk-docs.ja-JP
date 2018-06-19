---
title: BizTalk Server を使用して SQL Server で 1 つの XML パラメーターを持つストアド プロシージャを実行 |Microsoft ドキュメント
description: Biztalk WCF カスタム ポートと SQL アダプタを使用してストアド プロシージャで 1 つのパラメーターを渡す
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deb9333a-5e28-4e8d-8e0b-07b5a97a111b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02c5f239300140022b1d26f35664add744b630c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964600"
---
# <a name="execute-stored-procedures-with-a-single-xml-parameter-in-sql-server-using-biztalk-server"></a><span data-ttu-id="ea95b-103">BizTalk Server を使用して SQL Server で 1 つの XML パラメーターを持つストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-103">Execute stored procedures with a single XML parameter in SQL Server using BizTalk Server</span></span>
<span data-ttu-id="ea95b-104">」の説明に従って、他のストアド プロシージャの実行に似ていますが、1 つのパラメーターを受け取るストアド プロシージャを実行する[BizTalk Server を使用して SQL Server でストアド プロシージャの実行](execute-stored-procedures-in-sql-server-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-104">Executing a stored procedure that takes a single parameter is similar to executing any other stored procedure as described in [Execute Stored Procedures in SQL Server using BizTalk Server](execute-stored-procedures-in-sql-server-using-biztalk-server.md).</span></span> <span data-ttu-id="ea95b-105">ただし、上記のリンクで説明されているアプローチのデザイン時にストアド プロシージャのメタデータを生成し、実行時にプロシージャを呼び出すオーケストレーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea95b-105">However, for the approach described in the preceding link, you need to generate metadata for the stored procedure at design time and create an orchestration to invoke the procedure at run time.</span></span>  
  
 <span data-ttu-id="ea95b-106">その値の処理を行わず、ストアド プロシージャに 1 つの 1 つの値を渡すだけする場所のシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ea95b-106">Consider a scenario where you just want to pass one single value to a stored procedure without doing any processing on that value.</span></span> <span data-ttu-id="ea95b-107">このような場合に、メタデータの生成、オーケストレーションを作成、オーケストレーションを展開して、操作を実行するのオーバーヘッドがしません。</span><span class="sxs-lookup"><span data-stu-id="ea95b-107">In such cases, you don't want the overhead of generating metadata, creating an orchestration, deploying the orchestration, and executing the operation.</span></span> <span data-ttu-id="ea95b-108">代わりに、直接、ストアド プロシージャを呼び出すには、Wcf-custom または WCF-SQL 送信ポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ea95b-108">Rather, you can configure a WCF-Custom or WCF-SQL send port to directly invoke the stored procedure.</span></span> <span data-ttu-id="ea95b-109">このトピックは、これらのタスクを実行する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ea95b-109">This topic demonstrates how to perform these tasks using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea95b-110">このトピックでは、Wcf-custom を構成する方法についての送信を 1 つのパラメーターを受け取るストアド プロシージャを実行するためのポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-110">This topic provides instructions on how to configure a WCF-Custom send port for executing stored procedure that takes a single parameter.</span></span> <span data-ttu-id="ea95b-111">同じ手順を実行するには、WCF SQL ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-111">You can perform the same steps by configuring a WCF-SQL port.</span></span> <span data-ttu-id="ea95b-112">WCF SQL ポートの構成方法の詳細については、次を参照してください。 [WCF-SQL アダプターを使用してポートを構成する](configure-a-port-using-the-wcf-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-112">For instructions on configuring WCF-SQL port, see [Configure a Port using the WCF-SQL Adapter](configure-a-port-using-the-wcf-sql-adapter.md).</span></span>  
  
## <a name="invoke-stored-procedures-without-orchestration"></a><span data-ttu-id="ea95b-113">指揮なしのストアド プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="ea95b-113">Invoke stored procedures without orchestration</span></span>  
 <span data-ttu-id="ea95b-114">せず、オーケストレーションの単一のパラメーターを使用してストアド プロシージャを実行する方法を示すためには、このトピックは ADD_LAST_EMP_XML_INFO ストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-114">To demonstrate how to execute stored procedures with single parameters without an orchestration, this topic uses the ADD_LAST_EMP_XML_INFO stored procedure.</span></span> <span data-ttu-id="ea95b-115">この手順は、パラメーターとして XML 値を取得しに挿入、**アドレス**の列、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="ea95b-115">This procedure takes an XML value as a parameter and inserts it into the **Address** column of the **Employee** table.</span></span> <span data-ttu-id="ea95b-116">ストアド プロシージャに渡す XML 値が必要です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-116">You must have the XML value that you will pass to the stored procedure.</span></span> <span data-ttu-id="ea95b-117">ただし、アダプターを使用してストアド プロシージャを実行するには、プロシージャのスキーマに準拠した要求メッセージを送信する必要があります、値を XML を含む、**アドレス**フィールドでは、SQL Server にします。</span><span class="sxs-lookup"><span data-stu-id="ea95b-117">However, to execute the stored procedure using the adapter, you must send a request message conforming to the schema of the procedure, and containing the XML value for the **Address** field, to the SQL Server.</span></span> <span data-ttu-id="ea95b-118">そのため、によってその要求メッセージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea95b-118">So, you must create that request message by:</span></span>  
  
-   <span data-ttu-id="ea95b-119">使用して、**テンプレート**メッセージ テンプレートを使用して要求メッセージを作成することができますを使用して送信ポートの構成オプション。</span><span class="sxs-lookup"><span data-stu-id="ea95b-119">Using the **Template** option in the send port configuration using which you can create a request message using a message template.</span></span>  
  
-   <span data-ttu-id="ea95b-120">値、xml、**アドレス**フィールドをメッセージにします。</span><span class="sxs-lookup"><span data-stu-id="ea95b-120">Putting the XML value for the **Address** field into the message.</span></span>  
  
 <span data-ttu-id="ea95b-121">これらすべての手順については、このトピックで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-121">All these steps are described in detail in this topic.</span></span> <span data-ttu-id="ea95b-122">次の一連のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea95b-122">You must perform the following set of tasks:</span></span>  
  
1.  <span data-ttu-id="ea95b-123">ファイルを作成する受信ポートに挿入される XML ファイルをドロップする場所、**アドレス**XML フィールドの**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="ea95b-123">Create a FILE receive port where you will drop the XML file that will be inserted into the **Address** XML field of the **Employee** table.</span></span> <span data-ttu-id="ea95b-124">このポートを呼び出すと**MessageIn**ポートです。</span><span class="sxs-lookup"><span data-stu-id="ea95b-124">Suppose this port is called **MessageIn** port.</span></span>  
  
2.  <span data-ttu-id="ea95b-125">XML ファイルは、ファイルから取得の受信ポート、メッセージ テンプレートを使用して、メッセージを作成、ストアド プロシージャを実行する SQL Server に送信 Wcf-custom 一方向の送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-125">Create a WCF-Custom one-way send port that picks the XML file from the FILE receive port, constructs the message using the message template, and sends it to SQL Server to execute the stored procedure.</span></span>  
  
 <span data-ttu-id="ea95b-126">トピックのこの部分では、Wcf-custom を構成する手順についての送信ポート、メッセージのテンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-126">This part of the topic provides instructions on configuring a WCF-Custom send port with the message template.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea95b-127">このトピックの情報は、XML パラメーターを 1 つのストアド プロシージャを実行する方法を示します、場合でもは、任意のデータ型の 1 つのパラメーターを受け取るすべての操作を実行するタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea95b-127">Even though the information in this topic demonstrates how to execute a stored procedure with a single XML parameter, you can perform the tasks to perform any operation that takes a single parameter of any data type.</span></span> <span data-ttu-id="ea95b-128">唯一の違いは、特定の操作についてメッセージ テンプレートを作成する方法になります。</span><span class="sxs-lookup"><span data-stu-id="ea95b-128">The only difference will be in the way you create a message template for a specific operation.</span></span> <span data-ttu-id="ea95b-129">メッセージ テンプレートを作成するには、操作を実行するを使用する要求メッセージを実行して、オーケストレーションを使用して、パラメーターの値に置き換えて、BizTalk メッセージ本文。</span><span class="sxs-lookup"><span data-stu-id="ea95b-129">You can create a message template by taking the request message you would use to execute the operation using an orchestration and replacing the value of the parameter with the BizTalk message body.</span></span>  
  
##  <a name="BKMK_OneWay"></a><span data-ttu-id="ea95b-130">Wcf-custom 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-130">Configure a WCF-Custom send port</span></span>  
 <span data-ttu-id="ea95b-131">WCF カスタムを作成する前に、送信ポート、ファイルを作成することを確認の受信ポート、 **MessageIn**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-131">Before creating the WCF-Custom send port, make sure you created the FILE receive port, **MessageIn**.</span></span>  
  
1.  <span data-ttu-id="ea95b-132">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ea95b-132">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="ea95b-133">コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-133">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="ea95b-134">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-134">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4.  <span data-ttu-id="ea95b-135">右クリック**送信ポート**、指す**新規**、順にポイントし、**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-135">Right-click **Send Ports**, point to **New**, and then point to **Static One-way Send Port**.</span></span>  
  
5.  <span data-ttu-id="ea95b-136">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-136">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="ea95b-137">すべてを受信するポートを構成ファイルで破棄されたメッセージの受信ポート、 **MessageIn**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-137">Configure the port to receive all messages dropped at the FILE receive port, **MessageIn**.</span></span>  
  
    1.  <span data-ttu-id="ea95b-138">**送信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウからをクリックして**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-138">In the **Send Port Properties** dialog box, from the left pane, click **Filters**.</span></span>  
  
    2.  <span data-ttu-id="ea95b-139">右側のペインで下にある、**プロパティ**列では、グリッドをクリックし、 **BTS です。ReceivePortName**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ea95b-139">In the right pane, under the **Property** column, click the grid, and then select **BTS.ReceivePortName** property.</span></span>  
  
    3.  <span data-ttu-id="ea95b-140">**演算子**列で、"**==**"です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-140">For the **Operator** column, select “**==**”.</span></span>  
  
    4.  <span data-ttu-id="ea95b-141">**値**列で、受信ポートのファイルの名前を指定して`MessageIn`です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-141">For the **Value** column, specify the name of the FILE receive port, `MessageIn`.</span></span>  
  
7.  <span data-ttu-id="ea95b-142">**送信ポートのプロパティ**ダイアログ ボックスの**全般** タブから、**型**ドロップダウン リストで、 **Wcf-custom**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-142">In the **Send Port Properties** dialog box, on the **General** tab, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="ea95b-143">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-143">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="ea95b-144">クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-144">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for SQL Server.</span></span> <span data-ttu-id="ea95b-145">接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-145">For more information about the connection URI, see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="ea95b-146">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-146">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="ea95b-147">参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)各操作のアクションの一覧についてはします。</span><span class="sxs-lookup"><span data-stu-id="ea95b-147">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) for a list of actions for each operation.</span></span> <span data-ttu-id="ea95b-148">たとえば、ADD_LAST_EMP_XML_INFO を呼び出すアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-148">For example, the action to invoke the ADD_LAST_EMP_XML_INFO is:</span></span>  
  
        ```  
        Procedure/dbo/ADD_LAST_EMP_XML_INFO  
        ```  
  
    3.  <span data-ttu-id="ea95b-149">クリックして、**バインド**] タブとの間、**バインディングの種類**一覧で、[ **sqlBinding**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-149">Click the **Binding** tab, and from the **Binding Type** list, select **sqlBinding**.</span></span> <span data-ttu-id="ea95b-150">によって公開されている別のバインディング プロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-150">You can specify the different binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ea95b-151">バインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-151">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="ea95b-152">クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ea95b-152">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
        -   <span data-ttu-id="ea95b-153">選択、**シングル サインオンを使用しない**オプション、およびユーザー名を指定とパスワードを SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-153">Select the **Do not use Single Sign-On** option, and the specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="ea95b-154">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ea95b-154">Note that the user name and password are case-sensitive.</span></span>  
  
            > [!NOTE]
            >  <span data-ttu-id="ea95b-155">Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-155">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span>  
  
        -   <span data-ttu-id="ea95b-156">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-156">Select the **Use Single Sign-On** option, and then specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
             <span data-ttu-id="ea95b-157">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-157">For more information about security with respect to BizTalk Server, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>
  
    5.  <span data-ttu-id="ea95b-158">クリックして、**メッセージ**] タブで、し、[、**送信 WCF メッセージ本文**セクションで、選択、**テンプレート**オプション。</span><span class="sxs-lookup"><span data-stu-id="ea95b-158">Click the **Messages** tab, and in the **Outbound WCF message body** section, choose the **Template** option.</span></span>  
  
    6.  <span data-ttu-id="ea95b-159">**XML**テキスト ボックスで、WCF メッセージを構築するために使用されるテンプレートを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-159">In the **XML** text box, specify the template that will be used to construct the WCF message.</span></span> <span data-ttu-id="ea95b-160">これにより、WCF ベース ADD_LAST_EMP_XML_INFO 操作に準拠したメッセージを作成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-160">By doing so, you create a message that conforms to the ADD_LAST_EMP_XML_INFO operation for the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
         <span data-ttu-id="ea95b-161">![送信 WCF メッセージのテンプレートを指定](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")</span><span class="sxs-lookup"><span data-stu-id="ea95b-161">![Specify template for outbound WCF message](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")</span></span>  
  
         <span data-ttu-id="ea95b-162">ADD_LAST_EMP_XML_INFO ストアド プロシージャの次のテンプレートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea95b-162">For the ADD_LAST_EMP_XML_INFO stored procedure, you must specify the following template:</span></span>  
  
        ```  
        <ADD_LAST_EMP_XML_INFO xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
        <xml_info>  
        <bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/>  
        </xml_info>  
        </ADD_LAST_EMP_XML_INFO>  
        ```  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="ea95b-163">メッセージ テンプレートでのエンコードと、"string"送信ポートを使用して呼び出される操作のパラメーターの型に関係なく常にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea95b-163">The encoding in the message template must always be “string” irrespective of the type of the parameter for the operation that will be invoked using the send port.</span></span> <span data-ttu-id="ea95b-164">たとえば、ADD_LAST_EMP_XML_INFO は、XML 型のパラメーターを受け取りますが、文字列は、メッセージのテンプレートでのエンコーディングします。</span><span class="sxs-lookup"><span data-stu-id="ea95b-164">For example, the ADD_LAST_EMP_XML_INFO takes a parameter of type XML, but the encoding in the message template is string.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ea95b-165">このメッセージのテンプレートを作成するにはストアド プロシージャの要求メッセージをコピーして、BizTalk メッセージ本文 < xml_info > タグ内で値を置換します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-165">You can create this message template by copying the request message for the stored procedure and replacing the value within the <xml_info> tags with the BizTalk message body.</span></span> <span data-ttu-id="ea95b-166">使用して、プロシージャのスキーマを生成することによって、ストアド プロシージャの要求メッセージを取得できます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、および XML 要求を取得するスキーマのインスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-166">You can get the request message for the stored procedure by generating the schema for the procedure using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], and then generating an instance of the schema to get the request XML.</span></span>  
  
    7.  <span data-ttu-id="ea95b-167">戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-167">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="ea95b-168">**送信ハンドラー**一覧で、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-168">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="ea95b-169">**送信パイプライン**一覧に対応するパイプラインを選択して**PassThruTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-169">From the **Send pipeline** list, select the pipeline that corresponds to **PassThruTransmit**.</span></span>  
  
11. <span data-ttu-id="ea95b-170">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea95b-170">Click **OK**.</span></span>  
  
## <a name="start-the-application"></a><span data-ttu-id="ea95b-171">アプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-171">Start the Application</span></span>  
 <span data-ttu-id="ea95b-172">BizTalk アプリケーションを起動するには、両方のファイルを開始する場所を受信し、Wcf-custom 送信ポートが個別にします。</span><span class="sxs-lookup"><span data-stu-id="ea95b-172">To start the BizTalk application, you can start both the FILE receive location and the WCF-Custom send port individually.</span></span> <span data-ttu-id="ea95b-173">必要があります。 受信場所がファイルにマップされているフォルダーに XML ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ea95b-173">You must now copy an XML file to the folder mapped to the FILE receive location.</span></span> <span data-ttu-id="ea95b-174">BizTalk アプリケーションが、ファイルを使用し、XML 値は、Employee テーブルの [アドレス] 列に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="ea95b-174">The BizTalk application consumes the file, and the XML value is inserted in the Address column of the Employee table.</span></span> <span data-ttu-id="ea95b-175">これは、SQL Server クライアントを使用して、従業員テーブルからレコードを選択して確認できます。</span><span class="sxs-lookup"><span data-stu-id="ea95b-175">You can verify this by using a SQL Server client and selecting records from the Employee table.</span></span>  
  
## <a name="using-a-two-way-wcf-custom-send-port"></a><span data-ttu-id="ea95b-176">双方向の Wcf-custom 送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-176">Using a Two-way WCF-Custom Send Port</span></span>  
 <span data-ttu-id="ea95b-177">セクションの下のこのトピックの手順に[Wcf-custom 送信ポートを構成する方法](../../core/how-to-configure-a-wcf-custom-send-port.md)BizTalk を使用しなくても 1 つのパラメーターを持つストアド プロシージャを実行する一方向の Wcf-custom 送信ポートを構成する方法を示しますオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="ea95b-177">The instructions in this topic, under the section [How to Configure a WCF-Custom Send Port](../../core/how-to-configure-a-wcf-custom-send-port.md), demonstrate how to configure a one-way WCF-Custom send port to execute a stored procedure with a single parameter without using a BizTalk orchestration.</span></span> <span data-ttu-id="ea95b-178">ただし、このような場合は、ストアド プロシージャが実行されたかどうかを確認が正常にする必要がある SQL Server データベースには Employee テーブルの [アドレス] 列を更新するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-178">However, in such a case, to verify whether the stored procedure is executed successfully you will have to verify in the SQL Server database whether the Address column in the Employee table is updated.</span></span>  
  
 <span data-ttu-id="ea95b-179">代わりに、ストアド プロシージャが正常に実行された場合は、SQL Server から応答も取得する双方向の Wcf-custom 送信ポートを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ea95b-179">Instead, you can create a two-way WCF-Custom send port that also gets the response from SQL Server if the stored procedure is executed successfully.</span></span> <span data-ttu-id="ea95b-180">双方向の WCF カスタム ポートを作成する場合は、いくつかの追加手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea95b-180">You must perform a few additional steps if you create a two-way WCF-Custom port.</span></span> <span data-ttu-id="ea95b-181">ファイルが必要がありますに注意してくださいでは、上記の手順で説明したようの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea95b-181">Note that you will still need a FILE receive location, as mentioned in the preceding instructions.</span></span>  
  
1.  <span data-ttu-id="ea95b-182">たとえば、双方向の Wcf-custom 送信ポートを作成する**ExecProcedure**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-182">Create a two-way WCF-Custom send port, for example, **ExecProcedure**.</span></span> <span data-ttu-id="ea95b-183">送信ポートを構成する手順は、一方向の送信ポートの場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="ea95b-183">The steps to configure the send port are similar to those for the one-way send port.</span></span> <span data-ttu-id="ea95b-184">唯一の違いは、双方向のポートにする必要がありますも指定する、受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="ea95b-184">The only difference is that for the two-way port you must also specify a receive pipeline.</span></span> <span data-ttu-id="ea95b-185">選択するかどうかを確認**PassThruReceive**受信パイプラインのです。</span><span class="sxs-lookup"><span data-stu-id="ea95b-185">Make sure you select **PassThruReceive** for the receive pipeline.</span></span>  
  
2.  <span data-ttu-id="ea95b-186">FILE 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-186">Create a FILE send port.</span></span> <span data-ttu-id="ea95b-187">このポートは、SQL Server データベースからの応答メッセージをフォルダーに削除されます。</span><span class="sxs-lookup"><span data-stu-id="ea95b-187">This port will drop the response message from the SQL Server database to a folder.</span></span> <span data-ttu-id="ea95b-188">使用して、**フィルター**  タブのポートのプロパティ ダイアログ ボックスには、Wcf-custom 送信ポートからすべての応答メッセージを受信する FILE 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-188">Using the **Filters** tab of the port properties dialog box, configure the FILE send port to receive all response messages from the WCF-Custom send port.</span></span>  
  
    1.  <span data-ttu-id="ea95b-189">**送信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウからをクリックして**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-189">In the **Send Port Properties** dialog box, from the left pane, click **Filters**.</span></span>  
  
    2.  <span data-ttu-id="ea95b-190">右側のペインで下にある、**プロパティ**列では、グリッドをクリックし、 **BTS です。SPName**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ea95b-190">In the right pane, under the **Property** column, click the grid, and then select **BTS.SPName** property.</span></span>  
  
    3.  <span data-ttu-id="ea95b-191">**演算子**列で、"**==**"です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-191">For the **Operator** column, select “**==**”.</span></span>  
  
    4.  <span data-ttu-id="ea95b-192">**値**列で、送信ポート、WCF カスタムの名前を指定して`ExecProcedure`です。</span><span class="sxs-lookup"><span data-stu-id="ea95b-192">For the **Value** column, specify the name of the WCF-Custom send port, `ExecProcedure`.</span></span>  
  
 <span data-ttu-id="ea95b-193">3 つすべてのポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-193">Start all the three ports.</span></span> <span data-ttu-id="ea95b-194">受信場所がファイルにマップされているフォルダーに XML ファイルのコピー。</span><span class="sxs-lookup"><span data-stu-id="ea95b-194">Copy an XML file to the folder mapped to the FILE receive location.</span></span> <span data-ttu-id="ea95b-195">FILE 送信ポートにマップされているフォルダーに応答を探します。</span><span class="sxs-lookup"><span data-stu-id="ea95b-195">Look for the response in the folder mapped to the FILE send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea95b-196">参照</span><span class="sxs-lookup"><span data-stu-id="ea95b-196">See Also</span></span>  
[<span data-ttu-id="ea95b-197">SQL アダプターを使用して BizTalk アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="ea95b-197">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)
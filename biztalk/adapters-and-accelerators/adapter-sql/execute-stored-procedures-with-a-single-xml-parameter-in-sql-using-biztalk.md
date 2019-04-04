---
title: BizTalk Server を使用して SQL Server での XML パラメーターを 1 つのストアド プロシージャの実行 |Microsoft Docs
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
ms.openlocfilehash: a71ee5be554393db10e65adb49694e7104bb011b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976925"
---
# <a name="execute-stored-procedures-with-a-single-xml-parameter-in-sql-server-using-biztalk-server"></a><span data-ttu-id="607a5-103">BizTalk Server を使用して SQL Server での XML パラメーターを 1 つのストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="607a5-103">Execute stored procedures with a single XML parameter in SQL Server using BizTalk Server</span></span>
<span data-ttu-id="607a5-104">1 つのパラメーターを受け取るストアド プロシージャを実行するは」の説明に従って、他のストアド プロシージャの実行に似ています[BizTalk Server を使用して SQL Server でのストアド プロシージャの実行](execute-stored-procedures-in-sql-server-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="607a5-104">Executing a stored procedure that takes a single parameter is similar to executing any other stored procedure as described in [Execute Stored Procedures in SQL Server using BizTalk Server](execute-stored-procedures-in-sql-server-using-biztalk-server.md).</span></span> <span data-ttu-id="607a5-105">ただし、上記のリンクで説明されているアプローチのデザイン時にストアド プロシージャのメタデータを生成し、実行時に、プロシージャを呼び出すオーケストレーションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="607a5-105">However, for the approach described in the preceding link, you need to generate metadata for the stored procedure at design time and create an orchestration to invoke the procedure at run time.</span></span>  
  
 <span data-ttu-id="607a5-106">その値に対して、処理を実行せずにストアド プロシージャを 1 つ 1 つの値を渡すだけする場所のシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="607a5-106">Consider a scenario where you just want to pass one single value to a stored procedure without doing any processing on that value.</span></span> <span data-ttu-id="607a5-107">このような場合、メタデータの生成、オーケストレーションを作成、オーケストレーションを展開して、操作の実行のオーバーヘッドは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="607a5-107">In such cases, you don't want the overhead of generating metadata, creating an orchestration, deploying the orchestration, and executing the operation.</span></span> <span data-ttu-id="607a5-108">代わりに、ストアド プロシージャを直接起動するには、Wcf-custom または WCF-SQL 送信ポートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="607a5-108">Rather, you can configure a WCF-Custom or WCF-SQL send port to directly invoke the stored procedure.</span></span> <span data-ttu-id="607a5-109">このトピックを使用してこれらのタスクを実行する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="607a5-109">This topic demonstrates how to perform these tasks using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="607a5-110">このトピックでは、Wcf-custom を構成する方法についての送信ポートを 1 つのパラメーターを受け取るストアド プロシージャの実行を提供します。</span><span class="sxs-lookup"><span data-stu-id="607a5-110">This topic provides instructions on how to configure a WCF-Custom send port for executing stored procedure that takes a single parameter.</span></span> <span data-ttu-id="607a5-111">WCF SQL ポートを構成することで、同じ手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="607a5-111">You can perform the same steps by configuring a WCF-SQL port.</span></span> <span data-ttu-id="607a5-112">WCF SQL ポートを構成する方法の詳細については、[WCF-SQL アダプターを使用してポートを構成する](configure-a-port-using-the-wcf-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="607a5-112">For instructions on configuring WCF-SQL port, see [Configure a Port using the WCF-SQL Adapter](configure-a-port-using-the-wcf-sql-adapter.md).</span></span>  
  
## <a name="invoke-stored-procedures-without-orchestration"></a><span data-ttu-id="607a5-113">指揮なしのストアド プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="607a5-113">Invoke stored procedures without orchestration</span></span>  
 <span data-ttu-id="607a5-114">オーケストレーションなしの 1 つのパラメーターを使用したストアド プロシージャを実行する方法を説明するためには、このトピックでは、ADD_LAST_EMP_XML_INFO ストアド プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="607a5-114">To demonstrate how to execute stored procedures with single parameters without an orchestration, this topic uses the ADD_LAST_EMP_XML_INFO stored procedure.</span></span> <span data-ttu-id="607a5-115">この手順を XML 値をパラメーターとして受け取りに挿入します、**アドレス**の列、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="607a5-115">This procedure takes an XML value as a parameter and inserts it into the **Address** column of the **Employee** table.</span></span> <span data-ttu-id="607a5-116">ストアド プロシージャに渡す XML 値が必要です。</span><span class="sxs-lookup"><span data-stu-id="607a5-116">You must have the XML value that you will pass to the stored procedure.</span></span> <span data-ttu-id="607a5-117">ただし、アダプターを使用してストアド プロシージャを実行するには、プロシージャのスキーマに準拠した要求メッセージを送信する必要があります、値、XML が含まれる、**アドレス**フィールドでは、SQL Server にします。</span><span class="sxs-lookup"><span data-stu-id="607a5-117">However, to execute the stored procedure using the adapter, you must send a request message conforming to the schema of the procedure, and containing the XML value for the **Address** field, to the SQL Server.</span></span> <span data-ttu-id="607a5-118">そのため、によってその要求メッセージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="607a5-118">So, you must create that request message by:</span></span>  
  
- <span data-ttu-id="607a5-119">使用して、**テンプレート**メッセージ テンプレートを使用して要求メッセージを作成することができますを使用して送信ポートの構成オプション。</span><span class="sxs-lookup"><span data-stu-id="607a5-119">Using the **Template** option in the send port configuration using which you can create a request message using a message template.</span></span>  
  
- <span data-ttu-id="607a5-120">値、xml、**アドレス**フィールドをメッセージにします。</span><span class="sxs-lookup"><span data-stu-id="607a5-120">Putting the XML value for the **Address** field into the message.</span></span>  
  
  <span data-ttu-id="607a5-121">これらすべての手順については、このトピックで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="607a5-121">All these steps are described in detail in this topic.</span></span> <span data-ttu-id="607a5-122">次の一連のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="607a5-122">You must perform the following set of tasks:</span></span>  
  
1. <span data-ttu-id="607a5-123">ファイルを作成する受信ポートに挿入される XML ファイルをドロップする場所、**アドレス**の XML フィールド、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="607a5-123">Create a FILE receive port where you will drop the XML file that will be inserted into the **Address** XML field of the **Employee** table.</span></span> <span data-ttu-id="607a5-124">このポートを呼び出すと**MessageIn**ポート。</span><span class="sxs-lookup"><span data-stu-id="607a5-124">Suppose this port is called **MessageIn** port.</span></span>  
  
2. <span data-ttu-id="607a5-125">XML ファイルは、ファイルから取得受信ポート、メッセージ テンプレートを使用して、メッセージを作成、ストアド プロシージャを実行する SQL Server に送信します Wcf-custom の一方向の送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="607a5-125">Create a WCF-Custom one-way send port that picks the XML file from the FILE receive port, constructs the message using the message template, and sends it to SQL Server to execute the stored procedure.</span></span>  
  
   <span data-ttu-id="607a5-126">Wcf-custom を構成する手順については、メッセージ テンプレートを使用してポートを送信、トピックのこの部分を提供します。</span><span class="sxs-lookup"><span data-stu-id="607a5-126">This part of the topic provides instructions on configuring a WCF-Custom send port with the message template.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="607a5-127">場合でも、このトピックの情報は、1 つの XML パラメーターでストアド プロシージャを実行する方法を示します、任意のデータ型の 1 つのパラメーターを受け取るすべての操作を実行するタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="607a5-127">Even though the information in this topic demonstrates how to execute a stored procedure with a single XML parameter, you can perform the tasks to perform any operation that takes a single parameter of any data type.</span></span> <span data-ttu-id="607a5-128">唯一の違いは、特定の操作のメッセージ テンプレートを作成する方法になります。</span><span class="sxs-lookup"><span data-stu-id="607a5-128">The only difference will be in the way you create a message template for a specific operation.</span></span> <span data-ttu-id="607a5-129">メッセージ テンプレートを作成するには、操作の実行を使用して要求メッセージを取得して、オーケストレーションを使用して、パラメーターの値に置き換えて、BizTalk メッセージ本文。</span><span class="sxs-lookup"><span data-stu-id="607a5-129">You can create a message template by taking the request message you would use to execute the operation using an orchestration and replacing the value of the parameter with the BizTalk message body.</span></span>  
  
##  <a name="BKMK_OneWay"></a> <span data-ttu-id="607a5-130">Wcf-custom 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="607a5-130">Configure a WCF-Custom send port</span></span>  
 <span data-ttu-id="607a5-131">WCF カスタムを作成する前に、送信ポート、ファイルを作成することを確認の受信ポート、 **MessageIn**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-131">Before creating the WCF-Custom send port, make sure you created the FILE receive port, **MessageIn**.</span></span>  
  
1. <span data-ttu-id="607a5-132">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="607a5-132">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="607a5-133">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-133">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="607a5-134">展開するアプリケーションを展開し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="607a5-134">Expand the application under which you want to deploy the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
4. <span data-ttu-id="607a5-135">右クリックして**送信ポート**、 をポイント**新規**、順にポイント**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-135">Right-click **Send Ports**, point to **New**, and then point to **Static One-way Send Port**.</span></span>  
  
5. <span data-ttu-id="607a5-136">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="607a5-136">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="607a5-137">すべてを受信するポートを構成ファイルで破棄されたメッセージの受信ポート、 **MessageIn**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-137">Configure the port to receive all messages dropped at the FILE receive port, **MessageIn**.</span></span>  
  
   1.  <span data-ttu-id="607a5-138">**送信ポートのプロパティ** ダイアログ ボックスで、左側のウィンドウからクリックして**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-138">In the **Send Port Properties** dialog box, from the left pane, click **Filters**.</span></span>  
  
   2.  <span data-ttu-id="607a5-139">右側のウィンドウで 、**プロパティ**列では、グリッドをクリックし、 **BTS します。ReceivePortName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="607a5-139">In the right pane, under the **Property** column, click the grid, and then select **BTS.ReceivePortName** property.</span></span>  
  
   3.  <span data-ttu-id="607a5-140">**演算子**列で、"**==**"。</span><span class="sxs-lookup"><span data-stu-id="607a5-140">For the **Operator** column, select “**==**”.</span></span>  
  
   4.  <span data-ttu-id="607a5-141">**値**列で、指定のファイルの名前の受信ポート、 `MessageIn`。</span><span class="sxs-lookup"><span data-stu-id="607a5-141">For the **Value** column, specify the name of the FILE receive port, `MessageIn`.</span></span>  
  
7. <span data-ttu-id="607a5-142">**送信ポートのプロパティ** ダイアログ ボックスの 、**全般** タブから、**型**ドロップダウン リストで、 **Wcf-custom**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-142">In the **Send Port Properties** dialog box, on the **General** tab, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="607a5-143">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="607a5-143">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="607a5-144">をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドで、SQL Server の接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="607a5-144">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for SQL Server.</span></span> <span data-ttu-id="607a5-145">接続 URI の詳細については、[SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="607a5-145">For more information about the connection URI, see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="607a5-146">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="607a5-146">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="607a5-147">参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)の各操作のアクションの一覧。</span><span class="sxs-lookup"><span data-stu-id="607a5-147">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) for a list of actions for each operation.</span></span> <span data-ttu-id="607a5-148">たとえば、ADD_LAST_EMP_XML_INFO を呼び出すアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="607a5-148">For example, the action to invoke the ADD_LAST_EMP_XML_INFO is:</span></span>  
  
      ```  
      Procedure/dbo/ADD_LAST_EMP_XML_INFO  
      ```  
  
   3. <span data-ttu-id="607a5-149">をクリックして、**バインド**] タブとの間、**バインドの種類**一覧で、[ **sqlBinding**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-149">Click the **Binding** tab, and from the **Binding Type** list, select **sqlBinding**.</span></span> <span data-ttu-id="607a5-150">によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="607a5-150">You can specify the different binding properties exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="607a5-151">バインド プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="607a5-151">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
   4. <span data-ttu-id="607a5-152">をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="607a5-152">Click the **Credentials** tab, and then do one of the following:</span></span>  
  
      -   <span data-ttu-id="607a5-153">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名の指定とパスワードを SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="607a5-153">Select the **Do not use Single Sign-On** option, and the specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="607a5-154">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="607a5-154">Note that the user name and password are case-sensitive.</span></span>  
  
          > [!NOTE]
          >  <span data-ttu-id="607a5-155">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="607a5-155">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span>  
  
      -   <span data-ttu-id="607a5-156">選択、**使用してシングル サインオン**オプション、し、関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="607a5-156">Select the **Use Single Sign-On** option, and then specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
           <span data-ttu-id="607a5-157">BizTalk Server に関するセキュリティの詳細については、[SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="607a5-157">For more information about security with respect to BizTalk Server, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).</span></span>
  
   5. <span data-ttu-id="607a5-158">をクリックして、**メッセージ** タブで、および、**送信 WCF メッセージ本文**セクションで、選択、**テンプレート**オプション。</span><span class="sxs-lookup"><span data-stu-id="607a5-158">Click the **Messages** tab, and in the **Outbound WCF message body** section, choose the **Template** option.</span></span>  
  
   6. <span data-ttu-id="607a5-159">**XML**テキスト ボックスに、WCF メッセージの構築に使用されるテンプレートを指定します。</span><span class="sxs-lookup"><span data-stu-id="607a5-159">In the **XML** text box, specify the template that will be used to construct the WCF message.</span></span> <span data-ttu-id="607a5-160">これにより、WCF ベースの ADD_LAST_EMP_XML_INFO 操作に準拠したメッセージを作成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="607a5-160">By doing so, you create a message that conforms to the ADD_LAST_EMP_XML_INFO operation for the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
       <span data-ttu-id="607a5-161">![送信 WCF メッセージのテンプレートを指定](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")</span><span class="sxs-lookup"><span data-stu-id="607a5-161">![Specify template for outbound WCF message](../../adapters-and-accelerators/adapter-sql/media/012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55.gif "012e9ff0-b78f-4a1d-8a3a-a7b8e3850d55")</span></span>  
  
       <span data-ttu-id="607a5-162">ADD_LAST_EMP_XML_INFO ストアド プロシージャで、次のテンプレートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="607a5-162">For the ADD_LAST_EMP_XML_INFO stored procedure, you must specify the following template:</span></span>  
  
      ```  
      <ADD_LAST_EMP_XML_INFO xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/dbo">  
      <xml_info>  
      <bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/>  
      </xml_info>  
      </ADD_LAST_EMP_XML_INFO>  
      ```  
  
      > [!IMPORTANT]
      >  <span data-ttu-id="607a5-163">メッセージ テンプレートでのエンコードと、"string"の送信ポートを使用して呼び出される操作のパラメーターの種類に関係なく常にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="607a5-163">The encoding in the message template must always be “string” irrespective of the type of the parameter for the operation that will be invoked using the send port.</span></span> <span data-ttu-id="607a5-164">たとえば、ADD_LAST_EMP_XML_INFO は、XML 型のパラメーターを受け取りますが、文字列は、メッセージのテンプレートでのエンコードします。</span><span class="sxs-lookup"><span data-stu-id="607a5-164">For example, the ADD_LAST_EMP_XML_INFO takes a parameter of type XML, but the encoding in the message template is string.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="607a5-165">ストアド プロシージャの要求メッセージをコピーして、< xml_info > タグ内の値に置き換えて、BizTalk メッセージ本文では、このメッセージ テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="607a5-165">You can create this message template by copying the request message for the stored procedure and replacing the value within the <xml_info> tags with the BizTalk message body.</span></span> <span data-ttu-id="607a5-166">使用してプロシージャのスキーマを生成することによって、ストアド プロシージャの要求メッセージを取得できます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、要求の XML を取得するスキーマのインスタンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="607a5-166">You can get the request message for the stored procedure by generating the schema for the procedure using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], and then generating an instance of the schema to get the request XML.</span></span>  
  
   7. <span data-ttu-id="607a5-167">戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="607a5-167">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="607a5-168">**送信ハンドラー**一覧で、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-168">From the **Send handler** list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="607a5-169">**送信パイプライン**に対応するパイプラインを選択リストで、 **PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-169">From the **Send pipeline** list, select the pipeline that corresponds to **PassThruTransmit**.</span></span>  
  
11. <span data-ttu-id="607a5-170">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="607a5-170">Click **OK**.</span></span>  
  
## <a name="start-the-application"></a><span data-ttu-id="607a5-171">アプリケーションを起動します</span><span class="sxs-lookup"><span data-stu-id="607a5-171">Start the Application</span></span>  
 <span data-ttu-id="607a5-172">BizTalk アプリケーションを開始するには、両方のファイルを開始する受信場所と、Wcf-custom 送信ポートを個別にします。</span><span class="sxs-lookup"><span data-stu-id="607a5-172">To start the BizTalk application, you can start both the FILE receive location and the WCF-Custom send port individually.</span></span> <span data-ttu-id="607a5-173">これで、受信場所のファイルにマップされているフォルダーに XML ファイルをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="607a5-173">You must now copy an XML file to the folder mapped to the FILE receive location.</span></span> <span data-ttu-id="607a5-174">BizTalk アプリケーションが、ファイルを使用して、XML 値は、Employee テーブルの [アドレス] 列に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="607a5-174">The BizTalk application consumes the file, and the XML value is inserted in the Address column of the Employee table.</span></span> <span data-ttu-id="607a5-175">これは、SQL Server クライアントを使用して、Employee テーブルからレコードを選択して確認できます。</span><span class="sxs-lookup"><span data-stu-id="607a5-175">You can verify this by using a SQL Server client and selecting records from the Employee table.</span></span>  
  
## <a name="using-a-two-way-wcf-custom-send-port"></a><span data-ttu-id="607a5-176">双方向の Wcf-custom 送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="607a5-176">Using a Two-way WCF-Custom Send Port</span></span>  
 <span data-ttu-id="607a5-177">このトピックで、セクションの指示[Wcf-custom 送信ポートを構成する方法](../../core/how-to-configure-a-wcf-custom-send-port.md)BizTalk を使用しなくても 1 つのパラメーターを持つストアド プロシージャを実行する一方向の Wcf-custom 送信ポートを構成する方法を示しますオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="607a5-177">The instructions in this topic, under the section [How to Configure a WCF-Custom Send Port](../../core/how-to-configure-a-wcf-custom-send-port.md), demonstrate how to configure a one-way WCF-Custom send port to execute a stored procedure with a single parameter without using a BizTalk orchestration.</span></span> <span data-ttu-id="607a5-178">ただし、このような場合は、ストアド プロシージャを実行するかどうかを確認する正常にする必要がある SQL Server データベースの Employee テーブルの [アドレス] 列が更新されるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="607a5-178">However, in such a case, to verify whether the stored procedure is executed successfully you will have to verify in the SQL Server database whether the Address column in the Employee table is updated.</span></span>  
  
 <span data-ttu-id="607a5-179">代わりに、ストアド プロシージャが正常に実行される場合も SQL Server からの応答を取得する双方向の Wcf-custom 送信ポートを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="607a5-179">Instead, you can create a two-way WCF-Custom send port that also gets the response from SQL Server if the stored procedure is executed successfully.</span></span> <span data-ttu-id="607a5-180">双方向の WCF カスタム ポートを作成する場合、いくつか追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="607a5-180">You must perform a few additional steps if you create a two-way WCF-Custom port.</span></span> <span data-ttu-id="607a5-181">ファイルが必要がありますに注意してくださいでは、上記の手順で説明したように、場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="607a5-181">Note that you will still need a FILE receive location, as mentioned in the preceding instructions.</span></span>  
  
1. <span data-ttu-id="607a5-182">たとえば、双方向の Wcf-custom 送信ポートを作成**ExecProcedure**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-182">Create a two-way WCF-Custom send port, for example, **ExecProcedure**.</span></span> <span data-ttu-id="607a5-183">送信ポートを構成する手順は、一方向の送信ポートの場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="607a5-183">The steps to configure the send port are similar to those for the one-way send port.</span></span> <span data-ttu-id="607a5-184">唯一の違いは、双方向のポートにする必要がありますも指定する受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="607a5-184">The only difference is that for the two-way port you must also specify a receive pipeline.</span></span> <span data-ttu-id="607a5-185">選択するかどうかを確認**PassThruReceive**受信パイプラインの。</span><span class="sxs-lookup"><span data-stu-id="607a5-185">Make sure you select **PassThruReceive** for the receive pipeline.</span></span>  
  
2. <span data-ttu-id="607a5-186">ファイル送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="607a5-186">Create a FILE send port.</span></span> <span data-ttu-id="607a5-187">フォルダーに SQL Server データベースから、このポートは、応答メッセージをドロップします。</span><span class="sxs-lookup"><span data-stu-id="607a5-187">This port will drop the response message from the SQL Server database to a folder.</span></span> <span data-ttu-id="607a5-188">使用して、**フィルター**  タブのポートのプロパティ ダイアログ ボックスで、Wcf-custom 送信ポートからすべての応答メッセージを受信する FILE 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="607a5-188">Using the **Filters** tab of the port properties dialog box, configure the FILE send port to receive all response messages from the WCF-Custom send port.</span></span>  
  
   1.  <span data-ttu-id="607a5-189">**送信ポートのプロパティ** ダイアログ ボックスで、左側のウィンドウからクリックして**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="607a5-189">In the **Send Port Properties** dialog box, from the left pane, click **Filters**.</span></span>  
  
   2.  <span data-ttu-id="607a5-190">右側のウィンドウで 、**プロパティ**列では、グリッドをクリックし、 **BTS します。SPName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="607a5-190">In the right pane, under the **Property** column, click the grid, and then select **BTS.SPName** property.</span></span>  
  
   3.  <span data-ttu-id="607a5-191">**演算子**列で、"**==**"。</span><span class="sxs-lookup"><span data-stu-id="607a5-191">For the **Operator** column, select “**==**”.</span></span>  
  
   4.  <span data-ttu-id="607a5-192">**値**列で、送信ポートの WCF カスタムの名前を指定`ExecProcedure`します。</span><span class="sxs-lookup"><span data-stu-id="607a5-192">For the **Value** column, specify the name of the WCF-Custom send port, `ExecProcedure`.</span></span>  
  
   <span data-ttu-id="607a5-193">3 つすべてのポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="607a5-193">Start all the three ports.</span></span> <span data-ttu-id="607a5-194">コピーをファイルにマップされているフォルダーに XML ファイルの受信場所。</span><span class="sxs-lookup"><span data-stu-id="607a5-194">Copy an XML file to the folder mapped to the FILE receive location.</span></span> <span data-ttu-id="607a5-195">FILE 送信ポートにマップされたフォルダー内の応答を参照してください。</span><span class="sxs-lookup"><span data-stu-id="607a5-195">Look for the response in the folder mapped to the FILE send port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607a5-196">参照</span><span class="sxs-lookup"><span data-stu-id="607a5-196">See Also</span></span>  
[<span data-ttu-id="607a5-197">SQL アダプターを使用して BizTalk アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="607a5-197">Develop BizTalk applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)
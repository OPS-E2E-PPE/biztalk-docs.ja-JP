---
title: SQL Server 接続 URI の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 688e2215-a4d8-4f55-a37c-7d91c3de080f
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c58812b9fc3404b9922cf05c84717f3c95e05435
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007579"
---
# <a name="create-the-sql-server-connection-uri"></a><span data-ttu-id="f6628-102">SQL Server 接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="f6628-102">Create the SQL Server connection URI</span></span>
<span data-ttu-id="f6628-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]接続 URI には、アダプターが SQL Server データベースへの接続を確立するために使用するプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6628-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] connection URI contains properties that the adapter uses to establish a connection to the SQL Server database.</span></span> <span data-ttu-id="f6628-104">このトピックでは、SQL Server の接続 URI、に関する情報を提供し、その他のさまざまなプログラミング シナリオで URI を指定する方法を説明するトピックへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="f6628-104">This topic provides information about the SQL Server connection URI, and provides links to other topics that explain how to specify a URI in different programming scenarios.</span></span>  
  
##  <a name="FailoverPartner"></a> <span data-ttu-id="f6628-105">SQL アダプターの接続 URI</span><span class="sxs-lookup"><span data-stu-id="f6628-105">The Connection URI for the SQL Adapter</span></span>  
 <span data-ttu-id="f6628-106">一般的なエンドポイント アドレスで WCF の URI として表されます。 `scheme://hostinfoparams?query_string`、場所。</span><span class="sxs-lookup"><span data-stu-id="f6628-106">A typical endpoint address URI in WCF is represented as: `scheme://hostinfoparams?query_string`, where:</span></span>  
  
- <span data-ttu-id="f6628-107">スキームは、スキームの名前です。</span><span class="sxs-lookup"><span data-stu-id="f6628-107">scheme is the scheme name.</span></span>  
  
- <span data-ttu-id="f6628-108">hostinfoparams はホストへの接続を確立するために必要な情報は、します。たとえば、サーバー名です。</span><span class="sxs-lookup"><span data-stu-id="f6628-108">hostinfoparams is information required to establish the connection to the host; for example, a server name.</span></span>  
  
- <span data-ttu-id="f6628-109">クエリ文字列は、疑問符 (?) で区切られたパラメーターのオプションの名前と値のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="f6628-109">query_string is an optional name-value collection of parameters delimited by a question mark (?).</span></span>  
  
  <span data-ttu-id="f6628-110">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI はこの基本的な形式に従います、次のように実装されます。</span><span class="sxs-lookup"><span data-stu-id="f6628-110">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] connection URI adheres to this basic format and is implemented as follows:</span></span>  
  
```  
  
mssql://[Server_Name[:Portno]]/[Database_Instance_Name]/[Database_Name]?FailoverPartner=[Partner_Server_Name]&InboundId=[Inbound_ID]  
```  
  
 <span data-ttu-id="f6628-111">ここで、`mssql`用 SQL Server の接続 URI のスキームです。</span><span class="sxs-lookup"><span data-stu-id="f6628-111">where, `mssql` is the scheme for the SQL Server connection URI.</span></span>  
  
 <span data-ttu-id="f6628-112">次の表では、接続 URI に含まれるプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f6628-112">The following table explains the properties contained in the connection URI.</span></span>  
  
|<span data-ttu-id="f6628-113">接続 URI のプロパティ</span><span class="sxs-lookup"><span data-stu-id="f6628-113">Connection URI Property</span></span>|<span data-ttu-id="f6628-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f6628-114">Category</span></span>|<span data-ttu-id="f6628-115">説明</span><span class="sxs-lookup"><span data-stu-id="f6628-115">Description</span></span>|  
|-----------------------------|--------------|-----------------|  
|<span data-ttu-id="f6628-116">[サーバー名]</span><span class="sxs-lookup"><span data-stu-id="f6628-116">[SERVER_NAME]</span></span>|<span data-ttu-id="f6628-117">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="f6628-117">hostinfoparams</span></span>|<span data-ttu-id="f6628-118">SQL Server がインストールされているサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="f6628-118">Name of the server on which SQL Server is installed.</span></span> <span data-ttu-id="f6628-119">値を指定しない場合、アダプターは、サーバー名として"localhost"を前提としていて、ローカル サーバー上の SQL Server データベースとの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="f6628-119">If you do not specify a value, the adapter assumes the server name as “localhost” and establishes a connection with the SQL Server database on the local server.</span></span>|  
|<span data-ttu-id="f6628-120">[PORTNO]</span><span class="sxs-lookup"><span data-stu-id="f6628-120">[PORTNO]</span></span>|<span data-ttu-id="f6628-121">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="f6628-121">hostinfoparams</span></span>|<span data-ttu-id="f6628-122">接続が確立されているポート番号。</span><span class="sxs-lookup"><span data-stu-id="f6628-122">The port number where the connection is established.</span></span> <span data-ttu-id="f6628-123">値を指定しない場合、アダプターは、既定のポートを介して接続します。</span><span class="sxs-lookup"><span data-stu-id="f6628-123">If you do not specify a value, the adapter connects through the default port.</span></span>|  
|<span data-ttu-id="f6628-124">[データベース インスタンス名]</span><span class="sxs-lookup"><span data-stu-id="f6628-124">[DATABASE_INSTANCE_NAME]</span></span>|<span data-ttu-id="f6628-125">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="f6628-125">hostinfoparams</span></span>|<span data-ttu-id="f6628-126">接続に SQL Server インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="f6628-126">Name of the SQL Server instance to connect to.</span></span> <span data-ttu-id="f6628-127">値を指定しない場合、アダプターは、既定のデータベース インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="f6628-127">If you do not specify a value, the adapter connects to the default database instance.</span></span>|  
|<span data-ttu-id="f6628-128">[DATABASE_NAME]</span><span class="sxs-lookup"><span data-stu-id="f6628-128">[DATABASE_NAME]</span></span>|<span data-ttu-id="f6628-129">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="f6628-129">hostinfoparams</span></span>|<span data-ttu-id="f6628-130">接続するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f6628-130">Name of the database to connect to.</span></span> <span data-ttu-id="f6628-131">値を指定しない場合、アダプターは、既定のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="f6628-131">If you do not specify a value, the adapter connects to the default database.</span></span>|  
|<span data-ttu-id="f6628-132">[PARTNER_SERVER_NAME]</span><span class="sxs-lookup"><span data-stu-id="f6628-132">[PARTNER_SERVER_NAME]</span></span>|<span data-ttu-id="f6628-133">query_string</span><span class="sxs-lookup"><span data-stu-id="f6628-133">query_string</span></span>|<span data-ttu-id="f6628-134">場合に、プライマリ SQL Server データベースの接続にフェールオーバーの SQL Server データベースの名前は使用できません。</span><span class="sxs-lookup"><span data-stu-id="f6628-134">Name of the failover SQL Server database to connect to if the primary SQL Server database is not available.</span></span> <span data-ttu-id="f6628-135">高可用性の SQL Server についての詳細については、[SQL Server データベースのミラーリング](https://msdn.microsoft.com/library/5h52hef8.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6628-135">For more information about high availability with respect to SQL Server, see [Database Mirroring in SQL Server](https://msdn.microsoft.com/library/5h52hef8.aspx).</span></span>|  
|<span data-ttu-id="f6628-136">[INBOUND_ID]</span><span class="sxs-lookup"><span data-stu-id="f6628-136">[INBOUND_ID]</span></span>|<span data-ttu-id="f6628-137">query_string</span><span class="sxs-lookup"><span data-stu-id="f6628-137">query_string</span></span>|<span data-ttu-id="f6628-138">接続して一意の URI に追加するための識別子です。</span><span class="sxs-lookup"><span data-stu-id="f6628-138">An identifier that you add to the connection URI to make it unique.</span></span> <span data-ttu-id="f6628-139">メタデータを生成する場合は、この接続のパラメーターを指定する必要があります、 **TypedPolling**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="f6628-139">You must provide this connection parameter if you want to generate metadata for the **TypedPolling** inbound operation.</span></span> <span data-ttu-id="f6628-140">また、BizTalk アプリケーションでは、複数の受信場所が、同じデータベースをポーリングした場合受信 ID が、接続をアダプター クライアント異なる上の同じデータベースからポーリング メッセージを受信できるように一意である URI の受信場所。</span><span class="sxs-lookup"><span data-stu-id="f6628-140">Also, in a BizTalk application, if you have multiple receive locations polling the same database, the inbound ID makes the connection URI unique, thereby enabling adapter clients to receive polling messages from the same database on different receive locations.</span></span> <span data-ttu-id="f6628-141">詳細については、[受信ポーリング メッセージ間で複数受信ポートから BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6628-141">For more information, see [Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f6628-142">これらの接続文字列プロパティの詳細については、[SqlConnection.ConnectionString プロパティ](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6628-142">For more information about these connection string properties, see [SqlConnection.ConnectionString Property](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx).</span></span>
  
## <a name="sql-server-credentials-and-the-connection-uri"></a><span data-ttu-id="f6628-143">SQL Server 資格情報と接続 URI</span><span class="sxs-lookup"><span data-stu-id="f6628-143">SQL Server Credentials and the Connection URI</span></span>  
 <span data-ttu-id="f6628-144">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI で指定する資格情報をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f6628-144">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support specifying credentials in the connection URI.</span></span> <span data-ttu-id="f6628-145">使用するアプリケーションで資格情報の指定の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6628-145">For more information about specifying credentials in your applications that use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Secure your SQL applications](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).</span></span>  
  
## <a name="using-special-characters-in-the-connection-uri"></a><span data-ttu-id="f6628-146">接続 URI で特殊文字の使用</span><span class="sxs-lookup"><span data-stu-id="f6628-146">Using Special Characters in the Connection URI</span></span>  
 <span data-ttu-id="f6628-147">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続パラメーター値のいずれかの特殊文字を含む URI を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6628-147">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support specifying a connection URI that has special characters for any of the parameter values.</span></span> <span data-ttu-id="f6628-148">接続パラメーターの値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="f6628-148">If the connection parameter values contain special characters, make sure you do one of the following:</span></span>  
  
- <span data-ttu-id="f6628-149">URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せず。</span><span class="sxs-lookup"><span data-stu-id="f6628-149">If you are specifying the URI in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] using [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="f6628-150">直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、特殊文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6628-150">If you specify the URI directly in the **Configure a URI** field and the connection parameters contain special characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
   <span data-ttu-id="f6628-151">たとえば、URI の接続に名前を持つパラメーター `sql server`、として指定する必要があります`sql%20server`します。</span><span class="sxs-lookup"><span data-stu-id="f6628-151">For example, if the connection URI has a parameter with name `sql server`, you must specify it as `sql%20server`.</span></span>  
  
- <span data-ttu-id="f6628-152">送信の作成中に、URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、特殊文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6628-152">If you are specifying the URI while creating a send or receive port in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, and the connection parameters contain special characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
## <a name="using-the-connection-uri-to-connect-to-the-sql-server-database"></a><span data-ttu-id="f6628-153">SQL Server データベースに接続する接続 URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6628-153">Using the Connection URI to Connect to the SQL Server Database</span></span>  
 <span data-ttu-id="f6628-154">次に、サンプルの接続 URI の[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f6628-154">The following is a sample connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
```  
mssql://sql_server/sql_server_instance//  
```  
  
 <span data-ttu-id="f6628-155">前の例では、"sql_server"は、SQL Server がインストールされている"sql_server_instance"に接続するデータベース インスタンスの名前には、コンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="f6628-155">In the preceding example, “sql_server” is the name of the computer on which SQL Server is installed whereas “sql_server_instance” is the name of the database instance to connect to.</span></span> <span data-ttu-id="f6628-156">データベース名が指定されていないため、アダプターは、既定のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="f6628-156">Because no database name is specified, the adapter will connect to the default database.</span></span>  
  
 <span data-ttu-id="f6628-157">接続と同じコンピューターに SQL Server データベースがインストールされている URI の例を次に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f6628-157">The following is an example of a connection URI where the SQL Server database is installed on the same computer as the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="f6628-158">この例では、アダプターは、"my_database"ローカル コンピューターの"sql_server_instance"データベース インスタンスのデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="f6628-158">In this example, the adapter connects to the database “my_database” for the “sql_server_instance” database instance on the local computer.</span></span>  
  
```  
mssql://localhost/sql_server_instance/my_database/  
```  
  
 <span data-ttu-id="f6628-159">この例では、アダプターは、ローカル コンピューターで実行されている既定のインスタンスの既定のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="f6628-159">In this example, the adapter connects to the default database for the default instance running on the local computer.</span></span>  
  
```  
mssql://localhost///  
```  
  
 <span data-ttu-id="f6628-160">SQL Server への接続を指定する方法についてはデータベースの場合にします。</span><span class="sxs-lookup"><span data-stu-id="f6628-160">For information about how to specify a connection to the SQL Server database when you:</span></span>  
  
- <span data-ttu-id="f6628-161">使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6628-161">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], see [Connect to SQL Server in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="f6628-162">送信ポートを構成または BizTalk Server ソリューションでの受信ポート (場所) を参照してください[SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6628-162">Configure a send port or receive port (location) in a BizTalk Server solution, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span>
  
- <span data-ttu-id="f6628-163">プログラミング ソリューションで WCF チャネル モデルを使用して、参照してください[SQL アダプターを使用してチャネルを作成](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="f6628-163">Use the WCF channel model in a programming solution, see [Create a channel using the SQL adapter](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="f6628-164">プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[クライアント バインディングを構成、SQL アダプターの](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6628-164">Use the WCF service model in a programming solution, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6628-165">参照</span><span class="sxs-lookup"><span data-stu-id="f6628-165">See Also</span></span>  
[<span data-ttu-id="f6628-166">SQL アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="f6628-166">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)
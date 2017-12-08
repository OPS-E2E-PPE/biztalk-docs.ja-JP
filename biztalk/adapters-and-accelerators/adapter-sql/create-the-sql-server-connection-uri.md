---
title: "SQL Server 接続 URI を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 688e2215-a4d8-4f55-a37c-7d91c3de080f
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f31b6d6919924d3bb4bb1ac6c817c3f3b3d77dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-the-sql-server-connection-uri"></a><span data-ttu-id="e2dba-102">SQL Server の接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-102">Create the SQL Server connection URI</span></span>
<span data-ttu-id="e2dba-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]接続 URI には、アダプターは、SQL Server データベースへの接続を確立するために使用するプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2dba-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] connection URI contains properties that the adapter uses to establish a connection to the SQL Server database.</span></span> <span data-ttu-id="e2dba-104">このトピックでは、SQL Server の接続 URI、に関する情報を提供し、その他のさまざまなプログラミング シナリオでの URI を指定する方法を説明するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-104">This topic provides information about the SQL Server connection URI, and provides links to other topics that explain how to specify a URI in different programming scenarios.</span></span>  
  
##  <a name="FailoverPartner"></a><span data-ttu-id="e2dba-105">SQL アダプターの接続 URI</span><span class="sxs-lookup"><span data-stu-id="e2dba-105">The Connection URI for the SQL Adapter</span></span>  
 <span data-ttu-id="e2dba-106">一般的なエンドポイント アドレスで WCF の URI として表されます。 `scheme://hostinfoparams?query_string`、場所。</span><span class="sxs-lookup"><span data-stu-id="e2dba-106">A typical endpoint address URI in WCF is represented as: `scheme://hostinfoparams?query_string`, where:</span></span>  
  
-   <span data-ttu-id="e2dba-107">スキームは、スキーム名です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-107">scheme is the scheme name.</span></span>  
  
-   <span data-ttu-id="e2dba-108">hostinfoparams はホストへの接続を確立するために必要な情報たとえば、サーバー名です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-108">hostinfoparams is information required to establish the connection to the host; for example, a server name.</span></span>  
  
-   <span data-ttu-id="e2dba-109">query_string は疑問符 (?) で区切られたパラメーターの省略可能な名前と値のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="e2dba-109">query_string is an optional name-value collection of parameters delimited by a question mark (?).</span></span>  
  
 <span data-ttu-id="e2dba-110">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI はこの基本的な形式に従います、次のように実装します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-110">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] connection URI adheres to this basic format and is implemented as follows:</span></span>  
  
```  
  
mssql://[Server_Name[:Portno]]/[Database_Instance_Name]/[Database_Name]?FailoverPartner=[Partner_Server_Name]&InboundId=[Inbound_ID]  
```  
  
 <span data-ttu-id="e2dba-111">ここで、`mssql`用 SQL Server の接続 URI のスキームです。</span><span class="sxs-lookup"><span data-stu-id="e2dba-111">where, `mssql` is the scheme for the SQL Server connection URI.</span></span>  
  
 <span data-ttu-id="e2dba-112">次の表では、接続 URI に含まれるプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-112">The following table explains the properties contained in the connection URI.</span></span>  
  
|<span data-ttu-id="e2dba-113">接続 URI のプロパティ</span><span class="sxs-lookup"><span data-stu-id="e2dba-113">Connection URI Property</span></span>|<span data-ttu-id="e2dba-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e2dba-114">Category</span></span>|<span data-ttu-id="e2dba-115">Description</span><span class="sxs-lookup"><span data-stu-id="e2dba-115">Description</span></span>|  
|-----------------------------|--------------|-----------------|  
|<span data-ttu-id="e2dba-116">[サーバー名]</span><span class="sxs-lookup"><span data-stu-id="e2dba-116">[SERVER_NAME]</span></span>|<span data-ttu-id="e2dba-117">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="e2dba-117">hostinfoparams</span></span>|<span data-ttu-id="e2dba-118">SQL Server がインストールされているサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e2dba-118">Name of the server on which SQL Server is installed.</span></span> <span data-ttu-id="e2dba-119">値を指定しない場合、アダプターは"localhost"としてサーバー名を前提としていて、ローカル サーバー上の SQL Server データベースとの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-119">If you do not specify a value, the adapter assumes the server name as “localhost” and establishes a connection with the SQL Server database on the local server.</span></span>|  
|<span data-ttu-id="e2dba-120">[PORTNO]</span><span class="sxs-lookup"><span data-stu-id="e2dba-120">[PORTNO]</span></span>|<span data-ttu-id="e2dba-121">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="e2dba-121">hostinfoparams</span></span>|<span data-ttu-id="e2dba-122">接続が確立されているポート番号です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-122">The port number where the connection is established.</span></span> <span data-ttu-id="e2dba-123">値を指定しない場合、アダプターは、既定のポートを介して接続します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-123">If you do not specify a value, the adapter connects through the default port.</span></span>|  
|<span data-ttu-id="e2dba-124">[データベース インスタンス名]</span><span class="sxs-lookup"><span data-stu-id="e2dba-124">[DATABASE_INSTANCE_NAME]</span></span>|<span data-ttu-id="e2dba-125">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="e2dba-125">hostinfoparams</span></span>|<span data-ttu-id="e2dba-126">接続に SQL Server インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="e2dba-126">Name of the SQL Server instance to connect to.</span></span> <span data-ttu-id="e2dba-127">値を指定しない場合、アダプターは、既定のデータベース インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-127">If you do not specify a value, the adapter connects to the default database instance.</span></span>|  
|<span data-ttu-id="e2dba-128">[DATABASE_NAME]</span><span class="sxs-lookup"><span data-stu-id="e2dba-128">[DATABASE_NAME]</span></span>|<span data-ttu-id="e2dba-129">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="e2dba-129">hostinfoparams</span></span>|<span data-ttu-id="e2dba-130">接続先のデータベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-130">Name of the database to connect to.</span></span> <span data-ttu-id="e2dba-131">値を指定しない場合、アダプターは、既定のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-131">If you do not specify a value, the adapter connects to the default database.</span></span>|  
|<span data-ttu-id="e2dba-132">[PARTNER_SERVER_NAME]</span><span class="sxs-lookup"><span data-stu-id="e2dba-132">[PARTNER_SERVER_NAME]</span></span>|<span data-ttu-id="e2dba-133">query_string</span><span class="sxs-lookup"><span data-stu-id="e2dba-133">query_string</span></span>|<span data-ttu-id="e2dba-134">フェールオーバーの SQL Server データベースに接続する場合は、プライマリ SQL Server データベースの名前は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e2dba-134">Name of the failover SQL Server database to connect to if the primary SQL Server database is not available.</span></span> <span data-ttu-id="e2dba-135">SQL Server に対する高可用性の詳細については、次を参照してください。 [SQL Server でデータベース ミラーリング](https://msdn.microsoft.com/library/5h52hef8.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-135">For more information about high availability with respect to SQL Server, see [Database Mirroring in SQL Server](https://msdn.microsoft.com/library/5h52hef8.aspx).</span></span>|  
|<span data-ttu-id="e2dba-136">[INBOUND_ID]</span><span class="sxs-lookup"><span data-stu-id="e2dba-136">[INBOUND_ID]</span></span>|<span data-ttu-id="e2dba-137">query_string</span><span class="sxs-lookup"><span data-stu-id="e2dba-137">query_string</span></span>|<span data-ttu-id="e2dba-138">接続 URI を一意になるように追加するための識別子です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-138">An identifier that you add to the connection URI to make it unique.</span></span> <span data-ttu-id="e2dba-139">メタデータを生成する場合は、この接続のパラメーターを指定する必要があります、 **TypedPolling**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-139">You must provide this connection parameter if you want to generate metadata for the **TypedPolling** inbound operation.</span></span> <span data-ttu-id="e2dba-140">また、BizTalk アプリケーションで複数の受信場所に同じデータベースをポーリングした場合、受信 ID では、受信場所の接続 URI の一意なアダプター クライアント異なる上の同じデータベースからポーリング メッセージを受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e2dba-140">Also, in a BizTalk application, if you have multiple receive locations polling the same database, the inbound ID makes the connection URI unique, thereby enabling adapter clients to receive polling messages from the same database on different receive locations.</span></span> <span data-ttu-id="e2dba-141">詳細については、次を参照してください。[受信ポーリング メッセージ間で複数の受信ポートから BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-141">For more information, see [Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e2dba-142">これらの接続文字列プロパティの詳細については、次を参照してください。 [SqlConnection.ConnectionString プロパティ](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-142">For more information about these connection string properties, see [SqlConnection.ConnectionString Property](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx).</span></span>
  
## <a name="sql-server-credentials-and-the-connection-uri"></a><span data-ttu-id="e2dba-143">SQL Server 資格情報と接続 URI</span><span class="sxs-lookup"><span data-stu-id="e2dba-143">SQL Server Credentials and the Connection URI</span></span>  
 <span data-ttu-id="e2dba-144">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI で指定する資格情報をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e2dba-144">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support specifying credentials in the connection URI.</span></span> <span data-ttu-id="e2dba-145">使用するアプリケーションでの資格情報の指定の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-145">For more information about specifying credentials in your applications that use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Secure your SQL applications](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).</span></span>  
  
## <a name="using-special-characters-in-the-connection-uri"></a><span data-ttu-id="e2dba-146">接続 URI の特殊文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-146">Using Special Characters in the Connection URI</span></span>  
 <span data-ttu-id="e2dba-147">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]パラメーター値のいずれかの特殊文字が含まれている URI の接続の指定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e2dba-147">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support specifying a connection URI that has special characters for any of the parameter values.</span></span> <span data-ttu-id="e2dba-148">接続パラメーター値に特殊文字が含まれている場合は、次のいずれかの操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-148">If the connection parameter values contain special characters, make sure you do one of the following:</span></span>  
  
-   <span data-ttu-id="e2dba-149">内の URI を指定する場合は[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、として指定する必要があります-では、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。</span><span class="sxs-lookup"><span data-stu-id="e2dba-149">If you are specifying the URI in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] using [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="e2dba-150">直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、特殊文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2dba-150">If you specify the URI directly in the **Configure a URI** field and the connection parameters contain special characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
     <span data-ttu-id="e2dba-151">たとえば、接続 URI に名前を持つパラメーター `sql server`、として指定する必要があります`sql%20server`です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-151">For example, if the connection URI has a parameter with name `sql server`, you must specify it as `sql%20server`.</span></span>  
  
-   <span data-ttu-id="e2dba-152">送信の作成中に URI を指定する、または、受信ポートのかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール、および接続パラメーターは、特殊文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2dba-152">If you are specifying the URI while creating a send or receive port in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, and the connection parameters contain special characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
## <a name="using-the-connection-uri-to-connect-to-the-sql-server-database"></a><span data-ttu-id="e2dba-153">SQL Server データベースに接続する接続 URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-153">Using the Connection URI to Connect to the SQL Server Database</span></span>  
 <span data-ttu-id="e2dba-154">次はサンプルの接続 URI を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-154">The following is a sample connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
```  
mssql://sql_server/sql_server_instance//  
```  
  
 <span data-ttu-id="e2dba-155">前の例では、"sql_server"は、SQL Server がインストールされている"sql_server_instance"に接続するデータベース インスタンスの名前には、コンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-155">In the preceding example, “sql_server” is the name of the computer on which SQL Server is installed whereas “sql_server_instance” is the name of the database instance to connect to.</span></span> <span data-ttu-id="e2dba-156">データベース名が指定されていないため、アダプターは既定のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-156">Because no database name is specified, the adapter will connect to the default database.</span></span>  
  
 <span data-ttu-id="e2dba-157">接続と同じコンピューターに SQL Server データベースがインストールされている URI の例を次に示します、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-157">The following is an example of a connection URI where the SQL Server database is installed on the same computer as the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="e2dba-158">この例では、アダプターは、"my_database"、"sql_server_instance"データベース インスタンス、ローカル コンピューター上のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-158">In this example, the adapter connects to the database “my_database” for the “sql_server_instance” database instance on the local computer.</span></span>  
  
```  
mssql://localhost/sql_server_instance/my_database/  
```  
  
 <span data-ttu-id="e2dba-159">この例では、アダプターは、ローカル コンピューターで実行されている既定のインスタンスの既定のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-159">In this example, the adapter connects to the default database for the default instance running on the local computer.</span></span>  
  
```  
mssql://localhost///  
```  
  
 <span data-ttu-id="e2dba-160">SQL Server への接続を指定する方法についてはデータベースの場合にします。</span><span class="sxs-lookup"><span data-stu-id="e2dba-160">For information about how to specify a connection to the SQL Server database when you:</span></span>  
  
-   <span data-ttu-id="e2dba-161">使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-161">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], see [Connect to SQL Server in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
-   <span data-ttu-id="e2dba-162">送信ポートを構成するか、BizTalk Server ソリューションでの受信ポート (場所) を参照してください[SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-162">Configure a send port or receive port (location) in a BizTalk Server solution, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span>
  
-   <span data-ttu-id="e2dba-163">プログラミング ソリューションで、WCF チャネル モデルを使用して、参照してください[SQL アダプターを使用して、チャネルの作成](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-163">Use the WCF channel model in a programming solution, see [Create a channel using the SQL adapter](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md).</span></span>  
  
-   <span data-ttu-id="e2dba-164">プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2dba-164">Use the WCF service model in a programming solution, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2dba-165">参照</span><span class="sxs-lookup"><span data-stu-id="e2dba-165">See Also</span></span>  
[<span data-ttu-id="e2dba-166">SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e2dba-166">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)
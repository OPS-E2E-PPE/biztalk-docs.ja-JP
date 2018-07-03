---
title: アダプターを使用して Oracle データベースへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection string
- uniform resource identifier
- Oracle database, connecting to
- URI
- connection URI
ms.assetid: 5d5598e5-aba0-4c73-8e97-9156475b93c4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a645ae3a2db79e9e2b5b4e46c758e37dfb0a1a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004323"
---
# <a name="connect-to-oracle-database-using-the-adapter"></a><span data-ttu-id="bdbb6-102">アダプターを使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-102">Connect to Oracle Database using the adapter</span></span>
<span data-ttu-id="bdbb6-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET 11.1.0.7 を使用して Oracle データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] uses ODP.NET 11.1.0.7 to connect to the Oracle database.</span></span> <span data-ttu-id="bdbb6-104">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアント接続の Uniform Resource Identifier (URI) を Oracle データベースへの接続と呼ばれる接続文字列を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-104">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] requires adapter clients to provide a connection string, called the connection Uniform Resource Identifier (URI), to connect to the Oracle database.</span></span> <span data-ttu-id="bdbb6-105">内部的には、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースに接続するデータベース接続文字列に URI をマップします。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-105">Internally, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] maps the URI to a database connection string to connect to the Oracle database.</span></span> <span data-ttu-id="bdbb6-106">接続 URI では、アダプター クライアントは、外部システムに接続する接続パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-106">With a connection URI, adapter clients can specify connection parameters to connect to an external system.</span></span>  
  
 <span data-ttu-id="bdbb6-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]により、2 つの方法を次のように Oracle データベースに接続するクライアントはアダプター。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to connect to the Oracle database in the following two ways:</span></span>  
  
- <span data-ttu-id="bdbb6-108">**Tnsnames.ora を使用して**: 接続アダプター クライアントによって提供された URI には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-108">**Using tnsnames.ora**: The connection URI provided by the adapter client contains only the net service name specified in the tnsnames.ora file.</span></span> <span data-ttu-id="bdbb6-109">アダプターは、tnsnames.ora ファイルで、net サービス名のエントリから、サーバー名、サービス名、およびポート番号などの接続パラメーターを抽出します。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-109">The adapter extracts the connection parameters such as server name, service name, and port number from the net service name entry in the tnsnames.ora file.</span></span> <span data-ttu-id="bdbb6-110">このアプローチを使用するには、tnsnames.ora ファイルで Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-110">To use this approach, the computer running the Oracle client must be configured to include the net service name for the Oracle database in the tnsnames.ora file.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="bdbb6-111">Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [Oracle データベース アダプターの接続 URI の構成](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md)場合は、複数の 39 文字を含めることはできませんをトランザクションでの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-111">Due to an Oracle Client limitation, the **DataSourceName** parameter (net service name) in the [Configure the connection URI for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md) cannot contain more than 39 characters if you are performing operations in a transaction.</span></span> <span data-ttu-id="bdbb6-112">値が指定されているため、必ず、 **DataSourceName**パラメーターは 39 文字未満のトランザクションで操作を実行する場合。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-112">Therefore, make sure that the value specified for the **DataSourceName** parameter is less than or equal to 39 characters if you will be performing operations in a transaction.</span></span>  
  
- <span data-ttu-id="bdbb6-113">**Tnsnames.ora を使用せず**: 接続アダプター クライアントによって提供された URI には、サーバー名、サービス名、およびポート番号などの接続パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-113">**Without using tnsnames.ora**: The connection URI provided by the adapter clients contains the connection parameters such as server name, service name, and port number.</span></span> <span data-ttu-id="bdbb6-114">この場合は、tnsnames.ora ファイル、または実際の tnsnames.ora ファイル自体には、net サービス名は、クライアント コンピューターに存在する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-114">In this case, the net service name in the tnsnames.ora file, or the actual tnsnames.ora file itself, does not need to be present on the client computer.</span></span> <span data-ttu-id="bdbb6-115">これは、機能は、お客様の組織での Oracle データベースに接続するユーザーの数が多いがあり、サーバーの追加/更新を手動で追加/更新すべてのクライアント コンピューターで tnsnames.ora ファイルで接続の詳細を発生させない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-115">This is helpful when you have a large number of users connecting to the Oracle database in your organization, and adding/updating servers does not lead to manually adding/updating the connection details in the tnsnames.ora file on every client computer.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="bdbb6-116">トランザクションで操作を実行している場合、この接続のモードがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-116">This mode of connectivity is not supported if you are performing operations in a transaction.</span></span> <span data-ttu-id="bdbb6-117">これは、Oracle クライアントの制限です。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-117">This is due to a limitation of Oracle Client.</span></span>  
  
  <span data-ttu-id="bdbb6-118">Oracle データベースへの接続に関する詳細については、次を参照してください。 [Oracle データベースへの接続を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-118">For more information about connecting to the Oracle database, see [Create a connection to the Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md).</span></span>  
  
  <span data-ttu-id="bdbb6-119">Oracle データベースとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-119">Make sure you comply with the security guidelines when establishing a connection with the Oracle database.</span></span> <span data-ttu-id="bdbb6-120">セキュリティのガイドラインの詳細については、次を参照してください。 [Oracle データベース アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-120">For more information about security guidelines, see [Secure your Oracle Database applications](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md).</span></span>  
  
## <a name="windows-authentication"></a><span data-ttu-id="bdbb6-121">[Windows 認証]</span><span class="sxs-lookup"><span data-stu-id="bdbb6-121">Windows Authentication</span></span>  
 <span data-ttu-id="bdbb6-122">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースへの接続中に Windows 認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-122">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports Windows Authentication while connecting to the Oracle database.</span></span> <span data-ttu-id="bdbb6-123">Windows 認証では、アダプター クライアントは Windows ログオン資格情報に基づいて、ユーザーの id を調べるし、Windows 環境の組み込みのセキュリティを活用できます。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-123">With Windows Authentication, the adapter clients can determine a user’s identity based on Windows logon credentials, and can leverage the built-in security of the Windows environment.</span></span> <span data-ttu-id="bdbb6-124">Windows 認証を使用して Oracle データベースに接続する方法の詳細については、次を参照してください。 [、Oracle データベースを使用して Windows 認証への接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="bdbb6-124">For information about connecting to the Oracle database by using Windows Authentication, see [Connect to the Oracle Database Using Windows Authentication](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdbb6-125">参照</span><span class="sxs-lookup"><span data-stu-id="bdbb6-125">See Also</span></span>  
 [<span data-ttu-id="bdbb6-126">BizTalk Adapter for Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="bdbb6-126">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
---
title: アダプターを使用して SQL Server への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 727d73e6-fb84-48ce-ae72-5de70dcae8b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b11db610e76a6bac856b8104506f64e4539cf6ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369928"
---
# <a name="connect-to-sql-server-using-the-adapter"></a><span data-ttu-id="0f3b0-102">アダプターを使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-102">Connect to SQL Server using the adapter</span></span>
<span data-ttu-id="0f3b0-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアント接続の Uniform Resource Identifier (URI) を SQL Server データベースへの接続と呼ばれる接続文字列を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] requires adapter clients to provide a connection string, called the connection Uniform Resource Identifier (URI), to connect to the SQL Server database.</span></span> <span data-ttu-id="0f3b0-104">内部的には、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] URI を SQL Server データベースに接続するデータベース接続文字列にマップされます。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-104">Internally, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] maps the URI to a database connection string to connect to the SQL Server database.</span></span> <span data-ttu-id="0f3b0-105">接続 URI では、アダプター クライアントは、外部システムに接続する接続パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-105">With a connection URI, adapter clients can specify connection parameters to connect to an external system.</span></span> <span data-ttu-id="0f3b0-106">接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-106">For more information about the connection URI, see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
 <span data-ttu-id="0f3b0-107">URI の接続でスタンバイ プライマリ SQL Server データベースが使用できない場合に接続するコンピューターのフェールオーバーの SQL Server データベースの名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-107">In the connection URI, you can also specify the name of a failover SQL Server database on a standby computer to connect to if the primary SQL Server database is not available.</span></span> <span data-ttu-id="0f3b0-108">フェールオーバーの SQL Server データベースには、プライマリ SQL Server データベースのミラーをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-108">The failover SQL Server database must be a mirror of the primary SQL Server database.</span></span> <span data-ttu-id="0f3b0-109">パラメーターを使用して、省略可能な FailoverPartner 接続 URI で、フェールオーバー SQL Server データベースが指定されました。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-109">The failover SQL Server database is specified using an optional parameter, FailoverPartner, in the connection URI.</span></span> <span data-ttu-id="0f3b0-110">フェールオーバーの SQL Server データベースを提供することにより、高可用性とデータの冗長性。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-110">Providing a failover SQL Server database ensures high availability and data redundancy.</span></span> <span data-ttu-id="0f3b0-111">高可用性の SQL Server についての詳細については、次を参照してください。 [SQL Server データベースのミラーリング](https://msdn.microsoft.com/library/5h52hef8.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-111">For more information about high availability with respect to SQL Server, see [Database Mirroring in SQL Server](https://msdn.microsoft.com/library/5h52hef8.aspx).</span></span>
  
 <span data-ttu-id="0f3b0-112">SQL Server データベースとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-112">Make sure you comply with the security guidelines when establishing a connection with the SQL Server database.</span></span> <span data-ttu-id="0f3b0-113">セキュリティのガイドラインの詳細については、次を参照してください。 [SQL アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-113">For more information about security guidelines, see [Secure your SQL applications](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f3b0-114">参照</span><span class="sxs-lookup"><span data-stu-id="0f3b0-114">See Also</span></span>  
 <span data-ttu-id="0f3b0-115">[BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0f3b0-115">[Overview of BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md) </span></span>  
 [<span data-ttu-id="0f3b0-116">SQL Server への接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="0f3b0-116">Create a Connection to SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)
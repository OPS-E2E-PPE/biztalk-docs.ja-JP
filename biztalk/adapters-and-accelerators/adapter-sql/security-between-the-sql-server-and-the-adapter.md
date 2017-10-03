---
title: "SQL Server とアダプター間のセキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4b0fd11-6753-4f52-9be7-3b6fa330fb8b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8673aee316a8a2ef83011ab3dd85016a99df1162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-between-the-sql-server-and-the-adapter"></a><span data-ttu-id="a7dba-102">SQL Server とアダプター間のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a7dba-102">Security between the SQL Server and the adapter</span></span>
<span data-ttu-id="a7dba-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と互換性が標準の方法では、データベース サーバーとデータ交換をセキュリティで保護するために使用 SSO と IPSEC などです。</span><span class="sxs-lookup"><span data-stu-id="a7dba-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is compatible with the standard methods, such as SSO and IPSEC used to secure data exchanges with the database server.</span></span> <span data-ttu-id="a7dba-104">セキュリティ保護されていないデータの交換には、承認されていないアクターにデータを公開できます。</span><span class="sxs-lookup"><span data-stu-id="a7dba-104">Unsecured data exchanges can expose data to unauthorized actors.</span></span> <span data-ttu-id="a7dba-105">SQL Server のセキュリティに関する問題については、次を参照してください。 [for SQL Server のセキュリティに関する考慮事項](http://go.microsoft.com/fwlink/p/?LinkId=196954)SQL のドキュメントにします。</span><span class="sxs-lookup"><span data-stu-id="a7dba-105">For information about security issues with SQL Server, see [Security Considerations for SQL Server](http://go.microsoft.com/fwlink/p/?LinkId=196954) in the SQL documentation.</span></span>  
  
 <span data-ttu-id="a7dba-106">インターネット プロトコル セキュリティ (IPsec) を使用して、データ交換のセキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="a7dba-106">You can improve the security of data exchanges by using Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="a7dba-107">IPsec は、オープン標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。</span><span class="sxs-lookup"><span data-stu-id="a7dba-107">IPsec is a framework of open standards for protecting communications over Internet Protocol (IP) networks.</span></span> <span data-ttu-id="a7dba-108">すべてのデータは、IPSec の間で交換される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と SQL ネットワーク経由でサーバーを暗号化すると、データを使用するアクターが承認されていないのは困難になります。</span><span class="sxs-lookup"><span data-stu-id="a7dba-108">With IPSec, any data exchanged between the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and the SQL server over the network is encrypted, making it difficult for unauthorized actors to use the data.</span></span> <span data-ttu-id="a7dba-109">IPsec および Microsoft の製品で IPsec を使用する方法の詳細については、Microsoft TechNet の記事を参照してください。 [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955)です。</span><span class="sxs-lookup"><span data-stu-id="a7dba-109">For more information about IPsec and about using IPsec with Microsoft products, see the Microsoft TechNet article [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955).</span></span>  
  
 <span data-ttu-id="a7dba-110">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データベースと、確立された接続での認証に、SSO と統合セキュリティをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a7dba-110">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports SSO and Integrated Security for authentication on the connections that it establishes with the database.</span></span> <span data-ttu-id="a7dba-111">SSO を使用して資格情報は暗号化し、レジストリに格納されています。</span><span class="sxs-lookup"><span data-stu-id="a7dba-111">With SSO, the credentials are encrypted and stored in the registry.</span></span> <span data-ttu-id="a7dba-112">システムでは、これらの資格情報を使用して、未承認のアクターによって認識がそれらを入力するユーザーを要求する代わりに、アクセスを決定します。</span><span class="sxs-lookup"><span data-stu-id="a7dba-112">The system uses these credentials to determine access instead of requiring the user to enter them where they might be seen by unauthorized actors.</span></span> <span data-ttu-id="a7dba-113">統合セキュリティは、SQL server へのアクセスにログオンしたユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7dba-113">Integrated Security uses the credentials of the logged on user to access the SQL server.</span></span> <span data-ttu-id="a7dba-114">これは、ユーザーが資格情報を入力する必要もなくなります。</span><span class="sxs-lookup"><span data-stu-id="a7dba-114">This also eliminates the need for users to enter credentials.</span></span> <span data-ttu-id="a7dba-115">データベース管理者を正常に動作する統合セキュリティのユーザーの資格情報を受け入れるように SQL を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7dba-115">The database administrator must configure SQL to accept the users credentials for Integrated Security to work correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7dba-116">参照</span><span class="sxs-lookup"><span data-stu-id="a7dba-116">See Also</span></span>  
[<span data-ttu-id="a7dba-117">SQL アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="a7dba-117">Secure your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)
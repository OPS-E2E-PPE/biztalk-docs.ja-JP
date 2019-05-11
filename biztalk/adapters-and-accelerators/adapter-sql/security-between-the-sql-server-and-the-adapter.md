---
title: SQL Server とアダプター間のセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b0fd11-6753-4f52-9be7-3b6fa330fb8b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3414cb5ed82cc9003e6207c4a58150dd914d2a19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367945"
---
# <a name="security-between-the-sql-server-and-the-adapter"></a><span data-ttu-id="e6774-102">SQL Server とアダプター間のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="e6774-102">Security between the SQL Server and the adapter</span></span>
<span data-ttu-id="e6774-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データベース サーバーとのデータ交換をセキュリティで保護するために使用 SSO と IPSEC など、標準の方法と互換性が。</span><span class="sxs-lookup"><span data-stu-id="e6774-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is compatible with the standard methods, such as SSO and IPSEC used to secure data exchanges with the database server.</span></span> <span data-ttu-id="e6774-104">セキュリティ保護されていないデータの交換には、不正なアクターにデータを公開できます。</span><span class="sxs-lookup"><span data-stu-id="e6774-104">Unsecured data exchanges can expose data to unauthorized actors.</span></span> <span data-ttu-id="e6774-105">SQL Server セキュリティ上の問題については、次を参照してください。 [for SQL Server のセキュリティに関する考慮事項](http://go.microsoft.com/fwlink/p/?LinkId=196954)SQL ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="e6774-105">For information about security issues with SQL Server, see [Security Considerations for SQL Server](http://go.microsoft.com/fwlink/p/?LinkId=196954) in the SQL documentation.</span></span>  
  
 <span data-ttu-id="e6774-106">インターネット プロトコル セキュリティ (IPsec) を使用してデータ交換のセキュリティを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e6774-106">You can improve the security of data exchanges by using Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="e6774-107">IPsec は、オープンな標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。</span><span class="sxs-lookup"><span data-stu-id="e6774-107">IPsec is a framework of open standards for protecting communications over Internet Protocol (IP) networks.</span></span> <span data-ttu-id="e6774-108">すべてのデータは、IPSec の間で交換される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と、SQL、ネットワーク経由でサーバーを暗号化すると、不正なアクター データを使用するが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="e6774-108">With IPSec, any data exchanged between the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and the SQL server over the network is encrypted, making it difficult for unauthorized actors to use the data.</span></span> <span data-ttu-id="e6774-109">IPsec および Microsoft 製品で IPsec を使用する方法の詳細については、Microsoft TechNet の記事を参照してください。 [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955)します。</span><span class="sxs-lookup"><span data-stu-id="e6774-109">For more information about IPsec and about using IPsec with Microsoft products, see the Microsoft TechNet article [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955).</span></span>  
  
 <span data-ttu-id="e6774-110">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データベースと、確立された接続での認証の SSO と統合セキュリティをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e6774-110">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports SSO and Integrated Security for authentication on the connections that it establishes with the database.</span></span> <span data-ttu-id="e6774-111">Sso、資格情報が暗号化され、レジストリに格納されています。</span><span class="sxs-lookup"><span data-stu-id="e6774-111">With SSO, the credentials are encrypted and stored in the registry.</span></span> <span data-ttu-id="e6774-112">システムでは、これらの資格情報を使って、不正なアクターによって表示される可能性を入力するように求めるのではなくアクセスを決定します。</span><span class="sxs-lookup"><span data-stu-id="e6774-112">The system uses these credentials to determine access instead of requiring the user to enter them where they might be seen by unauthorized actors.</span></span> <span data-ttu-id="e6774-113">統合セキュリティは、SQL server へのアクセスにログオンしたユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6774-113">Integrated Security uses the credentials of the logged on user to access the SQL server.</span></span> <span data-ttu-id="e6774-114">これもユーザー資格情報を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e6774-114">This also eliminates the need for users to enter credentials.</span></span> <span data-ttu-id="e6774-115">データベース管理者を正常に動作する統合セキュリティのユーザーの資格情報を受け入れるように SQL を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6774-115">The database administrator must configure SQL to accept the users credentials for Integrated Security to work correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6774-116">参照</span><span class="sxs-lookup"><span data-stu-id="e6774-116">See Also</span></span>  
[<span data-ttu-id="e6774-117">SQL アプリケーションをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="e6774-117">Secure your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)
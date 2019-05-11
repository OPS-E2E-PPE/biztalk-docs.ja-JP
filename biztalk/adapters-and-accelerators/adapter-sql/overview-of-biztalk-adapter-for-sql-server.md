---
title: BizTalk Adapter for SQL Server の概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e46690e-d5c4-4d6b-b7a0-9a5adf4431cd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a026cabfbfd2dfb846ec3dd2ca27483f5c564fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368505"
---
# <a name="overview-of-biztalk-adapter-for-sql-server"></a><span data-ttu-id="29211-102">BizTalk Adapter for SQL Server の概要</span><span class="sxs-lookup"><span data-stu-id="29211-102">Overview of BizTalk Adapter for SQL Server</span></span>
<span data-ttu-id="29211-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] WCF サービスとしての SQL Server データベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="29211-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes the SQL Server database as a WCF service.</span></span> <span data-ttu-id="29211-104">アダプター クライアントは、アダプターを使用した SOAP メッセージを交換することで、SQL Server データベースで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="29211-104">Adapter clients can perform operations on the SQL Server database by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="29211-105">アダプターは、SOAP メッセージを使用し、操作を実行する適切な ADO.NET 呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="29211-105">The adapter consumes the SOAP message and makes appropriate ADO.NET calls to perform the operation.</span></span> <span data-ttu-id="29211-106">アダプターは、SOAP メッセージの形式でクライアントに SQL Server データベースからの応答を返します。</span><span class="sxs-lookup"><span data-stu-id="29211-106">The adapter returns the response from the SQL Server database back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="29211-107">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (テーブル、ビュー、およびプロシージャ) などの SQL Server データベースのアイテムのサーフェスのメタデータ。</span><span class="sxs-lookup"><span data-stu-id="29211-107">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] surfaces metadata of artifacts in the SQL Server database (such as tables, views, and procedures).</span></span>  <span data-ttu-id="29211-108">このメタデータには、Web サービス記述言語 (WSDL) の形式で SOAP メッセージの構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="29211-108">This metadata describes the structure of a SOAP message in the form of Web Services Description Language (WSDL).</span></span> <span data-ttu-id="29211-109">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアントの操作のメタデータを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="29211-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations.</span></span> <span data-ttu-id="29211-110">アダプターには、プログラミング ソリューションで使用できるプログラミングの成果物も生成されます。</span><span class="sxs-lookup"><span data-stu-id="29211-110">The adapter also generates programming artifacts that can be used in your programming solution.</span></span> <span data-ttu-id="29211-111">詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="29211-111">For more information about [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], see [Connect to SQL Server in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
 <span data-ttu-id="29211-112">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ADO.NET を使用して、SQL Server データベースと通信します。</span><span class="sxs-lookup"><span data-stu-id="29211-112">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses ADO.NET to communicate with the SQL Server database.</span></span> <span data-ttu-id="29211-113">使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の方法で SQL Server データベースと通信します。</span><span class="sxs-lookup"><span data-stu-id="29211-113">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to communicate with the SQL Server database in the following ways:</span></span>  
  
- <span data-ttu-id="29211-114">BizTalk アプリケーションを開発しています。</span><span class="sxs-lookup"><span data-stu-id="29211-114">By developing BizTalk applications.</span></span> <span data-ttu-id="29211-115">詳細については、次を参照してください。[開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="29211-115">For more information, see [Develop BizTalk applications](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="29211-116">使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。</span><span class="sxs-lookup"><span data-stu-id="29211-116">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="29211-117">詳細については、次を参照してください。 [WCF サービス モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="29211-117">For more information, see [Develop applications using the WCF Service model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="29211-118">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="29211-118">By using the WCF channel model.</span></span> <span data-ttu-id="29211-119">詳細については、次を参照してください。 [WCF チャネル モデルを使用してアプリケーションを開発](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="29211-119">For more information, see [Develop applications using the WCF Channel model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29211-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="29211-120">In This Section</span></span>  
  
-   [<span data-ttu-id="29211-121">アダプターは、SQL Server にどのように接続しますか。</span><span class="sxs-lookup"><span data-stu-id="29211-121">How Does the Adapter Connect to SQL Server?</span></span>](https://msdn.microsoft.com/library/dd788114.aspx) 
  
-   [<span data-ttu-id="29211-122">アダプターのサーフェスの SQL サーバーのメタデータをどのようにか。</span><span class="sxs-lookup"><span data-stu-id="29211-122">How Does the Adapter Surface SQL Server Metadata?</span></span>](https://msdn.microsoft.com/library/dd787941.aspx)  
  
-  <span data-ttu-id="29211-123">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="29211-123">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>  
  
-   [<span data-ttu-id="29211-124">SQL アダプターによってサポートされる操作</span><span class="sxs-lookup"><span data-stu-id="29211-124">What operations are supported by the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/what-operations-are-supported-by-the-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="29211-125">参照</span><span class="sxs-lookup"><span data-stu-id="29211-125">See Also</span></span>  
 [<span data-ttu-id="29211-126">BizTalk Adapter for SQL Server を理解する</span><span class="sxs-lookup"><span data-stu-id="29211-126">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)
---
title: BizTalk Adapter 用 Oracle Database の概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, overview
- ODP.NET
- Oracle Data Provider for .NET 2.0
ms.assetid: 852b8f82-ab34-45b8-ad7f-263d719a87f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b874b5523256342a4e8ae14b2c475ede11fe279
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214210"
---
# <a name="overview-of-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="c9949-102">BizTalk Adapter 用 Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="c9949-102">Overview of BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="c9949-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]を WCF サービスとして Oracle データベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="c9949-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes the Oracle database as a WCF service.</span></span> <span data-ttu-id="c9949-104">アダプターのクライアントは、アダプターと SOAP メッセージを交換することで、Oracle データベースで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9949-104">Adapter clients can perform operations on the Oracle database by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="c9949-105">アダプターは、WCF メッセージを処理し、操作を実行する適切な ODP.NET 呼び出しします。</span><span class="sxs-lookup"><span data-stu-id="c9949-105">The adapter consumes the WCF message and makes appropriate ODP.NET calls to perform the operation.</span></span> <span data-ttu-id="c9949-106">アダプターは、SOAP メッセージの形式でクライアントに Oracle データベースからの応答を返します。</span><span class="sxs-lookup"><span data-stu-id="c9949-106">The adapter returns the response from the Oracle database back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="c9949-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WSDL の形でメッセージの SOAP の構造を記述する Oracle データベース アイテム (テーブル、関数、プロシージャなど) のサーフェス メタデータ。</span><span class="sxs-lookup"><span data-stu-id="c9949-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces metadata of Oracle database artifacts (tables, functions, procedures, etc.) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="c9949-108">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、および[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]アダプター クライアント操作のメタデータを取得するには、プログラミング ソリューションで使用できるプログラミングの成果物を生成します。</span><span class="sxs-lookup"><span data-stu-id="c9949-108">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], and [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span>  
  
 <span data-ttu-id="c9949-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle Data Provider for .NET (ODP.NET) を使用して Oracle データベースと通信します。</span><span class="sxs-lookup"><span data-stu-id="c9949-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the Oracle Data Provider for .NET (ODP.NET) to communicate with the Oracle database.</span></span> <span data-ttu-id="c9949-110">使用することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次のように、Oracle データベースと通信します。</span><span class="sxs-lookup"><span data-stu-id="c9949-110">You can use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to communicate with the Oracle database in the following ways:</span></span>  
  
-   <span data-ttu-id="c9949-111">BizTalk アプリケーションを開発することによりします。</span><span class="sxs-lookup"><span data-stu-id="c9949-111">By developing BizTalk applications.</span></span> <span data-ttu-id="c9949-112">参照してください[、BizTalk アプリケーションの開発](../../core/develop-your-biztalk-applications.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="c9949-112">See [Develop your BizTalk applications](../../core/develop-your-biztalk-applications.md) for more information.</span></span>  
  
-   <span data-ttu-id="c9949-113">使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。</span><span class="sxs-lookup"><span data-stu-id="c9949-113">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="c9949-114">参照してください[WCF サービス モデルを使用して Oracle データベースの開発アプリケーション](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="c9949-114">See [Develop Oracle Database applications using the WCF Service model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) for more information.</span></span>  
  
-   <span data-ttu-id="c9949-115">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9949-115">By using the WCF channel model.</span></span> <span data-ttu-id="c9949-116">参照してください[WCF チャネル モデルを使用して Oracle データベースの開発アプリケーション](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="c9949-116">See [Develop Oracle Database applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) for more information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9949-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c9949-117">In This Section</span></span>  
  
-   <span data-ttu-id="c9949-118">[アダプターは、Oracle データベースにどのように接続しますか。](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="c9949-118">[How Does the Adapter Connect to an Oracle Database?](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="c9949-119">[アダプター メタデータの表面の Oracle がどのようにしますか。](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="c9949-119">[How Does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="c9949-120">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="c9949-120">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>  
  
-   [<span data-ttu-id="c9949-121">アダプターの処理のトランザクションがどのようにしますか。</span><span class="sxs-lookup"><span data-stu-id="c9949-121">How does the Adapter Handle Transactions?</span></span>](https://msdn.microsoft.com/library/dd788428.aspx)  
  
-   [<span data-ttu-id="c9949-122">Oracle データベースでの LOB データ型のストリーミング サポート</span><span class="sxs-lookup"><span data-stu-id="c9949-122">Streaming Support for LOB Data Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="c9949-123">どのような操作、Oracle データベース アダプターによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c9949-123">What operations are supported by the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/what-operations-are-supported-by-the-oracle-database-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="c9949-124">参照</span><span class="sxs-lookup"><span data-stu-id="c9949-124">See Also</span></span>  
 [<span data-ttu-id="c9949-125">Oracle データベースの Biztalk アダプターの理解</span><span class="sxs-lookup"><span data-stu-id="c9949-125">Understanding the Biztalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)
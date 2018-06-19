---
title: SQL アダプタのクライアントの機能 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f638154b-0a09-4f89-9c52-2a62fafec7dc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0d1df3a7d5c5748db4b0d3f365d80d84ff1f670
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222714"
---
# <a name="features-for-sql-adapter-clients"></a><span data-ttu-id="9265c-102">SQL アダプタのクライアントの機能</span><span class="sxs-lookup"><span data-stu-id="9265c-102">Features for SQL adapter clients</span></span>
<span data-ttu-id="9265c-103">トピックで説明されている機能だけでなく[概要の BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)では、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアント用の便利な次の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="9265c-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md), the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
-   <span data-ttu-id="9265c-104">**バインドのプロパティを使用してアダプターを構成するためのサポート**です。</span><span class="sxs-lookup"><span data-stu-id="9265c-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="9265c-105">アダプターのクライアントを構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を特定のバインディング プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="9265c-105">Adapter clients can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="9265c-106">たとえば、クライアントが、接続の最大数で許可されている接続プール内の特定の接続文字列の設定を指定できます、 **MaxConnectionPoolSize**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="9265c-106">For example, clients can specify the maximum number of connections allowed in a connection pool for a specific connection string by setting the **MaxConnectionPoolSize** binding property.</span></span> <span data-ttu-id="9265c-107">詳細については、次を参照してください。 [BizTalk Adapter for SQL Server アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="9265c-107">For more information, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
-   <span data-ttu-id="9265c-108">**操作のパラメーターに null 値のサポート**です。</span><span class="sxs-lookup"><span data-stu-id="9265c-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="9265c-109">アダプターのクライアントは、XSD"nillable"属性を使用して操作のパラメーターを null 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9265c-109">Adapter clients can provide null values for operation parameters using the XSD "nillable" attribute.</span></span>  
  
-   <span data-ttu-id="9265c-110">**BizTalk で動的ポートのサポート**です。</span><span class="sxs-lookup"><span data-stu-id="9265c-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="9265c-111">BizTalk を通じて[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]からのメッセージの動的なルーティングできるようにする動的なポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="9265c-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="9265c-112">詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="9265c-112">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).</span></span>  
  
-   <span data-ttu-id="9265c-113">**パフォーマンス カウンターのサポート**です。</span><span class="sxs-lookup"><span data-stu-id="9265c-113">**Support for performance counters**.</span></span> <span data-ttu-id="9265c-114">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントで使用する WCF ベースのパフォーマンス カウンターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9265c-114">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="9265c-115">パフォーマンス カウンターの詳細については、次を参照してください。 [SQL アダプターで使用するパフォーマンス カウンター](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="9265c-115">For more information about performance counters, see [Use Performance Counters with the SQL adapter](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9265c-116">参照</span><span class="sxs-lookup"><span data-stu-id="9265c-116">See Also</span></span>  
 [<span data-ttu-id="9265c-117">BizTalk Adapter for SQL Server の概要</span><span class="sxs-lookup"><span data-stu-id="9265c-117">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)
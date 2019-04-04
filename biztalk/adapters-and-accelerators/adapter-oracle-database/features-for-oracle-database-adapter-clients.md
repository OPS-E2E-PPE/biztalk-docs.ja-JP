---
title: Oracle データベース アダプター クライアントの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data streaming, support for
- binding properties
- adapter, features
- adapters, configuring
- message versioning, support for
- XML data streaming
- performance counters, support for
- dynamic ports in BizTalk, support for
- data streaming
ms.assetid: 63b52573-80a5-4206-95c3-478b86718fee
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce283c3fd63f72d67e31806e86bf9caa08555dd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976179"
---
# <a name="features-for-oracle-database-adapter-clients"></a><span data-ttu-id="a1514-102">Oracle データベース アダプター クライアントの機能</span><span class="sxs-lookup"><span data-stu-id="a1514-102">Features for Oracle Database adapter clients</span></span>
<span data-ttu-id="a1514-103">トピックで説明されている機能だけでなく[概要の BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントに役立つ次の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="a1514-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md), the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
- <span data-ttu-id="a1514-104">**バインドのプロパティを使用してアダプターを構成するためのサポート**します。</span><span class="sxs-lookup"><span data-stu-id="a1514-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="a1514-105">アダプター クライアントを構成することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]特定のバインド プロパティを指定しています。</span><span class="sxs-lookup"><span data-stu-id="a1514-105">Adapter clients can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="a1514-106">クライアントが、ODP.NET 接続プールを設定して使用するアダプターを構成するなど、 **UseOracleConnectionPool**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="a1514-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="a1514-107">詳細については、[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1514-107">For more information, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
- <span data-ttu-id="a1514-108">**操作のパラメーターに null 値のサポート**します。</span><span class="sxs-lookup"><span data-stu-id="a1514-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="a1514-109">アダプター クライアントでは、入力 XML の"nil"属性を使用して操作のパラメーターの null 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a1514-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
- <span data-ttu-id="a1514-110">**BizTalk で動的ポートのサポート**します。</span><span class="sxs-lookup"><span data-stu-id="a1514-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="a1514-111">BizTalk から[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]からのメッセージの動的ルーティングできるようにする動的ポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="a1514-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="a1514-112">詳細については、[動的ポートを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1514-112">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md).</span></span>  
  
- <span data-ttu-id="a1514-113">**パフォーマンス カウンターのサポート**します。</span><span class="sxs-lookup"><span data-stu-id="a1514-113">**Support for performance counters**.</span></span> <span data-ttu-id="a1514-114">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントで使用するための WCF ベースのパフォーマンス カウンターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a1514-114">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="a1514-115">パフォーマンス カウンターの詳細については、[パフォーマンス カウンター](../../core/performance-counters.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1514-115">For more information about performance counters, see [Performance Counters](../../core/performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1514-116">参照</span><span class="sxs-lookup"><span data-stu-id="a1514-116">See Also</span></span>  
 [<span data-ttu-id="a1514-117">BizTalk Adapter for Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="a1514-117">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
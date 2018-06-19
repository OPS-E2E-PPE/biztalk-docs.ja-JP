---
title: Oracle データベース アダプターのクライアントの機能 |Microsoft ドキュメント
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
ms.openlocfilehash: b120c948ef3d9821af0a79e91fd718e3a1f33137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214322"
---
# <a name="features-for-oracle-database-adapter-clients"></a><span data-ttu-id="f8867-102">Oracle データベース アダプターのクライアントの機能</span><span class="sxs-lookup"><span data-stu-id="f8867-102">Features for Oracle Database adapter clients</span></span>
<span data-ttu-id="f8867-103">トピックで説明されている機能だけでなく[概要の BizTalk Adapter 用 Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアント用の便利な次の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="f8867-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md), the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
-   <span data-ttu-id="f8867-104">**バインドのプロパティを使用してアダプターを構成するためのサポート**です。</span><span class="sxs-lookup"><span data-stu-id="f8867-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="f8867-105">アダプターのクライアントを構成することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を特定のバインディング プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8867-105">Adapter clients can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="f8867-106">クライアントが設定して、ODP.NET 接続プールを使用するアダプターを構成するなど、 **UseOracleConnectionPool**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="f8867-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="f8867-107">詳細については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8867-107">For more information, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
-   <span data-ttu-id="f8867-108">**操作のパラメーターに null 値のサポート**です。</span><span class="sxs-lookup"><span data-stu-id="f8867-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="f8867-109">アダプターのクライアントは、入力 XML ファイルの"nil"属性を使用して操作のパラメーターを null 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f8867-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
-   <span data-ttu-id="f8867-110">**BizTalk で動的ポートのサポート**です。</span><span class="sxs-lookup"><span data-stu-id="f8867-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="f8867-111">BizTalk を通じて[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]からのメッセージの動的なルーティングできるようにする動的なポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="f8867-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="f8867-112">詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8867-112">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md).</span></span>  
  
-   <span data-ttu-id="f8867-113">**パフォーマンス カウンターのサポート**です。</span><span class="sxs-lookup"><span data-stu-id="f8867-113">**Support for performance counters**.</span></span> <span data-ttu-id="f8867-114">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントで使用する WCF ベースのパフォーマンス カウンターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f8867-114">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="f8867-115">パフォーマンス カウンターの詳細については、次を参照してください。[パフォーマンス カウンター](../../core/performance-counters.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8867-115">For more information about performance counters, see [Performance Counters](../../core/performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8867-116">参照</span><span class="sxs-lookup"><span data-stu-id="f8867-116">See Also</span></span>  
 [<span data-ttu-id="f8867-117">BizTalk Adapter 用 Oracle Database の概要</span><span class="sxs-lookup"><span data-stu-id="f8867-117">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
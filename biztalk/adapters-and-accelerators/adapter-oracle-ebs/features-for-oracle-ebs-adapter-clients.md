---
title: Oracle EBS アダプター クライアントの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50256fb7-5f0c-4b32-87e6-98f49da0b360
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 974f75eaa2416ae11572a1b29eb682d6bc7c0172
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968883"
---
# <a name="features-for-oracle-ebs-adapter-clients"></a><span data-ttu-id="c1964-102">Oracle EBS アダプター クライアントの機能</span><span class="sxs-lookup"><span data-stu-id="c1964-102">Features for Oracle EBS adapter clients</span></span>
<span data-ttu-id="c1964-103">トピックで説明されている機能だけでなく[概要の BizTalk Adapter for Oracle E-business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e)、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]アダプター クライアントに役立つ次の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="c1964-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e), the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
- <span data-ttu-id="c1964-104">**バインドのプロパティを使用してアダプターを構成するためのサポート**します。</span><span class="sxs-lookup"><span data-stu-id="c1964-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="c1964-105">アダプター クライアントを構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]特定のバインド プロパティを指定しています。</span><span class="sxs-lookup"><span data-stu-id="c1964-105">Adapter clients can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="c1964-106">クライアントが、ODP.NET 接続プールを設定して使用するアダプターを構成するなど、 **UseOracleConnectionPool**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c1964-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="c1964-107">詳細については、次を参照してください。 [for Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1964-107">For more information, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
- <span data-ttu-id="c1964-108">**操作のパラメーターに null 値のサポート**します。</span><span class="sxs-lookup"><span data-stu-id="c1964-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="c1964-109">アダプター クライアントでは、入力 XML の"nil"属性を使用して操作のパラメーターの null 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1964-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
- <span data-ttu-id="c1964-110">**BizTalk で動的ポートのサポート**します。</span><span class="sxs-lookup"><span data-stu-id="c1964-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="c1964-111">BizTalk から[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]からのメッセージの動的ルーティングできるようにする動的ポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="c1964-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="c1964-112">詳細については、次を参照してください。 [SQL アダプターで構成する動的ポート](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1964-112">For more information, see [Configure Dynamic Ports in the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1964-113">参照</span><span class="sxs-lookup"><span data-stu-id="c1964-113">See Also</span></span>  
[<span data-ttu-id="c1964-114">BizTalk Adapter for Oracle E-Business Suite について</span><span class="sxs-lookup"><span data-stu-id="c1964-114">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
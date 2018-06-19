---
title: Oracle EBS アダプター クライアント機能 |Microsoft ドキュメント
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
ms.openlocfilehash: 2da086390fe049a5333dda40a35e19f46298dda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217258"
---
# <a name="features-for-oracle-ebs-adapter-clients"></a><span data-ttu-id="877ca-102">Oracle EBS アダプターのクライアントの機能</span><span class="sxs-lookup"><span data-stu-id="877ca-102">Features for Oracle EBS adapter clients</span></span>
<span data-ttu-id="877ca-103">トピックで説明されている機能だけでなく[概要の BizTalk Adapter for Oracle E-business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e)では、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]アダプター クライアント用の便利な次の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="877ca-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e), the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
-   <span data-ttu-id="877ca-104">**バインドのプロパティを使用してアダプターを構成するためのサポート**です。</span><span class="sxs-lookup"><span data-stu-id="877ca-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="877ca-105">アダプターのクライアントを構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を特定のバインディング プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="877ca-105">Adapter clients can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="877ca-106">クライアントが設定して、ODP.NET 接続プールを使用するアダプターを構成するなど、 **UseOracleConnectionPool**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="877ca-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="877ca-107">詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="877ca-107">For more information, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
-   <span data-ttu-id="877ca-108">**操作のパラメーターに null 値のサポート**です。</span><span class="sxs-lookup"><span data-stu-id="877ca-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="877ca-109">アダプターのクライアントは、入力 XML ファイルの"nil"属性を使用して操作のパラメーターを null 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="877ca-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
-   <span data-ttu-id="877ca-110">**BizTalk で動的ポートのサポート**です。</span><span class="sxs-lookup"><span data-stu-id="877ca-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="877ca-111">BizTalk を通じて[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]からのメッセージの動的なルーティングできるようにする動的なポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="877ca-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="877ca-112">詳細については、次を参照してください。 [SQL アダプターで動的ポートを構成](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="877ca-112">For more information, see [Configure Dynamic Ports in the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="877ca-113">参照</span><span class="sxs-lookup"><span data-stu-id="877ca-113">See Also</span></span>  
[<span data-ttu-id="877ca-114">Oracle E-business Suite の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="877ca-114">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
---
title: "WCF LOB Adapter SDK のさまざまなコンポーネントとアーキテクチャを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 293189be-61d7-44f4-8ba6-e5550516d9b4
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feea57176512bb42306feb8b60a10a887a020145
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understand-the-architecture-and-different-components-of-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="5238f-102">WCF LOB Adapter SDK のさまざまなコンポーネントとアーキテクチャを理解します。</span><span class="sxs-lookup"><span data-stu-id="5238f-102">Understand the architecture and different components of the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="5238f-103">について、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]さまざまなコンポーネントと、WCF の役割を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5238f-103">Read about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] to help understand the different components, and the role of WCF.</span></span>  

<span data-ttu-id="5238f-104">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ツールおよび基幹業務システムを再利用可能なメタデータが豊富なアダプターを開発するための一貫したフレームワークを提供するコンポーネントのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="5238f-104">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is a collection of tools and components that provide a consistent framework for developing reusable, metadata-rich adapters for line-of-business systems.</span></span> <span data-ttu-id="5238f-105">アダプターを使用して記述、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]カスタム WCF バインドとして公開され、WCF 対応クライアントで利用できることができます。</span><span class="sxs-lookup"><span data-stu-id="5238f-105">Adapters written using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] are surfaced as custom WCF bindings and can be consumed by a WCF-capable client.</span></span>  
  
## <a name="features-and-components-overview"></a><span data-ttu-id="5238f-106">機能とコンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="5238f-106">Features and components overview</span></span>
<span data-ttu-id="5238f-107">[Windows Communication Foundation 行のビジネス アダプター SDK](what-is-the-windows-communication-foundation-line-of-business-adapter-sdk.md) SDK を構成するコンポーネントおよび機能の概要を説明し、メタデータ、接続の管理について説明し、WCF の一般的な用語について説明します。</span><span class="sxs-lookup"><span data-stu-id="5238f-107">[What Is the Windows Communication Foundation Line of Business Adapter SDK](what-is-the-windows-communication-foundation-line-of-business-adapter-sdk.md) provides an overview of the features and components that make up the SDK, and describes the metadata, connection management, and describes the common WCF terms.</span></span>

## <a name="role-of-wcf"></a><span data-ttu-id="5238f-108">WCF の役割</span><span class="sxs-lookup"><span data-stu-id="5238f-108">Role of WCF</span></span>  
<span data-ttu-id="5238f-109">[WCF LOB Adapter SDK による WCF を使用する方法を読み取る](read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk.md)SDK と WCF との関係について説明します。</span><span class="sxs-lookup"><span data-stu-id="5238f-109">[Read how WCF is used by the WCF LOB Adapter SDK](read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk.md) explains the relationship with the SDK and WCF.</span></span>

## <a name="architecture-overview"></a><span data-ttu-id="5238f-110">アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="5238f-110">Architecture Overview</span></span>  
<span data-ttu-id="5238f-111">[アーキテクチャの概要](architecture-overview-of-the-wcf-lob-adapter-sdk.md)descrbied 内部のアーキテクチャと WCF LOB Adapter SDK の主要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="5238f-111">[Architecture overview ](architecture-overview-of-the-wcf-lob-adapter-sdk.md) descrbied the internal architecture and the main components of WCF LOB Adapter SDK.</span></span>
 
## <a name="connection-handler-metadata-custom-and-core-components"></a><span data-ttu-id="5238f-112">接続、ハンドラー、メタデータ、カスタム、およびコア コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5238f-112">Connection, handler, metadata, custom, and core components</span></span>
<span data-ttu-id="5238f-113">[WCF LOB Adapter SDK のキー コンポーネント](key-components-of-the-wcf-lob-adapter-sdk.md)これらさまざまなコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5238f-113">[Key Components of the WCF LOB Adapter SDK](key-components-of-the-wcf-lob-adapter-sdk.md) describes these different components.</span></span>

## <a name="biztalk-server-and-the-sdk"></a><span data-ttu-id="5238f-114">BizTalk Server と SDK</span><span class="sxs-lookup"><span data-stu-id="5238f-114">BizTalk Server and the SDK</span></span>  
[<span data-ttu-id="5238f-115">BizTalk Adapter for Oracle データベースと WCF LOB Adapter SDK</span><span class="sxs-lookup"><span data-stu-id="5238f-115">BizTalk Adapter for Oracle Database and the WCF LOB Adapter SDK</span></span>](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)   
  
## <a name="see-also"></a><span data-ttu-id="5238f-116">参照</span><span class="sxs-lookup"><span data-stu-id="5238f-116">See Also</span></span>  
 [<span data-ttu-id="5238f-117">BizTalk Server の概要</span><span class="sxs-lookup"><span data-stu-id="5238f-117">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)
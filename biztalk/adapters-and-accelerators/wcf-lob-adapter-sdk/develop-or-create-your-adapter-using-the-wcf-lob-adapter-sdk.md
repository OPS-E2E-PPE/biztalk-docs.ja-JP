---
title: "WCF LOB Adapter SDK を使用して、アダプターの作成や開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ca8c03a-1e4a-4077-b4cb-4e184b520bbb
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e7e4c76add25b53a8b3e32707c6a09b92636559
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="3ebf0-102">WCF LOB Adapter SDK を使用して、アダプターの作成や開発</span><span class="sxs-lookup"><span data-stu-id="3ebf0-102">Develop or create your adapter using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="3ebf0-103">このセクションの内容には使用してアダプターを開発する開発者向けの情報が含まれています、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3ebf0-103">This section contains information for developers who are creating adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="3ebf0-104">アダプターの開発が完了した後は通常、使用されるか .NET でまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]操作とデータを目的となる対象の基幹業務システムにアクセスする手段としての開発者。</span><span class="sxs-lookup"><span data-stu-id="3ebf0-104">Once the adapter has been developed, it is usually consumed by either .NET or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] developers as a way to access operations and data in a desired target line-of-business system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ebf0-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3ebf0-105">In This Section</span></span>  
  
-   [<span data-ttu-id="3ebf0-106">WCF LOB Adapter SDK を使用して、開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3ebf0-106">Development Best Practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="3ebf0-107">WCF LOB Adapter SDK の WSDL プロキシで使用する名前空間</span><span class="sxs-lookup"><span data-stu-id="3ebf0-107">Use namespaces with the WSDL-Proxy in the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="3ebf0-108">WCF LOB Adapter SDK では、WSDL PortType ドキュメント スキーマを説明します。</span><span class="sxs-lookup"><span data-stu-id="3ebf0-108">Describe the WSDL PortType Documentation Schema with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="3ebf0-109">WCF LOB Adapter SDK と、アダプター バージョンを管理します。</span><span class="sxs-lookup"><span data-stu-id="3ebf0-109">Manage adapter versioning with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/manage-adapter-versioning-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="3ebf0-110">サービスの動作を使用して、WCF LOB Adapter SDK を持つ資格情報を入力</span><span class="sxs-lookup"><span data-stu-id="3ebf0-110">Use a Service Behavior to enter credentials with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="3ebf0-111">WCF LOB Adapter SDK を使用するバインディングのプロパティとしてアダプターの設定を公開します。</span><span class="sxs-lookup"><span data-stu-id="3ebf0-111">Expose adapter settings as binding property using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="3ebf0-112">参照と WCF LOB Adapter SDK を使用してメタデータを検索</span><span class="sxs-lookup"><span data-stu-id="3ebf0-112">Browse and Search Metadata using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/browse-and-search-metadata-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="3ebf0-113">トランザクションのサポート</span><span class="sxs-lookup"><span data-stu-id="3ebf0-113">Transaction Support</span></span>](../../core/transaction-support.md)  
  
-   [<span data-ttu-id="3ebf0-114">WCF LOB Adapter SDK を使用して、IIS でアダプターをホストします。</span><span class="sxs-lookup"><span data-stu-id="3ebf0-114">Host an adapter in IIS using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="3ebf0-115">WCF LOB Adapter SDK を使用して作成されたアダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ebf0-115">Consume an Adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)  
  
## <a name="see-also"></a><span data-ttu-id="3ebf0-116">参照</span><span class="sxs-lookup"><span data-stu-id="3ebf0-116">See Also</span></span>  
 <span data-ttu-id="3ebf0-117">[WCF LOB Adapter SDK を概要します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="3ebf0-117">[Get started with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="3ebf0-118">WCF アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3ebf0-118">Troubleshooting the WCF Adapters</span></span>](../../core/troubleshooting-the-wcf-adapters.md)
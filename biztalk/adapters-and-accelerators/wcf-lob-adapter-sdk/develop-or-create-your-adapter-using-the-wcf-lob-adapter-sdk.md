---
title: 開発または WCF LOB Adapter SDK を使用して、アダプターの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ca8c03a-1e4a-4077-b4cb-4e184b520bbb
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d10f03639eb7c0c452887819d4c606d562ca7bf0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363661"
---
# <a name="develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="45740-102">開発または WCF LOB Adapter SDK を使用して、アダプターの作成</span><span class="sxs-lookup"><span data-stu-id="45740-102">Develop or create your adapter using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="45740-103">このセクションには使用してアダプターを作成している開発者向けの情報が含まれています、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="45740-103">This section contains information for developers who are creating adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="45740-104">いずれかの .NET で通常使用されるアダプターの開発が完了すると、または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]操作とデータを目的のターゲットの基幹業務システムにアクセスする手段として開発者。</span><span class="sxs-lookup"><span data-stu-id="45740-104">Once the adapter has been developed, it is usually consumed by either .NET or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] developers as a way to access operations and data in a desired target line-of-business system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45740-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="45740-105">In This Section</span></span>  
  
-   [<span data-ttu-id="45740-106">WCF LOB Adapter SDK を使用して開発のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="45740-106">Development Best Practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="45740-107">WCF LOB Adapter SDK の WSDL プロキシを使用した名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="45740-107">Use namespaces with the WSDL-Proxy in the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="45740-108">WCF LOB Adapter SDK と WSDL PortType ドキュメント スキーマについて説明します</span><span class="sxs-lookup"><span data-stu-id="45740-108">Describe the WSDL PortType Documentation Schema with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="45740-109">WCF LOB アダプター SDK を使用した、アダプター バージョンを管理します。</span><span class="sxs-lookup"><span data-stu-id="45740-109">Manage adapter versioning with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/manage-adapter-versioning-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="45740-110">サービスの動作を使用して、WCF LOB アダプター SDK を使用した資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="45740-110">Use a Service Behavior to enter credentials with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="45740-111">WCF LOB Adapter SDK を使用してバインドのプロパティとしてアダプターの設定を公開します。</span><span class="sxs-lookup"><span data-stu-id="45740-111">Expose adapter settings as binding property using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="45740-112">参照と WCF LOB Adapter SDK を使用してメタデータの検索</span><span class="sxs-lookup"><span data-stu-id="45740-112">Browse and Search Metadata using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/browse-and-search-metadata-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="45740-113">トランザクションのサポート</span><span class="sxs-lookup"><span data-stu-id="45740-113">Transaction Support</span></span>](../../core/transaction-support.md)  
  
-   [<span data-ttu-id="45740-114">WCF LOB Adapter SDK を使用して、IIS でアダプターをホストします。</span><span class="sxs-lookup"><span data-stu-id="45740-114">Host an adapter in IIS using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="45740-115">WCF LOB Adapter SDK を使用して作成されたアダプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="45740-115">Consume an Adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)  
  
## <a name="see-also"></a><span data-ttu-id="45740-116">参照</span><span class="sxs-lookup"><span data-stu-id="45740-116">See Also</span></span>  
 <span data-ttu-id="45740-117">[WCF LOB Adapter SDK を概要します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="45740-117">[Get started with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="45740-118">WCF アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="45740-118">Troubleshooting the WCF Adapters</span></span>](../../core/troubleshooting-the-wcf-adapters.md)
---
title: WCF サービスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81082cacafb1f04d54920648d8f588a4b2ccc50a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396733"
---
# <a name="using-wcf-services"></a><span data-ttu-id="74c15-102">WCF サービスの使用</span><span class="sxs-lookup"><span data-stu-id="74c15-102">Using WCF Services</span></span>
<span data-ttu-id="74c15-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Communication Foundation (WCF) 用の組み込みサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="74c15-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Windows Communication Foundation (WCF).</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="74c15-104">再利用し、すべての既存の WCF サービス、オーケストレーション内の集計ができます。</span><span class="sxs-lookup"><span data-stu-id="74c15-104">enables you to reuse and aggregate all your existing WCF services within your orchestrations.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="74c15-105">WCF サービスにもネイティブ アダプターのサポートを実装します。</span><span class="sxs-lookup"><span data-stu-id="74c15-105">also implements support for native adapters in WCF services.</span></span> <span data-ttu-id="74c15-106">ネイティブ アダプタのサポートは、スケーラビリティ、フォールト トレランス、およびコードを記述することがなく追跡の WCF サービスの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="74c15-106">Native adapter support provides scalability, fault tolerance, and tracking capabilities for WCF services without requiring you to write code.</span></span> <span data-ttu-id="74c15-107">WCF アダプターについては、次を参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="74c15-107">For information about the WCF adapters, see [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
 <span data-ttu-id="74c15-108">WCF サービスでのサポート[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は 2 つのカテゴリに分類されます: 発行または WCF サービスの場合は、作成または呼び出しまたは WCF サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="74c15-108">The WCF services support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] falls into two categories: publishing or creating WCF services, or calling or consuming WCF services.</span></span>  
  
 <span data-ttu-id="74c15-109">**WCF サービスの公開**</span><span class="sxs-lookup"><span data-stu-id="74c15-109">**Publishing WCF services**</span></span>  
  
 <span data-ttu-id="74c15-110">(公開) を公開するオーケストレーションおよびスキーマを WCF 分離 WCF アダプターで WCF サービスとしてのサービス ロジックとビジネス プロセス ロジック。</span><span class="sxs-lookup"><span data-stu-id="74c15-110">You can publish (expose) your orchestrations and schemas as WCF services with the WCF adapters to separate the WCF service logic from the business process logic.</span></span> <span data-ttu-id="74c15-111">分離を作成する、BizTalk WCF サービス公開ウィザードを使用する分離 WCF アダプタでの WCF 受信場所では、インターネット インフォメーション サービス (IIS) を実行する Web アプリケーションによってホストされています。</span><span class="sxs-lookup"><span data-stu-id="74c15-111">For isolated WCF adapters, you can use the BizTalk WCF Service Publishing Wizard to create isolated WCF receive locations hosted by Web applications running in Internet Information Services (IIS).</span></span> <span data-ttu-id="74c15-112">インプロセス WCF アダプタでは、BizTalk WCF サービス公開ウィザードで WCF の任意の場所のサービス メタデータを発行できます。</span><span class="sxs-lookup"><span data-stu-id="74c15-112">For the in-process WCF adapters, you can publish service metadata for any WCF locations with the BizTalk WCF Service Publishing Wizard.</span></span>  <span data-ttu-id="74c15-113">メタデータの公開では、svcutil.exe ユーティリティを使用してクライアント コードの作成を許可します。</span><span class="sxs-lookup"><span data-stu-id="74c15-113">The publishing of metadata allows the creation of client code using the svcutil.exe utility.</span></span>  
  
 <span data-ttu-id="74c15-114">**WCF サービスの使用**</span><span class="sxs-lookup"><span data-stu-id="74c15-114">**Consuming WCF services**</span></span>  
  
 <span data-ttu-id="74c15-115">BizTalk WCF サービス使用ウィザードを使用して、BizTalk オーケストレーションや種類、WCF サービスのメタデータ ドキュメントに基づいて WCF サービスを使用するなどの BizTalk アイテムを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="74c15-115">You can use the BizTalk WCF Service Consuming Wizard to generate the BizTalk artifacts, such as BizTalk orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span> <span data-ttu-id="74c15-116">メタデータは、クライアントとして外部サービスにアクセスする送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="74c15-116">Metadata allows a send port to access an external service as a client.</span></span> <span data-ttu-id="74c15-117">純粋に、バインド、およびコントラクト、エンドポイント アドレスを記述するメタデータが使用されます。</span><span class="sxs-lookup"><span data-stu-id="74c15-117">Metadata is used purely for describing the endpoint address, binding, and contract.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74c15-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="74c15-118">In This Section</span></span>  
  
-   [<span data-ttu-id="74c15-119">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="74c15-119">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="74c15-120">WCF サービスの利用</span><span class="sxs-lookup"><span data-stu-id="74c15-120">Consuming WCF Services</span></span>](../core/consuming-wcf-services.md)  
  
-   [<span data-ttu-id="74c15-121">WCF アダプターのメッセージ本文の指定</span><span class="sxs-lookup"><span data-stu-id="74c15-121">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="74c15-122">WCF アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="74c15-122">WCF Adapter Walkthroughs</span></span>](../core/wcf-adapter-walkthroughs.md)
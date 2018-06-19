---
title: WCF サービスの使用 |Microsoft ドキュメント
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
ms.openlocfilehash: 29b984bcda798796565113739c6088af6d569f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287794"
---
# <a name="using-wcf-services"></a><span data-ttu-id="5dba8-102">WCF サービスの使用</span><span class="sxs-lookup"><span data-stu-id="5dba8-102">Using WCF Services</span></span>
<span data-ttu-id="5dba8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Communication Foundation (WCF) の組み込みサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="5dba8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides built-in support for Windows Communication Foundation (WCF).</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5dba8-104">使用すると、再利用し、すべての既存の WCF サービス、オーケストレーション内に集約できます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-104"> enables you to reuse and aggregate all your existing WCF services within your orchestrations.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5dba8-105">WCF サービスでのネイティブ アダプタのサポートも実装します。</span><span class="sxs-lookup"><span data-stu-id="5dba8-105"> also implements support for native adapters in WCF services.</span></span> <span data-ttu-id="5dba8-106">ネイティブ アダプタのサポートにより、コードを記述しなくても、WCF サービスのスケーラビリティ、フォールト トレランス、および追跡の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-106">Native adapter support provides scalability, fault tolerance, and tracking capabilities for WCF services without requiring you to write code.</span></span> <span data-ttu-id="5dba8-107">WCF アダプターについては、次を参照してください。 [WCF アダプタ](../core/wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="5dba8-107">For information about the WCF adapters, see [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
 <span data-ttu-id="5dba8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での WCF サービスのサポートは、WCF サービスの公開 (作成) と WCF サービスの呼び出し (利用) の 2 種類に分類されます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-108">The WCF services support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] falls into two categories: publishing or creating WCF services, or calling or consuming WCF services.</span></span>  
  
 <span data-ttu-id="5dba8-109">**WCF サービスの公開**</span><span class="sxs-lookup"><span data-stu-id="5dba8-109">**Publishing WCF services**</span></span>  
  
 <span data-ttu-id="5dba8-110">WCF アダプタを使用してオーケストレーションとスキーマを Web サービスとして公開すると、WCF サービス ロジックとビジネス プロセス ロジックを区別できます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-110">You can publish (expose) your orchestrations and schemas as WCF services with the WCF adapters to separate the WCF service logic from the business process logic.</span></span> <span data-ttu-id="5dba8-111">分離 WCF アダプタでは、BizTalk WCF サービス公開ウィザードを使用して、インターネット インフォメーション サービス (IIS) で実行されている Web アプリケーションでホストされる分離された WCF 受信場所を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-111">For isolated WCF adapters, you can use the BizTalk WCF Service Publishing Wizard to create isolated WCF receive locations hosted by Web applications running in Internet Information Services (IIS).</span></span> <span data-ttu-id="5dba8-112">インプロセス WCF アダプタでは、BizTalk WCF サービス公開ウィザードを使用して、WCF に関する場所のサービス メタデータを公開できます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-112">For the in-process WCF adapters, you can publish service metadata for any WCF locations with the BizTalk WCF Service Publishing Wizard.</span></span>  <span data-ttu-id="5dba8-113">メタデータの公開によって、svcutil.exe ユーティリティを使用してクライアント コードを作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5dba8-113">The publishing of metadata allows the creation of client code using the svcutil.exe utility.</span></span>  
  
 <span data-ttu-id="5dba8-114">**WCF サービスの使用**</span><span class="sxs-lookup"><span data-stu-id="5dba8-114">**Consuming WCF services**</span></span>  
  
 <span data-ttu-id="5dba8-115">BizTalk WCF サービス使用ウィザードを使用すると、BizTalk オーケストレーションや種類など、WCF サービスのメタデータ ドキュメントに基づいて WCF サービスを利用するための BizTalk アイテムを生成できます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-115">You can use the BizTalk WCF Service Consuming Wizard to generate the BizTalk artifacts, such as BizTalk orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span> <span data-ttu-id="5dba8-116">メタデータによって、送信ポートはクライアントとして外部サービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-116">Metadata allows a send port to access an external service as a client.</span></span> <span data-ttu-id="5dba8-117">メタデータは、エンドポイント アドレス、バインド、およびコントラクトの記述にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dba8-117">Metadata is used purely for describing the endpoint address, binding, and contract.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5dba8-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5dba8-118">In This Section</span></span>  
  
-   [<span data-ttu-id="5dba8-119">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="5dba8-119">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)  
  
-   [<span data-ttu-id="5dba8-120">WCF サービスの使用</span><span class="sxs-lookup"><span data-stu-id="5dba8-120">Consuming WCF Services</span></span>](../core/consuming-wcf-services.md)  
  
-   [<span data-ttu-id="5dba8-121">WCF アダプタのメッセージ本文の指定</span><span class="sxs-lookup"><span data-stu-id="5dba8-121">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="5dba8-122">WCF アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="5dba8-122">WCF Adapter Walkthroughs</span></span>](../core/wcf-adapter-walkthroughs.md)
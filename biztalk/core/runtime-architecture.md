---
title: "ランタイム アーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- architecture, runtime
- runtime
ms.assetid: feff9a84-f19b-44c9-8d05-8e6015bb1ef9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e45ac745dbf6704f06f61155b3f57edfdec9e09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="runtime-architecture"></a><span data-ttu-id="03cc9-102">ランタイム アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="03cc9-102">Runtime Architecture</span></span>
<span data-ttu-id="03cc9-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のさまざまなコンポーネントに関する詳細な情報を確認する前に、コンポーネントが製品の全体的なアーキテクチャにどのように組み込まれているかを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="03cc9-103">Before reviewing more detailed information about the various components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is important that you have an understanding of how the components fit into the overall architecture of the product.</span></span> <span data-ttu-id="03cc9-104">BizTalk Server ランタイムは、メッセージがシステムに公開され、次に 1 つまたは複数のアクティブなサブスクライバーによって受信される公開/サブスクライブ アーキテクチャに基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="03cc9-104">The BizTalk Server runtime is built on a publish/subscribe architecture in which a message is published into the system, and then received by one or more active subscribers.</span></span> <span data-ttu-id="03cc9-105">このアーキテクチャの異なる特性がありますが、BizTalk Server で実装されるモデルとも呼ばれます*コンテンツ ベースのパブリッシュ/サブスクライブ*です。</span><span class="sxs-lookup"><span data-stu-id="03cc9-105">Different flavors of this architecture exist, but the model implemented in BizTalk Server is often called *content-based publish/subscribe*.</span></span>  
  
 <span data-ttu-id="03cc9-106">コンテンツ ベースの公開/サブスクライブ モデルでは、サブスクライバーはメッセージに関する条件のセットを使用して、受信するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="03cc9-106">In a content-based publish/subscribe model, subscribers specify the messages they want to receive using a set of criteria about the message.</span></span> <span data-ttu-id="03cc9-107">メッセージは公開されたときに評価され、サブスクリプションに一致するすべてのアクティブなサブスクライバー (フィルター式で示す) がメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="03cc9-107">The message is evaluated at the time it is published, and all of the active subscribers with matching subscriptions (indicated by filter expressions), receive the message.</span></span> <span data-ttu-id="03cc9-108">BizTalk Server では、サブスクリプションを構築するために使用する条件がメッセージの内容から取得される必要がなく、メッセージに関するコンテキスト情報も含まれる場合があるので、コンテンツ ベースという名前はあまりふさわしくありません。</span><span class="sxs-lookup"><span data-stu-id="03cc9-108">As it applies to BizTalk Server, content-based is a bit of a misnomer, however, because the criteria used to build subscriptions do not have to come from the message content, and may include contextual information about the message as well.</span></span> <span data-ttu-id="03cc9-109">サブスクリプション メカニズムの詳細については、「[パブリッシュとサブスクライブ アーキテクチャ](../core/publish-and-subscribe-architecture.md)です。</span><span class="sxs-lookup"><span data-stu-id="03cc9-109">For details of the subscription mechanism, see [Publish and Subscribe Architecture](../core/publish-and-subscribe-architecture.md).</span></span>  
  
 <span data-ttu-id="03cc9-110">次のセクションでは、BizTalk Server ランタイム アーキテクチャのさまざまなコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="03cc9-110">The sections that follow describe the various components of the BizTalk Server runtime architecture.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03cc9-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="03cc9-111">In This Section</span></span>  
  
-   [<span data-ttu-id="03cc9-112">BizTalk Server メッセージ</span><span class="sxs-lookup"><span data-stu-id="03cc9-112">The BizTalk Server Message</span></span>](../core/the-biztalk-server-message.md)  
  
-   [<span data-ttu-id="03cc9-113">メッセージのライフ サイクル</span><span class="sxs-lookup"><span data-stu-id="03cc9-113">Lifecycle of a Message</span></span>](../core/lifecycle-of-a-message.md)  
  
-   [<span data-ttu-id="03cc9-114">メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="03cc9-114">Processing the Message</span></span>](../core/processing-the-message.md)  
  
-   [<span data-ttu-id="03cc9-115">要求-応答のメッセージング</span><span class="sxs-lookup"><span data-stu-id="03cc9-115">Request-Response Messaging</span></span>](../core/request-response-messaging.md)  
  
-   [<span data-ttu-id="03cc9-116">メッセージング エンジン</span><span class="sxs-lookup"><span data-stu-id="03cc9-116">The Messaging Engine</span></span>](../core/the-messaging-engine.md)  
  
-   [<span data-ttu-id="03cc9-117">エンティティ</span><span class="sxs-lookup"><span data-stu-id="03cc9-117">Entities</span></span>](../core/entities.md)  
  
-   [<span data-ttu-id="03cc9-118">成果物</span><span class="sxs-lookup"><span data-stu-id="03cc9-118">Artifacts</span></span>](../core/artifacts.md)  
  
-   [<span data-ttu-id="03cc9-119">エンタープライズ シングル サインオン (SSO)</span><span class="sxs-lookup"><span data-stu-id="03cc9-119">Enterprise Single Sign-On (SSO)</span></span>](../core/enterprise-single-sign-on-sso.md)  
  
-   [<span data-ttu-id="03cc9-120">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="03cc9-120">Business Rules Engine</span></span>](../core/business-rules-engine.md)  
  
-   [<span data-ttu-id="03cc9-121">BizTalk アセンブリ</span><span class="sxs-lookup"><span data-stu-id="03cc9-121">BizTalk Assemblies</span></span>](../core/biztalk-assemblies.md)
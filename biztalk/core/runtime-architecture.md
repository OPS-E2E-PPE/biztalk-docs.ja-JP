---
title: ランタイムのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- architecture, runtime
- runtime
ms.assetid: feff9a84-f19b-44c9-8d05-8e6015bb1ef9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6b7a01f8919a1c2bee415df3733394462d59f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393973"
---
# <a name="runtime-architecture"></a><span data-ttu-id="a794a-102">ランタイム アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="a794a-102">Runtime Architecture</span></span>
<span data-ttu-id="a794a-103">さまざまなコンポーネントに関する情報を確認する前に詳細[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントが、製品の全体的なアーキテクチャに適合させる方法を理解することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="a794a-103">Before reviewing more detailed information about the various components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], it is important that you have an understanding of how the components fit into the overall architecture of the product.</span></span> <span data-ttu-id="a794a-104">BizTalk Server ランタイムは、メッセージが、システムに公開および 1 つまたは複数のアクティブなサブスクライバーで受信し、パブリッシュ/サブスクライブ アーキテクチャに基づいて構築されます。</span><span class="sxs-lookup"><span data-stu-id="a794a-104">The BizTalk Server runtime is built on a publish/subscribe architecture in which a message is published into the system, and then received by one or more active subscribers.</span></span> <span data-ttu-id="a794a-105">このアーキテクチャのさまざまな種類があります。 しかし、BizTalk Server で実装されるモデルとも呼ばれます*コンテンツに基づく公開/定期受信*します。</span><span class="sxs-lookup"><span data-stu-id="a794a-105">Different flavors of this architecture exist, but the model implemented in BizTalk Server is often called *content-based publish/subscribe*.</span></span>  
  
 <span data-ttu-id="a794a-106">コンテンツ ベースのパブリッシュ/サブスクライブ モデルでは、サブスクライバーは、メッセージに関する条件のセットを使用して受信するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="a794a-106">In a content-based publish/subscribe model, subscribers specify the messages they want to receive using a set of criteria about the message.</span></span> <span data-ttu-id="a794a-107">メッセージが発行時に評価され、すべてのアクティブなサブスクライバー (フィルター式によって示されます) のサブスクリプションに一致するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a794a-107">The message is evaluated at the time it is published, and all of the active subscribers with matching subscriptions (indicated by filter expressions), receive the message.</span></span> <span data-ttu-id="a794a-108">BizTalk Server に適用される、コンテンツに基づくが、若干不適切な名称、ただし、サブスクリプションを構築するための条件は、メッセージの内容から取得する必要はなくもメッセージに関するコンテキスト情報を含めることができますです。</span><span class="sxs-lookup"><span data-stu-id="a794a-108">As it applies to BizTalk Server, content-based is a bit of a misnomer, however, because the criteria used to build subscriptions do not have to come from the message content, and may include contextual information about the message as well.</span></span> <span data-ttu-id="a794a-109">サブスクリプション メカニズムの詳細については、次を参照してください。[発行およびサブスクライブ アーキテクチャ](../core/publish-and-subscribe-architecture.md)します。</span><span class="sxs-lookup"><span data-stu-id="a794a-109">For details of the subscription mechanism, see [Publish and Subscribe Architecture](../core/publish-and-subscribe-architecture.md).</span></span>  
  
 <span data-ttu-id="a794a-110">次のセクションでは、BizTalk Server ランタイム アーキテクチャのさまざまなコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a794a-110">The sections that follow describe the various components of the BizTalk Server runtime architecture.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a794a-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a794a-111">In This Section</span></span>  
  
-   [<span data-ttu-id="a794a-112">BizTalk Server メッセージ</span><span class="sxs-lookup"><span data-stu-id="a794a-112">The BizTalk Server Message</span></span>](../core/the-biztalk-server-message.md)  
  
-   [<span data-ttu-id="a794a-113">メッセージのライフサイクル</span><span class="sxs-lookup"><span data-stu-id="a794a-113">Lifecycle of a Message</span></span>](../core/lifecycle-of-a-message.md)  
  
-   [<span data-ttu-id="a794a-114">メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="a794a-114">Processing the Message</span></span>](../core/processing-the-message.md)  
  
-   [<span data-ttu-id="a794a-115">要求 - 応答メッセージング</span><span class="sxs-lookup"><span data-stu-id="a794a-115">Request-Response Messaging</span></span>](../core/request-response-messaging.md)  
  
-   [<span data-ttu-id="a794a-116">メッセージング エンジン</span><span class="sxs-lookup"><span data-stu-id="a794a-116">The Messaging Engine</span></span>](../core/the-messaging-engine.md)  
  
-   [<span data-ttu-id="a794a-117">エンティティ</span><span class="sxs-lookup"><span data-stu-id="a794a-117">Entities</span></span>](../core/entities.md)  
  
-   [<span data-ttu-id="a794a-118">アイテム</span><span class="sxs-lookup"><span data-stu-id="a794a-118">Artifacts</span></span>](../core/artifacts.md)  
  
-   [<span data-ttu-id="a794a-119">Enterprise Single Sign-On (SSO)</span><span class="sxs-lookup"><span data-stu-id="a794a-119">Enterprise Single Sign-On (SSO)</span></span>](../core/enterprise-single-sign-on-sso.md)  
  
-   [<span data-ttu-id="a794a-120">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="a794a-120">Business Rules Engine</span></span>](../core/business-rules-engine.md)  
  
-   [<span data-ttu-id="a794a-121">BizTalk アセンブリ</span><span class="sxs-lookup"><span data-stu-id="a794a-121">BizTalk Assemblies</span></span>](../core/biztalk-assemblies.md)
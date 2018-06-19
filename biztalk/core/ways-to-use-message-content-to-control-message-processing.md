---
title: メッセージ処理のコントロール メッセージの内容を使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e3792e-9cd4-42b6-8b9d-3c2a022a16d6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73d356496d07bb2227aa514ee68f2a2a51e2291b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288874"
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a><span data-ttu-id="43149-102">メッセージ処理を管理するためのメッセージの内容の使用方法</span><span class="sxs-lookup"><span data-stu-id="43149-102">Ways to Use Message Content to Control Message Processing</span></span>
<span data-ttu-id="43149-103">プロパティの昇格の 2 種類があります:**識別フィールド**と**プロパティ フィールド**、後者のプロパティ スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="43149-103">There are two types of property promotion: **Distinguished Fields** and **Property Fields**, the latter of which uses property schemas.</span></span> <span data-ttu-id="43149-104">BizTalk エディターで、管理する両方のプロパティの昇格の型を使用して、**プロパティの昇格**を使用してアクセスされる ダイアログ ボックス、**プロパティの昇格**のプロパティ、 **スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="43149-104">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43149-105">昇格できる値にはいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="43149-105">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="43149-106">詳細については、表を参照して[プロパティの昇格](../core/promoting-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="43149-106">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
 <span data-ttu-id="43149-107">シナリオの詳細に基づいて、使用するプロパティの昇格の種類を決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="43149-107">You must decide which type of property promotion to use based on the details of your scenario.</span></span> <span data-ttu-id="43149-108">次の相違を考慮**識別フィールド**プロパティの昇格と**プロパティ フィールド**プロパティの昇格。</span><span class="sxs-lookup"><span data-stu-id="43149-108">Consider the following distinctions between **Distinguished Field** property promotion and **Property Field** property promotion:</span></span>  
  
-   <span data-ttu-id="43149-109">**識別フィールド**メッセージのルーティングに参加できませんし、したがっては表示されません、フィルター式にします。</span><span class="sxs-lookup"><span data-stu-id="43149-109">**Distinguished Fields** cannot participate in message routing and therefore they do not appear in the filter expressions.</span></span> <span data-ttu-id="43149-110">識別フィールドは、オーケストレーションのコンテキスト内でのみ使用できます。ただし、メッセージの送受信を行うときのオーバーヘッドが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="43149-110">They are only available within the context of an orchestration but they have less overhead when sending and receiving messages.</span></span>  
  
-   <span data-ttu-id="43149-111">**識別フィールド**サイズの制限はありません。</span><span class="sxs-lookup"><span data-stu-id="43149-111">**Distinguished Fields** do not have any size limitations.</span></span> <span data-ttu-id="43149-112">**プロパティ フィールド**は 255 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="43149-112">**Property Fields** are limited to 255 characters.</span></span>  
  
-   <span data-ttu-id="43149-113">**識別フィールド**、個別のアイテムに対して作成するを必要としない**プロパティ フィールド**の作成とプロパティ スキーマのメンテナンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="43149-113">**Distinguished Fields** do not require any separate artifacts to be created whereas **Property Fields** require the creation and maintenance of a property schema.</span></span>  
  
 <span data-ttu-id="43149-114">これらの考慮事項をさせたとしてノードを昇格する必要があります**プロパティ フィールド**メッセージのルーティングまたは追跡目的での昇格させたプロパティを使用する場合にのみです。</span><span class="sxs-lookup"><span data-stu-id="43149-114">Drawing upon these considerations, you should promote nodes as **Property Fields** only when you intend to use the promoted properties for message routing or tracking purposes.</span></span> <span data-ttu-id="43149-115">それ以外の場合場合は、オーケストレーション内から昇格させたプロパティにアクセスすることのみが行う必要があります事実を利用する**識別フィールド**比べて簡単で、さらに使いやすいより**プロパティ フィールド**です。</span><span class="sxs-lookup"><span data-stu-id="43149-115">Otherwise, if you are only going to access the promoted properties from within your orchestrations, you should take advantage of the fact that **Distinguished Fields** are much cheaper, more lightweight, and more easy-to-use than **Property Fields**.</span></span>  
  
 <span data-ttu-id="43149-116">使用して昇格させたプロパティ、**識別フィールド**メカニズムは、オーケストレーション内からアクセスし、パイプラインやポートなどからアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="43149-116">Properties promoted by using the **Distinguished Field** mechanism are only accessible from within orchestrations and cannot be accessed from pipelines, ports, and so on.</span></span> <span data-ttu-id="43149-117">使用してプロパティを昇格する一方で、**プロパティ フィールド**プロパティ スキーマのメカニズムは、これらすべてのコンポーネントからアクセスできるとします。</span><span class="sxs-lookup"><span data-stu-id="43149-117">On the other hand, properties promoted by using the **Property Fields** and property schema mechanism are accessible from all of these components.</span></span> <span data-ttu-id="43149-118">また、プロパティ フィールドの値が 255 文字までに制限されていて、識別フィールドの値には制限がないという点も、重要な相違点といえます。</span><span class="sxs-lookup"><span data-stu-id="43149-118">Another important difference is that property field values are limited to 255 characters and distinguished field values have no such limit.</span></span>  
  
 <span data-ttu-id="43149-119">このセクションでは、これらの 2 種類のプロパティの昇格について説明します。また、メッセージ スキーマに対して、昇格させたプロパティを BizTalk エディターによって設定する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="43149-119">This section provides information about these two types of property promotion, including how information about how to establish such promoted properties for a message schema by using BizTalk Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43149-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="43149-120">In This Section</span></span>  
  
-   [<span data-ttu-id="43149-121">BizTalk メッセージ コンテキストのプロパティについて</span><span class="sxs-lookup"><span data-stu-id="43149-121">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)  
  
-   [<span data-ttu-id="43149-122">識別フィールドを使用してインスタンス メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="43149-122">Instance Message Processing Using Distinguished Fields</span></span>](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [<span data-ttu-id="43149-123">プロパティの昇格を使用してインスタンス メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="43149-123">Instance Message Processing Using Property Promotion</span></span>](../core/instance-message-processing-using-property-promotion.md)
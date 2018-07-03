---
title: メッセージ処理を制御するメッセージの内容を使用する方法 |Microsoft Docs
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
ms.openlocfilehash: b0036b9b16faf64d0768d2d5cc7ce1f828cfbffe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009363"
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a><span data-ttu-id="8b4ca-102">メッセージ処理を管理するためのメッセージの内容の使用方法</span><span class="sxs-lookup"><span data-stu-id="8b4ca-102">Ways to Use Message Content to Control Message Processing</span></span>
<span data-ttu-id="8b4ca-103">プロパティの昇格の 2 種類があります:**識別フィールド**と**プロパティ フィールド**、後者のプロパティ スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-103">There are two types of property promotion: **Distinguished Fields** and **Property Fields**, the latter of which uses property schemas.</span></span> <span data-ttu-id="8b4ca-104">BizTalk エディターでは、管理するこれらのプロパティの昇格の両方を使用して、**プロパティの昇格** ダイアログ ボックスを使用してアクセスできますが、**プロパティの昇格**のプロパティ、 **スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-104">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b4ca-105">昇格できる値にはいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-105">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="8b4ca-106">詳細については、表を参照して[プロパティの昇格](../core/promoting-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-106">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
 <span data-ttu-id="8b4ca-107">シナリオの詳細に基づいて、使用するプロパティの昇格の種類を決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-107">You must decide which type of property promotion to use based on the details of your scenario.</span></span> <span data-ttu-id="8b4ca-108">次の相違を考慮**識別フィールド**プロパティの昇格と**プロパティ フィールド**プロパティの昇格。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-108">Consider the following distinctions between **Distinguished Field** property promotion and **Property Field** property promotion:</span></span>  
  
- <span data-ttu-id="8b4ca-109">**識別フィールド**メッセージのルーティングに参加できないため、フィルター式で表示はされません。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-109">**Distinguished Fields** cannot participate in message routing and therefore they do not appear in the filter expressions.</span></span> <span data-ttu-id="8b4ca-110">識別フィールドは、オーケストレーションのコンテキスト内でのみ使用できます。ただし、メッセージの送受信を行うときのオーバーヘッドが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-110">They are only available within the context of an orchestration but they have less overhead when sending and receiving messages.</span></span>  
  
- <span data-ttu-id="8b4ca-111">**識別フィールド**サイズの制限はありません。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-111">**Distinguished Fields** do not have any size limitations.</span></span> <span data-ttu-id="8b4ca-112">**プロパティ フィールド**は 255 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-112">**Property Fields** are limited to 255 characters.</span></span>  
  
- <span data-ttu-id="8b4ca-113">**識別フィールド**、個別のアイテムに対して作成するを必要としない**プロパティ フィールド**の作成とプロパティ スキーマのメンテナンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-113">**Distinguished Fields** do not require any separate artifacts to be created whereas **Property Fields** require the creation and maintenance of a property schema.</span></span>  
  
  <span data-ttu-id="8b4ca-114">これらの考慮事項を培ったとしてノードを昇格する必要があります**プロパティ フィールド**のみのメッセージのルーティングまたは追跡目的で昇格させたプロパティを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-114">Drawing upon these considerations, you should promote nodes as **Property Fields** only when you intend to use the promoted properties for message routing or tracking purposes.</span></span> <span data-ttu-id="8b4ca-115">それ以外の場合場合は、オーケストレーション内から昇格させたプロパティにアクセスしようとしてのみを行う必要があります事実を利用する**識別フィールド**はかなり安くより軽量で、およびより簡単に使えるより**プロパティ フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-115">Otherwise, if you are only going to access the promoted properties from within your orchestrations, you should take advantage of the fact that **Distinguished Fields** are much cheaper, more lightweight, and more easy-to-use than **Property Fields**.</span></span>  
  
  <span data-ttu-id="8b4ca-116">使用して昇格させたプロパティ、**識別フィールド**メカニズムは、オーケストレーション内からアクセスし、パイプラインやポートなどからアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-116">Properties promoted by using the **Distinguished Field** mechanism are only accessible from within orchestrations and cannot be accessed from pipelines, ports, and so on.</span></span> <span data-ttu-id="8b4ca-117">使用してプロパティを昇格する一方で、**プロパティ フィールド**ありプロパティ スキーマのメカニズムでは、これらすべてのコンポーネントからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-117">On the other hand, properties promoted by using the **Property Fields** and property schema mechanism are accessible from all of these components.</span></span> <span data-ttu-id="8b4ca-118">また、プロパティ フィールドの値が 255 文字までに制限されていて、識別フィールドの値には制限がないという点も、重要な相違点といえます。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-118">Another important difference is that property field values are limited to 255 characters and distinguished field values have no such limit.</span></span>  
  
  <span data-ttu-id="8b4ca-119">このセクションでは、これらの 2 種類のプロパティの昇格について説明します。また、メッセージ スキーマに対して、昇格させたプロパティを BizTalk エディターによって設定する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="8b4ca-119">This section provides information about these two types of property promotion, including how information about how to establish such promoted properties for a message schema by using BizTalk Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b4ca-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8b4ca-120">In This Section</span></span>  
  
-   [<span data-ttu-id="8b4ca-121">BizTalk メッセージ コンテキストのプロパティについて</span><span class="sxs-lookup"><span data-stu-id="8b4ca-121">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)  
  
-   [<span data-ttu-id="8b4ca-122">識別フィールドを使用したインスタンス メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="8b4ca-122">Instance Message Processing Using Distinguished Fields</span></span>](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [<span data-ttu-id="8b4ca-123">プロパティの昇格を使用したインスタンス メッセージ処理</span><span class="sxs-lookup"><span data-stu-id="8b4ca-123">Instance Message Processing Using Property Promotion</span></span>](../core/instance-message-processing-using-property-promotion.md)
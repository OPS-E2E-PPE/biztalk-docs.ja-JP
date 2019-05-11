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
ms.openlocfilehash: b7791957dba89fab54813212fce3ecbd2c39fe19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393623"
---
# <a name="ways-to-use-message-content-to-control-message-processing"></a><span data-ttu-id="d9b3a-102">メッセージ処理を管理するためのメッセージの内容の使用方法</span><span class="sxs-lookup"><span data-stu-id="d9b3a-102">Ways to Use Message Content to Control Message Processing</span></span>
<span data-ttu-id="d9b3a-103">2 つの種類のプロパティの昇格があります。**識別フィールド**と**プロパティ フィールド**、後者のプロパティ スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-103">There are two types of property promotion: **Distinguished Fields** and **Property Fields**, the latter of which uses property schemas.</span></span> <span data-ttu-id="d9b3a-104">BizTalk エディターでは、管理するこれらのプロパティの昇格の両方を使用して、**プロパティの昇格** ダイアログ ボックスを使用してアクセスできますが、**プロパティの昇格**のプロパティ、 **スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-104">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9b3a-105">昇格可能な値にいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-105">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="d9b3a-106">詳細については、表を参照して[プロパティの昇格](../core/promoting-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-106">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
 <span data-ttu-id="d9b3a-107">シナリオの詳細に基づいて、使用するプロパティの昇格の種類を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-107">You must decide which type of property promotion to use based on the details of your scenario.</span></span> <span data-ttu-id="d9b3a-108">次の相違を考慮**識別フィールド**プロパティの昇格と**プロパティ フィールド**プロパティの昇格。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-108">Consider the following distinctions between **Distinguished Field** property promotion and **Property Field** property promotion:</span></span>  
  
- <span data-ttu-id="d9b3a-109">**識別フィールド**メッセージのルーティングに参加できないため、フィルター式で表示はされません。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-109">**Distinguished Fields** cannot participate in message routing and therefore they do not appear in the filter expressions.</span></span> <span data-ttu-id="d9b3a-110">オーケストレーションのコンテキスト内で使用できるだけが、メッセージの送受信時にオーバーヘッドが小さくなります。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-110">They are only available within the context of an orchestration but they have less overhead when sending and receiving messages.</span></span>  
  
- <span data-ttu-id="d9b3a-111">**識別フィールド**サイズの制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-111">**Distinguished Fields** do not have any size limitations.</span></span> <span data-ttu-id="d9b3a-112">**プロパティ フィールド**は 255 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-112">**Property Fields** are limited to 255 characters.</span></span>  
  
- <span data-ttu-id="d9b3a-113">**識別フィールド**、個別のアイテムに対して作成するを必要としない**プロパティ フィールド**の作成とプロパティ スキーマのメンテナンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-113">**Distinguished Fields** do not require any separate artifacts to be created whereas **Property Fields** require the creation and maintenance of a property schema.</span></span>  
  
  <span data-ttu-id="d9b3a-114">これらの考慮事項を培ったとしてノードを昇格する必要があります**プロパティ フィールド**のみのメッセージのルーティングまたは追跡目的で昇格させたプロパティを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-114">Drawing upon these considerations, you should promote nodes as **Property Fields** only when you intend to use the promoted properties for message routing or tracking purposes.</span></span> <span data-ttu-id="d9b3a-115">それ以外の場合場合は、オーケストレーション内から昇格させたプロパティにアクセスしようとしてのみを行う必要があります事実を利用する**識別フィールド**はかなり安くより軽量で、およびより簡単に使えるより**プロパティ フィールド**します。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-115">Otherwise, if you are only going to access the promoted properties from within your orchestrations, you should take advantage of the fact that **Distinguished Fields** are much cheaper, more lightweight, and more easy-to-use than **Property Fields**.</span></span>  
  
  <span data-ttu-id="d9b3a-116">使用して昇格させたプロパティ、**識別フィールド**メカニズムは、オーケストレーション内からアクセスし、パイプラインやポートなどからアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-116">Properties promoted by using the **Distinguished Field** mechanism are only accessible from within orchestrations and cannot be accessed from pipelines, ports, and so on.</span></span> <span data-ttu-id="d9b3a-117">使用してプロパティを昇格する一方で、**プロパティ フィールド**ありプロパティ スキーマのメカニズムでは、これらすべてのコンポーネントからアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-117">On the other hand, properties promoted by using the **Property Fields** and property schema mechanism are accessible from all of these components.</span></span> <span data-ttu-id="d9b3a-118">もう 1 つの重要な違いは、識別フィールドの値にこのような制限がありますいないをプロパティ フィールドの値は 255 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-118">Another important difference is that property field values are limited to 255 characters and distinguished field values have no such limit.</span></span>  
  
  <span data-ttu-id="d9b3a-119">このセクションは、これら 2 種類のプロパティの昇格などを設定する方法についての情報が BizTalk エディターを使用してメッセージ スキーマのプロパティを昇格する方法などについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d9b3a-119">This section provides information about these two types of property promotion, including how information about how to establish such promoted properties for a message schema by using BizTalk Editor.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9b3a-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d9b3a-120">In This Section</span></span>  
  
-   [<span data-ttu-id="d9b3a-121">BizTalk メッセージ コンテキストのプロパティについて</span><span class="sxs-lookup"><span data-stu-id="d9b3a-121">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)  
  
-   [<span data-ttu-id="d9b3a-122">識別フィールドを使用したインスタンス メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="d9b3a-122">Instance Message Processing Using Distinguished Fields</span></span>](../core/instance-message-processing-using-distinguished-fields.md)  
  
-   [<span data-ttu-id="d9b3a-123">プロパティの昇格を使用したインスタンス メッセージ処理</span><span class="sxs-lookup"><span data-stu-id="d9b3a-123">Instance Message Processing Using Property Promotion</span></span>](../core/instance-message-processing-using-property-promotion.md)
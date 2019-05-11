---
title: メッセージの構築図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Construct Message shape [Orchestration Designer], configuring
- Construct Message shape [Orchestration Designer]
- configuring [Orchestration Designer], Construct Message shapes
- Construct Message shape [Orchestration Designer], about Construct Message shape
ms.assetid: 8d052b4e-0873-4102-9462-6604423d0524
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a16900b1ee5c98c059b01f92a770f845330b9ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386168"
---
# <a name="how-to-configure-the-construct-message-shape"></a><span data-ttu-id="48213-102">メッセージの構築図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="48213-102">How to Configure the Construct Message Shape</span></span>
<span data-ttu-id="48213-103">![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")</span><span class="sxs-lookup"><span data-stu-id="48213-103">![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")</span></span>  
<span data-ttu-id="48213-104">メッセージの構築図形</span><span class="sxs-lookup"><span data-stu-id="48213-104">Construct Message shape</span></span>  
  
 <span data-ttu-id="48213-105">を構築するメッセージ変数を指定し、メッセージまたはメッセージの部分の割り当てを行います。</span><span class="sxs-lookup"><span data-stu-id="48213-105">You specify the message variable that you want to construct, and make assignments to the message or its parts.</span></span> <span data-ttu-id="48213-106">特定のメッセージに対するすべての割り当ては、同じメッセージの構築図形内で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48213-106">All assignments to any given message must take place within the same Construct Message shape.</span></span>  
  
 <span data-ttu-id="48213-107">既に構築されたメッセージ プロパティを変更する場合: が受信されたメッセージなど、2 番目の最初の割り当てと、新しいメッセージ インスタンスのプロパティを変更して新しいメッセージ インスタンスを構築する必要があります構築と変更の両方に同じメッセージの構築図形内で発生します。</span><span class="sxs-lookup"><span data-stu-id="48213-107">If you want to modify a property on a message that has already been constructed—such as a message that has been received—you must construct a new message instance by assigning the first to the second and then modifying the property on the new message instance; both the construction and modification occur within the same Construct Message shape.</span></span>  
  
### <a name="to-configure-a-construct-message-shape"></a><span data-ttu-id="48213-108">メッセージの構築図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="48213-108">To configure a Construct Message shape</span></span>  
  
1.  <span data-ttu-id="48213-109">[プロパティ] ウィンドウで使用して、**構築メッセージ**はこの図形がメッセージを指定するプロパティを構築します。</span><span class="sxs-lookup"><span data-stu-id="48213-109">In the Properties window, use the **Messages Constructed** property to specify which messages this shape will construct.</span></span>  
  
2.  <span data-ttu-id="48213-110">追加し、1 つ以上構成**変換**または**メッセージの割り当て**図形内で、**メッセージの構築図形**します。</span><span class="sxs-lookup"><span data-stu-id="48213-110">Add and configure one or more **Transform** or **Message Assignment** shapes inside the **Construct Message shape**.</span></span>
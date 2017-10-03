---
title: "メッセージの構築図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Construct Message shape [Orchestration Designer], configuring
- Construct Message shape [Orchestration Designer]
- configuring [Orchestration Designer], Construct Message shapes
- Construct Message shape [Orchestration Designer], about Construct Message shape
ms.assetid: 8d052b4e-0873-4102-9462-6604423d0524
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07b73e7fe62463767894808d7e95f12cf963e4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-construct-message-shape"></a><span data-ttu-id="1226a-102">メッセージの構築図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="1226a-102">How to Configure the Construct Message Shape</span></span>
![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")  
<span data-ttu-id="1226a-103">メッセージの構築図形</span><span class="sxs-lookup"><span data-stu-id="1226a-103">Construct Message shape</span></span>  
  
 <span data-ttu-id="1226a-104">さらに、構築するメッセージ変数を指定して、メッセージまたはメッセージの部分に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1226a-104">You specify the message variable that you want to construct, and make assignments to the message or its parts.</span></span> <span data-ttu-id="1226a-105">特定のメッセージに対するすべての割り当ては、同じメッセージの構築図形内で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1226a-105">All assignments to any given message must take place within the same Construct Message shape.</span></span>  
  
 <span data-ttu-id="1226a-106">既に構築されたメッセージのプロパティを変更する場合: が受信されたメッセージなど、2 番目に最初を割り当てる場合や、新しいメッセージ インスタンスのプロパティを変更して、新しいメッセージ インスタンスを構築する必要があります構築と変更の両方に同じメッセージの構築図形内で発生します。</span><span class="sxs-lookup"><span data-stu-id="1226a-106">If you want to modify a property on a message that has already been constructed—such as a message that has been received—you must construct a new message instance by assigning the first to the second and then modifying the property on the new message instance; both the construction and modification occur within the same Construct Message shape.</span></span>  
  
### <a name="to-configure-a-construct-message-shape"></a><span data-ttu-id="1226a-107">メッセージの構築図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="1226a-107">To configure a Construct Message shape</span></span>  
  
1.  <span data-ttu-id="1226a-108">[プロパティ] ウィンドウで使用して、**構築メッセージ**するこの図形がメッセージを指定するプロパティが構築されます。</span><span class="sxs-lookup"><span data-stu-id="1226a-108">In the Properties window, use the **Messages Constructed** property to specify which messages this shape will construct.</span></span>  
  
2.  <span data-ttu-id="1226a-109">追加して 1 つまたは複数を構成する**変換**または**メッセージの割り当て**図形の内側、**メッセージの構築図形**です。</span><span class="sxs-lookup"><span data-stu-id="1226a-109">Add and configure one or more **Transform** or **Message Assignment** shapes inside the **Construct Message shape**.</span></span>
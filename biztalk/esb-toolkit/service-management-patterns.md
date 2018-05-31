---
title: サービス管理パターン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fea915c-0074-472e-909b-fbbd88d7359c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a48639fb2a540b5b2597b34ad95ee390b4382c34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294626"
---
# <a name="service-management-patterns"></a><span data-ttu-id="23252-102">サービス管理のパターン</span><span class="sxs-lookup"><span data-stu-id="23252-102">Service Management Patterns</span></span>
## <a name="repair-and-resubmit"></a><span data-ttu-id="23252-103">修復し、再実行してください。</span><span class="sxs-lookup"><span data-stu-id="23252-103">Repair and Resubmit</span></span>  
 <span data-ttu-id="23252-104">修復と再送信のパターンが定義され、ソリューションをサービス メッセージを処理することがないと適切に、失敗したメッセージの形式での状態を外部化は、利用できるように、メッセージの内容を有効にする修復し、サービスに再送信する必要があります。メッセージの処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="23252-104">The Repair and Resubmit pattern defines a solution in which a service is unable to process a message and needs to gracefully externalize its state in the form of the failed message, enabling the message content to be available for repair and then resubmit it to a service to continue processing the message.</span></span>  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="23252-105">メカニズムによって Microsoft BizTalk メッセージングとオーケストレーションの例外を正規化して公開されている追加のアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="23252-105"> includes mechanisms by which Microsoft BizTalk messaging and orchestration exceptions can be normalized and exposed for additional action.</span></span> <span data-ttu-id="23252-106">ESB ソリューションを設計するときに、例外を処理する方法のアカウントを必要があります。</span><span class="sxs-lookup"><span data-stu-id="23252-106">When designing an ESB solution, it is important to account for how exceptions will be handled.</span></span> <span data-ttu-id="23252-107">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を例外を表示および管理する方法を示すサンプル ESB 管理ポータル アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="23252-107">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes a sample ESB Management Portal application that demonstrates how exceptions can be viewed and managed.</span></span> <span data-ttu-id="23252-108">修復および ESB 管理ポータルのサンプル アプリケーションを使用して例外を再送信の詳細については、次を参照してください。[修復と再送信メッセージ](../esb-toolkit/repairing-and-resubmitting-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="23252-108">For detailed information about repairing and resubmitting exceptions using the ESB Management Portal sample application, see [Repairing and Resubmitting Messages](../esb-toolkit/repairing-and-resubmitting-messages.md).</span></span>
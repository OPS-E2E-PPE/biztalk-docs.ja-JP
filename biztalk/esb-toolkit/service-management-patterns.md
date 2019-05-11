---
title: サービス管理のパターン |Microsoft Docs
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
ms.openlocfilehash: 1ec777e46dada4a47f00cff666b6924e448ef8b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392031"
---
# <a name="service-management-patterns"></a><span data-ttu-id="5bf3c-102">サービス管理パターン</span><span class="sxs-lookup"><span data-stu-id="5bf3c-102">Service Management Patterns</span></span>
## <a name="repair-and-resubmit"></a><span data-ttu-id="5bf3c-103">修復と再送信</span><span class="sxs-lookup"><span data-stu-id="5bf3c-103">Repair and Resubmit</span></span>  
 <span data-ttu-id="5bf3c-104">修復と再送信のパターンをサービスがメッセージを処理できないとを正常に失敗したメッセージの形式でその状態を外部化を修復し、サービスに再送信できるメッセージの内容を有効にする必要があるソリューションを定義しますメッセージの処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="5bf3c-104">The Repair and Resubmit pattern defines a solution in which a service is unable to process a message and needs to gracefully externalize its state in the form of the failed message, enabling the message content to be available for repair and then resubmit it to a service to continue processing the message.</span></span>  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] <span data-ttu-id="5bf3c-105">追加の操作のメカニズムでは、Microsoft BizTalk メッセージングとオーケストレーションの例外正規化できが公開されているが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5bf3c-105">includes mechanisms by which Microsoft BizTalk messaging and orchestration exceptions can be normalized and exposed for additional action.</span></span> <span data-ttu-id="5bf3c-106">ESB ソリューションを設計するには、これが例外を処理する方法のアカウントに重要です。</span><span class="sxs-lookup"><span data-stu-id="5bf3c-106">When designing an ESB solution, it is important to account for how exceptions will be handled.</span></span> <span data-ttu-id="5bf3c-107">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外を表示および管理する方法を示すサンプル ESB 管理ポータル アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5bf3c-107">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes a sample ESB Management Portal application that demonstrates how exceptions can be viewed and managed.</span></span> <span data-ttu-id="5bf3c-108">ESB 管理ポータルのサンプル アプリケーションを使用して例外を再送信の修復と詳細については、次を参照してください。[修復と再送信メッセージ](../esb-toolkit/repairing-and-resubmitting-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="5bf3c-108">For detailed information about repairing and resubmitting exceptions using the ESB Management Portal sample application, see [Repairing and Resubmitting Messages](../esb-toolkit/repairing-and-resubmitting-messages.md).</span></span>
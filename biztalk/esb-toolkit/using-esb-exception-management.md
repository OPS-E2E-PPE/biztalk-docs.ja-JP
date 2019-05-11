---
title: ESB 例外管理を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de6ce411-2d34-4fd8-9644-6fbc9cec266d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f3f44f7575c42b4719e6b05431178212c36210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396430"
---
# <a name="using-esb-exception-management"></a><span data-ttu-id="c4c01-102">ESB 例外管理を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4c01-102">Using ESB Exception Management</span></span>
<span data-ttu-id="c4c01-103">エラーと例外については、いくつかの ESB で別の処理ステージ中にコンテキストの範囲で発生します。</span><span class="sxs-lookup"><span data-stu-id="c4c01-103">Errors and exceptions can occur in a range of contexts and during a number of different processing stages in an ESB.</span></span> <span data-ttu-id="c4c01-104">このセクションでは、例外の処理に関する情報を提供し、ESB 管理ポータルの詳細を公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4c01-104">This section provides information about handling exceptions and describes how you can publish details through the ESB Management Portal.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="c4c01-105">概要</span><span class="sxs-lookup"><span data-stu-id="c4c01-105">Overview</span></span>  
 <span data-ttu-id="c4c01-106">BizTalk Server ソリューションでは、Enterprise Library などのフレームワークの使用などの例外を処理するために多くの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="c4c01-106">There are many ways to handle exceptions in a BizTalk Server solution, including using frameworks such as the Enterprise Library.</span></span> <span data-ttu-id="c4c01-107">ただし、ESB と BizTalk Server で開発する場合は、メッセージ ベースの環境で作業しています。</span><span class="sxs-lookup"><span data-stu-id="c4c01-107">However, when developing with ESB and BizTalk Server, you are working in a message-based environment.</span></span> <span data-ttu-id="c4c01-108">メッセージ指向では、BizTalk ソリューション内のすべてと、BizTalk 開発者は、メッセージ指向の方法で検討します。</span><span class="sxs-lookup"><span data-stu-id="c4c01-108">Everything in a BizTalk solution is message-oriented, and BizTalk developers think in a message-oriented way.</span></span> <span data-ttu-id="c4c01-109">そのため、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外処理へのメッセージ指向のアプローチを実装します。</span><span class="sxs-lookup"><span data-stu-id="c4c01-109">Therefore, the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implements a message-oriented approach to exception handling.</span></span>  
  
 <span data-ttu-id="c4c01-110">ESB 例外管理フレームワークが例外を監視する柔軟なアプローチを提供し、ソリューションの外部から発生するエラー応答に使用する設計パターンに従います: business ユニット レベルでおそらくします。</span><span class="sxs-lookup"><span data-stu-id="c4c01-110">The ESB Exception Management Framework follows a design pattern that provides a flexible approach to exception monitoring and enables error responses to originate from outside of the solution—perhaps at business-unit level.</span></span>  
  
 <span data-ttu-id="c4c01-111">次のトピックでは、さらに詳しく ESB 例外管理フレームワークについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4c01-111">The following topics discuss the ESB Exception Management Framework in more detail:</span></span>  
  
-   [<span data-ttu-id="c4c01-112">ESB 例外管理フレームワークの設計</span><span class="sxs-lookup"><span data-stu-id="c4c01-112">Design of the ESB Exception Management Framework</span></span>](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [<span data-ttu-id="c4c01-113">例外管理フレームワークのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="c4c01-113">The Components of the Exception Management Framework</span></span>](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [<span data-ttu-id="c4c01-114">例外管理フレームワークを利用する</span><span class="sxs-lookup"><span data-stu-id="c4c01-114">Using the Exception Management Framework</span></span>](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [<span data-ttu-id="c4c01-115">カスタム例外ハンドラーを作成する</span><span class="sxs-lookup"><span data-stu-id="c4c01-115">Creating Custom Exception Handlers</span></span>](../esb-toolkit/creating-custom-exception-handlers.md)
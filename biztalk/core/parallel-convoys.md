---
title: パラレルなコンボイ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Parallel Task shape [Orchestration Designer], concurrent receive tasks
- messages, convoys
- correlation sets, concurrent receive tasks
- correlation sets, Parallel Task shape [Orchestration Designer]
- orchestrations, messages
- messages, correlating to orchestrations
ms.assetid: 036aa8c0-f49c-47f0-ac1e-6c667bca3811
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c6993aa3c5dd47cb5b554dd8ab2080020ebb80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264842"
---
# <a name="parallel-convoys"></a><span data-ttu-id="8d850-102">パラレルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="8d850-102">Parallel Convoys</span></span>
<span data-ttu-id="8d850-103">パラレルなコンボイによって、複数の単一メッセージを結合して必要とされる結果を実現することができます。</span><span class="sxs-lookup"><span data-stu-id="8d850-103">A parallel convoy enables multiple single messages to join together to achieve a required result.</span></span> <span data-ttu-id="8d850-104">関連する一連のメッセージは任意の順序で受信されることがありますが、BizTalk Server は、プロセスの開始前にそのメッセージのすべてを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d850-104">The set of related messages can arrive in any order, but BizTalk Server must receive all of them before starting the process.</span></span>  
  
 <span data-ttu-id="8d850-105">たとえば、病院が新しい患者を受け入れる場合、病院は、保険情報、病歴、連絡先情報など患者からの情報をいくつか必要とします。</span><span class="sxs-lookup"><span data-stu-id="8d850-105">For example, when a hospital admits a new patient, the hospital requires several pieces of information from the patient, including insurance information, past medical history, and contact information.</span></span> <span data-ttu-id="8d850-106">保険の専門家、看護士、受付など職種の異なる何人かの人でこの情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="8d850-106">Several different people collect this information, including an insurance specialist, a nurse, and a receptionist.</span></span> <span data-ttu-id="8d850-107">これらの情報は異なる複数のシステムで処理されます。</span><span class="sxs-lookup"><span data-stu-id="8d850-107">Several different systems process this information.</span></span> <span data-ttu-id="8d850-108">これらの情報がどのような順序で収集され、提出されるかは決まっていません。</span><span class="sxs-lookup"><span data-stu-id="8d850-108">The order in which collection and submission of this information occurs is not guaranteed.</span></span> <span data-ttu-id="8d850-109">たとえば、情報収集者は別の患者の相手をするのに忙しいかもしれないし、医療記録部門のスケジュールが遅れている場合や保険システムが正しく機能していない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8d850-109">For example, information collectors may be busy with other patients, the medical records department may be behind in their schedule, or the insurance system may not be functioning correctly.</span></span> <span data-ttu-id="8d850-110">患者に関するこの情報を組織立った方法で収集することは、その患者が病院にいる間は常に必要となります。</span><span class="sxs-lookup"><span data-stu-id="8d850-110">Assembling this information for the patient in an organized manner must occur throughout the time the patient spends at the hospital.</span></span> <span data-ttu-id="8d850-111">これによって、患者は適切な医療処置と正確な医療費の請求を受けることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="8d850-111">This guarantees that the patient receives appropriate care and accurate billing.</span></span>  
  
 <span data-ttu-id="8d850-112">上記のシナリオは、パラレルなコンボイ メッセージの処理を必要とするビジネス シナリオの例です。</span><span class="sxs-lookup"><span data-stu-id="8d850-112">The preceding scenario is an example of a business scenario that requires parallel convoy message processing.</span></span> <span data-ttu-id="8d850-113">そのビジネス要件では、患者を病院に受け入れる前に、3 つの異なる種類のメッセージを受け取ることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="8d850-113">The business requirements dictate the receipt of three different types of messages before admitting the patient into the hospital.</span></span> <span data-ttu-id="8d850-114">これらの 3 つのメッセージは、保険メッセージ、病歴メッセージ、患者メッセージです。</span><span class="sxs-lookup"><span data-stu-id="8d850-114">These three messages are the Insurance, History, and Patient messages.</span></span> <span data-ttu-id="8d850-115">患者に関するこれらのメッセージのいずれもが最初に届くメッセージとなる可能性があり、これによって競合状態が発生します。</span><span class="sxs-lookup"><span data-stu-id="8d850-115">Any one of these messages can be the first message to arrive for the patient, and this creates a race condition.</span></span> <span data-ttu-id="8d850-116">解決するのにはこの問題は、3 つ**受信**図形が入れられます、**並列アクション**図形および各受信がアクティブとしてマークされて = True です。</span><span class="sxs-lookup"><span data-stu-id="8d850-116">To resolve this issue, three **Receive** shapes are put into a **Parallel Actions** shape and each receive is marked as Activate = True.</span></span> <span data-ttu-id="8d850-117">これによって、3 つのうちどのメッセージでもオーケストレーションを開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8d850-117">This enables any one of the three messages to start the orchestration.</span></span> <span data-ttu-id="8d850-118">オーケストレーション インスタンスは、処理をさらには進めず、他の 2 つのメッセージが到着するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="8d850-118">The orchestration instance waits until the other two messages arrive before proceeding to further processing.</span></span>  
  
## <a name="implementing-parallel-convoys"></a><span data-ttu-id="8d850-119">パラレルなコンボイの実装</span><span class="sxs-lookup"><span data-stu-id="8d850-119">Implementing Parallel Convoys</span></span>  
 <span data-ttu-id="8d850-120">パラレルなコンボイは、BizTalk Server の "パラレルな相関受信" のメッセージング デザイン パターンを使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="8d850-120">You can implement parallel convoys by using the "parallel correlated receives" messaging design pattern in BizTalk Server.</span></span> <span data-ttu-id="8d850-121">パラレルな相関受信が相関関係の 2 つまたは複数の分岐でステートメントを受信、**並列アクション**図形です。</span><span class="sxs-lookup"><span data-stu-id="8d850-121">Parallel correlated receives are correlated receive statements in two or more branches of a **Parallel Actions** shape.</span></span> <span data-ttu-id="8d850-122">関連付けを複数の並列タスクで初期化する場合は、関連付けられた受信のそれぞれで、まったく同じ関連付けのセットを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d850-122">If a correlation is initialized in more than one parallel task, each correlated receive must initialize exactly the same set of correlations.</span></span> <span data-ttu-id="8d850-123">関連するメッセージを受信するこのようなタスクが実際の初期化を実行する最初およびで他のタスクの検証は実行、**並列アクション**オーケストレーションの図形です。</span><span class="sxs-lookup"><span data-stu-id="8d850-123">The first such task that receives a correlated message performs the actual initialization, and validation is performed on the other tasks in the **Parallel Actions** shape in orchestration.</span></span>  
  
 <span data-ttu-id="8d850-124">パラレルなコンボイの実装の例を参照してください、SDK サンプル「パラレルなコンボイ」 [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="8d850-124">For an example of parallel convoy implementation, see the SDK sample "Parallel Convoy" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d850-125">参照</span><span class="sxs-lookup"><span data-stu-id="8d850-125">See Also</span></span>  
 <span data-ttu-id="8d850-126">[コンボイ シナリオの](../core/working-with-convoy-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="8d850-126">[Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md) </span></span>  
 [<span data-ttu-id="8d850-127">シーケンシャルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="8d850-127">Sequential Convoys</span></span>](../core/sequential-convoys.md)
---
title: パラレルなコンボイ |Microsoft Docs
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
ms.openlocfilehash: edc797c59332d9a2453f38afd5daffabfbcdac9d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393418"
---
# <a name="parallel-convoys"></a><span data-ttu-id="ed9eb-102">パラレルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="ed9eb-102">Parallel Convoys</span></span>
<span data-ttu-id="ed9eb-103">パラレルなコンボイにより、複数の単一メッセージを結合して必要な結果を実現します。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-103">A parallel convoy enables multiple single messages to join together to achieve a required result.</span></span> <span data-ttu-id="ed9eb-104">一連の関連メッセージが任意の順序で受信されることは、BizTalk Server は、プロセスを開始する前にそれらのすべてを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-104">The set of related messages can arrive in any order, but BizTalk Server must receive all of them before starting the process.</span></span>  
  
 <span data-ttu-id="ed9eb-105">たとえば、新しい患者を病院に受け入れる、ときに、病院、保険情報、過去の病歴、および連絡先情報など患者からのいくつかの情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-105">For example, when a hospital admits a new patient, the hospital requires several pieces of information from the patient, including insurance information, past medical history, and contact information.</span></span> <span data-ttu-id="ed9eb-106">複数のスタッフは、保険の専門家、看護師、受付など、この情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-106">Several different people collect this information, including an insurance specialist, a nurse, and a receptionist.</span></span> <span data-ttu-id="ed9eb-107">複数の異なるシステムでは、この情報を処理します。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-107">Several different systems process this information.</span></span> <span data-ttu-id="ed9eb-108">コレクションとこの送信順序とは限りません情報が発生します。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-108">The order in which collection and submission of this information occurs is not guaranteed.</span></span> <span data-ttu-id="ed9eb-109">たとえば、情報コレクターがビジー状態の他の患者である可能性があります、医療記録部門がありますの背後にある自分のスケジュールでまたは保険システムが正しく機能していません。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-109">For example, information collectors may be busy with other patients, the medical records department may be behind in their schedule, or the insurance system may not be functioning correctly.</span></span> <span data-ttu-id="ed9eb-110">整理された方法で、患者の情報をアセンブルする必要があります、患者が病院に費やした時間全体で発生します。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-110">Assembling this information for the patient in an organized manner must occur throughout the time the patient spends at the hospital.</span></span> <span data-ttu-id="ed9eb-111">これにより、患者が適切な注意と正確な課金を受け取ることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-111">This guarantees that the patient receives appropriate care and accurate billing.</span></span>  
  
 <span data-ttu-id="ed9eb-112">上記のシナリオでは、パラレルなコンボイ メッセージの処理を必要とするビジネス シナリオの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-112">The preceding scenario is an example of a business scenario that requires parallel convoy message processing.</span></span> <span data-ttu-id="ed9eb-113">ビジネス要件では、患者を病院の受け入れを許可する前に次の 3 つの異なる種類のメッセージの受信によって決まります。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-113">The business requirements dictate the receipt of three different types of messages before admitting the patient into the hospital.</span></span> <span data-ttu-id="ed9eb-114">これら 3 つのメッセージは、保険、履歴、および患者メッセージです。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-114">These three messages are the Insurance, History, and Patient messages.</span></span> <span data-ttu-id="ed9eb-115">これらのメッセージのいずれかは、患者の最初のメッセージ、競合状態が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-115">Any one of these messages can be the first message to arrive for the patient, and this creates a race condition.</span></span> <span data-ttu-id="ed9eb-116">解決するのにはこの問題は、3 つ**受信**図形が入れられます、**並列アクション**図形と各受信は、アクティブ化としてマークされて = True。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-116">To resolve this issue, three **Receive** shapes are put into a **Parallel Actions** shape and each receive is marked as Activate = True.</span></span> <span data-ttu-id="ed9eb-117">これにより、オーケストレーションを開始する 3 つのメッセージのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-117">This enables any one of the three messages to start the orchestration.</span></span> <span data-ttu-id="ed9eb-118">オーケストレーション インスタンスは、さらに処理を続行する前に他の 2 つのメッセージが到着するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-118">The orchestration instance waits until the other two messages arrive before proceeding to further processing.</span></span>  
  
## <a name="implementing-parallel-convoys"></a><span data-ttu-id="ed9eb-119">パラレルなコンボイの実装</span><span class="sxs-lookup"><span data-stu-id="ed9eb-119">Implementing Parallel Convoys</span></span>  
 <span data-ttu-id="ed9eb-120">パラレルなコンボイを使用して実装することができます、"パラレルな相関受信"メッセージング デザイン パターンを BizTalk Server です。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-120">You can implement parallel convoys by using the "parallel correlated receives" messaging design pattern in BizTalk Server.</span></span> <span data-ttu-id="ed9eb-121">パラレルな相関受信が相関関係の 2 つ以上の分岐でステートメントを受信する**並列アクション**図形。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-121">Parallel correlated receives are correlated receive statements in two or more branches of a **Parallel Actions** shape.</span></span> <span data-ttu-id="ed9eb-122">相関関係は、1 つ以上の並列タスクで初期化されている場合、関連付けられた受信の各はまったく同じ相関関係のセットを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-122">If a correlation is initialized in more than one parallel task, each correlated receive must initialize exactly the same set of correlations.</span></span> <span data-ttu-id="ed9eb-123">相関関係を持つメッセージを受信するこのようなタスクが実際の初期化を実行する最初と検証は他のタスクを実行、**並列アクション**オーケストレーションの図形。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-123">The first such task that receives a correlated message performs the actual initialization, and validation is performed on the other tasks in the **Parallel Actions** shape in orchestration.</span></span>  
  
 <span data-ttu-id="ed9eb-124">パラレルなコンボイの実装などの SDK サンプル「パラレルなコンボイ」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="ed9eb-124">For an example of parallel convoy implementation, see the SDK sample "Parallel Convoy" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9eb-125">参照</span><span class="sxs-lookup"><span data-stu-id="ed9eb-125">See Also</span></span>  
 <span data-ttu-id="ed9eb-126">[コンボイ シナリオの](../core/working-with-convoy-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="ed9eb-126">[Working with Convoy Scenarios](../core/working-with-convoy-scenarios.md) </span></span>  
 [<span data-ttu-id="ed9eb-127">シーケンシャルなコンボイ</span><span class="sxs-lookup"><span data-stu-id="ed9eb-127">Sequential Convoys</span></span>](../core/sequential-convoys.md)
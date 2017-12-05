---
title: "ビジネス シナリオのサンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78229d903461fe2b84033b036ef02b2838832fc0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="sample-business-scenario"></a><span data-ttu-id="38408-102">このサンプル ビジネス シナリオ</span><span class="sxs-lookup"><span data-stu-id="38408-102">Sample Business Scenario</span></span>
<span data-ttu-id="38408-103">医療プロセスは複雑な多くの場合、れ多くのシステム。</span><span class="sxs-lookup"><span data-stu-id="38408-103">Health care processes are often complex and involve many systems.</span></span> <span data-ttu-id="38408-104">例としては患者を病院に入ったときに発生するプロセスし医師がラボ テスト用の患者情報を送信します。</span><span class="sxs-lookup"><span data-stu-id="38408-104">An example is the process that occurs when a patient enters a hospital, and a physician sends the patient for a lab test.</span></span> <span data-ttu-id="38408-105">この手順に関係するには 5 つのパーティを示します。</span><span class="sxs-lookup"><span data-stu-id="38408-105">Involved in this procedure are five parties:</span></span>  
  
-   <span data-ttu-id="38408-106">推進医師</span><span class="sxs-lookup"><span data-stu-id="38408-106">The attending physician</span></span>  
  
-   <span data-ttu-id="38408-107">病院登録システム</span><span class="sxs-lookup"><span data-stu-id="38408-107">The Hospital Registration System</span></span>  
  
-   <span data-ttu-id="38408-108">医療注文入力システム</span><span class="sxs-lookup"><span data-stu-id="38408-108">The Clinical Order Entry System</span></span>  
  
-   <span data-ttu-id="38408-109">ラボ システム</span><span class="sxs-lookup"><span data-stu-id="38408-109">The Laboratory System</span></span>  
  
-   <span data-ttu-id="38408-110">課金システム</span><span class="sxs-lookup"><span data-stu-id="38408-110">The Billing System</span></span>  
  
 <span data-ttu-id="38408-111">次の手順は、このプロセスで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38408-111">The following steps might occur in this process:</span></span>  
  
1.  <span data-ttu-id="38408-112">推進医師は、患者を登録します。</span><span class="sxs-lookup"><span data-stu-id="38408-112">The attending doctor registers the patient.</span></span>  
  
    1.  <span data-ttu-id="38408-113">ADT ^ 病院登録システムによって O04 登録メッセージをブロードキャストします。</span><span class="sxs-lookup"><span data-stu-id="38408-113">An ADT^O04 registration message is broadcast by the Hospital Registration System.</span></span>  
  
    2.  <span data-ttu-id="38408-114">ADT ^ 治療注文入力システムおよび実験システムなど、メッセージをサブスクライブするすべての部門が O04 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="38408-114">The ADT^O04 message is received by all departments that subscribe to the message, including the Clinical Order Entry System and the Laboratory System.</span></span>  
  
2.  <span data-ttu-id="38408-115">医師は、ラボ機能からの診断の調査を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="38408-115">The doctor orders a diagnostic study from the laboratory facility.</span></span>  
  
    1.  <span data-ttu-id="38408-116">ORM ^ O01 注文メッセージはビジネス ルールの検証後に、治療の注文エントリ システムから送信します。</span><span class="sxs-lookup"><span data-stu-id="38408-116">An ORM^O01 order message is sent from the Clinical Order Entry System, after validation of business rules.</span></span>  
  
    2.  <span data-ttu-id="38408-117">ORM ^ 実験システム O01 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="38408-117">The ORM^O01 message is received by the Laboratory System.</span></span>  
  
3.  <span data-ttu-id="38408-118">ラボは、注文を受信し、確認メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="38408-118">The laboratory receives the order, and returns a confirmation.</span></span>  
  
    1.  <span data-ttu-id="38408-119">ORR ^ O02 注文確認メッセージが送信されるラボ システムで注文を実行できることを示すです。</span><span class="sxs-lookup"><span data-stu-id="38408-119">An ORR^O02 order-confirmation message is sent by the Laboratory System, indicating that the order can be executed.</span></span>  
  
    2.  <span data-ttu-id="38408-120">ORR ^ 治療注文入力システムが O02 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="38408-120">The ORR^O02 message is received by the Clinical Order Entry System.</span></span>  
  
4.  <span data-ttu-id="38408-121">テストの完了時には、ラボは、医師およびその他の部門に結果を送信します。</span><span class="sxs-lookup"><span data-stu-id="38408-121">On completion of the tests, the laboratory sends the results to the doctor and other departments.</span></span>  
  
    1.  <span data-ttu-id="38408-122">ORU ^ ラボ システムから R01 テスト結果のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="38408-122">An ORU^R01 test-results message is sent from the Laboratory System.</span></span>  
  
    2.  <span data-ttu-id="38408-123">ORU ^ 治療注文入力システムと課金システムが R01 メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="38408-123">The ORU^R01 message is received by the Clinical Order Entry System and the Billing System.</span></span>  
  
    3.  <span data-ttu-id="38408-124">インターフェイスのエンジンは、ワイヤレス PDA の演習の結果を受信すると、博士に電子メール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="38408-124">The Interface Engine sends out an e-mail message to the doctor, who receives the lab results on his wireless PDA.</span></span>  
  
## <a name="the-btahl7-solution"></a><span data-ttu-id="38408-125">BTAHL7 ソリューション</span><span class="sxs-lookup"><span data-stu-id="38408-125">The BTAHL7 Solution</span></span>  
 <span data-ttu-id="38408-126">上記で説明したサンプル ビジネス シナリオでは、統合が必要な医療システムの例を示します。</span><span class="sxs-lookup"><span data-stu-id="38408-126">The sample business scenario outlined above is an example of a health care system that needs integration.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="38408-127">BizTalk Server [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 次の機能を搭載したこのシナリオのソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="38408-127">BizTalk Server with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) provides a solution for this scenario that features the following functionality:</span></span>  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="38408-128">すべてのハブとスポークの配置に関連するシステムを統合します。</span><span class="sxs-lookup"><span data-stu-id="38408-128"> integrates all of the systems involved in a hub-and-spoke arrangement.</span></span> <span data-ttu-id="38408-129">各システムと直接通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="38408-129">Each system communicates directly with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="38408-130">相互に直接通信するためにはありません。</span><span class="sxs-lookup"><span data-stu-id="38408-130">They do not have to communicate directly to each other.</span></span>  
  
2.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="38408-131">ネイティブ HL7 でエンコードされたメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="38408-131"> handles HL7-encoded messages natively.</span></span> <span data-ttu-id="38408-132">カスタム コーディングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="38408-132">No custom coding is required.</span></span>  
  
3.  <span data-ttu-id="38408-133">ADT ^ O04 登録メッセージにサブスクライブできるようにするすべてのシステムに送信します。</span><span class="sxs-lookup"><span data-stu-id="38408-133">The ADT^O04 registration message is broadcast to all systems that subscribe to it.</span></span> <span data-ttu-id="38408-134">パブリッシャーとサブスクライバーのメッセージング モデル[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]柔軟に設定および管理メッセージをサブスクライブ システムの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="38408-134">The publisher-subscriber messaging model for [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] provides flexibility in setting up and maintaining the list of systems subscribing to the message.</span></span> <span data-ttu-id="38408-135">システムを追加したり、システムの残りの部分に影響を与えずに、サブスクリプションの一覧から削除することができます。</span><span class="sxs-lookup"><span data-stu-id="38408-135">You can add systems to or delete them from the subscription list without affecting the rest of the system.</span></span>  
  
4.  <span data-ttu-id="38408-136">ORM の検証に使用されるビジネス ルール ^ O01 注文メッセージは、システムの残りの部分に影響を与えずに動的に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="38408-136">The business rule used to validate the ORM^O01 order message can be changed dynamically without affecting the rest of the system.</span></span>  
  
5.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="38408-137">ORR を自動的に生成するように構成する ^ O02 注文確認 (ACK) メッセージ。</span><span class="sxs-lookup"><span data-stu-id="38408-137"> can be configured to automatically generate the ORR^O02 order-confirmation (ACK) message.</span></span>  
  
6.  <span data-ttu-id="38408-138">必要に応じて、他のユーザーと、送信するためのメッセージのバッチおよびから確認メッセージをバッチ内で上での処理できます。</span><span class="sxs-lookup"><span data-stu-id="38408-138">If necessary, you can batch any of the messages with others for sending, and process them on receipt from within the batch.</span></span>  
  
7.  <span data-ttu-id="38408-139">に対して、エンジンのすべてのメッセージを検証することができます、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X スキーマは、HL7 組織によって発行されました。</span><span class="sxs-lookup"><span data-stu-id="38408-139">You can validate all messages in the engine and against the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2X schemas published by the HL7 organization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38408-140">参照</span><span class="sxs-lookup"><span data-stu-id="38408-140">See Also</span></span>  
 [<span data-ttu-id="38408-141">BizTalk Server がビジネス ニーズを解決するしくみ</span><span class="sxs-lookup"><span data-stu-id="38408-141">How BizTalk Server Solves the Business Need</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)
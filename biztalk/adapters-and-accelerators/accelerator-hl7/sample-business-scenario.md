---
title: ビジネス シナリオのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c84acde2b7d3049c415954a561c1a53edb16a0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289944"
---
# <a name="sample-business-scenario"></a><span data-ttu-id="46487-102">サンプル ビジネス シナリオ</span><span class="sxs-lookup"><span data-stu-id="46487-102">Sample Business Scenario</span></span>
<span data-ttu-id="46487-103">医療のプロセスは複雑では多くの場合、多くのシステムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46487-103">Health care processes are often complex and involve many systems.</span></span> <span data-ttu-id="46487-104">例としては、患者が病院では、入力したときに発生するプロセスと、医師が患者のラボ テストを送信します。</span><span class="sxs-lookup"><span data-stu-id="46487-104">An example is the process that occurs when a patient enters a hospital, and a physician sends the patient for a lab test.</span></span> <span data-ttu-id="46487-105">この手順に関連するには 5 つのパーティを示します。</span><span class="sxs-lookup"><span data-stu-id="46487-105">Involved in this procedure are five parties:</span></span>  
  
- <span data-ttu-id="46487-106">在籍している医師</span><span class="sxs-lookup"><span data-stu-id="46487-106">The attending physician</span></span>  
  
- <span data-ttu-id="46487-107">病院の登録システム</span><span class="sxs-lookup"><span data-stu-id="46487-107">The Hospital Registration System</span></span>  
  
- <span data-ttu-id="46487-108">臨床注文入力システム</span><span class="sxs-lookup"><span data-stu-id="46487-108">The Clinical Order Entry System</span></span>  
  
- <span data-ttu-id="46487-109">ラボ システム</span><span class="sxs-lookup"><span data-stu-id="46487-109">The Laboratory System</span></span>  
  
- <span data-ttu-id="46487-110">課金システム</span><span class="sxs-lookup"><span data-stu-id="46487-110">The Billing System</span></span>  
  
  <span data-ttu-id="46487-111">次の手順は、このプロセスで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="46487-111">The following steps might occur in this process:</span></span>  
  
1.  <span data-ttu-id="46487-112">在籍している医師は患者を登録します。</span><span class="sxs-lookup"><span data-stu-id="46487-112">The attending doctor registers the patient.</span></span>  
  
    1.  <span data-ttu-id="46487-113">ADT ^ 病院の登録システムによって O04 登録メッセージをブロードキャストします。</span><span class="sxs-lookup"><span data-stu-id="46487-113">An ADT^O04 registration message is broadcast by the Hospital Registration System.</span></span>  
  
    2.  <span data-ttu-id="46487-114">ADT ^ O04 メッセージ Clinical、受注システムとテスト システムを含むメッセージにサブスクライブするすべての部門で受信されます。</span><span class="sxs-lookup"><span data-stu-id="46487-114">The ADT^O04 message is received by all departments that subscribe to the message, including the Clinical Order Entry System and the Laboratory System.</span></span>  
  
2.  <span data-ttu-id="46487-115">医師は、実験施設から診断調査を指示します。</span><span class="sxs-lookup"><span data-stu-id="46487-115">The doctor orders a diagnostic study from the laboratory facility.</span></span>  
  
    1.  <span data-ttu-id="46487-116">ORM ^ O01 注文メッセージはビジネス ルールの検証後に、臨床注文入力システムから送信します。</span><span class="sxs-lookup"><span data-stu-id="46487-116">An ORM^O01 order message is sent from the Clinical Order Entry System, after validation of business rules.</span></span>  
  
    2.  <span data-ttu-id="46487-117">ORM ^ O01 メッセージ ラボ システムで受信されます。</span><span class="sxs-lookup"><span data-stu-id="46487-117">The ORM^O01 message is received by the Laboratory System.</span></span>  
  
3.  <span data-ttu-id="46487-118">ラボは、注文を受信し、確認メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="46487-118">The laboratory receives the order, and returns a confirmation.</span></span>  
  
    1.  <span data-ttu-id="46487-119">ORR ^ O02 注文確認メッセージは順序を実行できることを示す、研究室のシステムで送信します。</span><span class="sxs-lookup"><span data-stu-id="46487-119">An ORR^O02 order-confirmation message is sent by the Laboratory System, indicating that the order can be executed.</span></span>  
  
    2.  <span data-ttu-id="46487-120">ORR ^ O02 メッセージ臨床注文入力システムによって受信されます。</span><span class="sxs-lookup"><span data-stu-id="46487-120">The ORR^O02 message is received by the Clinical Order Entry System.</span></span>  
  
4.  <span data-ttu-id="46487-121">テストの完了時に、ラボは、医師と他の部門に結果を送信します。</span><span class="sxs-lookup"><span data-stu-id="46487-121">On completion of the tests, the laboratory sends the results to the doctor and other departments.</span></span>  
  
    1.  <span data-ttu-id="46487-122">ORU ^ テスト システムから R01 テスト結果のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="46487-122">An ORU^R01 test-results message is sent from the Laboratory System.</span></span>  
  
    2.  <span data-ttu-id="46487-123">ORU ^ R01 メッセージ Clinical、受注システムと課金システムで受信されます。</span><span class="sxs-lookup"><span data-stu-id="46487-123">The ORU^R01 message is received by the Clinical Order Entry System and the Billing System.</span></span>  
  
    3.  <span data-ttu-id="46487-124">インターフェイスのエンジンは、ワイヤレス PDA でラボの結果を受信すると、doctor を電子メール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="46487-124">The Interface Engine sends out an e-mail message to the doctor, who receives the lab results on his wireless PDA.</span></span>  
  
## <a name="the-btahl7-solution"></a><span data-ttu-id="46487-125">BTAHL7 ソリューション</span><span class="sxs-lookup"><span data-stu-id="46487-125">The BTAHL7 Solution</span></span>  
 <span data-ttu-id="46487-126">上記で説明したサンプル ビジネス シナリオでは、統合が必要な医療システムの例を示します。</span><span class="sxs-lookup"><span data-stu-id="46487-126">The sample business scenario outlined above is an example of a health care system that needs integration.</span></span> <span data-ttu-id="46487-127">Microsoft BizTalk Accelerator for HL7 の MicrosoftBizTalk サーバー ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) このシナリオでは、次の機能を紹介するソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="46487-127">MicrosoftBizTalk Server with Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) provides a solution for this scenario that features the following functionality:</span></span>  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="46487-128">すべてのハブとスポークの配置に関連するシステムを統合します。</span><span class="sxs-lookup"><span data-stu-id="46487-128">integrates all of the systems involved in a hub-and-spoke arrangement.</span></span> <span data-ttu-id="46487-129">各システムと直接通信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="46487-129">Each system communicates directly with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="46487-130">これらは相互に直接通信するためにはありません。</span><span class="sxs-lookup"><span data-stu-id="46487-130">They do not have to communicate directly to each other.</span></span>  
  
2. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="46487-131">ネイティブ HL7 でエンコードされたメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="46487-131">handles HL7-encoded messages natively.</span></span> <span data-ttu-id="46487-132">独自のコーディングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="46487-132">No custom coding is required.</span></span>  
  
3. <span data-ttu-id="46487-133">ADT ^ O04 登録メッセージは、サブスクライブするすべてのシステムにブロードキャストされます。</span><span class="sxs-lookup"><span data-stu-id="46487-133">The ADT^O04 registration message is broadcast to all systems that subscribe to it.</span></span> <span data-ttu-id="46487-134">パブリッシャーとサブスクライバーのメッセージング モデル[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を設定すると、メッセージをサブスクライブ システムのリストを保持する柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="46487-134">The publisher-subscriber messaging model for [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] provides flexibility in setting up and maintaining the list of systems subscribing to the message.</span></span> <span data-ttu-id="46487-135">システムを追加したり、システムの残りの部分に影響を与えずに、サブスクリプションの一覧から削除することができます。</span><span class="sxs-lookup"><span data-stu-id="46487-135">You can add systems to or delete them from the subscription list without affecting the rest of the system.</span></span>  
  
4. <span data-ttu-id="46487-136">ビジネス ルールの ORM の検証に使用される ^ O01 注文メッセージは、システムの残りの部分に影響を与えずに動的に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="46487-136">The business rule used to validate the ORM^O01 order message can be changed dynamically without affecting the rest of the system.</span></span>  
  
5. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="46487-137">ORR を自動的に生成するように構成できる ^ O02 注文確認 (ACK) メッセージ。</span><span class="sxs-lookup"><span data-stu-id="46487-137">can be configured to automatically generate the ORR^O02 order-confirmation (ACK) message.</span></span>  
  
6. <span data-ttu-id="46487-138">必要に応じて、他のユーザーと、送信するためのメッセージのいずれかのバッチを処理しからの受信バッチ内でイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="46487-138">If necessary, you can batch any of the messages with others for sending, and process them on receipt from within the batch.</span></span>  
  
7. <span data-ttu-id="46487-139">に対して、エンジンですべてのメッセージを検証することができます、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X スキーマが HL7 組織によって発行されました。</span><span class="sxs-lookup"><span data-stu-id="46487-139">You can validate all messages in the engine and against the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2X schemas published by the HL7 organization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46487-140">参照</span><span class="sxs-lookup"><span data-stu-id="46487-140">See Also</span></span>  
 [<span data-ttu-id="46487-141">BizTalk Server がビジネス ニーズを解決するしくみ</span><span class="sxs-lookup"><span data-stu-id="46487-141">How BizTalk Server Solves the Business Need</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)
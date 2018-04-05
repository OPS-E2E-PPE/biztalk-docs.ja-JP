---
title: エンド ツー エンド Tutorial1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.endtoendtutorial
helpviewer_keywords:
- end-to-end tutorial, about the tutorial
- end-to-end tutorial
- tutorials, end-to-end tutorial
ms.assetid: 90625edc-70a0-42c9-a2fb-8eeb5465d766
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90dc31ac286f8ce1e38d9a511eb319828d8ae939
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="638d6-102">エンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="638d6-102">End-to-End Tutorial</span></span>
<span data-ttu-id="638d6-103">このチュートリアルには、使用する方法を説明する詳しい手順が含まれています。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]がサブスクライバーとパブリッシャーのシナリオでビジネス プロセスを容易になります。</span><span class="sxs-lookup"><span data-stu-id="638d6-103">This tutorial contains detailed steps that describe how you use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a subscriber and publisher scenario.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="638d6-104">このチュートリアルを使用するのには、BTAHL7 をインストールするときにテスト ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="638d6-104">To use this tutorial, you must install the test tools when installing BTAHL7.</span></span> <span data-ttu-id="638d6-105">BTAHL7 をインストールする標準的なインストールを実行した場合必要があります、カスタム インストールを実行し、このチュートリアルでは正常に動作する順序でテスト ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="638d6-105">If you performed a typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="638d6-106">**カスタム セットアップ**、BTAHL7 カスタム インストールの選択画面**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="638d6-106">At the **Custom Setup** screen of the BTAHL7 custom installation, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="638d6-107">詳細については、次を参照してください。 [BizTalk Accelerator 用 HL7 インストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)です。</span><span class="sxs-lookup"><span data-stu-id="638d6-107">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="declarative-scenario"></a><span data-ttu-id="638d6-108">宣言型のシナリオ</span><span class="sxs-lookup"><span data-stu-id="638d6-108">Declarative Scenario</span></span>  
 <span data-ttu-id="638d6-109">このチュートリアルでは、公開/定期受信または宣言のシナリオを使用します。</span><span class="sxs-lookup"><span data-stu-id="638d6-109">This tutorial uses the publish/subscribe or declarative scenario.</span></span> <span data-ttu-id="638d6-110">宣言型では、ビジネスのフローは次の図に示すようなです。</span><span class="sxs-lookup"><span data-stu-id="638d6-110">In the declarative scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="638d6-111">次の図に、番号付きリストでは、ワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="638d6-111">The numbered list following the figure describes the workflow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")  
<span data-ttu-id="638d6-112">宣言型のシナリオでは、ビジネスのフローを示す図</span><span class="sxs-lookup"><span data-stu-id="638d6-112">Figure showing the flow of business for the declarative scenario</span></span>  
  
1.  <span data-ttu-id="638d6-113">ワークフローは、特定のサブスクライバーにメッセージを送信するなど、受付放電と転送システムは、パブリッシャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="638d6-113">The workflow begins when the publisher, for example, an Admissions Discharge and Transfer system, sends a message to specific subscribers.</span></span> <span data-ttu-id="638d6-114">ワークフローでパブリッシャー"Tutorial_ADTSystem"であり、メッセージが呼び出された"**ADT ^ A103**"。</span><span class="sxs-lookup"><span data-stu-id="638d6-114">The publisher in the workflow is "Tutorial_ADTSystem", and the message is called "**ADT^A103**."</span></span>  
  
2.  <span data-ttu-id="638d6-115">メッセージは、さらに受信、処理、検証、再フォーマットし、およびサブスクライバーにメッセージをルーティングし BTAHL7 インターフェイス エンジンにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="638d6-115">The message is routed to the BTAHL7 Interface Engine, which in turn receives, processes, validates, reformats, and then routes the message to subscribers.</span></span>  
  
3.  <span data-ttu-id="638d6-116">このシナリオでは、サブスクライバーは、医療施設の情報システム (Tutorial_HISystem) 薬局システム (Tutorial_RXSystem)。</span><span class="sxs-lookup"><span data-stu-id="638d6-116">The subscribers in this scenario are a Hospital Information System (Tutorial_HISystem) and a Pharmacy System (Tutorial_RXSystem).</span></span> <span data-ttu-id="638d6-117">このシナリオでは、ファイルと MLLP の両方の種類のアダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="638d6-117">This scenario uses both File and MLLP adapter types.</span></span> <span data-ttu-id="638d6-118">パブリッシャーは、サブスクライバーに注意する必要はありませんし、BTAHL7 適切に受信確認を送信、パブリッシャーにメッセージを処理した後にします。</span><span class="sxs-lookup"><span data-stu-id="638d6-118">The publisher does not need to be aware of the subscribers and BTAHL7 appropriately sends an acknowledgment to the publisher after processing the message.</span></span>  
  
4.  <span data-ttu-id="638d6-119">パブリッシャーは、送信、ADT ^ A03 メッセージ (Tutorial_1WayReceivePort) 一方向の MLLP アダプターを経由します。</span><span class="sxs-lookup"><span data-stu-id="638d6-119">The publisher sends the ADT^A03 message through a one-way MLLP adapter (Tutorial_1WayReceivePort).</span></span>  
  
5.  <span data-ttu-id="638d6-120">このメッセージの送信先は、BTAHL7 インターフェイス エンジンでは、受信メッセージには送信元メッセージが含まれています (MSH3 Tutorial_ADTSystem を =) と送信先メッセージ (MSH5 = BTAHL7InterfaceEngine)。</span><span class="sxs-lookup"><span data-stu-id="638d6-120">The destination of this message is the BTAHL7 Interface Engine, so the incoming message contains a source message (MSH3 = Tutorial_ADTSystem) and a destination message (MSH5 = BTAHL7InterfaceEngine).</span></span>  
  
6.  <span data-ttu-id="638d6-121">BTAHL7 では、メッセージを適切に検証した後、受信確認 (ACK) を生成し、ファイル アダプター経由 Tutorial_ADTSystem に受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="638d6-121">BTAHL7 generates an acknowledgment (ACK) after appropriately validating the message, and then sends the acknowledgment to the Tutorial_ADTSystem through the File adapter.</span></span>  
  
7.  <span data-ttu-id="638d6-122">Tutorial_HISystem システムと Tutorial_RXSystem システムは、BTAHL7 インターフェイス エンジンによって受信された ADT メッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="638d6-122">The Tutorial_HISystem system and the Tutorial_RXSystem system subscribe to the ADT message received by the BTAHL7 Interface Engine.</span></span>  
  
8.  <span data-ttu-id="638d6-123">使用して、各フィールドの値を指定する場合に、変換、 **MSH マップ**BTAHL7 構成エクスプ ローラー タブ。</span><span class="sxs-lookup"><span data-stu-id="638d6-123">The transformation occurs when you specify values for the respective fields by using the **MSH Map** tab in BTAHL7 Configuration Explorer.</span></span>  
  
     <span data-ttu-id="638d6-124">たとえば、パーティ Tutorial_RXSystem が MSH3 = BTHL7 で指定された、 **MSH マップ**タブです。そのため、サブスクライバーによって受信されたメッセージは MSH3 フィールドの値として"BTAHL7"があります。</span><span class="sxs-lookup"><span data-stu-id="638d6-124">For example, the party Tutorial_RXSystem has MSH3=BTHL7 specified in the **MSH Map** tab. Therefore, the message received by the subscriber will have "BTAHL7" as the value for the MSH3 field.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="638d6-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="638d6-125">In this section</span></span>  
  
-   [<span data-ttu-id="638d6-126">インストールのテスト</span><span class="sxs-lookup"><span data-stu-id="638d6-126">Testing Your Installation</span></span>](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [<span data-ttu-id="638d6-127">このチュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="638d6-127">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [<span data-ttu-id="638d6-128">手順 1: を作成し、ヘッダーと受信確認スキーマを展開</span><span class="sxs-lookup"><span data-stu-id="638d6-128">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="638d6-129">手順 2: v2.3.1 の一般的なスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="638d6-129">Step 2: Create Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="638d6-130">手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="638d6-130">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [<span data-ttu-id="638d6-131">手順 4: 作成、ADT を受け入れるための受信ポート ^ MLLP アダプターを使用して ADT システムから A03 メッセージ</span><span class="sxs-lookup"><span data-stu-id="638d6-131">Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [<span data-ttu-id="638d6-132">手順 5: ファイル アダプタを使用して、ADT システムに受信確認を配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="638d6-132">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [<span data-ttu-id="638d6-133">手順 6: ADT を配信する送信ポートを作成する ^ A03 メッセージをファイル アダプターを使用して RX システム</span><span class="sxs-lookup"><span data-stu-id="638d6-133">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [<span data-ttu-id="638d6-134">手順 7: ADT を配信する送信ポートを作成する ^ MLLP アダプターを使用して自分に A03 メッセージ</span><span class="sxs-lookup"><span data-stu-id="638d6-134">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [<span data-ttu-id="638d6-135">手順 8: パーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="638d6-135">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [<span data-ttu-id="638d6-136">手順 9: BizTalk Server を再起動します。</span><span class="sxs-lookup"><span data-stu-id="638d6-136">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="638d6-137">手順 10: エンド ツー エンド シナリオを確認してください。</span><span class="sxs-lookup"><span data-stu-id="638d6-137">Step 10: Verify the End-to-End Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a><span data-ttu-id="638d6-138">参照</span><span class="sxs-lookup"><span data-stu-id="638d6-138">See also</span></span>
[<span data-ttu-id="638d6-139">使い始める BizTalk Accelerator 用 HL7</span><span class="sxs-lookup"><span data-stu-id="638d6-139">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)
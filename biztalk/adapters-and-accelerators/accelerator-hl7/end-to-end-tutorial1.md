---
title: エンド ツー エンド Tutorial1 |Microsoft Docs
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
ms.openlocfilehash: 264a6eee008b9b327185c931ad4e5ac60cdc995a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000739"
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="9acb7-102">エンド ツー エンドのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="9acb7-102">End-to-End Tutorial</span></span>
<span data-ttu-id="9acb7-103">このチュートリアルには、Microsoft の使用方法を説明する詳細な手順が含まれています。[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]サブスクライバーとパブリッシャーのシナリオでビジネス プロセスを容易にします。</span><span class="sxs-lookup"><span data-stu-id="9acb7-103">This tutorial contains detailed steps that describe how you use Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a subscriber and publisher scenario.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9acb7-104">このチュートリアルを使用するには、BTAHL7 をインストールするときに、テスト ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acb7-104">To use this tutorial, you must install the test tools when installing BTAHL7.</span></span> <span data-ttu-id="9acb7-105">コード型の BTAHL7 をインストールする一般的なインストールを実行した場合、カスタム インストールを実行テスト ツールを正常に動作するには、このチュートリアルの順序でインストールし、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acb7-105">If you performed a typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="9acb7-106">**カスタム セットアップ**、BTAHL7 カスタム インストールの選択画面**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="9acb7-106">At the **Custom Setup** screen of the BTAHL7 custom installation, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="9acb7-107">詳細については、次を参照してください。 [BizTalk Accelerator for HL7 のインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)します。</span><span class="sxs-lookup"><span data-stu-id="9acb7-107">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="declarative-scenario"></a><span data-ttu-id="9acb7-108">宣言型のシナリオ</span><span class="sxs-lookup"><span data-stu-id="9acb7-108">Declarative Scenario</span></span>  
 <span data-ttu-id="9acb7-109">このチュートリアルでは、パブリッシュ/サブスクライブまたは宣言型のシナリオを使用します。</span><span class="sxs-lookup"><span data-stu-id="9acb7-109">This tutorial uses the publish/subscribe or declarative scenario.</span></span> <span data-ttu-id="9acb7-110">宣言型のシナリオでは、ビジネスのフローは次の図に示されている似ています。</span><span class="sxs-lookup"><span data-stu-id="9acb7-110">In the declarative scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="9acb7-111">次の図は、番号付きリストでは、ワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9acb7-111">The numbered list following the figure describes the workflow.</span></span>  
  
 <span data-ttu-id="9acb7-112">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")</span><span class="sxs-lookup"><span data-stu-id="9acb7-112">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")</span></span>  
<span data-ttu-id="9acb7-113">宣言型のシナリオでは、ビジネスのフローを示す図</span><span class="sxs-lookup"><span data-stu-id="9acb7-113">Figure showing the flow of business for the declarative scenario</span></span>  
  
1.  <span data-ttu-id="9acb7-114">ワークフローは、特定のサブスクライバーにメッセージを送信するなど、入学放電と転送のシステムは、パブリッシャーを開始します。</span><span class="sxs-lookup"><span data-stu-id="9acb7-114">The workflow begins when the publisher, for example, an Admissions Discharge and Transfer system, sends a message to specific subscribers.</span></span> <span data-ttu-id="9acb7-115">ワークフローの発行元は、"Tutorial_ADTSystem"と、メッセージが呼び出された"**ADT ^ A103**"。</span><span class="sxs-lookup"><span data-stu-id="9acb7-115">The publisher in the workflow is "Tutorial_ADTSystem", and the message is called "**ADT^A103**."</span></span>  
  
2.  <span data-ttu-id="9acb7-116">メッセージは、さらに受信、処理、検証、書式を再設定、およびサブスクライバーにメッセージをルーティングし BTAHL7 インターフェイス エンジンにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9acb7-116">The message is routed to the BTAHL7 Interface Engine, which in turn receives, processes, validates, reformats, and then routes the message to subscribers.</span></span>  
  
3.  <span data-ttu-id="9acb7-117">このシナリオでは、サブスクライバーとは、病院情報システム (Tutorial_HISystem) および薬剤システム (Tutorial_RXSystem) です。</span><span class="sxs-lookup"><span data-stu-id="9acb7-117">The subscribers in this scenario are a Hospital Information System (Tutorial_HISystem) and a Pharmacy System (Tutorial_RXSystem).</span></span> <span data-ttu-id="9acb7-118">このシナリオでは、ファイルと MLLP アダプターの種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="9acb7-118">This scenario uses both File and MLLP adapter types.</span></span> <span data-ttu-id="9acb7-119">パブリッシャーは、サブスクライバーを意識する必要はありませんし、BTAHL7 適切に受信確認を送信、パブリッシャーに、メッセージの処理後にします。</span><span class="sxs-lookup"><span data-stu-id="9acb7-119">The publisher does not need to be aware of the subscribers and BTAHL7 appropriately sends an acknowledgment to the publisher after processing the message.</span></span>  
  
4.  <span data-ttu-id="9acb7-120">パブリッシャーは、送信、ADT ^ A03 メッセージ (Tutorial_1WayReceivePort) 一方向の MLLP アダプターを経由します。</span><span class="sxs-lookup"><span data-stu-id="9acb7-120">The publisher sends the ADT^A03 message through a one-way MLLP adapter (Tutorial_1WayReceivePort).</span></span>  
  
5.  <span data-ttu-id="9acb7-121">このメッセージの送信先には、BTAHL7 インターフェイス エンジンがあるため、受信メッセージには送信元メッセージが含まれています (MSH3 Tutorial_ADTSystem =) と送信先のメッセージ (MSH5 BTAHL7InterfaceEngine =)。</span><span class="sxs-lookup"><span data-stu-id="9acb7-121">The destination of this message is the BTAHL7 Interface Engine, so the incoming message contains a source message (MSH3 = Tutorial_ADTSystem) and a destination message (MSH5 = BTAHL7InterfaceEngine).</span></span>  
  
6.  <span data-ttu-id="9acb7-122">BTAHL7 では、メッセージを適切に検証した後、受信確認 (ACK) を生成し、ファイル アダプター経由 Tutorial_ADTSystem に受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="9acb7-122">BTAHL7 generates an acknowledgment (ACK) after appropriately validating the message, and then sends the acknowledgment to the Tutorial_ADTSystem through the File adapter.</span></span>  
  
7.  <span data-ttu-id="9acb7-123">Tutorial_HISystem システムと Tutorial_RXSystem システムは、BTAHL7 インターフェイス エンジンによって受信された ADT メッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="9acb7-123">The Tutorial_HISystem system and the Tutorial_RXSystem system subscribe to the ADT message received by the BTAHL7 Interface Engine.</span></span>  
  
8.  <span data-ttu-id="9acb7-124">変換は、使用して、それぞれのフィールドの値を指定するときに発生します。、 **MSH マップ**BTAHL7 構成エクスプ ローラー タブ。</span><span class="sxs-lookup"><span data-stu-id="9acb7-124">The transformation occurs when you specify values for the respective fields by using the **MSH Map** tab in BTAHL7 Configuration Explorer.</span></span>  
  
     <span data-ttu-id="9acb7-125">パーティ Tutorial_RXSystem の MSH3 がなどで指定された BTHL7 =、 **MSH マップ**タブ。したがって、サブスクライバーで受信したメッセージでは、MSH3 フィールドの値として"BTAHL7"があります。</span><span class="sxs-lookup"><span data-stu-id="9acb7-125">For example, the party Tutorial_RXSystem has MSH3=BTHL7 specified in the **MSH Map** tab. Therefore, the message received by the subscriber will have "BTAHL7" as the value for the MSH3 field.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9acb7-126">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9acb7-126">In this section</span></span>  
  
-   [<span data-ttu-id="9acb7-127">インストールのテスト</span><span class="sxs-lookup"><span data-stu-id="9acb7-127">Testing Your Installation</span></span>](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [<span data-ttu-id="9acb7-128">チュートリアルを使用する準備</span><span class="sxs-lookup"><span data-stu-id="9acb7-128">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [<span data-ttu-id="9acb7-129">手順 1: ヘッダーと確認スキーマの作成と展開</span><span class="sxs-lookup"><span data-stu-id="9acb7-129">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="9acb7-130">手順 2: v2.3.1 の一般的なスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="9acb7-130">Step 2: Create Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="9acb7-131">手順 3: トリガー イベント (メッセージ) プロジェクトの作成と展開</span><span class="sxs-lookup"><span data-stu-id="9acb7-131">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [<span data-ttu-id="9acb7-132">手順 4: MLLP Adapter を使用して ADT System から ADT^A03 メッセージを受け入れるための受信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="9acb7-132">Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [<span data-ttu-id="9acb7-133">手順 5: ファイル アダプターを使用して ADT System に受診確認を配信する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="9acb7-133">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [<span data-ttu-id="9acb7-134">手順 6: ファイル アダプターを使用して RX System に ADT^A03 メッセージを配信する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="9acb7-134">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [<span data-ttu-id="9acb7-135">手順 7: MLLP アダプターを使用して HIS に ADT^A03 メッセージを配信する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="9acb7-135">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [<span data-ttu-id="9acb7-136">手順 8: パーティ情報の構成</span><span class="sxs-lookup"><span data-stu-id="9acb7-136">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [<span data-ttu-id="9acb7-137">手順 9: BizTalk Server の再起動</span><span class="sxs-lookup"><span data-stu-id="9acb7-137">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="9acb7-138">手順 10: エンド ツー エンド シナリオの確認</span><span class="sxs-lookup"><span data-stu-id="9acb7-138">Step 10: Verify the End-to-End Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a><span data-ttu-id="9acb7-139">参照</span><span class="sxs-lookup"><span data-stu-id="9acb7-139">See also</span></span>
[<span data-ttu-id="9acb7-140">BizTalk Accelerator for HL7 の概要</span><span class="sxs-lookup"><span data-stu-id="9acb7-140">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)
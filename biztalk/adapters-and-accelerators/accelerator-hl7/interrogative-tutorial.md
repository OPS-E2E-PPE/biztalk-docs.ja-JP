---
title: "Interrogative チュートリアル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b35a5bc8ba7574df7499fef5d63a100993c4201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interrogative-tutorial"></a><span data-ttu-id="0f058-102">Interrogative チュートリアル</span><span class="sxs-lookup"><span data-stu-id="0f058-102">Interrogative Tutorial</span></span>
<span data-ttu-id="0f058-103">このチュートリアルには、使用する方法を説明する詳しい手順が含まれています。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]クエリ/応答シナリオでビジネス プロセスを容易にします。</span><span class="sxs-lookup"><span data-stu-id="0f058-103">This tutorial contains detailed steps that describe how you use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a Query/Response scenario.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f058-104">このチュートリアルを使用するのには、MLLP テスト ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f058-104">To use this tutorial, you must install the MLLP test tools.</span></span> <span data-ttu-id="0f058-105">BTAHL7 の一般的なインストールでは、これらのツールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="0f058-105">These tools are not installed by a Typical installation of BTAHL7.</span></span> <span data-ttu-id="0f058-106">カスタム インストールを実行しを選択する必要があります**MLLP テスト ツール**アダプター フォルダーからおよび**テスト インスタンス**Artifacts フォルダからです。</span><span class="sxs-lookup"><span data-stu-id="0f058-106">You must run a Custom installation and select **MLLP Test Tool** from the Adapter folder and **Test Instances** from the Artifacts folder.</span></span> <span data-ttu-id="0f058-107">テスト ツールがインストールされている場合、システムがフォルダーに含まれます\<*ドライブ*: > \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\MLLP ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="0f058-107">If the test tools are installed, your system will contain the folder \<*drive*:>\Program Files\Microsoft BizTalk \<version> Accelerator for HL7\SDK\MLLP Utilities.</span></span> <span data-ttu-id="0f058-108">参照してください[用 HL7 BizTalk アクセラレータをインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)です。</span><span class="sxs-lookup"><span data-stu-id="0f058-108">See [install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="interrogative-scenario"></a><span data-ttu-id="0f058-109">Interrogative シナリオ</span><span class="sxs-lookup"><span data-stu-id="0f058-109">Interrogative Scenario</span></span>  
 <span data-ttu-id="0f058-110">このチュートリアルでは、クエリ/応答または Interrogative シナリオを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f058-110">This tutorial uses the Query/Response or Interrogative scenario.</span></span> <span data-ttu-id="0f058-111">このシナリオでは、ビジネスのフローは、次の図に示されるに似ています。</span><span class="sxs-lookup"><span data-stu-id="0f058-111">In this scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="0f058-112">次の図に、番号付きリストでは、ワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0f058-112">The numbered list following the figure describes the workflow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")  
  
1.  <span data-ttu-id="0f058-113">ワークフローの開始、受付放電転送 (ADT) システムが病院情報システムにクエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="0f058-113">The workflow begins when an Admissions Discharge and Transfer (ADT) system sends a query to the Hospital Information System.</span></span> <span data-ttu-id="0f058-114">HL7 メッセージを使用して、"**クエリ ^ Q01**"スキーマです。</span><span class="sxs-lookup"><span data-stu-id="0f058-114">The HL7 message uses the "**QRY^Q01**" schema.</span></span> <span data-ttu-id="0f058-115">MllpSend ユーティリティが、ADT をシミュレートする、チュートリアルでは、ADT により、病院情報システムをクエリ メッセージを送信するシステムの受信ポート、BTAHL7 統合エンジンでします。</span><span class="sxs-lookup"><span data-stu-id="0f058-115">In the tutorial, the MllpSend utility simulates the ADT system sending the query message to the Hospital Information System through the ADT receive port in the BTAHL7 Integration Engine.</span></span>  
  
2.  <span data-ttu-id="0f058-116">BTAHL7 統合エンジンは、ADT システムからクエリ メッセージを受信し、それを検証します。</span><span class="sxs-lookup"><span data-stu-id="0f058-116">The BTAHL7 Integration Engine receives the query message from the ADT system and validates it.</span></span> <span data-ttu-id="0f058-117">その後、BTAHL7 パイプラインは、ADT に戻る受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="0f058-117">Then, the BTAHL7 pipeline sends an acknowledgment back to ADT.</span></span>  
  
3.  <span data-ttu-id="0f058-118">BTAHL7 インターフェイス エンジンは、メッセージを処理し、ルート、HIS を通じて HIS 変換先にクエリ メッセージのパーティ ポート。</span><span class="sxs-lookup"><span data-stu-id="0f058-118">The BTAHL7 Interface Engine processes the message, and then routes the query message to the HIS destination party through the HIS send port.</span></span>  
  
4.  <span data-ttu-id="0f058-119">元のクエリから、受信確認を受信した後は、ADT システムは、応答を待ちます。</span><span class="sxs-lookup"><span data-stu-id="0f058-119">After receiving the acknowledgment from the original query, the ADT system waits for a response.</span></span> <span data-ttu-id="0f058-120">受信ポートに、HIS によって応答メッセージが再度病院情報システム送信します。</span><span class="sxs-lookup"><span data-stu-id="0f058-120">The Hospital Information System sends a response message back through the HIS receive port.</span></span> <span data-ttu-id="0f058-121">このチュートリアルでは、MllpSend ユーティリティは、応答メッセージを送信する、病院情報システムをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="0f058-121">For this tutorial, the MllpSend utility simulates the Hospital Information System sending the response message.</span></span>  
  
5.  <span data-ttu-id="0f058-122">BTAHL7 インターフェイス エンジンは、応答メッセージを処理し、ADT 送信ポート経由の送信先パーティにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="0f058-122">The BTAHL7 Interface Engine processes the response message and then routes it to the destination party through the ADT send port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f058-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0f058-123">In this section</span></span>  
  
-   [<span data-ttu-id="0f058-124">このチュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="0f058-124">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [<span data-ttu-id="0f058-125">手順 1: を作成し、共通のヘッダーと受信確認スキーマを展開</span><span class="sxs-lookup"><span data-stu-id="0f058-125">Step 1: Create and Deploy Common Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="0f058-126">手順 2: V2.4 の一般的なスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f058-126">Step 2: Create Common Schemas for V2.4</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [<span data-ttu-id="0f058-127">手順 3: を作成し、トリガー イベント (メッセージ) プロジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="0f058-127">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [<span data-ttu-id="0f058-128">手順 4: 作成、ADT クエリ メッセージを受け入れるための受信ポート</span><span class="sxs-lookup"><span data-stu-id="0f058-128">Step 4: Create the Receive Port for Accepting ADT Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [<span data-ttu-id="0f058-129">手順 5: 作成、彼のメッセージを受け入れるための受信ポート</span><span class="sxs-lookup"><span data-stu-id="0f058-129">Step 5: Create the Receive Port for Accepting HIS Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [<span data-ttu-id="0f058-130">手順 6: クエリ メッセージを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f058-130">Step 6: Create a Send Port to Deliver Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [<span data-ttu-id="0f058-131">手順 7: 応答メッセージを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f058-131">Step 7: Create a Send Port to Deliver Response Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [<span data-ttu-id="0f058-132">手順 8: パーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="0f058-132">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [<span data-ttu-id="0f058-133">手順 9: BizTalk Server を再起動します。</span><span class="sxs-lookup"><span data-stu-id="0f058-133">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [<span data-ttu-id="0f058-134">手順 10: Interrogative シナリオを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f058-134">Step 10: Verify the Interrogative Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a><span data-ttu-id="0f058-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="0f058-135">Next step</span></span>  
 [<span data-ttu-id="0f058-136">このチュートリアルを使用する準備をしています</span><span class="sxs-lookup"><span data-stu-id="0f058-136">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a><span data-ttu-id="0f058-137">参照</span><span class="sxs-lookup"><span data-stu-id="0f058-137">See Also</span></span>  
[<span data-ttu-id="0f058-138">使い始める BizTalk Accelerator 用 HL7</span><span class="sxs-lookup"><span data-stu-id="0f058-138">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)
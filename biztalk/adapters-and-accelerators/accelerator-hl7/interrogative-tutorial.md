---
title: Interrogative チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92c832de8b6572e5ac70b79db1cbcc75d3812ea6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003203"
---
# <a name="interrogative-tutorial"></a><span data-ttu-id="ac3f1-102">Interrogative チュートリアル</span><span class="sxs-lookup"><span data-stu-id="ac3f1-102">Interrogative Tutorial</span></span>
<span data-ttu-id="ac3f1-103">このチュートリアルには、Microsoft の使用方法を説明する詳細な手順が含まれています。[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]クエリ/応答シナリオでビジネス プロセスを容易にします。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-103">This tutorial contains detailed steps that describe how you use Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a Query/Response scenario.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac3f1-104">このチュートリアルを使用するには、MLLP テスト ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-104">To use this tutorial, you must install the MLLP test tools.</span></span> <span data-ttu-id="ac3f1-105">これらのツールは、BTAHL7 の一般的なインストールではインストールされません。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-105">These tools are not installed by a Typical installation of BTAHL7.</span></span> <span data-ttu-id="ac3f1-106">カスタム インストールを実行し、選択する必要があります**MLLP テスト ツール**アダプター フォルダーから、**テスト インスタンス**Artifacts フォルダから。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-106">You must run a Custom installation and select **MLLP Test Tool** from the Adapter folder and **Test Instances** from the Artifacts folder.</span></span> <span data-ttu-id="ac3f1-107">テスト ツールがインストールされている場合、フォルダーが、システムが含まれます\<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-107">If the test tools are installed, your system will contain the folder \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span> <span data-ttu-id="ac3f1-108">参照してください[for HL7 の BizTalk アクセラレータのインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-108">See [install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="interrogative-scenario"></a><span data-ttu-id="ac3f1-109">Interrogative シナリオ</span><span class="sxs-lookup"><span data-stu-id="ac3f1-109">Interrogative Scenario</span></span>  
 <span data-ttu-id="ac3f1-110">このチュートリアルでは、クエリ/応答または Interrogative シナリオを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-110">This tutorial uses the Query/Response or Interrogative scenario.</span></span> <span data-ttu-id="ac3f1-111">このシナリオでは、ビジネスのフローは次の図に示されている似ています。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-111">In this scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="ac3f1-112">次の図は、番号付きリストでは、ワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-112">The numbered list following the figure describes the workflow.</span></span>  
  
 <span data-ttu-id="ac3f1-113">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")</span><span class="sxs-lookup"><span data-stu-id="ac3f1-113">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")</span></span>  
  
1.  <span data-ttu-id="ac3f1-114">ワークフローの開始、入学退院および転送 (ADT) システムでは、クエリを送信、病院の情報システムへ。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-114">The workflow begins when an Admissions Discharge and Transfer (ADT) system sends a query to the Hospital Information System.</span></span> <span data-ttu-id="ac3f1-115">HL7 メッセージで使用する、"**QRY ^ Q01**"スキーマ。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-115">The HL7 message uses the "**QRY^Q01**" schema.</span></span> <span data-ttu-id="ac3f1-116">MllpSend ユーティリティが ADT をシミュレートするチュートリアルでは、BTAHL7 の統合エンジンで受信ポートを ADT を介して病院情報システムにクエリ メッセージを送信するシステムです。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-116">In the tutorial, the MllpSend utility simulates the ADT system sending the query message to the Hospital Information System through the ADT receive port in the BTAHL7 Integration Engine.</span></span>  
  
2.  <span data-ttu-id="ac3f1-117">BTAHL7 の統合エンジンは ADT system からのクエリ メッセージを受信して検証します。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-117">The BTAHL7 Integration Engine receives the query message from the ADT system and validates it.</span></span> <span data-ttu-id="ac3f1-118">次に、BTAHL7 のパイプラインは、ADT に戻る受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-118">Then, the BTAHL7 pipeline sends an acknowledgment back to ADT.</span></span>  
  
3.  <span data-ttu-id="ac3f1-119">BTAHL7 インターフェイスのエンジンは、メッセージを処理をルート、HIS をパーティの HIS の変換先にクエリ メッセージを送信ポート。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-119">The BTAHL7 Interface Engine processes the message, and then routes the query message to the HIS destination party through the HIS send port.</span></span>  
  
4.  <span data-ttu-id="ac3f1-120">ADT system は、元のクエリから、受信確認を受信した後の応答を待機します。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-120">After receiving the acknowledgment from the original query, the ADT system waits for a response.</span></span> <span data-ttu-id="ac3f1-121">応答メッセージは、HIS によって再度病院情報システムの送信ポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-121">The Hospital Information System sends a response message back through the HIS receive port.</span></span> <span data-ttu-id="ac3f1-122">このチュートリアルでは、MllpSend ユーティリティは、病院情報システムは応答メッセージの送信をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-122">For this tutorial, the MllpSend utility simulates the Hospital Information System sending the response message.</span></span>  
  
5.  <span data-ttu-id="ac3f1-123">BTAHL7 インターフェイスのエンジンは、応答メッセージを処理し、ADT の送信ポート経由の送信先パーティにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ac3f1-123">The BTAHL7 Interface Engine processes the response message and then routes it to the destination party through the ADT send port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac3f1-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ac3f1-124">In this section</span></span>  
  
-   [<span data-ttu-id="ac3f1-125">チュートリアルを使用する準備</span><span class="sxs-lookup"><span data-stu-id="ac3f1-125">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [<span data-ttu-id="ac3f1-126">手順 1: 一般的なヘッダーと確認スキーマの作成と展開</span><span class="sxs-lookup"><span data-stu-id="ac3f1-126">Step 1: Create and Deploy Common Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="ac3f1-127">手順 2: V2.4 の一般的なスキーマの作成</span><span class="sxs-lookup"><span data-stu-id="ac3f1-127">Step 2: Create Common Schemas for V2.4</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [<span data-ttu-id="ac3f1-128">手順 3: トリガー イベント (メッセージ) プロジェクトの作成と展開</span><span class="sxs-lookup"><span data-stu-id="ac3f1-128">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [<span data-ttu-id="ac3f1-129">手順 4: ADT クエリ メッセージを受け入れるための受信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="ac3f1-129">Step 4: Create the Receive Port for Accepting ADT Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [<span data-ttu-id="ac3f1-130">手順 5: HIS メッセージを受け入れるための受信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="ac3f1-130">Step 5: Create the Receive Port for Accepting HIS Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [<span data-ttu-id="ac3f1-131">手順 6: クエリ メッセージを配信する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="ac3f1-131">Step 6: Create a Send Port to Deliver Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [<span data-ttu-id="ac3f1-132">手順 7: 応答メッセージを配信する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="ac3f1-132">Step 7: Create a Send Port to Deliver Response Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [<span data-ttu-id="ac3f1-133">手順 8: パーティ情報の構成</span><span class="sxs-lookup"><span data-stu-id="ac3f1-133">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [<span data-ttu-id="ac3f1-134">手順 9: BizTalk Server の再起動</span><span class="sxs-lookup"><span data-stu-id="ac3f1-134">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [<span data-ttu-id="ac3f1-135">手順 10: Interrogative シナリオの確認</span><span class="sxs-lookup"><span data-stu-id="ac3f1-135">Step 10: Verify the Interrogative Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a><span data-ttu-id="ac3f1-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="ac3f1-136">Next step</span></span>  
 [<span data-ttu-id="ac3f1-137">チュートリアルを使用する準備</span><span class="sxs-lookup"><span data-stu-id="ac3f1-137">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a><span data-ttu-id="ac3f1-138">参照</span><span class="sxs-lookup"><span data-stu-id="ac3f1-138">See Also</span></span>  
[<span data-ttu-id="ac3f1-139">BizTalk Accelerator for HL7 の概要</span><span class="sxs-lookup"><span data-stu-id="ac3f1-139">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)
---
title: '手順 11: オーケストレーション変数を作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
- message enrichment tutorial, orchestrations
ms.assetid: 3d1f792d-fe74-4373-86fa-3debda55e732
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a640b938628ebe3dcd6757e3f6fdfd7b1108880d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962248"
---
# <a name="step-11-create-orchestration-variables"></a><span data-ttu-id="e2bf7-102">手順 11: オーケストレーション変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-102">Step 11: Create Orchestration Variables</span></span>
<span data-ttu-id="e2bf7-103">このステップでは、オーケストレーションによって送受信されたメッセージ インスタンスのオーケストレーション変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-103">In this step, you create the orchestration variables for the message instances sent and received by the orchestration.</span></span>  
  
 <span data-ttu-id="e2bf7-104">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) シリアライザーでは、次の要素の名前。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-104">The BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) serializer expects the following part names.</span></span> <span data-ttu-id="e2bf7-105">他の部分名を持つ、マルチパート メッセージを作成する場合、シリアライザーは、メッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-105">If you create a multipart message with any other part names, the serializer rejects the message.</span></span> <span data-ttu-id="e2bf7-106">メッセージ部分名は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-106">The message part names are:</span></span>  
  
-   <span data-ttu-id="e2bf7-107">MSHSegment</span><span class="sxs-lookup"><span data-stu-id="e2bf7-107">MSHSegment</span></span>  
  
-   <span data-ttu-id="e2bf7-108">BodySegments</span><span class="sxs-lookup"><span data-stu-id="e2bf7-108">BodySegments</span></span>  
  
-   <span data-ttu-id="e2bf7-109">Z セグメント</span><span class="sxs-lookup"><span data-stu-id="e2bf7-109">Z segments</span></span>  
  
 <span data-ttu-id="e2bf7-110">Z セグメント パーツに関する重要な情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-110">The following is important information about Z segment parts:</span></span>  
  
-   <span data-ttu-id="e2bf7-111">すべてのメッセージは、かどうか、Z セグメントは存在するかに関係なく、前述のように、3 つの部分を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-111">All messages contain three parts as described above, regardless of whether a Z segment is present or not.</span></span>  
  
-   <span data-ttu-id="e2bf7-112">Z セグメントの一部を使用するには、末尾 (つまりも宣言されていないこと) スキーマで定義されていないメッセージのインスタンスからデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-112">You use a Z segment part to contain data from the message instance, which is trailing and not defined in the schema (which also means that it is undeclared).</span></span>  
  
-   <span data-ttu-id="e2bf7-113">宣言されていないデータがない場合は、Z のセグメントの一部が空白です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-113">If there is no undeclared data, the Z segment part is blank.</span></span> <span data-ttu-id="e2bf7-114">BizTalk マッパー; 内の中間 XML を表示するときに Z セグメント部分は表示されません。ただし、BizTalk 状態と動作状況の追跡 (HAT) ツールで、各メッセージに 3 つの部分を表示します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-114">You do not see the Z segment parts when viewing the intermediate XML within BizTalk Mapper; however, in the BizTalk Health and Activity Tracking (HAT) tool, you see three parts to each message.</span></span>  
  
### <a name="to-create-orchestration-variables"></a><span data-ttu-id="e2bf7-115">オーケストレーション変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="e2bf7-115">To create orchestration variables</span></span>  
  
1.  <span data-ttu-id="e2bf7-116">クリックして、**オーケストレーション ビュー**  タブの横に、**ソリューション エクスプ ローラー**ソリューション エクスプ ローラーの下にあるタブ。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-116">Click the **Orchestration View** tab next to the **Solution Explorer** tab beneath the Solutions Explorer.</span></span>  
  
2.  <span data-ttu-id="e2bf7-117">**オーケストレーション** ウィンドウを右クリックして**メッセージ**、順にクリック**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-117">In the **Orchestration View** pane, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="e2bf7-118">変更、**識別子**プロパティに、**プロパティ**ペイン**DoorbellInputMessage**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-118">Change the **Identifier** property in the **Properties** pane to **DoorbellInputMessage**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="e2bf7-119">**プロパティ**ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、クリックして**BTAHL7_Project.Doorbell**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-119">In the **Properties** pane, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7_Project.Doorbell**.</span></span>  
  
5.  <span data-ttu-id="e2bf7-120">手順 2 および 3 という名前の別のメッセージを作成する**DoorbellOutputMessage**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-120">Repeat steps 2 and 3 to create another message named **DoorbellOutputMessage**.</span></span>  
  
6.  <span data-ttu-id="e2bf7-121">**プロパティ**ウィンドウのドロップダウン リストで、**メッセージの種類**、展開**スキーマ**、クリックして**BTAHL7Schemas.ADT_A04_22_GLO_DEF**.</span><span class="sxs-lookup"><span data-stu-id="e2bf7-121">In the **Properties** pane, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7Schemas.ADT_A04_22_GLO_DEF**.</span></span>  
  
7.  <span data-ttu-id="e2bf7-122">**オーケストレーション** ウィンドウで、展開、**型**ノード。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-122">In the **Orchestration View** pane, expand the **Types** node.</span></span> <span data-ttu-id="e2bf7-123">右クリック**マルチパート メッセージの種類**、クリックして**新しいマルチパート メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-123">Right-click **Multi-part Message Types**, and then click **New Multi-part Message Type**.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="e2bf7-124">という名前の新しいメッセージ型を作成**MultipartType_1**という名前の新しいメッセージと共に**MessagePart_1**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-124"> creates a new message type named **MultipartType_1** along with a new message named **MessagePart_1**.</span></span>  
  
8.  <span data-ttu-id="e2bf7-125">をクリックして**MultipartType_1**、し、、**プロパティ**ウィンドウで、をクリックして**識別子**新しい名前を入力して**DoorbellFinalMessageType**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-125">Click **MultipartType_1**, and in the **Properties** window, click **Identifier** and type the new name **DoorbellFinalMessageType**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2bf7-126">手順 9 ~ 15 では、マルチパート メッセージの部分を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-126">In steps 9 through 15, you will create the parts of the multipart message.</span></span> <span data-ttu-id="e2bf7-127">マルチパート メッセージの部分を作成する順序が重要です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-127">The order in which you create the parts of a multipart message is important.</span></span> <span data-ttu-id="e2bf7-128">常に、ヘッダー、本文し Z セグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-128">Always create the header, then the body, then the Z segment.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2bf7-129">1 回作成し、メッセージ部分をという名前を変更しないこと。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-129">Once you have created and named the message parts, do not rename them.</span></span> <span data-ttu-id="e2bf7-130">必要に応じて、古いボディ部を削除し、新しい名前で新しいボディ部を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-130">If necessary, delete the old body part, and create a new body part with a new name.</span></span>  
  
9. <span data-ttu-id="e2bf7-131">**型**ウィンドウで、**マルチパート メッセージの種類**、展開**DoorbellFinalMessageType**、順にクリック**MessagePart_1**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-131">In the **Types** window, under **Multi-part Message Types**, expand **DoorbellFinalMessageType**, and then click **MessagePart_1**.</span></span> <span data-ttu-id="e2bf7-132">**プロパティ** ウィンドウで、入力**MSHSegment**の**識別子**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-132">In the **Properties** pane, enter **MSHSegment** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="e2bf7-133">ドロップダウン リストで**型**、展開 **.NET クラス**、クリックして\<**参照されたアセンブリから選択\>** です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-133">In the drop-down list for **Type**, expand **.NET Classes**, and then click \<**Select from referenced assemblies\>**.</span></span>  
  
10. <span data-ttu-id="e2bf7-134">**成果物の種類の選択**ダイアログ ボックスで、左側のウィンドウでをクリックして**System.Xml**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-134">In the **Select Artifact Type** dialog box, in the left pane, click **System.Xml**.</span></span> <span data-ttu-id="e2bf7-135">右側のウィンドウでをクリックして**XmlDocument**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-135">In the right pane, click **XmlDocument**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="e2bf7-136">オーケストレーションの種類 ウィンドウで、右クリック**DoorbellFinalMessageType**、クリックして**新しいメッセージ部分**MessagePart_1 を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-136">In the Orchestration View window, right-click **DoorbellFinalMessageType**, and then click **New Message Part** to create MessagePart_1.</span></span>  
  
12. <span data-ttu-id="e2bf7-137">**プロパティ**ウィンドウで、入力**BodySegments**の**識別子**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-137">In the **Properties** window, enter **BodySegments** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="e2bf7-138">ドロップダウン リストで**型**、展開**スキーマ**、し、 **BTAHL7Schemas.ADT_A04_22_GLO_DEF**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-138">In the drop-down list for **Type**, expand **Schemas**, and then select **BTAHL7Schemas.ADT_A04_22_GLO_DEF** from the drop-down list.</span></span>  
  
13. <span data-ttu-id="e2bf7-139">設定、**メッセージのボディ部**プロパティを**True**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-139">Set the **Message Body Part** property to **True**.</span></span>  
  
14. <span data-ttu-id="e2bf7-140">**オーケストレーション**ウィンドウを右クリックして**DoorbellFinalMessageType**、順にクリック**新しいメッセージ部分**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-140">In the **Orchestration View** window, right-click **DoorbellFinalMessageType**, and then click **New Message Part**.</span></span>  
  
15. <span data-ttu-id="e2bf7-141">**プロパティ** ウィンドウで、入力**ZSegments**の**識別子**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-141">In the **Properties** pane, enter **ZSegments** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="e2bf7-142">をクリックして**型**、展開 **.NET クラス**、順にクリック**System.String**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-142">Click **Type**, expand **.NET Classes**, and then click **System.String** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2bf7-143">使用する**System.String** Z が Z セグメントには、スキーマに準拠する必要のない文字列データが含まれているために、メッセージ部分をセグメントのです。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-143">You use **System.String** for the Z segments message part, because a Z segment contains string data that does not need to conform to a schema.</span></span>  
  
16. <span data-ttu-id="e2bf7-144">**オーケストレーション**ウィンドウを右クリックして**メッセージ**、順にクリック**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-144">In the **Orchestration View** window, right-click **Messages**, and then click **New Message**.</span></span>  
  
17. <span data-ttu-id="e2bf7-145">**プロパティ**ウィンドウで、入力**DoorbellFinalMessage**の**識別子**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-145">In the **Properties** window, enter **DoorbellFinalMessage** for **Identifier**, and then press **Enter**.</span></span> <span data-ttu-id="e2bf7-146">ドロップダウン リストで**メッセージの種類**、展開**マルチパート メッセージの種類**、クリックして**BTAHL7_Project.DoorbellFinalMessageType**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-146">In the drop-down list for **Message Type**, expand **Multi-part Message Types**, and then click **BTAHL7_Project.DoorbellFinalMessageType**.</span></span>  
  
18. <span data-ttu-id="e2bf7-147">**オーケストレーション**ウィンドウを右クリックして**変数**、順にクリック**新しい変数**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-147">In the **Orchestration View** window, right-click **Variables**, and then click **New Variable**.</span></span>  
  
19. <span data-ttu-id="e2bf7-148">**プロパティ** ウィンドウで、入力**HeaderInfo**の**識別子**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-148">In the **Properties** pane, enter **HeaderInfo** for **Identifier**, then press **Enter**.</span></span> <span data-ttu-id="e2bf7-149">ドロップダウン リストで**型**をダブルクリックして\< **.NET クラス\>** です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-149">In the drop-down list for **Type**, double-click \<**.NET Class\>**.</span></span>  
  
20. <span data-ttu-id="e2bf7-150">**成果物の種類の選択**ウィンドウの左側のウィンドウでをクリックして**System.Xml**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-150">In the **Select Artifact Type** window, in the left pane, click **System.Xml**.</span></span> <span data-ttu-id="e2bf7-151">右側のウィンドウでをクリックして**XmlDocument**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-151">In the right pane, click **XmlDocument**, and then click **OK**.</span></span>  
  
21. <span data-ttu-id="e2bf7-152">**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-152">In the **File** menu, click **Save All**.</span></span>  
  
 <span data-ttu-id="e2bf7-153">進みます[手順 12: オーケストレーション図形を構成する](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2bf7-153">Proceed to [Step 12: Configure Orchestration Shapes](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2bf7-154">参照</span><span class="sxs-lookup"><span data-stu-id="e2bf7-154">See Also</span></span>  
 [<span data-ttu-id="e2bf7-155">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="e2bf7-155">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)
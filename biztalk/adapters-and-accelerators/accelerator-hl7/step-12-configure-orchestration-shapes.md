---
title: '手順 12: オーケストレーション図形の構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, orchestration shapes
- orchestrations, shapes
- message enrichment tutorial, orchestrations
ms.assetid: 9388254b-2841-4489-838e-de913ceff151
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f21c373aacc949b95588c66f1243936b15ea9e89
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006427"
---
# <a name="step-12-configure-orchestration-shapes"></a><span data-ttu-id="36275-102">手順 12: オーケストレーション図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="36275-102">Step 12: Configure Orchestration Shapes</span></span>
<span data-ttu-id="36275-103">このステップでは、不十分な構成のスマート タグを削除するためにオーケストレーション図形の構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="36275-103">In this step, you complete the configuration of the orchestration shapes in order to remove the insufficient configuration smart tags.</span></span> <span data-ttu-id="36275-104">指定する**DoorbellOutputMessage**最初の変換プロセスの出力として指定する**DoorbellMap.btm**そのプロセスで使用されるマップとして。</span><span class="sxs-lookup"><span data-stu-id="36275-104">You designate **DoorbellOutputMessage** as the output of the first transform process, designating **DoorbellMap.btm** as the map used in that process.</span></span> <span data-ttu-id="36275-105">指定する**DoorbellFinalMessage** 2 番目の出力と同じプロセスを変換およびその他のフィールドのデータを持つメッセージを拡充する式を追加します。</span><span class="sxs-lookup"><span data-stu-id="36275-105">You then designate **DoorbellFinalMessage** as the output of the second transform process, and add the expression that enriches the message with additional field data.</span></span>  
  
 <span data-ttu-id="36275-106">**前提条件:** [サポート技術情報記事 941261](http://support.microsoft.com/kb/941261)オーケストレーションの構成を設定する前に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36275-106">**Prerequisite:** [KB article 941261](http://support.microsoft.com/kb/941261) must be applied before setting up Orchestration Configuration.</span></span>  
  
### <a name="to-configure-orchestration-shapes"></a><span data-ttu-id="36275-107">オーケストレーション図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="36275-107">To configure orchestration shapes</span></span>  
  
1.  <span data-ttu-id="36275-108">Visual Studio のオーケストレーションのデザイン ビュー画面、をクリックして、 **ConstructMessage_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="36275-108">On the orchestration Design view surface of Visual Studio, click the **ConstructMessage_1** shape.</span></span>  
  
2.  <span data-ttu-id="36275-109">**プロパティ**ウィンドウで、をクリックして、**構築メッセージ**プロパティを選択**DoorbellOutputMessage**ドロップダウン リストを押してからから**入力**です。</span><span class="sxs-lookup"><span data-stu-id="36275-109">In the **Properties** window, click the **Messages Constructed** property, select **DoorbellOutputMessage** from the drop-down list, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="36275-110">オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellTransform**図形の内側、 **ConstructMessage_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="36275-110">On the orchestration Design view surface, click the **DoorbellTransform** shape inside of the **ConstructMessage_1** shape.</span></span> <span data-ttu-id="36275-111">**プロパティ**ウィンドウで、をクリックして**マップ名**、属性フィールドで省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36275-111">In the **Properties** window, click **Map Name**, and then click the ellipsis (…) button in the attribute field.</span></span>  
  
4.  <span data-ttu-id="36275-112">変換の構成] ダイアログ ボックスで、[**既存のマップ**です。</span><span class="sxs-lookup"><span data-stu-id="36275-112">In the Transform Configuration dialog box, select **Existing Map**.</span></span> <span data-ttu-id="36275-113">**完全修飾マップ名**ドロップダウン リストをクリックして**BTAHL7_Project.DoorbellMap**です。</span><span class="sxs-lookup"><span data-stu-id="36275-113">In the **Fully Qualified Map Name** drop-down list, click **BTAHL7_Project.DoorbellMap**.</span></span>  
  
5.  <span data-ttu-id="36275-114">をクリックして**ソース**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="36275-114">Click **Source** in the left pane.</span></span>  
  
6.  <span data-ttu-id="36275-115">空のボックスをクリックして**変数名** をクリック**DoorBellInputMessage**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="36275-115">Click the empty box under **Variable Name** and click **DoorBellInputMessage** from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="36275-116">をクリックして**先**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="36275-116">Click **Destination** in the left pane.</span></span>  
  
8.  <span data-ttu-id="36275-117">空のボックスをクリックして**変数名** をクリック**DoorbellOutputMessage**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="36275-117">Click the empty box under **Variable Name** and click **DoorbellOutputMessage** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="36275-118">をクリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="36275-118">Click **OK** to save changes.</span></span>  
  
10. <span data-ttu-id="36275-119">オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **ConstructMessage_2**図形です。</span><span class="sxs-lookup"><span data-stu-id="36275-119">On the orchestration Design view surface, click the **ConstructMessage_2** shape.</span></span>  
  
11. <span data-ttu-id="36275-120">**プロパティ**ウィンドウで、をクリックして**構築メッセージ** **DoorbellFinalMessage**ドロップダウン リスト、キーを押しますから**を入力してください**.</span><span class="sxs-lookup"><span data-stu-id="36275-120">In the **Properties** window, click **Messages Constructed**, select **DoorbellFinalMessage** from the drop-down list, and then press **Enter**.</span></span>  
  
12. <span data-ttu-id="36275-121">オーケストレーション デザイン ビュー サーフェイスで、をクリックして、 **DoorbellFinalTransform**図形の内側、 **ConstructMessage_2**図形です。</span><span class="sxs-lookup"><span data-stu-id="36275-121">On the orchestration Design view surface, click the **DoorbellFinalTransform** shape inside of the **ConstructMessage_2** shape.</span></span> <span data-ttu-id="36275-122">**プロパティ**ウィンドウで、をクリックして**式**BizTalk 式エディターを開くに省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36275-122">In the **Properties** window, click **Expression**, and then click the ellipsis (…) button to open BizTalk Expression Editor.</span></span>  
  
13. <span data-ttu-id="36275-123">BizTalk 式エディターでは、テキスト フィールドをクリックし、次のテキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36275-123">In BizTalk Expression Editor, click in the text field and paste the following text:</span></span>  
  
    ```  
    HeaderInfo = new System.Xml.XmlDocument();   
    HeaderInfo.LoadXml("<ns0:MSH_25_GLO_DEF xmlns:ns0=\"http://microsoft.com/HealthCare/HL7/2X\">  
        <MSH><MSH.2_EncodingCharacters>^~\\&</MSH.2_EncodingCharacters><MSH.3_SendingApplication>  
        <HD.0_NamespaceId>SrcApp</HD.0_NamespaceId><HD.1_UniversalId>SrcAppUid</HD.1_UniversalId>  
        </MSH.3_SendingApplication><MSH.4_SendingFacility><HD.0_NamespaceId>srcFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>srcFacUid</HD.1_UniversalId></MSH.4_SendingFacility><MSH.5_ReceivingApplication>  
        <HD.0_NamespaceId>dstApp</HD.0_NamespaceId><HD.1_UniversalId>dstAppUid</HD.1_UniversalId>  
        </MSH.5_ReceivingApplication><MSH.6_ReceivingFacility><HD.0_NamespaceId>dstFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>dstFacUid</HD.1_UniversalId></MSH.6_ReceivingFacility><MSH.7_DateTimeOfMessage>  
        <TS.1>200307092343</TS.1></MSH.7_DateTimeOfMessage><MSH.8_Security>sec</MSH.8_Security>  
        <MSH.9_MessageType><CM_MSG.0_MessageType>ADT</CM_MSG.0_MessageType>  
        <CM_MSG.1_TriggerEvent>A04</CM_MSG.1_TriggerEvent></MSH.9_MessageType>  
        <MSH.10_MessageControlId>msgid2134</MSH.10_MessageControlId><MSH.11_ProcessingId>  
        <PT.0_ProcessingId>P</PT.0_ProcessingId></MSH.11_ProcessingId><MSH.12_VersionId>  
       <VID_0_VersionId>2.2</VID_0_VersionId></MSH.12_VersionId></MSH></ns0:MSH_25_GLO_DEF>");  
  
    DoorbellFinalMessage.MSHSegment = HeaderInfo;  
    DoorbellFinalMessage.BodySegments = DoorbellOutputMessage;  
    DoorbellFinalMessage.ZSegments = "";  
  
    DoorbellFinalMessage(BTAHL7Schemas.MSH1) = 124;   
    DoorbellFinalMessage(BTAHL7Schemas.MessageEncoding) = 65001;  
    DoorbellFinalMessage(BTAHL7Schemas.MSH2) = "^~\\&";  
    DoorbellFinalMessage(BTAHL7Schemas.ParseError) = false;   
    DoorbellFinalMessage(BTAHL7Schemas.ZPartPresent) = false;  
    DoorbellFinalMessage(BTAHL7Schemas.SegmentDelimiter2Char) = true;  
  
    ```  
  
14. <span data-ttu-id="36275-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36275-124">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="36275-125">式では、"HeaderInfo.LoadXml"には、キャリッジ リターンと、式内のスペースを削除します。</span><span class="sxs-lookup"><span data-stu-id="36275-125">In the "HeaderInfo.LoadXml" expression, delete the carriage returns and spaces within the expression.</span></span> <span data-ttu-id="36275-126">"HeaderInfo.LoadXml"ステートメントは、1 つの行にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36275-126">The "HeaderInfo.LoadXml" statement should be on one line.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="36275-127">上記のテキストの最初のブロックは、ハード コーディングされた XML ヘッダーの例を示します。</span><span class="sxs-lookup"><span data-stu-id="36275-127">The first block of the preceding text is an example of a hard-coded XML header.</span></span> <span data-ttu-id="36275-128">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーには、ヘッダー セグメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="36275-128">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer requires a header segment.</span></span> <span data-ttu-id="36275-129">お客様の環境のニーズに合わせてこれらのヘッダー値をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="36275-129">You can customize these header values according to the needs of your environment.</span></span> <span data-ttu-id="36275-130">上記のテキストの 2 番目のブロックでは、マルチパート メッセージで必要な 3 つのメッセージ部分を定義します。</span><span class="sxs-lookup"><span data-stu-id="36275-130">The second block of the preceding text defines the three message parts required in a multipart message.</span></span> <span data-ttu-id="36275-131">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーには、マルチパート メッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="36275-131">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer requires a multipart message.</span></span> <span data-ttu-id="36275-132">上記のテキストの 3 番目のブロックには、昇格させたプロパティが含まれています。 を、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] HL7 フラット ファイル メッセージに XML メッセージをシリアル化するためにシリアライザーを調べます。</span><span class="sxs-lookup"><span data-stu-id="36275-132">The third block of the preceding text contains the promoted properties that the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer examines in order to serialize an XML message into an HL7 flat-file message.</span></span>  
  
 <span data-ttu-id="36275-133">進みます[手順 13: を作成し、ポートを構成する](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="36275-133">Proceed to [Step 13: Create and Configure Ports](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36275-134">参照</span><span class="sxs-lookup"><span data-stu-id="36275-134">See Also</span></span>  
 [<span data-ttu-id="36275-135">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="36275-135">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)
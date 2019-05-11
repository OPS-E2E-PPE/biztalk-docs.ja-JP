---
title: 手順 3:作成し、送信先パーティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8746f115-9f69-4593-9943-9ccda45cd900
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80dff125e13ffb12acaeb98664957ed4e681ffa3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288902"
---
# <a name="step-3-create-and-configure-a-destination-party"></a><span data-ttu-id="0d934-102">手順 3:作成し、送信先パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0d934-102">Step 3: Create and Configure a Destination Party</span></span>
<span data-ttu-id="0d934-103">この手順では、作成し、バッチの作成シナリオでは、送信先パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0d934-103">In this step, you create and configure a destination party for the Create-Batch scenario.</span></span> <span data-ttu-id="0d934-104">選択することも、メッセージを[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]バッチとバッチ スケジュール、そのパーティに対して定義されています。</span><span class="sxs-lookup"><span data-stu-id="0d934-104">You also select the messages that [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] batches and the batch schedules, as defined for that party.</span></span> <span data-ttu-id="0d934-105">フォルダーにファイルをコピーした後 1 時間に 1 つのバッチ送信時間をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="0d934-105">You schedule the batch send time as one hour after copying the files into the folder.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="0d934-106">その後 1 時間の頻度での受信メッセージをバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="0d934-106">batches any messages received thereafter with a frequency of one hour.</span></span>  
  
### <a name="to-create-and-configure-a-destination-party"></a><span data-ttu-id="0d934-107">作成して送信先パーティを構成するには</span><span class="sxs-lookup"><span data-stu-id="0d934-107">To create and configure a destination party</span></span>  
  
1. <span data-ttu-id="0d934-108">右クリックし、BizTalk Server 管理コンソールで**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**。</span><span class="sxs-lookup"><span data-stu-id="0d934-108">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="0d934-109">パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに「 **Tutorial_BatchDest**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0d934-109">In the Party Properties dialog box, in the **Name** box, type **Tutorial_BatchDest**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="0d934-110">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**をクリックして**BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="0d934-110">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
4. <span data-ttu-id="0d934-111">BTAHL7 構成エクスプ ローラーでの**パーティ**コンソール ツリーで、タブをクリックして**Tutorial_BatchDest**します。</span><span class="sxs-lookup"><span data-stu-id="0d934-111">In BTAHL7 Configuration Explorer, on the **Parties** tab in the console tree, click **Tutorial_BatchDest**.</span></span>  
  
5. <span data-ttu-id="0d934-112">をクリックして、**受信確認**詳細ペインでタブ。</span><span class="sxs-lookup"><span data-stu-id="0d934-112">Click the **Acknowledgment** tab in the Details pane.</span></span> <span data-ttu-id="0d934-113">いることを確認、**受信確認の種類**は**None**します。</span><span class="sxs-lookup"><span data-stu-id="0d934-113">Verify that the **Acknowledgment type** is **None**.</span></span>  
  
6. <span data-ttu-id="0d934-114">をクリックして、**バッチ定義**タブ。**使用可能なメッセージ**ペインで、 **BTAHL7Schemas.ADT_A03_231_GLO_DEF**します。</span><span class="sxs-lookup"><span data-stu-id="0d934-114">Click the **Batch Definition** tab. In the **Available Messages** pane, select **BTAHL7Schemas.ADT_A03_231_GLO_DEF**.</span></span> <span data-ttu-id="0d934-115">右矢印を移動 をクリックして (**>>**) に、このスキーマを追加する**選択したメッセージを**、順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="0d934-115">Click the Move to the right arrow (**>>**) to add this schema to **Selected Messages**, and then click **Save**.</span></span>  
  
7. <span data-ttu-id="0d934-116">をクリックして、**バッチ スケジュール**タブ。**後にバッチを繰り返す**セクションで、いることを確認**時間**が選択されているし、入力**1**で、**時間**ボックス。</span><span class="sxs-lookup"><span data-stu-id="0d934-116">Click the **Batch Schedule** tab. In the **Repeat Batch After** section, verify that **Hours** is selected, and then type **1** in the **Hours** box.</span></span> <span data-ttu-id="0d934-117">**時間前最初のバッチに**ボックスに「 **1**、順にクリックします**開始スケジュール**します。</span><span class="sxs-lookup"><span data-stu-id="0d934-117">In the **Hours before first batch** box, type **1**, and then click **Start Schedule**.</span></span>  
  
   <span data-ttu-id="0d934-118">続行する[手順 4。バッチの作成シナリオでは、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="0d934-118">Proceed to [Step 4: Configure the Source Party for the Create-Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md).</span></span>
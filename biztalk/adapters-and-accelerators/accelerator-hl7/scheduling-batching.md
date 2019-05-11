---
title: バッチ処理のスケジュール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1522a050fc6cc1b690cdd59adb26ddde5d7449f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289903"
---
# <a name="scheduling-batching"></a><span data-ttu-id="eca6c-102">バッチ処理のスケジュール</span><span class="sxs-lookup"><span data-stu-id="eca6c-102">Scheduling Batching</span></span>
<span data-ttu-id="eca6c-103">使用する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]構成エクスプ ローラーでアクティブ化、要求、または、送信バッチを終了します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="eca6c-104">2 つの手順から成る、送信バッチをアクティブ化: 時間ベースの構成またはメッセージが条件とし、送信バッチ処理オーケストレーションの開始をカウントします。</span><span class="sxs-lookup"><span data-stu-id="eca6c-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="eca6c-105">次に示します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**バッチ スケジュール**タブ。</span><span class="sxs-lookup"><span data-stu-id="eca6c-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Schedule** tab.</span></span>  
  
 <span data-ttu-id="eca6c-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")</span><span class="sxs-lookup"><span data-stu-id="eca6c-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")</span></span>  
  
 <span data-ttu-id="eca6c-107">次の手順を使用して開きます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーとスケジュールがバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-107">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and schedule batching.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="eca6c-108">BTAHL7 構成エクスプ ローラーを開く</span><span class="sxs-lookup"><span data-stu-id="eca6c-108">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="eca6c-109">クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-schedule-message-batching"></a><span data-ttu-id="eca6c-110">メッセージのバッチ処理をスケジュールするには</span><span class="sxs-lookup"><span data-stu-id="eca6c-110">To schedule message batching</span></span>  
  
1.  <span data-ttu-id="eca6c-111">BTAHL7 構成エクスプ ローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="eca6c-111">Open BTAHL7 Configuration Explorer.</span></span>  
  
2.  <span data-ttu-id="eca6c-112">BTAHL7 構成エクスプ ローラーでの**BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスの 、**パーティ** タブで、構成するパーティを選択し、**バッチ スケジュール**  タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eca6c-112">In BTAHL7 Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Schedule** tab, do the following:</span></span>  
  
    |<span data-ttu-id="eca6c-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="eca6c-113">Use this</span></span>|<span data-ttu-id="eca6c-114">目的</span><span class="sxs-lookup"><span data-stu-id="eca6c-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="eca6c-115">**時間前に、の最初のバッチします。**</span><span class="sxs-lookup"><span data-stu-id="eca6c-115">**Hours before first batch**</span></span>|<span data-ttu-id="eca6c-116">最初のバッチを開始する前に、時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-116">Type the number of hours before the first batch is to start.</span></span>|  
    |<span data-ttu-id="eca6c-117">**後のバッチを繰り返す**</span><span class="sxs-lookup"><span data-stu-id="eca6c-117">**Repeat Batch After**</span></span>|<span data-ttu-id="eca6c-118">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-118">Select one of the following:</span></span><br /><br /> <span data-ttu-id="eca6c-119">-   **時間**します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-119">-   **Hours**.</span></span> <span data-ttu-id="eca6c-120">バッチ処理を繰り返す時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-120">Type the number of hours to repeat the batch process.</span></span><br /><span data-ttu-id="eca6c-121">-   **メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-121">-   **Messages**.</span></span> <span data-ttu-id="eca6c-122">次のバッチ処理する前に処理するメッセージの数を入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-122">Type the number of messages you want to process before the next batch process begins.</span></span>|  
    |<span data-ttu-id="eca6c-123">**バッチのコントロール**</span><span class="sxs-lookup"><span data-stu-id="eca6c-123">**Batch Control**</span></span>|<span data-ttu-id="eca6c-124">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-124">Select one of the following:</span></span><br /><br /> <span data-ttu-id="eca6c-125">-   **スケジュールの開始**:バッチ スケジュールの開始を選択します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-125">-   **Start Schedule**: Select to start the batch schedule.</span></span><br /><span data-ttu-id="eca6c-126">-   **今すぐ送信**:選択すると、バッチ処理をすぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-126">-   **Send Now**: Select to start the batch process immediately.</span></span><br /><span data-ttu-id="eca6c-127">-   **スケジュールの終了**:現在のバッチ スケジュールの停止を選択します。</span><span class="sxs-lookup"><span data-stu-id="eca6c-127">-   **Stop Schedule**: Select to stop the current batch schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eca6c-128">参照</span><span class="sxs-lookup"><span data-stu-id="eca6c-128">See Also</span></span>  
 [<span data-ttu-id="eca6c-129">受信確認のバッチ処理の構成</span><span class="sxs-lookup"><span data-stu-id="eca6c-129">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)
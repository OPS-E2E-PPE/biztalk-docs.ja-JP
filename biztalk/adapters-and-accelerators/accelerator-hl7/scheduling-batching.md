---
title: "バッチ処理のスケジュール設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08337171897a4a78e605054e9126e8c8238d5fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scheduling-batching"></a><span data-ttu-id="25000-102">バッチ処理のスケジュール設定</span><span class="sxs-lookup"><span data-stu-id="25000-102">Scheduling Batching</span></span>
<span data-ttu-id="25000-103">使用する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]をアクティブ化、要求、または送信バッチが終了するエクスプ ローラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="25000-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="25000-104">送信バッチをアクティブ化する 2 つの手順で構成されています: 時間ベースの構成またはメッセージが条件とし、送信バッチ処理オーケストレーションの開始をカウントします。</span><span class="sxs-lookup"><span data-stu-id="25000-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="25000-105">次の図に示しています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**バッチ スケジュール**タブです。</span><span class="sxs-lookup"><span data-stu-id="25000-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Schedule** tab.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")  
  
 <span data-ttu-id="25000-106">開くには、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エクスプ ローラーの構成とスケジュールがバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="25000-106">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and schedule batching.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="25000-107">BTAHL7 構成エクスプ ローラーを開く</span><span class="sxs-lookup"><span data-stu-id="25000-107">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="25000-108">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="25000-108">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-schedule-message-batching"></a><span data-ttu-id="25000-109">メッセージのバッチ処理をスケジュールするには</span><span class="sxs-lookup"><span data-stu-id="25000-109">To schedule message batching</span></span>  
  
1.  <span data-ttu-id="25000-110">BTAHL7 構成エクスプ ローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="25000-110">Open BTAHL7 Configuration Explorer.</span></span>  
  
2.  <span data-ttu-id="25000-111">BTAHL7 構成エクスプ ローラーで、、 **BTAHL7 構成エクスプ ローラー**ダイアログ ボックスの**パーティ** タブで、構成するパーティを選択し、**バッチ スケジュール**  タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="25000-111">In BTAHL7 Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Schedule** tab, do the following:</span></span>  
  
    |<span data-ttu-id="25000-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="25000-112">Use this</span></span>|<span data-ttu-id="25000-113">目的</span><span class="sxs-lookup"><span data-stu-id="25000-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="25000-114">**時間前に、の最初のバッチします。**</span><span class="sxs-lookup"><span data-stu-id="25000-114">**Hours before first batch**</span></span>|<span data-ttu-id="25000-115">最初のバッチを開始する前に、時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="25000-115">Type the number of hours before the first batch is to start.</span></span>|  
    |<span data-ttu-id="25000-116">**後にバッチを繰り返す**</span><span class="sxs-lookup"><span data-stu-id="25000-116">**Repeat Batch After**</span></span>|<span data-ttu-id="25000-117">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="25000-117">Select one of the following:</span></span><br /><br /> <span data-ttu-id="25000-118">-   **時間**です。</span><span class="sxs-lookup"><span data-stu-id="25000-118">-   **Hours**.</span></span> <span data-ttu-id="25000-119">バッチ処理を繰り返す時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="25000-119">Type the number of hours to repeat the batch process.</span></span><br /><span data-ttu-id="25000-120">-   **メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="25000-120">-   **Messages**.</span></span> <span data-ttu-id="25000-121">次のバッチ処理する前に処理するメッセージの数を入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="25000-121">Type the number of messages you want to process before the next batch process begins.</span></span>|  
    |<span data-ttu-id="25000-122">**バッチの制御**</span><span class="sxs-lookup"><span data-stu-id="25000-122">**Batch Control**</span></span>|<span data-ttu-id="25000-123">次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="25000-123">Select one of the following:</span></span><br /><br /> <span data-ttu-id="25000-124">-   **スケジュールの開始**: バッチ スケジュールの開始を選択します。</span><span class="sxs-lookup"><span data-stu-id="25000-124">-   **Start Schedule**: Select to start the batch schedule.</span></span><br /><span data-ttu-id="25000-125">-   **今すぐ送信**: バッチを開始する選択をすぐに処理します。</span><span class="sxs-lookup"><span data-stu-id="25000-125">-   **Send Now**: Select to start the batch process immediately.</span></span><br /><span data-ttu-id="25000-126">-   **スケジュールを停止**: 現在のバッチ スケジュールを停止する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="25000-126">-   **Stop Schedule**: Select to stop the current batch schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25000-127">参照</span><span class="sxs-lookup"><span data-stu-id="25000-127">See Also</span></span>  
 [<span data-ttu-id="25000-128">受信確認をバッチ処理を構成します。</span><span class="sxs-lookup"><span data-stu-id="25000-128">Configuring Batching Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)
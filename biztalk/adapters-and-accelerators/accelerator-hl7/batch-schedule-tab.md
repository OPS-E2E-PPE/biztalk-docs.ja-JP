---
title: "バッチ スケジュール タブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.configurationexplorer.tab.batchschedule
helpviewer_keywords:
- batching, scheduling
- Batch Schedule tab [Configuration Explorer]
- scheduling batching
ms.assetid: 3792388b-6af2-41c2-8f41-bdfda7e17b2b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d870abad399dcca76c32a3a8d0e8c6637fc93284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batch-schedule-tab"></a><span data-ttu-id="e61c2-102">[バッチ スケジュール] タブ</span><span class="sxs-lookup"><span data-stu-id="e61c2-102">Batch Schedule Tab</span></span>
<span data-ttu-id="e61c2-103">使用する、**バッチ スケジュール** タブをアクティブ化、要求、または送信バッチを終了します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-103">You use the **Batch Schedule** tab to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="e61c2-104">送信バッチをアクティブ化する 2 つの手順で構成されています: 時間ベースの構成またはメッセージが条件とし、送信バッチ処理オーケストレーションの開始をカウントします。</span><span class="sxs-lookup"><span data-stu-id="e61c2-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="e61c2-105">構成することができます[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]時間ベースを使用して、送信バッチを作成またはメッセージのカウントの条件または両方の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="e61c2-105">You can configure [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to create an outbound batch using time-based or message count criteria or a combination of both.</span></span> <span data-ttu-id="e61c2-106">バッチ アクティベーション条件を設定することは、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e61c2-106">Setting batch activation criteria is optional.</span></span> <span data-ttu-id="e61c2-107">指定しない場合、バッチを手動でアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="e61c2-107">If not specified, you can activate a batch manually.</span></span> <span data-ttu-id="e61c2-108">時間ベースを使用してバッチをアクティブ化またはメッセージのカウントの条件にする場合は、バッチをアクティブ化する前にこれらの条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e61c2-108">If you want to activate a batch using time-based or message count criteria, you must specify these criteria before activating the batch.</span></span>  
  
 <span data-ttu-id="e61c2-109">**BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**バッチ スケジュール** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-109">In the **BTAHL7 Configuration Explorer** dialog box, on the **Batch Schedule** tab, do the following:</span></span>  
  
|<span data-ttu-id="e61c2-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e61c2-110">Use this</span></span>|<span data-ttu-id="e61c2-111">目的</span><span class="sxs-lookup"><span data-stu-id="e61c2-111">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="e61c2-112">**時間前に、の最初のバッチします。**</span><span class="sxs-lookup"><span data-stu-id="e61c2-112">**Hours before first batch**</span></span>|<span data-ttu-id="e61c2-113">最初のバッチを開始する前に時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-113">Type the number of hours before starting the first batch.</span></span><br /><br /> <span data-ttu-id="e61c2-114">バッチのコントロールとしてメッセージの数を選択すると、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e61c2-114">This option is not available when you select message count as the batch control.</span></span>|  
|<span data-ttu-id="e61c2-115">**後にバッチを繰り返す**</span><span class="sxs-lookup"><span data-stu-id="e61c2-115">**Repeat Batch After**</span></span>|<span data-ttu-id="e61c2-116">以下のオプションの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-116">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="e61c2-117">-                   **時間**です。</span><span class="sxs-lookup"><span data-stu-id="e61c2-117">-                   **Hours**.</span></span> <span data-ttu-id="e61c2-118">バッチ処理を繰り返す前に待機する時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-118">Type the number of hours to wait before repeating the batch process.</span></span><br /><br /> <span data-ttu-id="e61c2-119">-                   **メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="e61c2-119">-                   **Messages**.</span></span> <span data-ttu-id="e61c2-120">次のバッチを開始する前に処理するメッセージの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-120">Type the number of messages that you want to process before initiating the next batch.</span></span>|  
|<span data-ttu-id="e61c2-121">**バッチの制御**</span><span class="sxs-lookup"><span data-stu-id="e61c2-121">**Batch Control**</span></span>|<span data-ttu-id="e61c2-122">次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-122">Use the following options:</span></span><br /><br /> <span data-ttu-id="e61c2-123">-                   **スケジュールの開始**: バッチ スケジュールを開始するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-123">-                   **Start Schedule**: Select this option to start your batch schedule.</span></span><br /><br /> <span data-ttu-id="e61c2-124">-                   **今すぐ送信**: バッチ処理を直ちに開始するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-124">-                   **Send Now**: Select this option to start the batch process immediately.</span></span> <span data-ttu-id="e61c2-125">上書きされます。、**最初のバッチになるまで時間**と**後にバッチを繰り返して**設定します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-125">This overrides the **Hours before first batch** and **Repeat Batch After** settings.</span></span><br /><br /> <span data-ttu-id="e61c2-126">-                   **スケジュールを停止**: 現在のバッチ スケジュールを停止するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-126">-                   **Stop Schedule**: Select this option to stop the current batch schedule.</span></span> <span data-ttu-id="e61c2-127">これにより、現在のバッチを完了し、バッチ オーケストレーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="e61c2-127">This completes the current batch and then stops the batch orchestration.</span></span>|
---
title: バッチ スケジュール タブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchschedule
helpviewer_keywords:
- batching, scheduling
- Batch Schedule tab [Configuration Explorer]
- scheduling batching
ms.assetid: 3792388b-6af2-41c2-8f41-bdfda7e17b2b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bf479425a6a0e80b75791d9b43ee0880e6ada63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251808"
---
# <a name="batch-schedule-tab"></a><span data-ttu-id="b4793-102">[バッチ スケジュール] タブ</span><span class="sxs-lookup"><span data-stu-id="b4793-102">Batch Schedule Tab</span></span>
<span data-ttu-id="b4793-103">使用する、**バッチ スケジュール** タブをアクティブ化、要求、または、送信バッチを終了します。</span><span class="sxs-lookup"><span data-stu-id="b4793-103">You use the **Batch Schedule** tab to activate, request, or terminate an outbound batch.</span></span> <span data-ttu-id="b4793-104">2 つの手順から成る、送信バッチをアクティブ化: 時間ベースの構成またはメッセージが条件とし、送信バッチ処理オーケストレーションの開始をカウントします。</span><span class="sxs-lookup"><span data-stu-id="b4793-104">Activating an outbound batch consists of two steps: configuring time-based or message count criteria and then starting the outbound batching orchestration.</span></span>  
  
 <span data-ttu-id="b4793-105">構成できる[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を使用して、送信バッチを作成するには、時間ベースまたはメッセージの数の条件またはその両方の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="b4793-105">You can configure [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to create an outbound batch using time-based or message count criteria or a combination of both.</span></span> <span data-ttu-id="b4793-106">バッチ アクティベーション条件の設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b4793-106">Setting batch activation criteria is optional.</span></span> <span data-ttu-id="b4793-107">指定しない場合、バッチを手動でアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="b4793-107">If not specified, you can activate a batch manually.</span></span> <span data-ttu-id="b4793-108">時間ベースを使用してバッチをアクティブ化またはメッセージの数の条件にする場合は、バッチをアクティブ化する前にこれらの条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4793-108">If you want to activate a batch using time-based or message count criteria, you must specify these criteria before activating the batch.</span></span>  
  
 <span data-ttu-id="b4793-109">**BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**バッチ スケジュール** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b4793-109">In the **BTAHL7 Configuration Explorer** dialog box, on the **Batch Schedule** tab, do the following:</span></span>  
  
|<span data-ttu-id="b4793-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b4793-110">Use this</span></span>|<span data-ttu-id="b4793-111">目的</span><span class="sxs-lookup"><span data-stu-id="b4793-111">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="b4793-112">**時間前に、の最初のバッチします。**</span><span class="sxs-lookup"><span data-stu-id="b4793-112">**Hours before first batch**</span></span>|<span data-ttu-id="b4793-113">最初のバッチを開始する前に時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4793-113">Type the number of hours before starting the first batch.</span></span><br /><br /> <span data-ttu-id="b4793-114">バッチのコントロールとしてメッセージの数を選択すると、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b4793-114">This option is not available when you select message count as the batch control.</span></span>|  
|<span data-ttu-id="b4793-115">**後のバッチを繰り返す**</span><span class="sxs-lookup"><span data-stu-id="b4793-115">**Repeat Batch After**</span></span>|<span data-ttu-id="b4793-116">以下のオプションの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4793-116">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="b4793-117">-                   **時間**します。</span><span class="sxs-lookup"><span data-stu-id="b4793-117">-                   **Hours**.</span></span> <span data-ttu-id="b4793-118">バッチ処理の繰り返しの前に待機する時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4793-118">Type the number of hours to wait before repeating the batch process.</span></span><br /><br /> <span data-ttu-id="b4793-119">-                   **メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="b4793-119">-                   **Messages**.</span></span> <span data-ttu-id="b4793-120">次のバッチを開始する前に処理するメッセージの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4793-120">Type the number of messages that you want to process before initiating the next batch.</span></span>|  
|<span data-ttu-id="b4793-121">**バッチのコントロール**</span><span class="sxs-lookup"><span data-stu-id="b4793-121">**Batch Control**</span></span>|<span data-ttu-id="b4793-122">次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4793-122">Use the following options:</span></span><br /><br /> <span data-ttu-id="b4793-123">-                   **スケジュールの開始**:バッチ スケジュールを開始するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4793-123">-                   **Start Schedule**: Select this option to start your batch schedule.</span></span><br /><br /> <span data-ttu-id="b4793-124">-                   **今すぐ送信**:バッチ処理をすぐに開始するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4793-124">-                   **Send Now**: Select this option to start the batch process immediately.</span></span> <span data-ttu-id="b4793-125">これよりも優先されます、**最初のバッチの前に時間**と**後にバッチを繰り返す**設定。</span><span class="sxs-lookup"><span data-stu-id="b4793-125">This overrides the **Hours before first batch** and **Repeat Batch After** settings.</span></span><br /><br /> <span data-ttu-id="b4793-126">-                   **スケジュールの終了**:現在のバッチ スケジュールを停止するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4793-126">-                   **Stop Schedule**: Select this option to stop the current batch schedule.</span></span> <span data-ttu-id="b4793-127">これにより、現在のバッチが完了するとして、バッチ オーケストレーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="b4793-127">This completes the current batch and then stops the batch orchestration.</span></span>|
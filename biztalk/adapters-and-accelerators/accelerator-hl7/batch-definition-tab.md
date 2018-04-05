---
title: '[定義] タブをバッチ処理 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchdefinition
helpviewer_keywords:
- Batch Definition tab [Configuration Explorer]
- batching, configuring
- configuring, batching
ms.assetid: fe8685ef-5de5-4337-8691-8e4094056ace
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2270625a6e4512f2a99bea7a06812b601b48d44c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batch-definition-tab"></a><span data-ttu-id="3b422-102">[バッチの定義] タブ</span><span class="sxs-lookup"><span data-stu-id="3b422-102">Batch Definition Tab</span></span>
<span data-ttu-id="3b422-103">使用する、**バッチ定義**] タブの [受信バッチ処理、バッチを有効にする/、バッチをバッチ処理を送信バッチ処理の利用可能なスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b422-103">You use the **Batch Definition** tab to enable inbound batching, batch in/batch out batching, and select available schemas for outbound batching.</span></span>  
  
 <span data-ttu-id="3b422-104">**BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**バッチ定義** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="3b422-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Batch Definition** tab, do the following:</span></span>  
  
|<span data-ttu-id="3b422-105">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3b422-105">Use this</span></span>|<span data-ttu-id="3b422-106">目的</span><span class="sxs-lookup"><span data-stu-id="3b422-106">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="3b422-107">**断片化が必要**</span><span class="sxs-lookup"><span data-stu-id="3b422-107">**Fragmentation required**</span></span>|<span data-ttu-id="3b422-108">以下のオプションの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b422-108">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="3b422-109">-   **[はい]**です。</span><span class="sxs-lookup"><span data-stu-id="3b422-109">-   **Yes**.</span></span> <span data-ttu-id="3b422-110">断片化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3b422-110">To enable fragmentation.</span></span><br /><span data-ttu-id="3b422-111">-   **いいえ**です。</span><span class="sxs-lookup"><span data-stu-id="3b422-111">-   **No**.</span></span> <span data-ttu-id="3b422-112">断片化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3b422-112">To disable fragmentation.</span></span> <span data-ttu-id="3b422-113">**注:** 、新しいパーティの**断片化のために必要な**の既定値は**いいえ**です。</span><span class="sxs-lookup"><span data-stu-id="3b422-113">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>|  
|<span data-ttu-id="3b422-114">**必要な回復可能なインターチェンジのサポート**</span><span class="sxs-lookup"><span data-stu-id="3b422-114">**Recoverable interchange support required**</span></span>|<span data-ttu-id="3b422-115">以下のオプションの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b422-115">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="3b422-116">-   **True**です。</span><span class="sxs-lookup"><span data-stu-id="3b422-116">-   **True**.</span></span> <span data-ttu-id="3b422-117">回復可能なインターチェンジ サポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="3b422-117">To enable recoverable interchange support.</span></span><br /><span data-ttu-id="3b422-118">-   **FALSE**です。</span><span class="sxs-lookup"><span data-stu-id="3b422-118">-   **FALSE**.</span></span> <span data-ttu-id="3b422-119">回復可能なインターチェンジのサポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3b422-119">To disable recoverable interchange support.</span></span> <span data-ttu-id="3b422-120">**注:** 、新しいパーティの**断片化のために必要な**の既定値は**FALSE**場合にのみ有効との値**断片化のために必要な**は**いいえ**です。</span><span class="sxs-lookup"><span data-stu-id="3b422-120">**Note:**  For a new party, **Fragmentation Required** defaults to **FALSE** and is enabled only if the value of **Fragmentation Required** is **No**.</span></span>|  
|<span data-ttu-id="3b422-121">**メッセージを選択します。**</span><span class="sxs-lookup"><span data-stu-id="3b422-121">**Select Messages**</span></span>|<span data-ttu-id="3b422-122">使用可能なメッセージ ウィンドウから、バッチとして送信し、右矢印を移動するメッセージの種類を選択 (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="3b422-122">Select the message types you want to send as a batch from the Available Messages window and then click the Move to right arrow (**>>**).</span></span><br /><br /> <span data-ttu-id="3b422-123">受信確認メッセージをバッチ処理するには、ACK メッセージの種類を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b422-123">To batch incoming ACK messages, you must add the ACK message type.</span></span> <span data-ttu-id="3b422-124">これを行う ACK メッセージ スキーマを展開することによりします。</span><span class="sxs-lookup"><span data-stu-id="3b422-124">You do so by deploying the ACK message schema.</span></span>|  
|<span data-ttu-id="3b422-125">**メッセージの受信確認を選択します。**</span><span class="sxs-lookup"><span data-stu-id="3b422-125">**Select Message Acknowledgments**</span></span>|<span data-ttu-id="3b422-126">対象となるメッセージの種類を選択して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチとして利用可能なメッセージの Ack ウィンドウから、受信確認を送信し、右矢印を移動する (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="3b422-126">Select the message types for which you want [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to send the acknowledgments as a batch from the Available Message Acks window, and then click the Move to right arrow (**>>**).</span></span>|
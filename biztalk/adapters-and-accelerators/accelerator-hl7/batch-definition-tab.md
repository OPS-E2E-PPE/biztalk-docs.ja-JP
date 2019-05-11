---
title: バッチ処理の定義 タブ |Microsoft Docs
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
ms.openlocfilehash: 70d06bb7832d42264d90d0edd63faf5d747bf849
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247675"
---
# <a name="batch-definition-tab"></a><span data-ttu-id="2924a-102">[バッチの定義] タブ</span><span class="sxs-lookup"><span data-stu-id="2924a-102">Batch Definition Tab</span></span>
<span data-ttu-id="2924a-103">使用する、**バッチ定義**タブで受信バッチ処理、バッチを有効にする/バッチ アウト、バッチ処理して、送信バッチ処理の利用可能なスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="2924a-103">You use the **Batch Definition** tab to enable inbound batching, batch in/batch out batching, and select available schemas for outbound batching.</span></span>  

 <span data-ttu-id="2924a-104">**BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスで、**バッチ定義** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2924a-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Batch Definition** tab, do the following:</span></span>  


|                   <span data-ttu-id="2924a-105">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2924a-105">Use this</span></span>                   |                                                                                                                                                            <span data-ttu-id="2924a-106">目的</span><span class="sxs-lookup"><span data-stu-id="2924a-106">To do this</span></span>                                                                                                                                                            |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          <span data-ttu-id="2924a-107">**必要な断片化**</span><span class="sxs-lookup"><span data-stu-id="2924a-107">**Fragmentation required**</span></span>          |                                                           <span data-ttu-id="2924a-108">以下のオプションの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="2924a-108">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="2924a-109">-   **[はい]** します。</span><span class="sxs-lookup"><span data-stu-id="2924a-109">-   **Yes**.</span></span> <span data-ttu-id="2924a-110">断片化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2924a-110">To enable fragmentation.</span></span><br /><span data-ttu-id="2924a-111">-   **いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="2924a-111">-   **No**.</span></span> <span data-ttu-id="2924a-112">断片化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2924a-112">To disable fragmentation.</span></span> <span data-ttu-id="2924a-113">**注:** 新しいパーティに対して**断片化のために必要な**の既定値は**いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="2924a-113">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>                                                           |
| <span data-ttu-id="2924a-114">**必要な回復可能なインターチェンジのサポート**</span><span class="sxs-lookup"><span data-stu-id="2924a-114">**Recoverable interchange support required**</span></span> | <span data-ttu-id="2924a-115">以下のオプションの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="2924a-115">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="2924a-116">-   **True**します。</span><span class="sxs-lookup"><span data-stu-id="2924a-116">-   **True**.</span></span> <span data-ttu-id="2924a-117">回復可能なインターチェンジのサポートを有効にするには</span><span class="sxs-lookup"><span data-stu-id="2924a-117">To enable recoverable interchange support.</span></span><br /><span data-ttu-id="2924a-118">-   **FALSE**します。</span><span class="sxs-lookup"><span data-stu-id="2924a-118">-   **FALSE**.</span></span> <span data-ttu-id="2924a-119">回復可能なインターチェンジのサポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2924a-119">To disable recoverable interchange support.</span></span> <span data-ttu-id="2924a-120">**注:** 新しいパーティに対して**断片化のために必要な**の既定値は**FALSE**場合のみ有効ですしの値**断片化のために必要な**は**いいえ**。</span><span class="sxs-lookup"><span data-stu-id="2924a-120">**Note:**  For a new party, **Fragmentation Required** defaults to **FALSE** and is enabled only if the value of **Fragmentation Required** is **No**.</span></span> |
|             <span data-ttu-id="2924a-121">**メッセージを選択します。**</span><span class="sxs-lookup"><span data-stu-id="2924a-121">**Select Messages**</span></span>              |                              <span data-ttu-id="2924a-122">使用可能なメッセージ ウィンドウから、バッチとして送信し、右矢印を移動 をクリックするメッセージの種類を選択します (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="2924a-122">Select the message types you want to send as a batch from the Available Messages window and then click the Move to right arrow (**>>**).</span></span><br /><br /> <span data-ttu-id="2924a-123">受信確認メッセージをバッチ処理するには、ACK メッセージの種類を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2924a-123">To batch incoming ACK messages, you must add the ACK message type.</span></span> <span data-ttu-id="2924a-124">ACK メッセージ スキーマを展開する。 これを行います。</span><span class="sxs-lookup"><span data-stu-id="2924a-124">You do so by deploying the ACK message schema.</span></span>                              |
|      <span data-ttu-id="2924a-125">**メッセージの受信確認を選択します。**</span><span class="sxs-lookup"><span data-stu-id="2924a-125">**Select Message Acknowledgments**</span></span>      |                               <span data-ttu-id="2924a-126">対象となるメッセージの種類を選択します。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用可能なメッセージの Ack ウィンドウで、バッチとして受信確認を送信し、右矢印を移動 をクリックして (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="2924a-126">Select the message types for which you want [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] to send the acknowledgments as a batch from the Available Message Acks window, and then click the Move to right arrow (**>>**).</span></span>                                |


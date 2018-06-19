---
title: BizTalk Server で HL7 アクセラレータでのパーティ タブ |Microsoft ドキュメント
description: BTAHL7 構成エクスプ ローラーを使用して、既存のパーティを表示し、BizTalk Server で受信確認を構成します。
ms.custom: ''
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e01052c8-25c5-4736-8403-33f16fbd3fb7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d8572da051d046d46b6e895f11f07d3f9d9771c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206138"
---
# <a name="parties-in-btahl7-configuration-explorer"></a><span data-ttu-id="0ac11-103">BTAHL7 構成エクスプ ローラーでパーティ</span><span class="sxs-lookup"><span data-stu-id="0ac11-103">Parties in BTAHL7 Configuration Explorer</span></span>
<span data-ttu-id="0ac11-104">使用する、**パーティ** タブを使用できる関係者を表示および指定[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成を選択すると、特定の人および受信確認のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0ac11-104">You use the **Parties** tab to view the available parties and specify [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration for a particular party that you choose, and to configure properties for acknowledgments.</span></span> 

## <a name="parties-ui-explained"></a><span data-ttu-id="0ac11-105">UI のパーティの説明</span><span class="sxs-lookup"><span data-stu-id="0ac11-105">Parties UI explained</span></span>
<span data-ttu-id="0ac11-106">**パーティ** タブには、左と右ペイン両方にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ac11-106">The **Parties** tab contains both a left and right pane.</span></span> <span data-ttu-id="0ac11-107">使用可能なパーティは、左側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac11-107">The available parties appear in the left pane.</span></span> <span data-ttu-id="0ac11-108">右側のペインには、選択したパーティに対して、次のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ac11-108">The right pane contains the following tabs for the selected party:</span></span>  
  
-   <span data-ttu-id="0ac11-109">**パーティのエイリアス**です。</span><span class="sxs-lookup"><span data-stu-id="0ac11-109">**Party Aliases**.</span></span> <span data-ttu-id="0ac11-110">左側のペインで選択したパーティに関する情報を表示するのにには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac11-110">Use this tab to view information about the party you have selected from the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ac11-111">パーティを作成するのにには、BizTalk エクスプ ローラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac11-111">You use BizTalk Explorer to create parties.</span></span>  
  
-   <span data-ttu-id="0ac11-112">**定義のバッチ**です。</span><span class="sxs-lookup"><span data-stu-id="0ac11-112">**Batch Definition**.</span></span> <span data-ttu-id="0ac11-113">このタブを使用して構成する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="0ac11-113">Use this tab to configure [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
-   <span data-ttu-id="0ac11-114">**バッチ スケジュール**です。</span><span class="sxs-lookup"><span data-stu-id="0ac11-114">**Batch Schedule**.</span></span> <span data-ttu-id="0ac11-115">このタブを使用して、送信バッチをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="0ac11-115">Use this tab to activate outbound batches.</span></span>  
  
-   <span data-ttu-id="0ac11-116">**受信確認**です。</span><span class="sxs-lookup"><span data-stu-id="0ac11-116">**Acknowledgment**.</span></span> <span data-ttu-id="0ac11-117">このタブを使用して、受信および生成された受信確認のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ac11-117">Use this tab to specify the properties for inbound and generated acknowledgments.</span></span>  
  
-   <span data-ttu-id="0ac11-118">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="0ac11-118">**Validation**.</span></span> <span data-ttu-id="0ac11-119">このタブを使用すると、受信メッセージおよび生成されたメッセージのメッセージの検証オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac11-119">Use this tab to select the message validation options for inbound and generated messages.</span></span>  
  
-   <span data-ttu-id="0ac11-120">**MSH マップ**です。</span><span class="sxs-lookup"><span data-stu-id="0ac11-120">**MSH Map**.</span></span> <span data-ttu-id="0ac11-121">受信メッセージのメッセージ ヘッダーの変換を有効にするのにには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ac11-121">Use this tab to enable message header transformations for inbound messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ac11-122">パーティ エイリアス、バッチの定義、バッチ スケジュール、およびすべての取引パーティに対する受信確認情報を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ac11-122">You must configure party aliases, batch definitions, batch schedules, and acknowledgment information for all trading parties.</span></span>  
    > 
    >  <span data-ttu-id="0ac11-123">F5 キーを押して、またはパーティの一覧を右クリックして、パーティの一覧を更新してを選択することができます**更新**です。</span><span class="sxs-lookup"><span data-stu-id="0ac11-123">You can refresh the parties list by pressing F5, or by right-clicking the parties list, and select **Refresh**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0ac11-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="0ac11-124">Next steps</span></span>  
  
-   [<span data-ttu-id="0ac11-125">パーティ エイリアス タブ</span><span class="sxs-lookup"><span data-stu-id="0ac11-125">Party Aliases Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/party-aliases-tab.md)  
  
-   <span data-ttu-id="0ac11-126">[[バッチの定義] タブ](../../adapters-and-accelerators/accelerator-hl7/batch-definition-tab.md)</span><span class="sxs-lookup"><span data-stu-id="0ac11-126">[Batch Definition Tab](../../adapters-and-accelerators/accelerator-hl7/batch-definition-tab.md)</span></span>  
  
-   <span data-ttu-id="0ac11-127">[[バッチ スケジュール] タブ](../../adapters-and-accelerators/accelerator-hl7/batch-schedule-tab.md)</span><span class="sxs-lookup"><span data-stu-id="0ac11-127">[Batch Schedule Tab](../../adapters-and-accelerators/accelerator-hl7/batch-schedule-tab.md)</span></span>  
  
-   [<span data-ttu-id="0ac11-128">受信確認 タブ</span><span class="sxs-lookup"><span data-stu-id="0ac11-128">Acknowledgment Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-tab.md)  
  
-   <span data-ttu-id="0ac11-129">[[検証] タブ](../../adapters-and-accelerators/accelerator-hl7/validation-tab.md)</span><span class="sxs-lookup"><span data-stu-id="0ac11-129">[Validation Tab](../../adapters-and-accelerators/accelerator-hl7/validation-tab.md)</span></span>  
  
-   [<span data-ttu-id="0ac11-130">MSH マップ タブ</span><span class="sxs-lookup"><span data-stu-id="0ac11-130">MSH Map Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-map-tab.md)
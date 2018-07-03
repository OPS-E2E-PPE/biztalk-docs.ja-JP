---
title: BizTalk Server で HL7 アクセラレータ [パーティ] タブ |Microsoft Docs
description: BTAHL7 構成エクスプ ローラーを使用して、既存のパーティを表示し、受信確認を BizTalk Server の構成
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
ms.openlocfilehash: 2b048cccdcc46f4713967003c81671e062420377
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976315"
---
# <a name="parties-in-btahl7-configuration-explorer"></a><span data-ttu-id="36e7d-103">BTAHL7 構成エクスプ ローラーでパーティ</span><span class="sxs-lookup"><span data-stu-id="36e7d-103">Parties in BTAHL7 Configuration Explorer</span></span>
<span data-ttu-id="36e7d-104">使用する、**パーティ** タブを使用可能な関係者を表示および指定[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成を選択すると、特定のパーティおよび受信確認のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-104">You use the **Parties** tab to view the available parties and specify [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuration for a particular party that you choose, and to configure properties for acknowledgments.</span></span> 

## <a name="parties-ui-explained"></a><span data-ttu-id="36e7d-105">UI のパーティの説明</span><span class="sxs-lookup"><span data-stu-id="36e7d-105">Parties UI explained</span></span>
<span data-ttu-id="36e7d-106">**パーティ** タブには、左と右ウィンドウ両方にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="36e7d-106">The **Parties** tab contains both a left and right pane.</span></span> <span data-ttu-id="36e7d-107">使用可能なパーティは、左側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="36e7d-107">The available parties appear in the left pane.</span></span> <span data-ttu-id="36e7d-108">右側のウィンドウには、選択したパーティに対して、次のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="36e7d-108">The right pane contains the following tabs for the selected party:</span></span>  
  
- <span data-ttu-id="36e7d-109">**パーティのエイリアス**します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-109">**Party Aliases**.</span></span> <span data-ttu-id="36e7d-110">左側のウィンドウで選択したパーティに関する情報を表示するのにには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-110">Use this tab to view information about the party you have selected from the left pane.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="36e7d-111">パーティを作成するのにには、BizTalk エクスプ ローラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-111">You use BizTalk Explorer to create parties.</span></span>  
  
- <span data-ttu-id="36e7d-112">**定義のバッチ**します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-112">**Batch Definition**.</span></span> <span data-ttu-id="36e7d-113">このタブを使用して構成する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-113">Use this tab to configure [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
- <span data-ttu-id="36e7d-114">**バッチ スケジュール**します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-114">**Batch Schedule**.</span></span> <span data-ttu-id="36e7d-115">送信バッチをアクティブ化するのにには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-115">Use this tab to activate outbound batches.</span></span>  
  
- <span data-ttu-id="36e7d-116">**受信確認**します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-116">**Acknowledgment**.</span></span> <span data-ttu-id="36e7d-117">このタブを使用して、受信と生成される受信確認のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-117">Use this tab to specify the properties for inbound and generated acknowledgments.</span></span>  
  
- <span data-ttu-id="36e7d-118">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="36e7d-118">**Validation**.</span></span> <span data-ttu-id="36e7d-119">このタブを使用すると、受信、および生成されたメッセージのメッセージの検証オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-119">Use this tab to select the message validation options for inbound and generated messages.</span></span>  
  
- <span data-ttu-id="36e7d-120">**MSH マップ**します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-120">**MSH Map**.</span></span> <span data-ttu-id="36e7d-121">受信メッセージのメッセージ ヘッダーの変換を有効にするのにには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-121">Use this tab to enable message header transformations for inbound messages.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="36e7d-122">パーティ エイリアス、バッチ定義、バッチ スケジュール、およびすべての取引先パーティの受信確認情報を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36e7d-122">You must configure party aliases, batch definitions, batch schedules, and acknowledgment information for all trading parties.</span></span>  
  > 
  >  <span data-ttu-id="36e7d-123">F5 キーを押して、またはパーティの一覧を右クリックして、パーティの一覧を更新して、選択**更新**します。</span><span class="sxs-lookup"><span data-stu-id="36e7d-123">You can refresh the parties list by pressing F5, or by right-clicking the parties list, and select **Refresh**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="36e7d-124">次のステップ</span><span class="sxs-lookup"><span data-stu-id="36e7d-124">Next steps</span></span>  
  
-   [<span data-ttu-id="36e7d-125">パーティ エイリアス タブ</span><span class="sxs-lookup"><span data-stu-id="36e7d-125">Party Aliases Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/party-aliases-tab.md)  
  
-   <span data-ttu-id="36e7d-126">[[バッチの定義] タブ](../../adapters-and-accelerators/accelerator-hl7/batch-definition-tab.md)</span><span class="sxs-lookup"><span data-stu-id="36e7d-126">[Batch Definition Tab](../../adapters-and-accelerators/accelerator-hl7/batch-definition-tab.md)</span></span>  
  
-   <span data-ttu-id="36e7d-127">[[バッチ スケジュール] タブ](../../adapters-and-accelerators/accelerator-hl7/batch-schedule-tab.md)</span><span class="sxs-lookup"><span data-stu-id="36e7d-127">[Batch Schedule Tab](../../adapters-and-accelerators/accelerator-hl7/batch-schedule-tab.md)</span></span>  
  
-   [<span data-ttu-id="36e7d-128">受信確認 タブ</span><span class="sxs-lookup"><span data-stu-id="36e7d-128">Acknowledgment Tab</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-tab.md)  
  
-   <span data-ttu-id="36e7d-129">[[検証] タブ](../../adapters-and-accelerators/accelerator-hl7/validation-tab.md)</span><span class="sxs-lookup"><span data-stu-id="36e7d-129">[Validation Tab](../../adapters-and-accelerators/accelerator-hl7/validation-tab.md)</span></span>  
  
-   <span data-ttu-id="36e7d-130">[[MSH マップ] タブ](../../adapters-and-accelerators/accelerator-hl7/msh-map-tab.md)</span><span class="sxs-lookup"><span data-stu-id="36e7d-130">[MSH Map Tab](../../adapters-and-accelerators/accelerator-hl7/msh-map-tab.md)</span></span>
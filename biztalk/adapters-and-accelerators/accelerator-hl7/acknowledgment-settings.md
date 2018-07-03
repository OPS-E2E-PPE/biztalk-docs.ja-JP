---
title: 確認の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c1f19fa1a0d1abaad29f454f25f0d8608ed497
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967139"
---
# <a name="acknowledgment-settings"></a><span data-ttu-id="3989c-102">確認の設定</span><span class="sxs-lookup"><span data-stu-id="3989c-102">Acknowledgment Settings</span></span>
<span data-ttu-id="3989c-103">使用する、**受信確認**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (大まかに言って **[パーティ]** タブ) 確認 (ACK) の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3989c-103">You use the **Acknowledgment** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure acknowledgment (ACK) settings.</span></span>  
  
 <span data-ttu-id="3989c-104">次の受信確認の種類があります。</span><span class="sxs-lookup"><span data-stu-id="3989c-104">The following acknowledgment types are available:</span></span>  
  
- <span data-ttu-id="3989c-105">**None**。</span><span class="sxs-lookup"><span data-stu-id="3989c-105">**None**.</span></span> <span data-ttu-id="3989c-106">受信確認を構成したくない場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3989c-106">Select this option if you do not want to configure any acknowledgments.</span></span>  
  
- <span data-ttu-id="3989c-107">**元**します。</span><span class="sxs-lookup"><span data-stu-id="3989c-107">**Original**.</span></span> <span data-ttu-id="3989c-108">構成するには、このオプションを選択**MSH1 – フィールドの区切り記号**、 **MSH2 – 文字のエンコード**、および**MSH8 – セキュリティ**オプションのみです。</span><span class="sxs-lookup"><span data-stu-id="3989c-108">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and the **MSH8 – Security** options only.</span></span>  
  
- <span data-ttu-id="3989c-109">**強化された**します。</span><span class="sxs-lookup"><span data-stu-id="3989c-109">**Enhanced**.</span></span> <span data-ttu-id="3989c-110">すべての受信確認の使用可能なオプションを構成するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3989c-110">Select this option to configure all available acknowledgment options.</span></span>  
  
- <span data-ttu-id="3989c-111">**遅延**します。</span><span class="sxs-lookup"><span data-stu-id="3989c-111">**Deferred**.</span></span> <span data-ttu-id="3989c-112">構成するには、このオプションを選択**MSH1 – フィールドの区切り記号**、 **MSH2 – 文字のエンコード**、および**MSH8 – セキュリティ**オプションのみです。</span><span class="sxs-lookup"><span data-stu-id="3989c-112">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and **MSH8 – Security** options only.</span></span>  
  
- <span data-ttu-id="3989c-113">**静的**します。</span><span class="sxs-lookup"><span data-stu-id="3989c-113">**Static**.</span></span> <span data-ttu-id="3989c-114">構成するには、このオプションを選択、**成功**と**失敗**の確認オプション。</span><span class="sxs-lookup"><span data-stu-id="3989c-114">Select this option to configure the **On success** and **On failure** acknowledgment options.</span></span>  
  
  <span data-ttu-id="3989c-115">受信確認の種類を設定すると、受信確認の種類に応じて、ヘッダー フィールドと、受信確認の値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3989c-115">Once the acknowledgment type is set, you can set values for header fields and acknowledgments, depending upon the acknowledgment type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3989c-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3989c-116">In This Section</span></span>  
  
-   [<span data-ttu-id="3989c-117">ACK の構成設定</span><span class="sxs-lookup"><span data-stu-id="3989c-117">ACK Configuration Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [<span data-ttu-id="3989c-118">メッセージ受信確認の構成</span><span class="sxs-lookup"><span data-stu-id="3989c-118">Configuring Message Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)
---
title: "確認の設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- acknowledgements, acknowledgement types
- configuring, acknowledgements
ms.assetid: 99ab8caa-8788-4438-96db-8001a6523cc8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34eda8a977de0dadbad974268b46e4d580cc1f33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgment-settings"></a><span data-ttu-id="58ee0-102">確認の設定</span><span class="sxs-lookup"><span data-stu-id="58ee0-102">Acknowledgment Settings</span></span>
<span data-ttu-id="58ee0-103">使用する、**受信確認**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (、高レベルの下で**パーティ** タブ) 確認 (ACK) の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="58ee0-103">You use the **Acknowledgment** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure acknowledgment (ACK) settings.</span></span>  
  
 <span data-ttu-id="58ee0-104">次の受信確認の種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="58ee0-104">The following acknowledgment types are available:</span></span>  
  
-   <span data-ttu-id="58ee0-105">**None**。</span><span class="sxs-lookup"><span data-stu-id="58ee0-105">**None**.</span></span> <span data-ttu-id="58ee0-106">受信確認を構成したくない場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="58ee0-106">Select this option if you do not want to configure any acknowledgments.</span></span>  
  
-   <span data-ttu-id="58ee0-107">**元**です。</span><span class="sxs-lookup"><span data-stu-id="58ee0-107">**Original**.</span></span> <span data-ttu-id="58ee0-108">構成するのには、このオプションを選択**MSH1 – フィールド区切り文字**、 **MSH2 – 文字のエンコード**、および**MSH8 – セキュリティ**オプションのみです。</span><span class="sxs-lookup"><span data-stu-id="58ee0-108">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and the **MSH8 – Security** options only.</span></span>  
  
-   <span data-ttu-id="58ee0-109">**強化された**です。</span><span class="sxs-lookup"><span data-stu-id="58ee0-109">**Enhanced**.</span></span> <span data-ttu-id="58ee0-110">すべての受信確認の使用可能なオプションを構成するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="58ee0-110">Select this option to configure all available acknowledgment options.</span></span>  
  
-   <span data-ttu-id="58ee0-111">**遅延**です。</span><span class="sxs-lookup"><span data-stu-id="58ee0-111">**Deferred**.</span></span> <span data-ttu-id="58ee0-112">構成するのには、このオプションを選択**MSH1 – フィールド区切り文字**、 **MSH2 – 文字のエンコード**、および**MSH8 – セキュリティ**オプションのみです。</span><span class="sxs-lookup"><span data-stu-id="58ee0-112">Select this option to configure **MSH1 – Field Separator**, **MSH2 – Encoding Characters**, and **MSH8 – Security** options only.</span></span>  
  
-   <span data-ttu-id="58ee0-113">**静的**です。</span><span class="sxs-lookup"><span data-stu-id="58ee0-113">**Static**.</span></span> <span data-ttu-id="58ee0-114">構成するのには、このオプションを選択、**成功**と**エラー発生時に**受信確認のオプションです。</span><span class="sxs-lookup"><span data-stu-id="58ee0-114">Select this option to configure the **On success** and **On failure** acknowledgment options.</span></span>  
  
 <span data-ttu-id="58ee0-115">受信確認の種類を設定すると、受信確認の種類に応じて、ヘッダー フィールドと、受信確認の値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="58ee0-115">Once the acknowledgment type is set, you can set values for header fields and acknowledgments, depending upon the acknowledgment type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58ee0-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="58ee0-116">In This Section</span></span>  
  
-   [<span data-ttu-id="58ee0-117">確認の構成の設定</span><span class="sxs-lookup"><span data-stu-id="58ee0-117">ACK Configuration Settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-configuration-settings.md)  
  
-   [<span data-ttu-id="58ee0-118">メッセージの受信確認を構成します。</span><span class="sxs-lookup"><span data-stu-id="58ee0-118">Configuring Message Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)
---
title: "検証の設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 574e4a27342680ef4a37f6b12059cbf97bd9584a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="validation-settings"></a><span data-ttu-id="50a17-102">検証の設定</span><span class="sxs-lookup"><span data-stu-id="50a17-102">Validation Settings</span></span>
<span data-ttu-id="50a17-103">使用して[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、HL7 標準に対して、メッセージを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="50a17-103">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can validate your messages against the HL7 standard.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="50a17-104">送信または受信するメッセージが、HL7 標準に準拠しているメッセージの構造と本文セグメントを持ちます。</span><span class="sxs-lookup"><span data-stu-id="50a17-104"> ensures that the messages you send or receive have a message structure and body segment that conforms to the HL7 standard.</span></span> <span data-ttu-id="50a17-105">HL7 がサポートされているカスタム データ型を検証し、末尾の区切り記号を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="50a17-105">You can also validate HL7 supported custom data types, and allow trailing delimiters.</span></span> <span data-ttu-id="50a17-106">使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**検証を構成するには、タブ。</span><span class="sxs-lookup"><span data-stu-id="50a17-106">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab to configure validation.</span></span>  
  
## <a name="configuring-validation-settings"></a><span data-ttu-id="50a17-107">検証の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="50a17-107">Configuring Validation Settings</span></span>  
 <span data-ttu-id="50a17-108">使用する、**検証**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (下で、高度な**パーティ** タブ) 検証の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="50a17-108">You use the **Validation** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure validation settings.</span></span> <span data-ttu-id="50a17-109">次の種類の検証を選択します。</span><span class="sxs-lookup"><span data-stu-id="50a17-109">You can select the following types of validation:</span></span>  
  
-   <span data-ttu-id="50a17-110">構文、構造、およびメッセージ スキーマに基づく、本文のセグメントの概略図の検証</span><span class="sxs-lookup"><span data-stu-id="50a17-110">Syntax, structure, and schematic validation on body segments, based on the message schema</span></span>  
  
-   <span data-ttu-id="50a17-111">HL7 (DT、TS、TM、および TN) にカスタム データ型の標準の検証</span><span class="sxs-lookup"><span data-stu-id="50a17-111">HL7 standard validation on custom data types (DT, TS, TM, and TN)</span></span>  
  
-   <span data-ttu-id="50a17-112">フィールドの区切り記号 (末尾の区切り記号は許可されている) の検証</span><span class="sxs-lookup"><span data-stu-id="50a17-112">Validation of field delimiters (trailing delimiters are allowed)</span></span>  
  
 <span data-ttu-id="50a17-113">このタブを使用して、このパーティに対して、メッセージの検証に使用するスキーマの名前空間を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="50a17-113">Using this tab, you can also set the schema namespace used for the validation on the messages for this party.</span></span>  
  
 <span data-ttu-id="50a17-114">次の図に示しています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**タブです。</span><span class="sxs-lookup"><span data-stu-id="50a17-114">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab.</span></span>  
  
 <span data-ttu-id="50a17-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span><span class="sxs-lookup"><span data-stu-id="50a17-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span></span>  
<span data-ttu-id="50a17-116">BTAHL7 構成エクスプ ローラーの検証 タブ</span><span class="sxs-lookup"><span data-stu-id="50a17-116">BTAHL7 Configuration Explorer Validation tab</span></span>  
  
 <span data-ttu-id="50a17-117">次の手順を使用すると、検証の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="50a17-117">Use the following procedures to configure validation settings.</span></span>  
  
#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="50a17-118">BTAHL7 構成エクスプ ローラーを開く</span><span class="sxs-lookup"><span data-stu-id="50a17-118">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="50a17-119">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="50a17-119">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
#### <a name="to-configure-validation-settings"></a><span data-ttu-id="50a17-120">検証の設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="50a17-120">To configure validation settings</span></span>  
  
1.  <span data-ttu-id="50a17-121">BTAHL7 構成エクスプ ローラーで、**検証** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="50a17-121">In BTAHL7 Configuration Explorer on the **Validation** tab, do the following:</span></span>  
  
    |<span data-ttu-id="50a17-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="50a17-122">Use this</span></span>|<span data-ttu-id="50a17-123">目的</span><span class="sxs-lookup"><span data-stu-id="50a17-123">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="50a17-124">**本文のセグメントを検証します。**</span><span class="sxs-lookup"><span data-stu-id="50a17-124">**Validate body segments**</span></span>|<span data-ttu-id="50a17-125">構文、構造、およびスキーマの検証を実行するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="50a17-125">Select this option to perform syntax, structure, and schema validation.</span></span>|  
    |<span data-ttu-id="50a17-126">**カスタム データ型を検証します。**</span><span class="sxs-lookup"><span data-stu-id="50a17-126">**Validate custom data type**</span></span>|<span data-ttu-id="50a17-127">DT、TS、TM、および TN のカスタム データ型で HL7 標準の検証を実行するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="50a17-127">Select this option to perform HL7 standard validation on DT, TS, TM, and TN custom data types.</span></span>|  
    |<span data-ttu-id="50a17-128">**末尾の区切り記号 (区切り記号) を許可します。**</span><span class="sxs-lookup"><span data-stu-id="50a17-128">**Allow trailing delimiters (separators)**</span></span>|<span data-ttu-id="50a17-129">メッセージ インスタンスの末尾のフィールド区切り記号を有効にするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="50a17-129">Select this option to enable trailing field delimiters in message instances.</span></span>|  
    |<span data-ttu-id="50a17-130">**スキーマ Namespace**</span><span class="sxs-lookup"><span data-stu-id="50a17-130">**Schema Namespace**</span></span>|<span data-ttu-id="50a17-131">スキーマ名前空間の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="50a17-131">Type the schema namespace location.</span></span> <span data-ttu-id="50a17-132">既定値は、http://microsoft.com/HealthCare/HL7/2X です。</span><span class="sxs-lookup"><span data-stu-id="50a17-132">The default value is http://microsoft.com/HealthCare/HL7/2X.</span></span>|  
  
2.  <span data-ttu-id="50a17-133">**[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50a17-133">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a17-134">参照</span><span class="sxs-lookup"><span data-stu-id="50a17-134">See Also</span></span>  
 <span data-ttu-id="50a17-135">[ログの構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="50a17-135">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="50a17-136">[確認の設定](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span><span class="sxs-lookup"><span data-stu-id="50a17-136">[Acknowledgment Settings](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span></span>  
[<span data-ttu-id="50a17-137">操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定</span><span class="sxs-lookup"><span data-stu-id="50a17-137">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)
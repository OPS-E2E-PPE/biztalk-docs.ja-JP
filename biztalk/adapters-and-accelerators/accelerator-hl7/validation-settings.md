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
ms.openlocfilehash: 108f13dfbdc7b42027f57e70d913202b4d4e3100
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validation-settings"></a><span data-ttu-id="6f4fa-102">検証の設定</span><span class="sxs-lookup"><span data-stu-id="6f4fa-102">Validation Settings</span></span>
<span data-ttu-id="6f4fa-103">使用して[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、HL7 標準に対して、メッセージを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-103">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can validate your messages against the HL7 standard.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6f4fa-104">送信または受信するメッセージが、HL7 標準に準拠しているメッセージの構造と本文セグメントを持ちます。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-104"> ensures that the messages you send or receive have a message structure and body segment that conforms to the HL7 standard.</span></span> <span data-ttu-id="6f4fa-105">HL7 がサポートされているカスタム データ型を検証し、末尾の区切り記号を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-105">You can also validate HL7 supported custom data types, and allow trailing delimiters.</span></span> <span data-ttu-id="6f4fa-106">使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**検証を構成するには、タブ。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-106">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab to configure validation.</span></span>  
  
## <a name="configuring-validation-settings"></a><span data-ttu-id="6f4fa-107">検証の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-107">Configuring Validation Settings</span></span>  
 <span data-ttu-id="6f4fa-108">使用する、**検証**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (下で、高度な**パーティ** タブ) 検証の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-108">You use the **Validation** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure validation settings.</span></span> <span data-ttu-id="6f4fa-109">次の種類の検証を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-109">You can select the following types of validation:</span></span>  
  
-   <span data-ttu-id="6f4fa-110">構文、構造、およびメッセージ スキーマに基づく、本文のセグメントの概略図の検証</span><span class="sxs-lookup"><span data-stu-id="6f4fa-110">Syntax, structure, and schematic validation on body segments, based on the message schema</span></span>  
  
-   <span data-ttu-id="6f4fa-111">HL7 (DT、TS、TM、および TN) にカスタム データ型の標準の検証</span><span class="sxs-lookup"><span data-stu-id="6f4fa-111">HL7 standard validation on custom data types (DT, TS, TM, and TN)</span></span>  
  
-   <span data-ttu-id="6f4fa-112">フィールドの区切り記号 (末尾の区切り記号は許可されている) の検証</span><span class="sxs-lookup"><span data-stu-id="6f4fa-112">Validation of field delimiters (trailing delimiters are allowed)</span></span>  
  
 <span data-ttu-id="6f4fa-113">このタブを使用して、このパーティに対して、メッセージの検証に使用するスキーマの名前空間を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-113">Using this tab, you can also set the schema namespace used for the validation on the messages for this party.</span></span>  
  
 <span data-ttu-id="6f4fa-114">次の図に示しています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**タブです。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-114">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")  
<span data-ttu-id="6f4fa-115">BTAHL7 構成エクスプ ローラーの検証 タブ</span><span class="sxs-lookup"><span data-stu-id="6f4fa-115">BTAHL7 Configuration Explorer Validation tab</span></span>  
  
 <span data-ttu-id="6f4fa-116">次の手順を使用すると、検証の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-116">Use the following procedures to configure validation settings.</span></span>  
  
#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="6f4fa-117">BTAHL7 構成エクスプ ローラーを開く</span><span class="sxs-lookup"><span data-stu-id="6f4fa-117">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="6f4fa-118">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-118">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
#### <a name="to-configure-validation-settings"></a><span data-ttu-id="6f4fa-119">検証の設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="6f4fa-119">To configure validation settings</span></span>  
  
1.  <span data-ttu-id="6f4fa-120">BTAHL7 構成エクスプ ローラーで、**検証** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-120">In BTAHL7 Configuration Explorer on the **Validation** tab, do the following:</span></span>  
  
    |<span data-ttu-id="6f4fa-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6f4fa-121">Use this</span></span>|<span data-ttu-id="6f4fa-122">目的</span><span class="sxs-lookup"><span data-stu-id="6f4fa-122">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6f4fa-123">**本文のセグメントを検証します。**</span><span class="sxs-lookup"><span data-stu-id="6f4fa-123">**Validate body segments**</span></span>|<span data-ttu-id="6f4fa-124">構文、構造、およびスキーマの検証を実行するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-124">Select this option to perform syntax, structure, and schema validation.</span></span>|  
    |<span data-ttu-id="6f4fa-125">**カスタム データ型を検証します。**</span><span class="sxs-lookup"><span data-stu-id="6f4fa-125">**Validate custom data type**</span></span>|<span data-ttu-id="6f4fa-126">DT、TS、TM、および TN のカスタム データ型で HL7 標準の検証を実行するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-126">Select this option to perform HL7 standard validation on DT, TS, TM, and TN custom data types.</span></span>|  
    |<span data-ttu-id="6f4fa-127">**末尾の区切り記号 (区切り記号) を許可します。**</span><span class="sxs-lookup"><span data-stu-id="6f4fa-127">**Allow trailing delimiters (separators)**</span></span>|<span data-ttu-id="6f4fa-128">メッセージ インスタンスの末尾のフィールド区切り記号を有効にするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-128">Select this option to enable trailing field delimiters in message instances.</span></span>|  
    |<span data-ttu-id="6f4fa-129">**スキーマ Namespace**</span><span class="sxs-lookup"><span data-stu-id="6f4fa-129">**Schema Namespace**</span></span>|<span data-ttu-id="6f4fa-130">スキーマ名前空間の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-130">Type the schema namespace location.</span></span> <span data-ttu-id="6f4fa-131">既定値は、http://microsoft.com/HealthCare/HL7/2X です。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-131">The default value is http://microsoft.com/HealthCare/HL7/2X.</span></span>|  
  
2.  <span data-ttu-id="6f4fa-132">**[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f4fa-132">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f4fa-133">参照</span><span class="sxs-lookup"><span data-stu-id="6f4fa-133">See Also</span></span>  
 <span data-ttu-id="6f4fa-134">[ログの構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6f4fa-134">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="6f4fa-135">[確認の設定](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span><span class="sxs-lookup"><span data-stu-id="6f4fa-135">[Acknowledgment Settings](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span></span>  
[<span data-ttu-id="6f4fa-136">運用上のログ記録、メッセージのバッチ処理、検証および asknowledgment 設定</span><span class="sxs-lookup"><span data-stu-id="6f4fa-136">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)
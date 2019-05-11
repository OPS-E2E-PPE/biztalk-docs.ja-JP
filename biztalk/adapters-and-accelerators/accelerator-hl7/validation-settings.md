---
title: 検証の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, configuring
- configuring, validating
ms.assetid: ee08acac-99f9-4403-b2ae-01b80378aa58
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92fa9c8106dd8d00b3d7090e05d65b7d2632d193
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285347"
---
# <a name="validation-settings"></a><span data-ttu-id="fef01-102">検証の設定</span><span class="sxs-lookup"><span data-stu-id="fef01-102">Validation Settings</span></span>
<span data-ttu-id="fef01-103">使用して[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、HL7 標準に対してメッセージを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="fef01-103">Using [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)], you can validate your messages against the HL7 standard.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="fef01-104">HL7 標準に準拠しているメッセージの構造と本文セグメントを送信または受信するメッセージがあることをによりします。</span><span class="sxs-lookup"><span data-stu-id="fef01-104">ensures that the messages you send or receive have a message structure and body segment that conforms to the HL7 standard.</span></span> <span data-ttu-id="fef01-105">HL7 がサポートされているカスタム データ型を検証し、末尾の区切り記号を許可できます。</span><span class="sxs-lookup"><span data-stu-id="fef01-105">You can also validate HL7 supported custom data types, and allow trailing delimiters.</span></span> <span data-ttu-id="fef01-106">使用する、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**検証を構成するには、タブ。</span><span class="sxs-lookup"><span data-stu-id="fef01-106">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab to configure validation.</span></span>  

## <a name="configuring-validation-settings"></a><span data-ttu-id="fef01-107">検証の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fef01-107">Configuring Validation Settings</span></span>  
 <span data-ttu-id="fef01-108">使用する、**検証**タブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー (高レベルの下で**パーティ** タブ) 検証の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fef01-108">You use the **Validation** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (under the high-level **Parties** tab) to configure validation settings.</span></span> <span data-ttu-id="fef01-109">次の種類の検証を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fef01-109">You can select the following types of validation:</span></span>  

- <span data-ttu-id="fef01-110">構文、構造、およびメッセージ スキーマに基づく、本文のセグメントの概略図を検証</span><span class="sxs-lookup"><span data-stu-id="fef01-110">Syntax, structure, and schematic validation on body segments, based on the message schema</span></span>  

- <span data-ttu-id="fef01-111">カスタム データ型 (DT、TS、TM、および TN) の HL7 標準の検証</span><span class="sxs-lookup"><span data-stu-id="fef01-111">HL7 standard validation on custom data types (DT, TS, TM, and TN)</span></span>  

- <span data-ttu-id="fef01-112">(末尾の区切り記号を許可する) フィールドの区切り記号の検証</span><span class="sxs-lookup"><span data-stu-id="fef01-112">Validation of field delimiters (trailing delimiters are allowed)</span></span>  

  <span data-ttu-id="fef01-113">このタブを使用して、このパーティに対するメッセージの検証に使用するスキーマ名前空間を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fef01-113">Using this tab, you can also set the schema namespace used for the validation on the messages for this party.</span></span>  

  <span data-ttu-id="fef01-114">次に示します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**検証**タブ。</span><span class="sxs-lookup"><span data-stu-id="fef01-114">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Validation** tab.</span></span>  

  <span data-ttu-id="fef01-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span><span class="sxs-lookup"><span data-stu-id="fef01-115">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-val.gif "hl7_ops_val")</span></span>  
  <span data-ttu-id="fef01-116">BTAHL7 構成エクスプ ローラーの検証 タブ</span><span class="sxs-lookup"><span data-stu-id="fef01-116">BTAHL7 Configuration Explorer Validation tab</span></span>  

  <span data-ttu-id="fef01-117">検証の設定を構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="fef01-117">Use the following procedures to configure validation settings.</span></span>  

#### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="fef01-118">BTAHL7 構成エクスプ ローラーを開く</span><span class="sxs-lookup"><span data-stu-id="fef01-118">To open BTAHL7 Configuration Explorer</span></span>  

-   <span data-ttu-id="fef01-119">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk\<バージョン\>Accelerator for HL7**、 をクリックし、 **BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="fef01-119">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

#### <a name="to-configure-validation-settings"></a><span data-ttu-id="fef01-120">検証の設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="fef01-120">To configure validation settings</span></span>  

1. <span data-ttu-id="fef01-121">BTAHL7 構成エクスプ ローラーで、**検証** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fef01-121">In BTAHL7 Configuration Explorer on the **Validation** tab, do the following:</span></span>  


   |                  <span data-ttu-id="fef01-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fef01-122">Use this</span></span>                  |                                            <span data-ttu-id="fef01-123">目的</span><span class="sxs-lookup"><span data-stu-id="fef01-123">To do this</span></span>                                            |
   |--------------------------------------------|--------------------------------------------------------------------------------------------------|
   |         <span data-ttu-id="fef01-124">**本文のセグメントを検証します。**</span><span class="sxs-lookup"><span data-stu-id="fef01-124">**Validate body segments**</span></span>         |             <span data-ttu-id="fef01-125">構文、構造、およびスキーマ検証を実行するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fef01-125">Select this option to perform syntax, structure, and schema validation.</span></span>              |
   |       <span data-ttu-id="fef01-126">**カスタム データ型を検証します。**</span><span class="sxs-lookup"><span data-stu-id="fef01-126">**Validate custom data type**</span></span>        |  <span data-ttu-id="fef01-127">DT、TS、TM、TN、カスタム データ型で HL7 標準の検証を実行するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fef01-127">Select this option to perform HL7 standard validation on DT, TS, TM, and TN custom data types.</span></span>  |
   | <span data-ttu-id="fef01-128">**末尾の区切り記号 (区切り記号) を許可します。**</span><span class="sxs-lookup"><span data-stu-id="fef01-128">**Allow trailing delimiters (separators)**</span></span> |           <span data-ttu-id="fef01-129">メッセージ インスタンスで末尾のフィールド区切り記号を有効にするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fef01-129">Select this option to enable trailing field delimiters in message instances.</span></span>           |
   |            <span data-ttu-id="fef01-130">**スキーマの Namespace**</span><span class="sxs-lookup"><span data-stu-id="fef01-130">**Schema Namespace**</span></span>            | <span data-ttu-id="fef01-131">スキーマ名前空間の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="fef01-131">Type the schema namespace location.</span></span> <span data-ttu-id="fef01-132">既定値は http://microsoft.com/HealthCare/HL7/2X です。</span><span class="sxs-lookup"><span data-stu-id="fef01-132">The default value is http://microsoft.com/HealthCare/HL7/2X.</span></span> |


2. <span data-ttu-id="fef01-133">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fef01-133">Click **Save**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fef01-134">参照</span><span class="sxs-lookup"><span data-stu-id="fef01-134">See Also</span></span>  
 <span data-ttu-id="fef01-135">[ログの構成](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="fef01-135">[Logging Configuration](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md) </span></span>  
 <span data-ttu-id="fef01-136">[確認の設定](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span><span class="sxs-lookup"><span data-stu-id="fef01-136">[Acknowledgment Settings](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-settings.md) </span></span>  
[<span data-ttu-id="fef01-137">操作ログ記録、メッセージのバッチ処理、検証および受信確認の設定</span><span class="sxs-lookup"><span data-stu-id="fef01-137">Operational logging, message batching, validation and asknowledgment settings</span></span>](../../adapters-and-accelerators/accelerator-hl7/operational-logging-message-batching-validation-and-asknowledgment-settings.md)
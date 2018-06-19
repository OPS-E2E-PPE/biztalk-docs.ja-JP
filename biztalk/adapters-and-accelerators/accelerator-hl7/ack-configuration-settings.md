---
title: 確認の構成の設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- configuring, acknowledgements
ms.assetid: 46e92560-7b1e-4d53-9de8-8ded4de90695
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93dea42fd084f22b4644f0acbb21860d69f75027
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204410"
---
# <a name="ack-configuration-settings"></a><span data-ttu-id="45a39-102">確認の構成の設定</span><span class="sxs-lookup"><span data-stu-id="45a39-102">ACK Configuration Settings</span></span>
<span data-ttu-id="45a39-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]パーサーが取引先管理 (TPM) の設定に基づいて受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="45a39-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] parser generates acknowledgments based on Trading Partner Management (TPM) settings.</span></span> <span data-ttu-id="45a39-104">確認 (ACK) の設定は、パートナー情報に依存します。</span><span class="sxs-lookup"><span data-stu-id="45a39-104">The acknowledgment (ACK) settings are dependent on partner information.</span></span> <span data-ttu-id="45a39-105">スキーマの種類は使用されません。</span><span class="sxs-lookup"><span data-stu-id="45a39-105">Schema type is not used.</span></span> <span data-ttu-id="45a39-106">ときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]AL、SU または ER、含む MSH15 フィールドで、確認メッセージを受信[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK ヘッダーと TPM の構成の解析結果に基づくこのメッセージの ACK を送信することがあります。</span><span class="sxs-lookup"><span data-stu-id="45a39-106">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK message with the MSH15 field containing AL, SU or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] may send an ACK for this message based on the result of parsing the ACK header and TPM configuration.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="45a39-107">パートナー ACK 設定を取得し、次の 5 つの値のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="45a39-107"> retrieves the partner ACK settings and returns one of the following five values:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45a39-108">HL7 仕様では 1 4 からと生成される ACK メッセージの MSH15 フィールドを設定する項目を使用することが必須です。</span><span class="sxs-lookup"><span data-stu-id="45a39-108">The HL7 specification mandates that you use items 1 through 4 and to populate the MSH15 field of an ACK message that you generate.</span></span> <span data-ttu-id="45a39-109">項目 5 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-特定され、確認を生成しないようにを表します</span><span class="sxs-lookup"><span data-stu-id="45a39-109">Item 5 is [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-specific and denotes not to generate an ACK.</span></span>  
  
1.  <span data-ttu-id="45a39-110">AL – 常に</span><span class="sxs-lookup"><span data-stu-id="45a39-110">AL – Always</span></span>  
  
2.  <span data-ttu-id="45a39-111">NE – ことはありません。</span><span class="sxs-lookup"><span data-stu-id="45a39-111">NE – Never</span></span>  
  
3.  <span data-ttu-id="45a39-112">SU – 成功</span><span class="sxs-lookup"><span data-stu-id="45a39-112">SU – Success</span></span>  
  
4.  <span data-ttu-id="45a39-113">ER – エラー</span><span class="sxs-lookup"><span data-stu-id="45a39-113">ER – Error</span></span>  
  
5.  <span data-ttu-id="45a39-114">いいえ-ACK を生成しません。</span><span class="sxs-lookup"><span data-stu-id="45a39-114">NO – Do not generate an ACK</span></span>  
  
## <a name="ack-configuration-inconsistency"></a><span data-ttu-id="45a39-115">ACK の構成の不整合</span><span class="sxs-lookup"><span data-stu-id="45a39-115">ACK configuration inconsistency</span></span>  
 <span data-ttu-id="45a39-116">場合は、ACK 構成ユーザー インターフェイスの設定と、メッセージ インスタンス MSH15 と MSH16 フィールド内の値の間で不整合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が必要な 2 つの確認の生成のトリガーのいずれかの場合は、ACK を送信します。</span><span class="sxs-lookup"><span data-stu-id="45a39-116">In the case of inconsistency between the ACK configuration user interface settings and values inside the message instance MSH15 and MSH16 fields, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK when one of the two ACK generation triggers require it.</span></span> <span data-ttu-id="45a39-117">その他の不一致の場合は、インスタンス内のデータが構成ユーザー インターフェイスで設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="45a39-117">In the case of other inconsistencies, the data in the instance will override the setting in the configuration user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a39-118">参照</span><span class="sxs-lookup"><span data-stu-id="45a39-118">See Also</span></span>  
 <span data-ttu-id="45a39-119">[メッセージの受信確認を構成します。](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="45a39-119">[Configuring Message Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span></span>  
 [<span data-ttu-id="45a39-120">作成して、受信確認の処理</span><span class="sxs-lookup"><span data-stu-id="45a39-120">Creating and Processing Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)
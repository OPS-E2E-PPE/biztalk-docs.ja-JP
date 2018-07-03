---
title: 確認の構成の設定 |Microsoft Docs
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
ms.openlocfilehash: 06cedaee1ca0ad574920cfb646f69d63157c8e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968059"
---
# <a name="ack-configuration-settings"></a><span data-ttu-id="76007-102">ACK の構成設定</span><span class="sxs-lookup"><span data-stu-id="76007-102">ACK Configuration Settings</span></span>
<span data-ttu-id="76007-103">Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]パーサーが取引先管理 (TPM) の設定に基づいて受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="76007-103">The Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] parser generates acknowledgments based on Trading Partner Management (TPM) settings.</span></span> <span data-ttu-id="76007-104">確認 (ACK) の設定は、パートナー情報に依存します。</span><span class="sxs-lookup"><span data-stu-id="76007-104">The acknowledgment (ACK) settings are dependent on partner information.</span></span> <span data-ttu-id="76007-105">スキーマの種類は使用されません。</span><span class="sxs-lookup"><span data-stu-id="76007-105">Schema type is not used.</span></span> <span data-ttu-id="76007-106">ときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]AL、SU または ER、含む MSH15 フィールドで、確認メッセージを受け取る[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK ヘッダーと TPM の構成の解析結果に基づいて、このメッセージの ACK を送信することがあります。</span><span class="sxs-lookup"><span data-stu-id="76007-106">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK message with the MSH15 field containing AL, SU or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] may send an ACK for this message based on the result of parsing the ACK header and TPM configuration.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="76007-107"> 確認のパートナーの設定を取得し、次の 5 つの値のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="76007-107"> retrieves the partner ACK settings and returns one of the following five values:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76007-108">HL7 の仕様には、1 4 からと生成される ACK メッセージの MSH15 フィールドを設定する項目を使用することが定められています。</span><span class="sxs-lookup"><span data-stu-id="76007-108">The HL7 specification mandates that you use items 1 through 4 and to populate the MSH15 field of an ACK message that you generate.</span></span> <span data-ttu-id="76007-109">項目 5 が[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の特定、ACK を生成しないようにを表します</span><span class="sxs-lookup"><span data-stu-id="76007-109">Item 5 is [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-specific and denotes not to generate an ACK.</span></span>  
  
1.  <span data-ttu-id="76007-110">AL – 常に</span><span class="sxs-lookup"><span data-stu-id="76007-110">AL – Always</span></span>  
  
2.  <span data-ttu-id="76007-111">ありません – NE</span><span class="sxs-lookup"><span data-stu-id="76007-111">NE – Never</span></span>  
  
3.  <span data-ttu-id="76007-112">SU-成功</span><span class="sxs-lookup"><span data-stu-id="76007-112">SU – Success</span></span>  
  
4.  <span data-ttu-id="76007-113">ER – エラー</span><span class="sxs-lookup"><span data-stu-id="76007-113">ER – Error</span></span>  
  
5.  <span data-ttu-id="76007-114">[いいえ] – ACK を生成できません。</span><span class="sxs-lookup"><span data-stu-id="76007-114">NO – Do not generate an ACK</span></span>  
  
## <a name="ack-configuration-inconsistency"></a><span data-ttu-id="76007-115">ACK の構成の不一致</span><span class="sxs-lookup"><span data-stu-id="76007-115">ACK configuration inconsistency</span></span>  
 <span data-ttu-id="76007-116">場合は、ACK 構成ユーザー インターフェイスの設定とメッセージ インスタンス MSH15、MSH16 フィールド内の値の間に不整合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]が必要な 2 つの確認の生成のトリガーのいずれかの場合は、ACK を送信します。</span><span class="sxs-lookup"><span data-stu-id="76007-116">In the case of inconsistency between the ACK configuration user interface settings and values inside the message instance MSH15 and MSH16 fields, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an ACK when one of the two ACK generation triggers require it.</span></span> <span data-ttu-id="76007-117">その他の不整合の場合、インスタンス内のデータは構成ユーザー インターフェイスで設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="76007-117">In the case of other inconsistencies, the data in the instance will override the setting in the configuration user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76007-118">参照</span><span class="sxs-lookup"><span data-stu-id="76007-118">See Also</span></span>  
 <span data-ttu-id="76007-119">[メッセージの受信確認の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="76007-119">[Configuring Message Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md) </span></span>  
 [<span data-ttu-id="76007-120">受信確認の作成と処理</span><span class="sxs-lookup"><span data-stu-id="76007-120">Creating and Processing Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)
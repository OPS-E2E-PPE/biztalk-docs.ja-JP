---
title: "メッセージの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, messages
- messages, validating
ms.assetid: 720ab16a-7ab4-4741-9951-9ab10a2c4c24
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 940b6aa811cbee845b287c09a66c4b9753313ee0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-validation"></a><span data-ttu-id="36f11-102">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="36f11-102">Message Validation</span></span>
<span data-ttu-id="36f11-103">2.X が受信および送信パイプライン、メッセージの検証は HL7 で受信および送信の HL7 メッセージに対して発生します。</span><span class="sxs-lookup"><span data-stu-id="36f11-103">Message validation occurs for incoming and outgoing HL7 messages with HL7 2.X receive and send pipelines.</span></span> <span data-ttu-id="36f11-104">MSH (ヘッダー) セグメントのみまたはメッセージの本文全体の検証を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="36f11-104">You can configure validation for only the MSH (header) segment, or for the entire message body.</span></span> <span data-ttu-id="36f11-105">さらに、スキーマの一意のローカライズ バージョンに対して検証することができます。</span><span class="sxs-lookup"><span data-stu-id="36f11-105">In addition, it is possible to validate against unique localized versions of the schema.</span></span> <span data-ttu-id="36f11-106">ために、一意の名前空間の値を定義して (パーティ レベルでは、HL7 メッセージング構成と、メッセージを定義する実際のスキーマのターゲット名前空間プロパティの両方でこの名前空間の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="36f11-106">You accomplish this by defining a unique namespace value, and using this namespace value within both the HL7 messaging configuration (at the party level) and the target namespace property of the actual schema that defines the message.</span></span> <span data-ttu-id="36f11-107">実行時に、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) メッセージの解析と検証の適切なスキーマを選択する名前空間とスキーマのルート参照プロパティの組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="36f11-107">At run time, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the combination of namespace and the root reference property for the schema to select the appropriate schema for message parsing and validation.</span></span>  
  
 <span data-ttu-id="36f11-108">パーサーとシリアライザーは、メッセージに関連付けられているパーティの設定に基づく検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="36f11-108">The parser and serializer perform validation based on the settings for the party associated with a message.</span></span> <span data-ttu-id="36f11-109">バッチ処理、受信確認、およびメッセージ ヘッダーの上書きを含むその他のパーティの設定は、パーサーは、シリアライザーが検証を実行する方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="36f11-109">Other party settings, including batching, acknowledgment, and message-header override affect how the parser or serializer performs validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36f11-110">シリアライザーは一連の手順については、(該当する場合) を含む MSH マップでヘッダーの上書きを実行して、XML 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="36f11-110">The serializer performs a series of steps, including (if applicable) performing header overrides from an MSH map, and performing XML validation.</span></span> <span data-ttu-id="36f11-111">メッセージが本文の検証に合格した場合でもヘッダーの override キーワードと検証の処理がどちらも有効になり、ヘッダーのオーバーライド処理は、ヘッダー フィールドに不適切な値を入力すると場合に、メッセージで、検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="36f11-111">If the header override and validation processes are both enabled, and the header override process enters an incorrect value into a header field, the message will fail validation, even if the message were to pass body validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f11-112">参照</span><span class="sxs-lookup"><span data-stu-id="36f11-112">See Also</span></span>  
 [<span data-ttu-id="36f11-113">MSH 上書き</span><span class="sxs-lookup"><span data-stu-id="36f11-113">MSH Override</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)
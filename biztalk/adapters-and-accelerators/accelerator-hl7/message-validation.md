---
title: メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, messages
- messages, validating
ms.assetid: 720ab16a-7ab4-4741-9951-9ab10a2c4c24
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67d3da2162fedcb266e5b754e8bb55893238d7e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303679"
---
# <a name="message-validation"></a><span data-ttu-id="1ae50-102">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="1ae50-102">Message Validation</span></span>
<span data-ttu-id="1ae50-103">2.X の受信および送信パイプラインは、HL7 で受信および送信の HL7 メッセージのメッセージの検証が発生します。</span><span class="sxs-lookup"><span data-stu-id="1ae50-103">Message validation occurs for incoming and outgoing HL7 messages with HL7 2.X receive and send pipelines.</span></span> <span data-ttu-id="1ae50-104">MSH (ヘッダー) セグメントのまたはメッセージ本文全体の検証を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="1ae50-104">You can configure validation for only the MSH (header) segment, or for the entire message body.</span></span> <span data-ttu-id="1ae50-105">さらに、一意のローカライズされたバージョンのスキーマに対して検証することができます。</span><span class="sxs-lookup"><span data-stu-id="1ae50-105">In addition, it is possible to validate against unique localized versions of the schema.</span></span> <span data-ttu-id="1ae50-106">これを実現するには、一意の名前空間値を定義して、(パーティ レベル) では、HL7 メッセージング構成と、メッセージを定義する実際のスキーマのターゲット名前空間のプロパティの両方でこの名前空間の値を使用してします。</span><span class="sxs-lookup"><span data-stu-id="1ae50-106">You accomplish this by defining a unique namespace value, and using this namespace value within both the HL7 messaging configuration (at the party level) and the target namespace property of the actual schema that defines the message.</span></span> <span data-ttu-id="1ae50-107">実行時に、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) メッセージの解析と検証のための適切なスキーマを選択する名前空間とスキーマのルート参照プロパティの組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ae50-107">At run time, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the combination of namespace and the root reference property for the schema to select the appropriate schema for message parsing and validation.</span></span>  
  
 <span data-ttu-id="1ae50-108">パーサーとシリアライザーは、メッセージに関連付けられているパーティの設定に基づく検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="1ae50-108">The parser and serializer perform validation based on the settings for the party associated with a message.</span></span> <span data-ttu-id="1ae50-109">バッチ処理、受信確認、およびメッセージ ヘッダーの上書きを含む、他のパーティ設定では、パーサーまたはシリアライザーの検証を実行する方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="1ae50-109">Other party settings, including batching, acknowledgment, and message-header override affect how the parser or serializer performs validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ae50-110">シリアライザーは、一連の (存在する場合) を含む手順を実行します。 MSH マップでヘッダーの上書きを実行すると、XML の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="1ae50-110">The serializer performs a series of steps, including (if applicable) performing header overrides from an MSH map, and performing XML validation.</span></span> <span data-ttu-id="1ae50-111">ヘッダーの上書きと検証プロセスは、両方を有効にし、ヘッダーの上書きプロセス ヘッダー フィールドに誤った値を入力する場合、メッセージは、検証メッセージが本文の検証に合格した場合でも失敗します。</span><span class="sxs-lookup"><span data-stu-id="1ae50-111">If the header override and validation processes are both enabled, and the header override process enters an incorrect value into a header field, the message will fail validation, even if the message were to pass body validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae50-112">参照</span><span class="sxs-lookup"><span data-stu-id="1ae50-112">See Also</span></span>  
 [<span data-ttu-id="1ae50-113">MSH のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="1ae50-113">MSH Override</span></span>](../../adapters-and-accelerators/accelerator-hl7/msh-override.md)
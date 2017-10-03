---
title: "HL7 2.X アセンブラーでスキーマの決定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, assembler
- MSH5
- assembler, schemas
ms.assetid: 464c006e-4fae-4e2a-99ea-157301c0179e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50a430750846ae2567f063f9aa77221bad9c97e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a><span data-ttu-id="fb999-102">HL7 2.X アセンブラーでスキーマの決定</span><span class="sxs-lookup"><span data-stu-id="fb999-102">Schema Determination in the HL7 2.X Assembler</span></span>
<span data-ttu-id="fb999-103">メッセージが、このシリアライザーで、シリアライザーに送信されるときに[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) MSH5 を使用して (送信先パーティ)、メッセージ上で実行される操作を決定するメッセージのです。</span><span class="sxs-lookup"><span data-stu-id="fb999-103">When a message flows to the serializer, the serializer in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses MSH5 (destination party) of the message to determine the operations to be performed on the message.</span></span> <span data-ttu-id="fb999-104">このような操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fb999-104">Such operations include:</span></span>  
  
-   <span data-ttu-id="fb999-105">本文のセグメントの XML 検証を実行するかどうか</span><span class="sxs-lookup"><span data-stu-id="fb999-105">Whether to perform XML validation for body segments</span></span>  
  
-   <span data-ttu-id="fb999-106">本文のセグメントのカスタム データ型を検証するかどうか</span><span class="sxs-lookup"><span data-stu-id="fb999-106">Whether to validate custom data types for body segments</span></span>  
  
-   <span data-ttu-id="fb999-107">末尾の本体に区切り記号を許可するかどうか</span><span class="sxs-lookup"><span data-stu-id="fb999-107">Whether to allow trailing delimiters in the body</span></span>  
  
-   <span data-ttu-id="fb999-108">シリアライザーを使用するスキーマ ターゲットの名前空間</span><span class="sxs-lookup"><span data-stu-id="fb999-108">Which schema target namespace the serializer will use</span></span>  
  
-   <span data-ttu-id="fb999-109">かどうか、シリアライザーは、ヘッダーにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb999-109">Whether the serializer needs to map the header</span></span>  
  
 <span data-ttu-id="fb999-110">スキーマを決定するには、シリアライザーは次のとおり</span><span class="sxs-lookup"><span data-stu-id="fb999-110">To determine the schema, the serializer does the following:</span></span>  
  
-   <span data-ttu-id="fb999-111">ターゲットの名前空間の設定 (**TargetNS**) 送信先パーティに対して構成されている名前空間と同じ値を</span><span class="sxs-lookup"><span data-stu-id="fb999-111">Sets the target namespace (**TargetNS**) to the same value as the namespace configured for the destination party</span></span>  
  
-   <span data-ttu-id="fb999-112">抽出**Rootnode**から、 **BTS です。MessageType**昇格されたプロパティ</span><span class="sxs-lookup"><span data-stu-id="fb999-112">Extracts **Rootnode** from the **BTS.MessageType** promoted property</span></span>  
  
 <span data-ttu-id="fb999-113">**Doctype**なります**TargetNS「#」+ Rootnode**です。</span><span class="sxs-lookup"><span data-stu-id="fb999-113">The **doctype** becomes **TargetNS + "#" + Rootnode**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb999-114">参照</span><span class="sxs-lookup"><span data-stu-id="fb999-114">See Also</span></span>  
 <span data-ttu-id="fb999-115">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="fb999-115">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="fb999-116">BTAHL72X フラット ファイル処理</span><span class="sxs-lookup"><span data-stu-id="fb999-116">BTAHL72X Flat File Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)
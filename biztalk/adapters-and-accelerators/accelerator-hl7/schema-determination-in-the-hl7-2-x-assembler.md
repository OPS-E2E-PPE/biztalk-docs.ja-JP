---
title: HL7 2.X アセンブラーのスキーマの決定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, assembler
- MSH5
- assembler, schemas
ms.assetid: 464c006e-4fae-4e2a-99ea-157301c0179e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df5ebe635c656bc93a1df796eb4c778c2e99f329
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289936"
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a><span data-ttu-id="5e602-102">HL7 2.X アセンブラーのスキーマ決定</span><span class="sxs-lookup"><span data-stu-id="5e602-102">Schema Determination in the HL7 2.X Assembler</span></span>
<span data-ttu-id="5e602-103">シリアライザーにメッセージをフローするときでは、Microsoft BizTalk Accelerator for HL7 のシリアライザー ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) MSH5 を使用して (送信先パーティ) のメッセージに対して実行する操作を決定するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5e602-103">When a message flows to the serializer, the serializer in Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses MSH5 (destination party) of the message to determine the operations to be performed on the message.</span></span> <span data-ttu-id="5e602-104">このような操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e602-104">Such operations include:</span></span>  
  
- <span data-ttu-id="5e602-105">本文のセグメントの XML の検証を実行するかどうか</span><span class="sxs-lookup"><span data-stu-id="5e602-105">Whether to perform XML validation for body segments</span></span>  
  
- <span data-ttu-id="5e602-106">本文のセグメントのカスタム データ型を検証するかどうか</span><span class="sxs-lookup"><span data-stu-id="5e602-106">Whether to validate custom data types for body segments</span></span>  
  
- <span data-ttu-id="5e602-107">末尾の本体に区切り記号を許可するかどうか</span><span class="sxs-lookup"><span data-stu-id="5e602-107">Whether to allow trailing delimiters in the body</span></span>  
  
- <span data-ttu-id="5e602-108">シリアライザーを使用するスキーマ ターゲットの名前空間</span><span class="sxs-lookup"><span data-stu-id="5e602-108">Which schema target namespace the serializer will use</span></span>  
  
- <span data-ttu-id="5e602-109">シリアライザーがヘッダーにマップする必要があるかどうか</span><span class="sxs-lookup"><span data-stu-id="5e602-109">Whether the serializer needs to map the header</span></span>  
  
  <span data-ttu-id="5e602-110">スキーマを決定するには、シリアライザーは、次を行います。</span><span class="sxs-lookup"><span data-stu-id="5e602-110">To determine the schema, the serializer does the following:</span></span>  
  
- <span data-ttu-id="5e602-111">ターゲットの名前空間の設定 (**TargetNS**) 送信先のパーティ用に構成された名前空間と同じ値を</span><span class="sxs-lookup"><span data-stu-id="5e602-111">Sets the target namespace (**TargetNS**) to the same value as the namespace configured for the destination party</span></span>  
  
- <span data-ttu-id="5e602-112">抽出**Rootnode**から、 **BTS します。MessageType**プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="5e602-112">Extracts **Rootnode** from the **BTS.MessageType** promoted property</span></span>  
  
  <span data-ttu-id="5e602-113">**Doctype**なります**TargetNS「#」+ Rootnode**します。</span><span class="sxs-lookup"><span data-stu-id="5e602-113">The **doctype** becomes **TargetNS + "#" + Rootnode**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e602-114">参照</span><span class="sxs-lookup"><span data-stu-id="5e602-114">See Also</span></span>  
 <span data-ttu-id="5e602-115">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="5e602-115">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="5e602-116">BTAHL72X フラット ファイル処理</span><span class="sxs-lookup"><span data-stu-id="5e602-116">BTAHL72X Flat File Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)
---
title: HL7 の逆アセンブラーとアセンブラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, HL7
- disassembler, HL7
ms.assetid: 54e83a04-86c8-482f-bea3-dbbdeb4584d6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3762fedc26142bf91bef677255d1eaa7427ba2e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292989"
---
# <a name="hl7-disassembler-and-assembler"></a><span data-ttu-id="8cdbe-102">HL7 の逆アセンブラーとアセンブラー</span><span class="sxs-lookup"><span data-stu-id="8cdbe-102">HL7 Disassembler and Assembler</span></span>
<span data-ttu-id="8cdbe-103">HL7 の逆アセンブラーとアセンブラーは、HL7 でエンコードされたメッセージのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-103">The HL7 disassembler and assembler provide support for HL7-encoded messages.</span></span> <span data-ttu-id="8cdbe-104">Microsoft から[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML 形式では、Microsoft BizTalk Accelerator for HL7 のネイティブのメッセージを処理 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 の逆アセンブラーとアセンブラーを使用して、行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HL7 の統合エンジン。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-104">Since Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes messages natively in XML format, Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the HL7 disassembler and assembler to make [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] an HL7 integration engine.</span></span>  
  
## <a name="hl7-disassembler"></a><span data-ttu-id="8cdbe-105">HL7 の逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="8cdbe-105">HL7 Disassembler</span></span>  
 <span data-ttu-id="8cdbe-106">HL7 の逆アセンブラーでは、HL7 でエンコードされたメッセージの受信を処理のための XML セグメントに解析します。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-106">The HL7 disassembler parses incoming HL7-encoded messages into XML segments for processing.</span></span> <span data-ttu-id="8cdbe-107">検証メッセージのヘッダーと本文の基本的な検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-107">It performs validation of the message header, and basic validation of the body.</span></span> <span data-ttu-id="8cdbe-108">HL7 メッセージの解析に使用されるスキーマを決定します (を参照してください[、HL7 のスキーマ決定 2.X 逆アセンブラー](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md))、メッセージの送信元パーティの決定および本文の追加の検証を実行します (有効な場合、パーティ)。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-108">It determines the schema that it uses to parse the HL7 message (see [Schema Determination in the HL7 2.X Disassembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determines the source party for the message, and performs additional validation of the body (if enabled for the party).</span></span>  
  
## <a name="hl7-assembler"></a><span data-ttu-id="8cdbe-109">HL7 アセンブラー</span><span class="sxs-lookup"><span data-stu-id="8cdbe-109">HL7 Assembler</span></span>  
 <span data-ttu-id="8cdbe-110">HL7 アセンブラーは、XML のセグメントを送信 HL7 メッセージにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-110">The HL7 assembler serializes XML segments into an outgoing HL7 message.</span></span> <span data-ttu-id="8cdbe-111">HL7 メッセージをシリアル化するために使用するスキーマを決定します (を参照してください[、HL7 のスキーマ決定 2.X アセンブラー](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md))、メッセージの送信先パーティを決定および (パーティの有効な) 場合は、本文の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-111">It determines the schema that it uses to serialize the HL7 message (see [Schema Determination in the HL7 2.X Assembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determines the destination party for the message, and performs validation of the body (if enabled for the party).</span></span>  
  
 <span data-ttu-id="8cdbe-112">アセンブラーは、次の確認 (ACK) メッセージをシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-112">The assembler can serialize the following acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="8cdbe-113">スタティック</span><span class="sxs-lookup"><span data-stu-id="8cdbe-113">Static</span></span>  
  
- <span data-ttu-id="8cdbe-114">元のモード</span><span class="sxs-lookup"><span data-stu-id="8cdbe-114">Original mode</span></span>  
  
- <span data-ttu-id="8cdbe-115">拡張モード</span><span class="sxs-lookup"><span data-stu-id="8cdbe-115">Enhanced mode</span></span>  
  
  <span data-ttu-id="8cdbe-116">HL7 アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。</span><span class="sxs-lookup"><span data-stu-id="8cdbe-116">The HL7 assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cdbe-117">参照</span><span class="sxs-lookup"><span data-stu-id="8cdbe-117">See Also</span></span>  
 <span data-ttu-id="8cdbe-118">[BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span><span class="sxs-lookup"><span data-stu-id="8cdbe-118">[BTAHL72X Flat File Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span></span>  
 [<span data-ttu-id="8cdbe-119">BizTalk Accelerator for HL7 コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8cdbe-119">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
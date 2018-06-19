---
title: HL7 逆アセンブラおよびアセンブラ |Microsoft ドキュメント
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
ms.openlocfilehash: e81d621656fc678196f7f6fb709b29de87a3aaf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204930"
---
# <a name="hl7-disassembler-and-assembler"></a><span data-ttu-id="53350-102">HL7 逆アセンブラおよびアセンブラ</span><span class="sxs-lookup"><span data-stu-id="53350-102">HL7 Disassembler and Assembler</span></span>
<span data-ttu-id="53350-103">HL7 逆アセンブラおよびアセンブラは、HL7 でエンコードされたメッセージのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="53350-103">The HL7 disassembler and assembler provide support for HL7-encoded messages.</span></span> <span data-ttu-id="53350-104">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] XML 形式でネイティブのメッセージを処理[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 逆アセンブラおよびアセンブラを使用して行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HL7 統合エンジンです。</span><span class="sxs-lookup"><span data-stu-id="53350-104">Since [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes messages natively in XML format, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses the HL7 disassembler and assembler to make [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] an HL7 integration engine.</span></span>  
  
## <a name="hl7-disassembler"></a><span data-ttu-id="53350-105">HL7 の逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="53350-105">HL7 Disassembler</span></span>  
 <span data-ttu-id="53350-106">HL7 逆アセンブラーは、処理のための XML セグメントに着信 HL7 でエンコードされたメッセージを解析します。</span><span class="sxs-lookup"><span data-stu-id="53350-106">The HL7 disassembler parses incoming HL7-encoded messages into XML segments for processing.</span></span> <span data-ttu-id="53350-107">これは、検証メッセージのヘッダーと本文の基本的な検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="53350-107">It performs validation of the message header, and basic validation of the body.</span></span> <span data-ttu-id="53350-108">HL7 メッセージの解析に使用されるスキーマを決定 (を参照してください[で、HL7 スキーマの決定 2.X 逆アセンブラー](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md))、メッセージの送信元パーティの決定、および本文の追加の検証を実行します (有効な場合、パーティ) です。</span><span class="sxs-lookup"><span data-stu-id="53350-108">It determines the schema that it uses to parse the HL7 message (see [Schema Determination in the HL7 2.X Disassembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)), determines the source party for the message, and performs additional validation of the body (if enabled for the party).</span></span>  
  
## <a name="hl7-assembler"></a><span data-ttu-id="53350-109">HL7 アセンブラー</span><span class="sxs-lookup"><span data-stu-id="53350-109">HL7 Assembler</span></span>  
 <span data-ttu-id="53350-110">HL7 アセンブラーは、送信 HL7 メッセージに XML セグメントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="53350-110">The HL7 assembler serializes XML segments into an outgoing HL7 message.</span></span> <span data-ttu-id="53350-111">HL7 メッセージをシリアル化に使用されるスキーマを決定 (を参照してください[で、HL7 スキーマの決定 2.X アセンブラー](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md))、メッセージの送信先パーティの決定、および (有効な場合、パーティの)、本文の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="53350-111">It determines the schema that it uses to serialize the HL7 message (see [Schema Determination in the HL7 2.X Assembler](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)), determines the destination party for the message, and performs validation of the body (if enabled for the party).</span></span>  
  
 <span data-ttu-id="53350-112">アセンブラーは、次の確認 (ACK) メッセージをシリアル化できます。</span><span class="sxs-lookup"><span data-stu-id="53350-112">The assembler can serialize the following acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="53350-113">静的</span><span class="sxs-lookup"><span data-stu-id="53350-113">Static</span></span>  
  
-   <span data-ttu-id="53350-114">元のモード</span><span class="sxs-lookup"><span data-stu-id="53350-114">Original mode</span></span>  
  
-   <span data-ttu-id="53350-115">強化されたモード</span><span class="sxs-lookup"><span data-stu-id="53350-115">Enhanced mode</span></span>  
  
 <span data-ttu-id="53350-116">HL7 アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。</span><span class="sxs-lookup"><span data-stu-id="53350-116">The HL7 assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53350-117">参照</span><span class="sxs-lookup"><span data-stu-id="53350-117">See Also</span></span>  
 <span data-ttu-id="53350-118">[BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span><span class="sxs-lookup"><span data-stu-id="53350-118">[BTAHL72X Flat File Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md) </span></span>  
 [<span data-ttu-id="53350-119">BizTalk Accelerator for HL7 コンポーネント</span><span class="sxs-lookup"><span data-stu-id="53350-119">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
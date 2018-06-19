---
title: XML 逆アセンブラーまたはアセンブラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4978484f888290377986ee4ae8bf049c14a1b31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206650"
---
# <a name="xml-disassembler-and-assembler"></a><span data-ttu-id="14edd-102">XML 逆アセンブラーまたはアセンブラー</span><span class="sxs-lookup"><span data-stu-id="14edd-102">XML Disassembler and Assembler</span></span>
<span data-ttu-id="14edd-103">XML 逆アセンブラーまたはアセンブラーいることを確認[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) だけでなく、HL7 でエンコードされたメッセージをサポートしますも XML メッセージの受信/送信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="14edd-103">The XML disassembler and assembler ensure that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) not only supports HL7-encoded messages, but also supports incoming and/or outgoing XML messages.</span></span>  
  
## <a name="xml-disassembler"></a><span data-ttu-id="14edd-104">XML 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="14edd-104">XML Disassembler</span></span>  
 <span data-ttu-id="14edd-105">XML 逆アセンブラーは、受信 XML メッセージを処理するための XML セグメントに解析します。</span><span class="sxs-lookup"><span data-stu-id="14edd-105">The XML disassembler parses incoming XML messages into XML segments for processing.</span></span> <span data-ttu-id="14edd-106">メッセージを解析する際、逆アセンブラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="14edd-106">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
-   <span data-ttu-id="14edd-107">ハンドルのエスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="14edd-107">Handles escape sequences</span></span>  
  
-   <span data-ttu-id="14edd-108">必須/オプションのプロパティのチェックを処理します。</span><span class="sxs-lookup"><span data-stu-id="14edd-108">Handles checks of required/optional properties</span></span>  
  
-   <span data-ttu-id="14edd-109">ハンドル宣言 Z セグメント</span><span class="sxs-lookup"><span data-stu-id="14edd-109">Handles declared Z segments</span></span>  
  
 <span data-ttu-id="14edd-110">メッセージを解析する際、逆アセンブラーは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="14edd-110">As it parses the messages, the dissassembler performs the following:</span></span>  
  
-   <span data-ttu-id="14edd-111">構文検証</span><span class="sxs-lookup"><span data-stu-id="14edd-111">Syntactic validation</span></span>  
  
-   <span data-ttu-id="14edd-112">スキーマの検証 (有効な場合)</span><span class="sxs-lookup"><span data-stu-id="14edd-112">Schema validation (if enabled)</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="14edd-113">XML アセンブラー</span><span class="sxs-lookup"><span data-stu-id="14edd-113">XML Assembler</span></span>  
 <span data-ttu-id="14edd-114">XML アセンブラーは、送信 XML メッセージに XML セグメントをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="14edd-114">The XML assembler serializes XML segments into an outgoing XML message.</span></span> <span data-ttu-id="14edd-115">XML アセンブラーは、サポートしており、次の受信確認 (ACK) メッセージの作成します。</span><span class="sxs-lookup"><span data-stu-id="14edd-115">The XML assembler supports and creates the following acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="14edd-116">静的</span><span class="sxs-lookup"><span data-stu-id="14edd-116">Static</span></span>  
  
-   <span data-ttu-id="14edd-117">元のモード</span><span class="sxs-lookup"><span data-stu-id="14edd-117">Original mode</span></span>  
  
-   <span data-ttu-id="14edd-118">強化されたモード</span><span class="sxs-lookup"><span data-stu-id="14edd-118">Enhanced mode</span></span>  
  
 <span data-ttu-id="14edd-119">XML アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。</span><span class="sxs-lookup"><span data-stu-id="14edd-119">The XML assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14edd-120">参照</span><span class="sxs-lookup"><span data-stu-id="14edd-120">See Also</span></span>  
 <span data-ttu-id="14edd-121">[BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span><span class="sxs-lookup"><span data-stu-id="14edd-121">[BTAHL72XML Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span></span>  
 [<span data-ttu-id="14edd-122">BizTalk Accelerator for HL7 コンポーネント</span><span class="sxs-lookup"><span data-stu-id="14edd-122">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
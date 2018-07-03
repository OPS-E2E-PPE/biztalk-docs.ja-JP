---
title: XML 逆アセンブラーとアセンブラー |Microsoft Docs
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
ms.openlocfilehash: 3d8dfaf91d9b0d3d058c4d3e31cd67c652235eff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983043"
---
# <a name="xml-disassembler-and-assembler"></a><span data-ttu-id="bbef4-102">XML 逆アセンブラーとアセンブラー</span><span class="sxs-lookup"><span data-stu-id="bbef4-102">XML Disassembler and Assembler</span></span>
<span data-ttu-id="bbef4-103">XML 逆アセンブラーとアセンブラーことを確認します。 Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) だけでなく、HL7 でエンコードされたメッセージをサポートしますが、受信/送信 XML メッセージをもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bbef4-103">The XML disassembler and assembler ensure that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) not only supports HL7-encoded messages, but also supports incoming and/or outgoing XML messages.</span></span>  
  
## <a name="xml-disassembler"></a><span data-ttu-id="bbef4-104">XML 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="bbef4-104">XML Disassembler</span></span>  
 <span data-ttu-id="bbef4-105">XML 逆アセンブラーでは、受信 XML メッセージを処理するための XML セグメントに解析します。</span><span class="sxs-lookup"><span data-stu-id="bbef4-105">The XML disassembler parses incoming XML messages into XML segments for processing.</span></span> <span data-ttu-id="bbef4-106">メッセージを解析する際、逆アセンブラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbef4-106">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
- <span data-ttu-id="bbef4-107">ハンドルのエスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="bbef4-107">Handles escape sequences</span></span>  
  
- <span data-ttu-id="bbef4-108">必須/任意のプロパティのチェックを処理します。</span><span class="sxs-lookup"><span data-stu-id="bbef4-108">Handles checks of required/optional properties</span></span>  
  
- <span data-ttu-id="bbef4-109">ハンドルの Z セグメントの宣言</span><span class="sxs-lookup"><span data-stu-id="bbef4-109">Handles declared Z segments</span></span>  
  
  <span data-ttu-id="bbef4-110">メッセージを解析する際、逆アセンブラーは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbef4-110">As it parses the messages, the dissassembler performs the following:</span></span>  
  
- <span data-ttu-id="bbef4-111">構文の検証</span><span class="sxs-lookup"><span data-stu-id="bbef4-111">Syntactic validation</span></span>  
  
- <span data-ttu-id="bbef4-112">スキーマの検証 (有効な場合)</span><span class="sxs-lookup"><span data-stu-id="bbef4-112">Schema validation (if enabled)</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="bbef4-113">XML アセンブラー</span><span class="sxs-lookup"><span data-stu-id="bbef4-113">XML Assembler</span></span>  
 <span data-ttu-id="bbef4-114">XML アセンブラーは、XML のセグメントを送信 XML メッセージにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="bbef4-114">The XML assembler serializes XML segments into an outgoing XML message.</span></span> <span data-ttu-id="bbef4-115">XML アセンブラーは、サポートおよび次の受信確認 (ACK) メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbef4-115">The XML assembler supports and creates the following acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="bbef4-116">静的</span><span class="sxs-lookup"><span data-stu-id="bbef4-116">Static</span></span>  
  
- <span data-ttu-id="bbef4-117">元のモード</span><span class="sxs-lookup"><span data-stu-id="bbef4-117">Original mode</span></span>  
  
- <span data-ttu-id="bbef4-118">拡張モード</span><span class="sxs-lookup"><span data-stu-id="bbef4-118">Enhanced mode</span></span>  
  
  <span data-ttu-id="bbef4-119">XML アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。</span><span class="sxs-lookup"><span data-stu-id="bbef4-119">The XML assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbef4-120">参照</span><span class="sxs-lookup"><span data-stu-id="bbef4-120">See Also</span></span>  
 <span data-ttu-id="bbef4-121">[BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span><span class="sxs-lookup"><span data-stu-id="bbef4-121">[BTAHL72XML Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span></span>  
 [<span data-ttu-id="bbef4-122">BizTalk Accelerator for HL7 コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bbef4-122">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
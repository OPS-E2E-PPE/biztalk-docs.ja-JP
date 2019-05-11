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
ms.openlocfilehash: ccf8b71b08c35e94f710af12562060d477bf4abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285144"
---
# <a name="xml-disassembler-and-assembler"></a><span data-ttu-id="dd4c3-102">XML 逆アセンブラーとアセンブラー</span><span class="sxs-lookup"><span data-stu-id="dd4c3-102">XML Disassembler and Assembler</span></span>
<span data-ttu-id="dd4c3-103">XML 逆アセンブラーとアセンブラーことを確認します。 Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) だけでなく、HL7 でエンコードされたメッセージをサポートしますが、受信/送信 XML メッセージをもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dd4c3-103">The XML disassembler and assembler ensure that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) not only supports HL7-encoded messages, but also supports incoming and/or outgoing XML messages.</span></span>  
  
## <a name="xml-disassembler"></a><span data-ttu-id="dd4c3-104">XML 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="dd4c3-104">XML Disassembler</span></span>  
 <span data-ttu-id="dd4c3-105">XML 逆アセンブラーでは、受信 XML メッセージを処理するための XML セグメントに解析します。</span><span class="sxs-lookup"><span data-stu-id="dd4c3-105">The XML disassembler parses incoming XML messages into XML segments for processing.</span></span> <span data-ttu-id="dd4c3-106">メッセージを解析する際、逆アセンブラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd4c3-106">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
- <span data-ttu-id="dd4c3-107">ハンドルのエスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="dd4c3-107">Handles escape sequences</span></span>  
  
- <span data-ttu-id="dd4c3-108">必須/任意のプロパティのチェックを処理します。</span><span class="sxs-lookup"><span data-stu-id="dd4c3-108">Handles checks of required/optional properties</span></span>  
  
- <span data-ttu-id="dd4c3-109">ハンドルの Z セグメントの宣言</span><span class="sxs-lookup"><span data-stu-id="dd4c3-109">Handles declared Z segments</span></span>  
  
  <span data-ttu-id="dd4c3-110">メッセージを解析する際、逆アセンブラーは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="dd4c3-110">As it parses the messages, the dissassembler performs the following:</span></span>  
  
- <span data-ttu-id="dd4c3-111">構文の検証</span><span class="sxs-lookup"><span data-stu-id="dd4c3-111">Syntactic validation</span></span>  
  
- <span data-ttu-id="dd4c3-112">スキーマの検証 (有効な場合)</span><span class="sxs-lookup"><span data-stu-id="dd4c3-112">Schema validation (if enabled)</span></span>  
  
## <a name="xml-assembler"></a><span data-ttu-id="dd4c3-113">XML アセンブラー</span><span class="sxs-lookup"><span data-stu-id="dd4c3-113">XML Assembler</span></span>  
 <span data-ttu-id="dd4c3-114">XML アセンブラーは、XML のセグメントを送信 XML メッセージにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="dd4c3-114">The XML assembler serializes XML segments into an outgoing XML message.</span></span> <span data-ttu-id="dd4c3-115">XML アセンブラーは、サポートおよび次の受信確認 (ACK) メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd4c3-115">The XML assembler supports and creates the following acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="dd4c3-116">スタティック</span><span class="sxs-lookup"><span data-stu-id="dd4c3-116">Static</span></span>  
  
- <span data-ttu-id="dd4c3-117">元のモード</span><span class="sxs-lookup"><span data-stu-id="dd4c3-117">Original mode</span></span>  
  
- <span data-ttu-id="dd4c3-118">拡張モード</span><span class="sxs-lookup"><span data-stu-id="dd4c3-118">Enhanced mode</span></span>  
  
  <span data-ttu-id="dd4c3-119">XML アセンブラーでは、遅延の ACK メッセージをルーティングする機能もあります。</span><span class="sxs-lookup"><span data-stu-id="dd4c3-119">The XML assembler also has the ability to route deferred ACK messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd4c3-120">参照</span><span class="sxs-lookup"><span data-stu-id="dd4c3-120">See Also</span></span>  
 <span data-ttu-id="dd4c3-121">[BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span><span class="sxs-lookup"><span data-stu-id="dd4c3-121">[BTAHL72XML Processing](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md) </span></span>  
 [<span data-ttu-id="dd4c3-122">BizTalk Accelerator for HL7 コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dd4c3-122">BizTalk Accelerator for HL7 Components</span></span>](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)
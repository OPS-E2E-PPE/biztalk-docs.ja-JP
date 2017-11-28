---
title: "XML 情報は、XML 逆アセンブラー パイプライン コンポーネントで要素を設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], information set
- XML Disassembler [pipeline component], processing instructions
- pipeline components, XML Disassembler
ms.assetid: cc82344c-6c4b-4154-a662-0b7ae5caad30
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90b3140cbe23637160aafabdccb37104efd1d318
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="6b805-102">XML 情報は、XML 逆アセンブラー パイプライン コンポーネントで要素を設定</span><span class="sxs-lookup"><span data-stu-id="6b805-102">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="6b805-103">XML 逆アセンブラーでは、各種の XML 要素が次のように扱われます。</span><span class="sxs-lookup"><span data-stu-id="6b805-103">The XML Disassembler handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="6b805-104">要素</span><span class="sxs-lookup"><span data-stu-id="6b805-104">Element</span></span>|<span data-ttu-id="6b805-105">Description</span><span class="sxs-lookup"><span data-stu-id="6b805-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b805-106">comment</span><span class="sxs-lookup"><span data-stu-id="6b805-106">comment</span></span>|<span data-ttu-id="6b805-107">コメントはドキュメント内に保存されますが、XML エンべロープ内のコメントは保存されません。</span><span class="sxs-lookup"><span data-stu-id="6b805-107">Comments are preserved in the document; however, any comments in XML envelopes are not preserved.</span></span>|  
|<span data-ttu-id="6b805-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="6b805-108">CDATA</span></span>|<span data-ttu-id="6b805-109">CDATA はドキュメント内に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6b805-109">CDATA is preserved in the document.</span></span> <span data-ttu-id="6b805-110">ドキュメント外部 (エンベロープ内など) に現れる CDATA 要素は保存されません。</span><span class="sxs-lookup"><span data-stu-id="6b805-110">CDATA elements appearing outside of a document (for example, in an envelope) are not preserved.</span></span>|  
|<span data-ttu-id="6b805-111">処理命令</span><span class="sxs-lookup"><span data-stu-id="6b805-111">processing instructions</span></span>|<span data-ttu-id="6b805-112">XML 逆アセンブラーは、XML ドキュメント内または XML ドキュメントの前にある処理命令を保存します。</span><span class="sxs-lookup"><span data-stu-id="6b805-112">The XML Disassembler preserves processing instructions appearing in or before an XML document.</span></span> <span data-ttu-id="6b805-113">XML ドキュメントの後、あるいはエンベロープの前または後にある処理命令は、保存されません。</span><span class="sxs-lookup"><span data-stu-id="6b805-113">Processing instructions appearing after an XML document or before or after an envelope are not preserved.</span></span>|  
|<span data-ttu-id="6b805-114">XML 宣言</span><span class="sxs-lookup"><span data-stu-id="6b805-114">XML declaration</span></span>|<span data-ttu-id="6b805-115">受信 XML メッセージの XML 宣言要素はすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b805-115">The XML declaration element of any incoming XML message is removed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b805-116">参照</span><span class="sxs-lookup"><span data-stu-id="6b805-116">See Also</span></span>  
 <span data-ttu-id="6b805-117">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="6b805-117">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="6b805-118">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6b805-118">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
---
title: XML 情報は、XML 逆アセンブラー パイプライン コンポーネントで要素を設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], information set
- XML Disassembler [pipeline component], processing instructions
- pipeline components, XML Disassembler
ms.assetid: cc82344c-6c4b-4154-a662-0b7ae5caad30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b9d2b581a327f8d7009794338d431a2358db748
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298484"
---
# <a name="xml-information-set-elements-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="94223-102">XML 情報は、XML 逆アセンブラー パイプライン コンポーネントで要素を設定</span><span class="sxs-lookup"><span data-stu-id="94223-102">XML Information Set Elements in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="94223-103">XML 逆アセンブラーは、次のように XML 情報セットの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="94223-103">The XML Disassembler handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="94223-104">要素</span><span class="sxs-lookup"><span data-stu-id="94223-104">Element</span></span>|<span data-ttu-id="94223-105">説明</span><span class="sxs-lookup"><span data-stu-id="94223-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94223-106">comment</span><span class="sxs-lookup"><span data-stu-id="94223-106">comment</span></span>|<span data-ttu-id="94223-107">コメントはドキュメントに保存されます。ただし、XML エンベロープ内のコメントは保持されません。</span><span class="sxs-lookup"><span data-stu-id="94223-107">Comments are preserved in the document; however, any comments in XML envelopes are not preserved.</span></span>|  
|<span data-ttu-id="94223-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="94223-108">CDATA</span></span>|<span data-ttu-id="94223-109">CDATA はドキュメントに保持されます。</span><span class="sxs-lookup"><span data-stu-id="94223-109">CDATA is preserved in the document.</span></span> <span data-ttu-id="94223-110">(たとえば、エンベロープ) 内のドキュメントの外部に現れる CDATA 要素は保持されません。</span><span class="sxs-lookup"><span data-stu-id="94223-110">CDATA elements appearing outside of a document (for example, in an envelope) are not preserved.</span></span>|  
|<span data-ttu-id="94223-111">処理命令</span><span class="sxs-lookup"><span data-stu-id="94223-111">processing instructions</span></span>|<span data-ttu-id="94223-112">XML 逆アセンブラーでは、XML ドキュメントの以前のある処理命令が保持されます。</span><span class="sxs-lookup"><span data-stu-id="94223-112">The XML Disassembler preserves processing instructions appearing in or before an XML document.</span></span> <span data-ttu-id="94223-113">XML ドキュメントの後または前に、またはエンベロープの後にある処理命令は保持されません。</span><span class="sxs-lookup"><span data-stu-id="94223-113">Processing instructions appearing after an XML document or before or after an envelope are not preserved.</span></span>|  
|<span data-ttu-id="94223-114">XML 宣言</span><span class="sxs-lookup"><span data-stu-id="94223-114">XML declaration</span></span>|<span data-ttu-id="94223-115">受信 XML メッセージの XML 宣言の要素が削除されます。</span><span class="sxs-lookup"><span data-stu-id="94223-115">The XML declaration element of any incoming XML message is removed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94223-116">参照</span><span class="sxs-lookup"><span data-stu-id="94223-116">See Also</span></span>  
 <span data-ttu-id="94223-117">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="94223-117">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="94223-118">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="94223-118">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
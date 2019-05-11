---
title: 構造の強化、XML 逆アセンブラー パイプライン コンポーネントでのドキュメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], document structure
- pipeline components, XML Disassembler
ms.assetid: ac405bf2-f92b-4b45-8256-dd188ec9510a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7e4c7d2d99874684d80c7c413040d7da8ecf0b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350911"
---
# <a name="document-structure-enforcement-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="34eea-102">XML 逆アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="34eea-102">Document Structure Enforcement in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="34eea-103">ドキュメントまたはエンベロープ スキーマは、XML 逆アセンブラーで明示的に参照が、XML 逆アセンブラーは、スキーマに準拠したメッセージ型を持つドキュメントだけを処理します。</span><span class="sxs-lookup"><span data-stu-id="34eea-103">If a document or envelope schema is explicitly referenced in the XML Disassembler, the XML Disassembler processes only those documents with message types conforming to the schema.</span></span> <span data-ttu-id="34eea-104">その他のドキュメントは処理されません、それらの展開されたスキーマを参照するかどうかに関係なく。</span><span class="sxs-lookup"><span data-stu-id="34eea-104">No other documents are processed, regardless of whether a deployed schema is referenced for them.</span></span>  
  
 <span data-ttu-id="34eea-105">XML 逆アセンブラーのエンベロープ スキーマ; の指定した順序を強制します。ただし、ドキュメント スキーマの順序は強制されません。</span><span class="sxs-lookup"><span data-stu-id="34eea-105">The XML Disassembler enforces the specified order of envelope schemas; however, the order of document schemas is not enforced.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34eea-106">参照</span><span class="sxs-lookup"><span data-stu-id="34eea-106">See Also</span></span>  
 <span data-ttu-id="34eea-107">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="34eea-107">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="34eea-108">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="34eea-108">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
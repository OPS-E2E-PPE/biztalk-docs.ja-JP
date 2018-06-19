---
title: XML 逆アセンブラー パイプライン コンポーネントで検証を文書化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], document validation
- XML Disassembler [pipeline component], warnings
ms.assetid: feb25033-46d3-48ed-8e1f-0cd123e94149
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2dcea790208bf0234c67c8c941e6355fb367d82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239386"
---
# <a name="document-validation-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="9207a-102">XML 逆アセンブラー パイプライン コンポーネントにおけるドキュメントの検証</span><span class="sxs-lookup"><span data-stu-id="9207a-102">Document Validation in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="9207a-103">既定で、XML 逆アセンブラーは、スキーマに対する XML ドキュメントを検証しません。</span><span class="sxs-lookup"><span data-stu-id="9207a-103">By default, the XML Disassembler does not validate XML documents against a schema.</span></span> <span data-ttu-id="9207a-104">ただし、設定して XML ドキュメントを検証する XML 逆アセンブラーを構成することができます、**ドキュメント構造の検証**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="9207a-104">However, you can configure the XML Disassembler to validate an XML document by setting the **Validate Document Structure** property.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9207a-105">昇格するフィールドを簡単なデータ型で宣言している一方で複雑なデータを含む場合、プロパティの昇格で予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9207a-105">If a field for promotion is declared with a simple data type but contains complex data, the property promotion will cause unpredictable results.</span></span> <span data-ttu-id="9207a-106">このシナリオを避けるためには、構成設定によってドキュメントの検証を実行する、XML 逆アセンブラー、**ドキュメント構造の検証**プロパティを**True**です。</span><span class="sxs-lookup"><span data-stu-id="9207a-106">To avoid this scenario, configure the XML Disassembler to perform document validation by setting the **Validate Document Structure** property to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9207a-107">参照</span><span class="sxs-lookup"><span data-stu-id="9207a-107">See Also</span></span>  
 <span data-ttu-id="9207a-108">[XML 逆アセンブラー パイプライン コンポーネント](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9207a-108">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="9207a-109">XML 逆アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="9207a-109">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)
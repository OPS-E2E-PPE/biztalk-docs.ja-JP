---
title: "XML アセンブラー パイプライン コンポーネントにおける構造の強化を文書化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46dbc613439b24403c66c345b9023151b409213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="e77ff-102">XML アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="e77ff-102">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="e77ff-103">XML アセンブラーでドキュメントまたはエンベロープ スキーマが明示的に参照されている場合、参照されたスキーマに対応するメッセージ タイプのドキュメントだけが処理されます。</span><span class="sxs-lookup"><span data-stu-id="e77ff-103">If document or envelope schemas are explicitly referenced in the XML Assembler, the XML Assembler ensures that only documents with the message type corresponding to referenced schemas are processed.</span></span> <span data-ttu-id="e77ff-104">その他すべてのドキュメントは、該当するスキーマが配置されていたとしても、処理から除外されます。</span><span class="sxs-lookup"><span data-stu-id="e77ff-104">All the other documents are not processed even though a schema may be deployed for them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e77ff-105">エンベロープ スキーマは最初のメッセージからのみ取得されます。</span><span class="sxs-lookup"><span data-stu-id="e77ff-105">The envelope schema is taken from the first message only.</span></span> <span data-ttu-id="e77ff-106">エンベロープのプロパティは常に最初のメッセージから取得されます。</span><span class="sxs-lookup"><span data-stu-id="e77ff-106">The properties for the envelope are always taken from the first message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77ff-107">参照</span><span class="sxs-lookup"><span data-stu-id="e77ff-107">See Also</span></span>  
 <span data-ttu-id="e77ff-108">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="e77ff-108">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="e77ff-109">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="e77ff-109">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="e77ff-110">パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="e77ff-110">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)
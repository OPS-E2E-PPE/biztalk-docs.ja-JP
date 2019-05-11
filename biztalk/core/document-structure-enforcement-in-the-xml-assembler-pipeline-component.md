---
title: 構造の強化、XML アセンブラー パイプライン コンポーネントでのドキュメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ef167df5aaef827e11d33fc73191d46b68afb2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389524"
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="1fa18-102">XML アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="1fa18-102">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="1fa18-103">XML アセンブラーでドキュメントまたはエンベロープ スキーマが明示的に参照を場合、XML アセンブラーは、参照されたスキーマに対応するメッセージの種類のドキュメントだけを処理することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fa18-103">If document or envelope schemas are explicitly referenced in the XML Assembler, the XML Assembler ensures that only documents with the message type corresponding to referenced schemas are processed.</span></span> <span data-ttu-id="1fa18-104">その他すべてのドキュメントは、該当するスキーマが配置されていたとしても、処理から除外されます。</span><span class="sxs-lookup"><span data-stu-id="1fa18-104">All the other documents are not processed even though a schema may be deployed for them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1fa18-105">エンベロープ スキーマは最初のメッセージからのみ取得されます。</span><span class="sxs-lookup"><span data-stu-id="1fa18-105">The envelope schema is taken from the first message only.</span></span> <span data-ttu-id="1fa18-106">エンベロープのプロパティは常に最初のメッセージから取得されます。</span><span class="sxs-lookup"><span data-stu-id="1fa18-106">The properties for the envelope are always taken from the first message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa18-107">参照</span><span class="sxs-lookup"><span data-stu-id="1fa18-107">See Also</span></span>  
 <span data-ttu-id="1fa18-108">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="1fa18-108">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="1fa18-109">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="1fa18-109">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="1fa18-110">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="1fa18-110">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)
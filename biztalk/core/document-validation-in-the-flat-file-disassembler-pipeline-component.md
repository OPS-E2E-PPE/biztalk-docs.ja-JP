---
title: ドキュメントのフラット ファイル逆アセンブラー パイプライン コンポーネントの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- FFDasm.ValidateDocumentStructure property
- Flat File Disassembler [pipeline component], validating documents
- pipeline components, Flat File Disassembler
ms.assetid: 8cd777e4-8aba-4c17-92e8-958e5dd57d09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43802cde810d9803daa80ee8c070aecd8023eb57
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530812"
---
# <a name="document-validation-in-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="65c65-102">フラット ファイル逆アセンブラー パイプライン コンポーネントにおけるドキュメントの検証</span><span class="sxs-lookup"><span data-stu-id="65c65-102">Document Validation in the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="65c65-103">既定では、フラット ファイル逆アセンブラー コンポーネントは、ドキュメントの処理を検証しません。</span><span class="sxs-lookup"><span data-stu-id="65c65-103">By default, the Flat File Disassembler component does not validate documents it processes.</span></span> <span data-ttu-id="65c65-104">ただし、することが検証を有効に設定して、**ドキュメント構造の検証**にコンポーネントのプロパティを**True**、かを設定して、 **FFDasm.ValidateDocumentStructure**メッセージ コンテキスト プロパティを**True**します。</span><span class="sxs-lookup"><span data-stu-id="65c65-104">However, you can turn validation on by setting the **Validate document structure** property on the component to **True**, or by setting the **FFDasm.ValidateDocumentStructure** message context property to **True**.</span></span> <span data-ttu-id="65c65-105">ドキュメントの検証が実行に設定されている場合、フラット ファイル逆アセンブラーは、ドキュメントの構造とドキュメント、ヘッダー、およびトレーラーのスキーマに準拠していることを確認するヘッダーとトレーラー構造を検証します。</span><span class="sxs-lookup"><span data-stu-id="65c65-105">When document validation is set to run, the Flat File Disassembler validates the document structure as well as the header and trailer structures to ensure that they conform to the document, header, and trailer schemas.</span></span>  
  
 <span data-ttu-id="65c65-106">フラット ファイル逆アセンブラーが空のフィールドを削除することができ、ときに記録**suppress_empty_nodes ="True"** で指定された、 **schemaInfo**フラット ファイル XSD スキーマで注釈。</span><span class="sxs-lookup"><span data-stu-id="65c65-106">The Flat File Disassembler can remove empty fields and records when **suppress_empty_nodes="True"** is specified by the **schemaInfo** annotation in the flat file XSD schema.</span></span> <span data-ttu-id="65c65-107">使用する場合、 **schemaInfo**この方法で注釈は、空のフィールドとレコードは省略可能かどうかに関係なく、フラット ファイル逆アセンブラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="65c65-107">If you use the **schemaInfo** annotation in this way, the Flat File Disassembler removes empty fields and records regardless of whether they are optional.</span></span> <span data-ttu-id="65c65-108">XML 検証を使用する場合と検証エラーが発生 (フラット ファイル逆アセンブラーを設定するか**ドキュメント構造の検証**プロパティを**True**または XML 検証パイプライン コンポーネントを使用して).</span><span class="sxs-lookup"><span data-stu-id="65c65-108">This may cause validation errors if you use XML validation (either by setting the Flat File Disassembler **Validate document structure** property to **True** or by using the XML Validator pipeline component).</span></span> <span data-ttu-id="65c65-109">検証エラーが発生した場合、メッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="65c65-109">If a validation error occurs, the message is suspended.</span></span> <span data-ttu-id="65c65-110">Suppress_empty_nodes プロパティの詳細については、次を参照してください。[追加のフラット ファイル プロパティ](../core/additional-flat-file-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="65c65-110">For more information about the suppress_empty_nodes property, see [Additional Flat File Properties](../core/additional-flat-file-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c65-111">参照</span><span class="sxs-lookup"><span data-stu-id="65c65-111">See Also</span></span>  
 <span data-ttu-id="65c65-112">[フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="65c65-112">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="65c65-113">[フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="65c65-113">[How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="65c65-114">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="65c65-114">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)
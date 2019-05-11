---
title: フラット ファイル逆アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component]
- pipeline components, Flat File Disassembler
ms.assetid: 8d59f86e-ea16-4989-ada4-d24a51e3409a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f829960c2904dc429bc1092f9722b24a5997808
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387934"
---
# <a name="flat-file-disassembler-pipeline-component"></a><span data-ttu-id="7f0eb-102">フラット ファイル逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7f0eb-102">Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="7f0eb-103">フラット ファイル逆アセンブラー コンポーネントは、区切り文字および位置指定フラット ファイル形式のメッセージを解析し、XML 表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="7f0eb-103">The Flat File Disassembler component parses delimited and positional flat file format messages and converts them into an XML representation.</span></span> <span data-ttu-id="7f0eb-104">フラット ファイル逆アセンブラーは、フラット ファイル メッセージから、ヘッダーとトレーラー構造を削除し、個別のドキュメントに、メッセージ内のインターチェンジを中断します。</span><span class="sxs-lookup"><span data-stu-id="7f0eb-104">The Flat File Disassembler also removes the header and trailer structures from the flat file message, and breaks the interchange within the message into individual documents.</span></span> <span data-ttu-id="7f0eb-105">また、ドキュメントおよびヘッダーからプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="7f0eb-105">It also promotes properties from the documents and headers.</span></span>  
  
 <span data-ttu-id="7f0eb-106">フラット ファイルの詳細については、次を参照してください。[位置指定レコードのフラット ファイル メッセージ](../core/flat-file-messages-with-positional-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f0eb-106">For more information about flat files, see [Flat File Messages with Positional Records](../core/flat-file-messages-with-positional-records.md).</span></span> <span data-ttu-id="7f0eb-107">参照してください[で区切られたレコードのフラット ファイル メッセージ](../core/flat-file-messages-with-delimited-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f0eb-107">Also see [Flat File Messages with Delimited Records](../core/flat-file-messages-with-delimited-records.md).</span></span>  
  
 <span data-ttu-id="7f0eb-108">フラット ファイル逆アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。[フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f0eb-108">For information about configuring the Flat File Disassembler pipeline component, see [How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f0eb-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7f0eb-109">In This Section</span></span>  
  
-   [<span data-ttu-id="7f0eb-110">フラット ファイル逆アセンブラー パイプライン コンポーネントのドキュメント検証</span><span class="sxs-lookup"><span data-stu-id="7f0eb-110">Document Validation in the Flat File Disassembler Pipeline Component</span></span>](../core/document-validation-in-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="7f0eb-111">フラット ファイル逆アセンブラー パイプライン コンポーネントでの文字エンコード</span><span class="sxs-lookup"><span data-stu-id="7f0eb-111">Character Encoding in the Flat File Disassembler Pipeline Component</span></span>](../core/character-encoding-in-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="7f0eb-112">チュートリアル: ヘッダーとトレーラーを使用してフラット ファイル逆アセンブリ</span><span class="sxs-lookup"><span data-stu-id="7f0eb-112">Walkthrough: Flat File Disassembly Using a Header and Trailer</span></span>](../core/walkthrough-flat-file-disassembly-using-a-header-and-trailer.md)
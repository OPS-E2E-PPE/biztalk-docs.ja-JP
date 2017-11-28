---
title: "フラット ファイル逆アセンブラー パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component]
- pipeline components, Flat File Disassembler
ms.assetid: 8d59f86e-ea16-4989-ada4-d24a51e3409a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a05c8e72f98e8faa602b5d057c7d6b24dd9de83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-disassembler-pipeline-component"></a><span data-ttu-id="6b487-102">フラット ファイル逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6b487-102">Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="6b487-103">フラット ファイル逆アセンブラー コンポーネントは、区切られたフラット ファイルおよび位置指定のフラットファイルの形式のメッセージを解析し、XML 表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="6b487-103">The Flat File Disassembler component parses delimited and positional flat file format messages and converts them into an XML representation.</span></span> <span data-ttu-id="6b487-104">また、フラット ファイル逆アセンブラーは、フラット ファイル メッセージからヘッダー構造およびトレーラー構造を削除し、メッセージのインターチェンジを個別のドキュメントに分割します。</span><span class="sxs-lookup"><span data-stu-id="6b487-104">The Flat File Disassembler also removes the header and trailer structures from the flat file message, and breaks the interchange within the message into individual documents.</span></span> <span data-ttu-id="6b487-105">ドキュメントおよびヘッダーからのプロパティの昇格も行われます。</span><span class="sxs-lookup"><span data-stu-id="6b487-105">It also promotes properties from the documents and headers.</span></span>  
  
 <span data-ttu-id="6b487-106">フラット ファイルの詳細については、次を参照してください。[位置指定レコードのフラット ファイル メッセージ](../core/flat-file-messages-with-positional-records.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b487-106">For more information about flat files, see [Flat File Messages with Positional Records](../core/flat-file-messages-with-positional-records.md).</span></span> <span data-ttu-id="6b487-107">参照してください[区切り記号付きレコードとフラット ファイル メッセージ](../core/flat-file-messages-with-delimited-records.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b487-107">Also see [Flat File Messages with Delimited Records](../core/flat-file-messages-with-delimited-records.md).</span></span>  
  
 <span data-ttu-id="6b487-108">フラット ファイル逆アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [、フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b487-108">For information about configuring the Flat File Disassembler pipeline component, see [How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b487-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6b487-109">In This Section</span></span>  
  
-   [<span data-ttu-id="6b487-110">フラット ファイル逆アセンブラー パイプライン コンポーネントにおけるドキュメントの検証</span><span class="sxs-lookup"><span data-stu-id="6b487-110">Document Validation in the Flat File Disassembler Pipeline Component</span></span>](../core/document-validation-in-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="6b487-111">フラット ファイル逆アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="6b487-111">Character Encoding in the Flat File Disassembler Pipeline Component</span></span>](../core/character-encoding-in-the-flat-file-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="6b487-112">チュートリアル: フラット ファイル逆アセンブル ヘッダーおよびトレーラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b487-112">Walkthrough: Flat File Disassembly Using a Header and Trailer</span></span>](../core/walkthrough-flat-file-disassembly-using-a-header-and-trailer.md)
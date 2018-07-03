---
title: フラット ファイル逆アセンブラー パイプライン コンポーネントにおける文字エンコーディング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, Flat File Disassembler
- Flat File Disassembler [pipeline component], character encoding
ms.assetid: 0dbe24fb-c431-4edf-8aa9-4c040d6a7b32
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a7ef27ec23fb7470aff74df2915150f892e07a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988811"
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="27f45-102">フラット ファイル逆アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="27f45-102">Character Encoding in the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="27f45-103">フラット ファイル逆アセンブラーでは、次のアルゴリズムに基づいて、入力メッセージを処理するためのエンコードに使用する文字セットを決定します。</span><span class="sxs-lookup"><span data-stu-id="27f45-103">The following algorithm is used by the Flat File Disassembler component to determine which encoding to use for processing an incoming message:</span></span>  
  
1. <span data-ttu-id="27f45-104">バイト順マークがデータ内に存在する場合、これによってエンコード情報が決定されます。</span><span class="sxs-lookup"><span data-stu-id="27f45-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span> <span data-ttu-id="27f45-105">このエンコード情報は、逆アセンブラーでは保持されません (つまり、これは保存されません、 **XMLNorm.SourceCharset**プロパティ)。</span><span class="sxs-lookup"><span data-stu-id="27f45-105">This encoding information is not preserved by the disassembler (that is, it is not saved to the **XMLNorm.SourceCharset** property).</span></span>  
  
2. <span data-ttu-id="27f45-106">の場合、 **IBaseMessagePart.Charset**プロパティが設定されて、が指定されてエンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="27f45-106">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3. <span data-ttu-id="27f45-107">IBaseMessagePart.Charset プロパティも設定されていない場合、ヘッダーまたはドキュメント スキーマにコードページ情報が含まれていれば、これが使用されます。</span><span class="sxs-lookup"><span data-stu-id="27f45-107">Otherwise, if the header or document schema contains codepage information, it is used.</span></span>  
  
4. <span data-ttu-id="27f45-108">上記のいずれにも該当しない場合は、UTF-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="27f45-108">Otherwise, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="27f45-109">逆アセンブラーがでメッセージ コンテキストにエンコード情報を保存の前に、2、3、および 4 の場合、 **XMLNorm.SourceCharset**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="27f45-109">For the preceding cases 2, 3, and 4, the disassembler saves the encoding information on the message context in the **XMLNorm.SourceCharset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f45-110">参照</span><span class="sxs-lookup"><span data-stu-id="27f45-110">See Also</span></span>  
 <span data-ttu-id="27f45-111">[フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="27f45-111">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="27f45-112">[フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="27f45-112">[How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="27f45-113">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="27f45-113">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)
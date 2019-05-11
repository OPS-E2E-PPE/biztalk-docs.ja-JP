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
ms.openlocfilehash: 6949861ffa6197e6a0061a1a565bea3711e617d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357493"
---
# <a name="character-encoding-in-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="7fbee-102">フラット ファイル逆アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="7fbee-102">Character Encoding in the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="7fbee-103">次のアルゴリズムは、受信メッセージの処理に使用するエンコードを決定、フラット ファイル逆アセンブラー コンポーネントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fbee-103">The following algorithm is used by the Flat File Disassembler component to determine which encoding to use for processing an incoming message:</span></span>  
  
1. <span data-ttu-id="7fbee-104">データのバイト順マークが存在する場合、そこからはエンコード情報が判断されます。</span><span class="sxs-lookup"><span data-stu-id="7fbee-104">If a byte order mark exists in the data, encoding information is determined from it.</span></span> <span data-ttu-id="7fbee-105">このエンコード情報は、逆アセンブラーでは保持されません (つまり、これは保存されません、 **XMLNorm.SourceCharset**プロパティ)。</span><span class="sxs-lookup"><span data-stu-id="7fbee-105">This encoding information is not preserved by the disassembler (that is, it is not saved to the **XMLNorm.SourceCharset** property).</span></span>  
  
2. <span data-ttu-id="7fbee-106">の場合、 **IBaseMessagePart.Charset**プロパティが設定されて、が指定されてエンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fbee-106">Otherwise, if the **IBaseMessagePart.Charset** property is set, the encoding specified there is used.</span></span>  
  
3. <span data-ttu-id="7fbee-107">それ以外の場合、ヘッダーまたはドキュメント スキーマにコードページ情報が含まれる場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fbee-107">Otherwise, if the header or document schema contains codepage information, it is used.</span></span>  
  
4. <span data-ttu-id="7fbee-108">それ以外の場合、utf-8 エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fbee-108">Otherwise, UTF-8 encoding is used.</span></span>  
  
   <span data-ttu-id="7fbee-109">逆アセンブラーがでメッセージ コンテキストにエンコード情報を保存の前に、2、3、および 4 の場合、 **XMLNorm.SourceCharset**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7fbee-109">For the preceding cases 2, 3, and 4, the disassembler saves the encoding information on the message context in the **XMLNorm.SourceCharset** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fbee-110">参照</span><span class="sxs-lookup"><span data-stu-id="7fbee-110">See Also</span></span>  
 <span data-ttu-id="7fbee-111">[フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="7fbee-111">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="7fbee-112">[フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="7fbee-112">[How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="7fbee-113">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="7fbee-113">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)
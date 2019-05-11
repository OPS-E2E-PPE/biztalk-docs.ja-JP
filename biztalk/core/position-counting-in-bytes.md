---
title: 位置のカウント (バイト単位) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf666ec-d15e-4d2d-9df9-49189f352c65
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5801987517d66147a9c8110c945b8fdff84bc88b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396226"
---
# <a name="position-counting-in-bytes"></a><span data-ttu-id="0e384-102">位置のカウント (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="0e384-102">Position Counting in Bytes</span></span>

## <a name="overview"></a><span data-ttu-id="0e384-103">概要</span><span class="sxs-lookup"><span data-stu-id="0e384-103">Overview</span></span>

<span data-ttu-id="0e384-104">使用することができます、**カウント位置 (バイト単位)** のプロパティ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="0e384-104">You can use the **Count Positions In Bytes** property of the **Schema** node to:</span></span> 

* <span data-ttu-id="0e384-105">値の入力方法の指定、**位置指定値**と**位置指定オフセット**位置指定レコード内のさまざまなフィールドのプロパティが解釈されます</span><span class="sxs-lookup"><span data-stu-id="0e384-105">Specify how the values you enter for the **Positional Length** and **Positional Offset** properties of the various fields within positional records are interpreted</span></span>
* <span data-ttu-id="0e384-106">値の入力方法の指定、**タグ オフセット**位置指定レコード自体のプロパティが解釈されます</span><span class="sxs-lookup"><span data-stu-id="0e384-106">Specify how the values you enter for the **Tag Offset** property of the positional records themselves are interpreted</span></span>

<span data-ttu-id="0e384-107">既定では、これらの値が文字数として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="0e384-107">By default, these values are interpreted as a number of characters.</span></span> <span data-ttu-id="0e384-108">しかし、**カウント位置 (バイト単位)** プロパティに設定されて**True**、これらの値はバイト数として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="0e384-108">But when the **Count Positions In Bytes** property is set to **True**, these values are interpreted as a number of bytes.</span></span>  
  
 <span data-ttu-id="0e384-109">設定、**カウント位置 (バイト単位)** プロパティを**True**がマルチバイト文字を扱うときに必要な設定 (MBCS や DBCS) データ、または、SAP、メインフレームで、フラット ファイル メッセージが生成されるときに、または位置のバイト単位でカウントされる可能性が他のシステムです。</span><span class="sxs-lookup"><span data-stu-id="0e384-109">Setting the **Count Positions In Bytes** property to **True** might be necessary when dealing with multibyte character set (MBCS or DBCS) data, or when your flat file messages originate in SAP, mainframes, or other systems that may count positions in bytes.</span></span>  
  
 <span data-ttu-id="0e384-110">フィールドの長さ (バイト単位) をカウントする複雑な文字をエンコードするために使用バイト数が変数、および、フィールド境界の決定に関していくつかの問題が発生することができます。</span><span class="sxs-lookup"><span data-stu-id="0e384-110">Counting field lengths in bytes can be complicated when the number of bytes used to encode characters is variable, and can result in some issues with respect to determining field boundaries.</span></span> <span data-ttu-id="0e384-111">フラット ファイル逆アセンブラーは、このような状況でフラット ファイルを解析し、使用中で文字エン コードの知識に基づく適切に解析を行って決定しようとします。</span><span class="sxs-lookup"><span data-stu-id="0e384-111">When the flat file disassembler parses a flat file in such situations, it attempts to make appropriate parsing decisions based on its knowledge of the character encoding in use.</span></span>  
  
 <span data-ttu-id="0e384-112">この型の意思決定の解析の例では、先行バイト MBCS 文字エン コードに関するものです。</span><span class="sxs-lookup"><span data-stu-id="0e384-112">An example of this type of parsing decision concerns lead bytes in MBCS character encodings.</span></span> <span data-ttu-id="0e384-113">先頭バイトは、既知のバイト値のマルチバイト文字エン コードの開始に使用して、独自でこれを実行することはありません。</span><span class="sxs-lookup"><span data-stu-id="0e384-113">Lead bytes are well-known byte values that are used to begin multibyte character encodings, and which should never occur on their own.</span></span> <span data-ttu-id="0e384-114">文字ではなくバイトを使用してフィールドの長さを指定すると、フィールドの最後のバイトがあるが単独で全体の文字を構成することはできません、先行バイトを使用する状況が発生します。</span><span class="sxs-lookup"><span data-stu-id="0e384-114">When specifying the length of the fields using bytes rather than character, situations may arise in which the last byte in a field is found to be a lead byte, which cannot constitute an entire character on its own.</span></span> <span data-ttu-id="0e384-115">このような場合は、フラット ファイル逆アセンブラーは、前のフィールドの最後の文字として先行バイトの直前に現れた文字を扱うし、先行バイトで始まる次のフィールドの解析を開始します。</span><span class="sxs-lookup"><span data-stu-id="0e384-115">In such cases, the flat file disassembler will treat the character occurring just prior to the lead byte as the last character in the previous field, and begin parsing the next field starting with the lead byte.</span></span>  

<span data-ttu-id="0e384-116">これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0e384-116">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0e384-117">参照</span><span class="sxs-lookup"><span data-stu-id="0e384-117">See Also</span></span>  
 [<span data-ttu-id="0e384-118">位置指定レコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="0e384-118">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   

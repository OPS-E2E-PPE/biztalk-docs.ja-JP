---
title: 位置のカウント (バイト単位) |Microsoft ドキュメント
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
ms.openlocfilehash: c3cdb7bbf1f0d6af04f0cc28ed1bdb7477b259de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264034"
---
# <a name="position-counting-in-bytes"></a><span data-ttu-id="3c5f1-102">位置のカウント (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="3c5f1-102">Position Counting in Bytes</span></span>

## <a name="overview"></a><span data-ttu-id="3c5f1-103">概要</span><span class="sxs-lookup"><span data-stu-id="3c5f1-103">Overview</span></span>

<span data-ttu-id="3c5f1-104">使用することができます、**カウント位置 (バイト単位)** のプロパティ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-104">You can use the **Count Positions In Bytes** property of the **Schema** node to:</span></span> 

* <span data-ttu-id="3c5f1-105">値の入力方法の指定、**位置指定値**と**位置指定オフセット**位置指定レコード内のさまざまなフィールドのプロパティが解釈されます</span><span class="sxs-lookup"><span data-stu-id="3c5f1-105">Specify how the values you enter for the **Positional Length** and **Positional Offset** properties of the various fields within positional records are interpreted</span></span>
* <span data-ttu-id="3c5f1-106">値の入力方法の指定、**タグ オフセット**位置指定レコード自体のプロパティが解釈されます</span><span class="sxs-lookup"><span data-stu-id="3c5f1-106">Specify how the values you enter for the **Tag Offset** property of the positional records themselves are interpreted</span></span>

<span data-ttu-id="3c5f1-107">既定では、これらの値は、文字数として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-107">By default, these values are interpreted as a number of characters.</span></span> <span data-ttu-id="3c5f1-108">次の場合、**カウント位置 (バイト単位)** プロパティに設定されている**True**、これらの値はバイト数として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-108">But when the **Count Positions In Bytes** property is set to **True**, these values are interpreted as a number of bytes.</span></span>  
  
 <span data-ttu-id="3c5f1-109">設定、**カウント位置 (バイト単位)** プロパティを**True**可能性があるマルチバイト文字を扱うときに必要な設定 (MBCS や DBCS) のデータまたは SAP、メインフレームで、フラット ファイル メッセージの発生時に、またはバイト単位で位置のカウントが他のシステムです。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-109">Setting the **Count Positions In Bytes** property to **True** might be necessary when dealing with multibyte character set (MBCS or DBCS) data, or when your flat file messages originate in SAP, mainframes, or other systems that may count positions in bytes.</span></span>  
  
 <span data-ttu-id="3c5f1-110">フィールド長をバイト単位でカウントすると、文字のエンコードに使用されるバイト数が可変である場合に複雑になりやすく、フィールド境界の区切りに関連した問題が生じる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-110">Counting field lengths in bytes can be complicated when the number of bytes used to encode characters is variable, and can result in some issues with respect to determining field boundaries.</span></span> <span data-ttu-id="3c5f1-111">このような場合、フラット ファイル逆アセンブラーは、フラット ファイルを解析するときに、使用されている文字エンコードに基づいて、適切な解析方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-111">When the flat file disassembler parses a flat file in such situations, it attempts to make appropriate parsing decisions based on its knowledge of the character encoding in use.</span></span>  
  
 <span data-ttu-id="3c5f1-112">文字エンコードに基づいて解析方法を決定する際、MBCS 文字エンコードの先頭バイト (先行バイトともいう) が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-112">An example of this type of parsing decision concerns lead bytes in MBCS character encodings.</span></span> <span data-ttu-id="3c5f1-113">先頭バイトは、マルチバイト文字エンコードの始まりを示す目的で使用され、単独で出現することはありません。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-113">Lead bytes are well-known byte values that are used to begin multibyte character encodings, and which should never occur on their own.</span></span> <span data-ttu-id="3c5f1-114">フィールドの長さを文字単位ではなくバイト単位で指定する場合、フィールドの最後のバイトが先頭バイトになってしまう可能性があります。上記のとおり、先頭バイトが単独で文字を形成することはありえません。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-114">When specifying the length of the fields using bytes rather than character, situations may arise in which the last byte in a field is found to be a lead byte, which cannot constitute an entire character on its own.</span></span> <span data-ttu-id="3c5f1-115">このような場合、フラット ファイル逆アセンブラーは、先頭バイトの直前に現れた文字を、前のフィールドの最後の文字として扱い、末尾にある先頭バイトを次のフィールドの解析起点と見なします。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-115">In such cases, the flat file disassembler will treat the character occurring just prior to the lead byte as the last character in the previous field, and begin parsing the next field starting with the lead byte.</span></span>  

<span data-ttu-id="3c5f1-116">これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3c5f1-116">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3c5f1-117">参照</span><span class="sxs-lookup"><span data-stu-id="3c5f1-117">See Also</span></span>  
 [<span data-ttu-id="3c5f1-118">位置指定レコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="3c5f1-118">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   

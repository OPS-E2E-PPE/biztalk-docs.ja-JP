---
title: フラット ファイル メッセージの構造 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00f2adf6-a47c-498b-b5ae-c6bd55bafceb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfb2e5f159ad3b792393ad828e0addc7907030c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244122"
---
# <a name="structure-of-a-flat-file-message"></a><span data-ttu-id="86c0a-102">フラット ファイル メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="86c0a-102">Structure of a Flat File Message</span></span>
<span data-ttu-id="86c0a-103">Microsoft のコンテキストで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、フラット ファイル インスタンス メッセージを 3 つの論理部分を含むことのできるテキスト ファイルは、: ヘッダー、本文、およびトレーラー、その順序で。</span><span class="sxs-lookup"><span data-stu-id="86c0a-103">In the context of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a flat file instance message is a text file that can contain three logical parts: a header, a body, and a trailer, in that order.</span></span> <span data-ttu-id="86c0a-104">ヘッダーとトレーラーは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="86c0a-104">Both the header and the trailer are optional.</span></span> <span data-ttu-id="86c0a-105">次の例では、太字で本文を含むすべての 3 つの部分で構成されるフラット ファイル インスタンス メッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="86c0a-105">The following example shows a flat file instance message that consists of all three parts, with the body shown in bold type.</span></span>  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 <span data-ttu-id="86c0a-106">ヘッダー、本文、およびフラット ファイル インスタンス メッセージのトレーラーを正しく区別するために フラット ファイル逆アセンブラーを作成する必要があり、別のスキーマをそれぞれの構成します。</span><span class="sxs-lookup"><span data-stu-id="86c0a-106">For the flat file disassembler to correctly distinguish the header, the body, and the trailer of a flat file instance message, you must create and configure a separate schema for each of them.</span></span>  
  
 <span data-ttu-id="86c0a-107">フラット ファイル インスタンス メッセージの特定の部分、内のデータのさまざまな項目がグループ化するのには、レコード、最終的のサブレコードやフィールドと呼ばれるデータの個々 の項目を含めることができます自体。</span><span class="sxs-lookup"><span data-stu-id="86c0a-107">Within a particular part of a flat file instance message, different items of data are grouped into records, which themselves can contain subrecords and ultimately the individual items of data, known as fields.</span></span> <span data-ttu-id="86c0a-108">これらのレコードおよびフィールドは、異なる 2 つの基本的な手法のいずれかを使用して相互から区別されます。</span><span class="sxs-lookup"><span data-stu-id="86c0a-108">These records and fields are distinguished from each other using one of two different basic methodologies.</span></span> <span data-ttu-id="86c0a-109">最初の方法では、位置指定と呼ばれるは、その長さの予想値までのデータの短い項目を表示するために使用される埋め込み文字を使って、事前に確立された長さのあるデータの各アイテムを定義します。</span><span class="sxs-lookup"><span data-stu-id="86c0a-109">The first methodology, known as positional, defines each item of data to be of a pre-established length, with pad characters being used to bring a shorter item of data up to its expected length.</span></span> <span data-ttu-id="86c0a-110">区切られたと呼ばれる 2 つ目の方法論では、互いのデータ項目を分割するのに 1 つまたは複数の特殊文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="86c0a-110">The second methodology, known as delimited, uses one or more special characters to separate items of data from each other.</span></span> <span data-ttu-id="86c0a-111">この手法は、それ以外の場合に余分な埋め込み文字の必要性を回避できますが、データ自体には、文字または区切り記号として使用されている文字のシーケンスが含まれている場合、特別な考慮事項が導入されています。</span><span class="sxs-lookup"><span data-stu-id="86c0a-111">This methodology avoids the need for otherwise superfluous pad characters, but introduces some special considerations when the data itself contains the character or sequence of characters being used as a delimiter.</span></span>  
  
 <span data-ttu-id="86c0a-112">このセクションの残りの部分が BizTalk Server でのヘッダー、本文、およびフラット ファイル インスタンス メッセージ トレーラーの処理方法の概要を提供および省略可能な部分が存在するかどうかであるの部分を分離する方法を決める方法具体的には、受信フラット ファイル インスタンス メッセージを送信フラット ファイル インスタンス メッセージの部分を結合します。</span><span class="sxs-lookup"><span data-stu-id="86c0a-112">The remainder of this section provides a high-level overview of how BizTalk Server handles headers, bodies, and trailers in flat file instance messages, and specifically, how it decides whether the optional parts are present, and how it separates the parts of inbound flat file instance messages and combines the parts of outbound flat file instance messages.</span></span> <span data-ttu-id="86c0a-113">このセクションには、位置指定レコードおよびフィールドを使用するフラット ファイル インスタンス メッセージと使用には、レコードおよびフィールドが区切られているフラット ファイル インスタンス メッセージの間の違いについて追加の情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="86c0a-113">This section also provides additional information about the differences between flat file instance messages that employ positional records and fields and flat file instance messages that employ delimited records and fields.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="86c0a-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="86c0a-114">In This Section</span></span>  
  
-   [<span data-ttu-id="86c0a-115">フラット ファイル メッセージのヘッダー</span><span class="sxs-lookup"><span data-stu-id="86c0a-115">Flat File Message Headers</span></span>](../core/flat-file-message-headers.md)  
  
-   [<span data-ttu-id="86c0a-116">フラット ファイル メッセージの本文</span><span class="sxs-lookup"><span data-stu-id="86c0a-116">Flat File Message Bodies</span></span>](../core/flat-file-message-bodies.md)  
  
-   [<span data-ttu-id="86c0a-117">フラット ファイル メッセージのトレーラー</span><span class="sxs-lookup"><span data-stu-id="86c0a-117">Flat File Message Trailers</span></span>](../core/flat-file-message-trailers.md)  
  
-   [<span data-ttu-id="86c0a-118">位置指定のレコードのあるフラット ファイル メッセージ</span><span class="sxs-lookup"><span data-stu-id="86c0a-118">Flat File Messages with Positional Records</span></span>](../core/flat-file-messages-with-positional-records.md)  
  
-   [<span data-ttu-id="86c0a-119">区切られたレコードのあるフラット ファイル メッセージ</span><span class="sxs-lookup"><span data-stu-id="86c0a-119">Flat File Messages with Delimited Records</span></span>](../core/flat-file-messages-with-delimited-records.md)  
  
-   [<span data-ttu-id="86c0a-120">フラット ファイル レコードの移行</span><span class="sxs-lookup"><span data-stu-id="86c0a-120">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)
---
title: フラット ファイル メッセージの構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: badb8aacf6f2ed8ce9e38f1ea6bbe432a1d3b89e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278938"
---
# <a name="structure-of-a-flat-file-message"></a><span data-ttu-id="049dc-102">フラット ファイル メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="049dc-102">Structure of a Flat File Message</span></span>
<span data-ttu-id="049dc-103">Microsoft のコンテキストで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、フラット ファイル インスタンス メッセージは次の 3 つの論理部分を含めることができるテキスト ファイル: ヘッダー、本文、およびトレーラー、その順序で。</span><span class="sxs-lookup"><span data-stu-id="049dc-103">In the context of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a flat file instance message is a text file that can contain three logical parts: a header, a body, and a trailer, in that order.</span></span> <span data-ttu-id="049dc-104">ヘッダーおよびトレーラーはいずれも省略できます。</span><span class="sxs-lookup"><span data-stu-id="049dc-104">Both the header and the trailer are optional.</span></span> <span data-ttu-id="049dc-105">3 つすべての部分から成るフラット ファイル インスタンス メッセージの例を次に示します。太字で表示されている部分が本文です。</span><span class="sxs-lookup"><span data-stu-id="049dc-105">The following example shows a flat file instance message that consists of all three parts, with the body shown in bold type.</span></span>  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 <span data-ttu-id="049dc-106">フラット ファイル インスタンス メッセージのヘッダー、本文、およびトレーラーをフラット ファイル逆アセンブラーが正しく識別するためには、それぞれについて、個別のスキーマを作成し、構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="049dc-106">For the flat file disassembler to correctly distinguish the header, the body, and the trailer of a flat file instance message, you must create and configure a separate schema for each of them.</span></span>  
  
 <span data-ttu-id="049dc-107">フラット ファイル インスタンス メッセージの特定の部分内では、データの各項目がレコードとしてグループ化されます。レコード自体はサブ レコードを含むことができ、最終的には、個別のデータ項目 (フィールド) を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="049dc-107">Within a particular part of a flat file instance message, different items of data are grouped into records, which themselves can contain subrecords and ultimately the individual items of data, known as fields.</span></span> <span data-ttu-id="049dc-108">これらのレコードおよびフィールドは、基本的な 2 種類の方法を用いて相互に区別されます。</span><span class="sxs-lookup"><span data-stu-id="049dc-108">These records and fields are distinguished from each other using one of two different basic methodologies.</span></span> <span data-ttu-id="049dc-109">1 つ目は、位置指定による方法です。この方法では、各データ項目があらかじめ決められた長さになるように定義されます。長さの短いデータ項目は、埋め込み文字を使って決められた長さになるように調整されます。</span><span class="sxs-lookup"><span data-stu-id="049dc-109">The first methodology, known as positional, defines each item of data to be of a pre-established length, with pad characters being used to bring a shorter item of data up to its expected length.</span></span> <span data-ttu-id="049dc-110">2 つ目は、区切り記号を使った方法です。この方法では、データ項目が、1 つまたは複数の特殊文字を使って区切られます。</span><span class="sxs-lookup"><span data-stu-id="049dc-110">The second methodology, known as delimited, uses one or more special characters to separate items of data from each other.</span></span> <span data-ttu-id="049dc-111">埋め込み文字は不要ですが、区切り文字 (または区切り文字列) がデータ自体に含まれていた場合を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="049dc-111">This methodology avoids the need for otherwise superfluous pad characters, but introduces some special considerations when the data itself contains the character or sequence of characters being used as a delimiter.</span></span>  
  
 <span data-ttu-id="049dc-112">以降では、フラット ファイル インスタンス メッセージのヘッダー、本文、およびトレーラーが、BizTalk Server によってどのように処理されるかについて簡単に説明します。特に、省略可能な部分が存在するかどうかの判別方法のほか、受信フラット ファイル インスタンス メッセージの各部分を分割し、送信フラット ファイル インスタンス メッセージの各部分を結合する方法について取り上げます。</span><span class="sxs-lookup"><span data-stu-id="049dc-112">The remainder of this section provides a high-level overview of how BizTalk Server handles headers, bodies, and trailers in flat file instance messages, and specifically, how it decides whether the optional parts are present, and how it separates the parts of inbound flat file instance messages and combines the parts of outbound flat file instance messages.</span></span> <span data-ttu-id="049dc-113">また、このセクションでは、位置指定レコード/フィールドが使用されたフラット ファイル インスタンス メッセージと、区切り記号付きレコード/フィールドが使用されたフラット ファイル インスタンス メッセージとの違いについても詳しく説明しています。</span><span class="sxs-lookup"><span data-stu-id="049dc-113">This section also provides additional information about the differences between flat file instance messages that employ positional records and fields and flat file instance messages that employ delimited records and fields.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="049dc-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="049dc-114">In This Section</span></span>  
  
-   [<span data-ttu-id="049dc-115">フラット ファイル メッセージのヘッダー</span><span class="sxs-lookup"><span data-stu-id="049dc-115">Flat File Message Headers</span></span>](../core/flat-file-message-headers.md)  
  
-   [<span data-ttu-id="049dc-116">フラット ファイル メッセージの本文</span><span class="sxs-lookup"><span data-stu-id="049dc-116">Flat File Message Bodies</span></span>](../core/flat-file-message-bodies.md)  
  
-   [<span data-ttu-id="049dc-117">フラット ファイル メッセージのトレーラー</span><span class="sxs-lookup"><span data-stu-id="049dc-117">Flat File Message Trailers</span></span>](../core/flat-file-message-trailers.md)  
  
-   [<span data-ttu-id="049dc-118">位置指定レコードのあるフラット ファイル メッセージ</span><span class="sxs-lookup"><span data-stu-id="049dc-118">Flat File Messages with Positional Records</span></span>](../core/flat-file-messages-with-positional-records.md)  
  
-   [<span data-ttu-id="049dc-119">区切られたレコードのフラット ファイル メッセージ</span><span class="sxs-lookup"><span data-stu-id="049dc-119">Flat File Messages with Delimited Records</span></span>](../core/flat-file-messages-with-delimited-records.md)  
  
-   [<span data-ttu-id="049dc-120">フラット ファイル レコードの移行</span><span class="sxs-lookup"><span data-stu-id="049dc-120">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)
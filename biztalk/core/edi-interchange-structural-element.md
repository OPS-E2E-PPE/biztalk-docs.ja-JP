---
title: "EDI インターチェンジの構造体要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03f47ae2-fa0f-4d88-a700-85f3d515d2d0
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc07ae40a3665b47b446b61e24954ca9c588a6a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-interchange-structural-element"></a><span data-ttu-id="62dcb-102">EDI のインターチェンジ構造体要素</span><span class="sxs-lookup"><span data-stu-id="62dcb-102">EDI Interchange Structural Element</span></span>
<span data-ttu-id="62dcb-103">インターチェンジは、EDI メッセージの最上位レベルの構造体要素です。</span><span class="sxs-lookup"><span data-stu-id="62dcb-103">The interchange is the highest-level structural element of an EDI message.</span></span> <span data-ttu-id="62dcb-104">これには、2 つのパートナーによって交換される 1 つ以上のグループのコレクションが格納されます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-104">It contains a collection of one or more groups exchanged by two partners.</span></span> <span data-ttu-id="62dcb-105">インターチェンジの送信先は、1 つの取引先である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62dcb-105">The destination of an interchange must be a single trading partner.</span></span> <span data-ttu-id="62dcb-106">インターチェンジには、1 つ以上の種類のトランザクション セット/メッセージを格納できます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-106">Interchanges may contain transaction sets/message of one or more than one type.</span></span>  
  
 <span data-ttu-id="62dcb-107">インターチェンジでは、インターチェンジ自体とそれに含まれるグループおよびトランザクション セット/メッセージが、ヘッダーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-107">With an interchange, the interchange itself and the groups and transaction sets/messages within it are defined by headers.</span></span> <span data-ttu-id="62dcb-108">セグメント、データ要素、およびサブ要素は区切り記号によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-108">Segments, data elements, and sub-elements are delimited by separators.</span></span> <span data-ttu-id="62dcb-109">各区切り記号には既定値がありますが、パーティによって異なる文字で定義されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62dcb-109">Each separator has a default value, but may be defined as a different character for the party.</span></span> <span data-ttu-id="62dcb-110">EDIFACT インターチェンジでインターチェンジの区切り記号として使用するために選択されている文字は、独立した UNA インターチェンジ ヘッダーで定義されます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-110">In EDIFACT interchanges, the characters selected for use as separators in the interchange are defined in a separate UNA Interchange Header.</span></span> <span data-ttu-id="62dcb-111">X12 インターチェンジでは、区切り記号が ISA インターチェンジ ヘッダーで定義されます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-111">In X12 interchanges, separators are defined in the ISA Interchange Header.</span></span> <span data-ttu-id="62dcb-112">X12 では、データ要素の区切り記号は 4 番目の文字位置にある文字であり、データ セグメント終了記号は最後の文字位置にある文字です。</span><span class="sxs-lookup"><span data-stu-id="62dcb-112">Note that in X12, the data element separator is the character in the fourth character position, and the data segment terminator is the character in the last character position.</span></span> <span data-ttu-id="62dcb-113">他の X12 区切り記号およびすべての EDIFACT 区切り記号は、フィールドによって定義されます。たとえば、X12 コンポーネント区切り記号は ISA16 フィードによって定義され、EDIFACT データ要素の区切り記号は UNA2 フィールドによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-113">The other X12 separators and all the EDIFACT separators are defined by fields, such as the X12 component separator by the ISA16 field and the EDIFACT data element separator by the UNA2 field.</span></span>  
  
 <span data-ttu-id="62dcb-114">インターチェンジには、EDI メッセージを定義するエンベロープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-114">The interchange includes an envelope that defines the EDI message.</span></span> <span data-ttu-id="62dcb-115">エンベロープはインターチェンジ ヘッダー (X12 では ISA、EDIFACT では UNA/UNB) で始まり、インターチェンジ トレーラー (IEA/UNZ) で終わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="62dcb-115">The envelope must start with an Interchange Header (ISA in X12 or UNA/UNB in EDIFACT), and it must end with an Interchange Trailer (IEA/UNZ).</span></span> <span data-ttu-id="62dcb-116">インターチェンジ ヘッダーには、送信者と受信者、日時、バージョン番号、ヘッダーとトレーラーに一致する制御番号、およびその他の情報を定義する要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-116">The Interchange Header includes elements defining the sender and receiver, a date and time, a version number, a control number that matches the header and the trailer, and other information.</span></span>  
  
 <span data-ttu-id="62dcb-117">ISA12 フィールドと GS8 フィールド (X12 インターチェンジの場合)、および UNH2 フィールド (EDIFACT インターチェンジの場合) には、スキーマ探索に必要なバージョン情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-117">The ISA12 and GS8 fields (for X12 interchanges) and the UNH2 field (for EDIFACT interchanges) contain version information that is required for schema discovery.</span></span>  
  
 <span data-ttu-id="62dcb-118">インターチェンジ トレーラーには、インターチェンジ内のグループの数を示す要素があります。</span><span class="sxs-lookup"><span data-stu-id="62dcb-118">The Interchange Trailer has an element that indicates the number of groups within the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62dcb-119">機能セキュリティ ヘッダー、機能保証ヘッダー、機能セキュリティ値セグメント、および機能セキュリティ トレーラー セグメントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 の対象外です。</span><span class="sxs-lookup"><span data-stu-id="62dcb-119">The functional security header, functional assurance header, functional security value segment, and functional security trailer segments are beyond the scope of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2.</span></span> <span data-ttu-id="62dcb-120">このようなセグメントを含むインターチェンジを受信した場合、これらが認識不可能なセグメントであることを示すエラー ログが生成され、インターチェンジが中断されます。</span><span class="sxs-lookup"><span data-stu-id="62dcb-120">If an interchange with these segments is received, it will be suspended with an error log indicating that these are unidentified segments.</span></span>
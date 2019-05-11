---
title: EDI インターチェンジの構造体要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03f47ae2-fa0f-4d88-a700-85f3d515d2d0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416624a6aef721b6d792320aa5a3ac71650fb131
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389224"
---
# <a name="edi-interchange-structural-element"></a><span data-ttu-id="b8abf-102">EDI インターチェンジの構造体要素</span><span class="sxs-lookup"><span data-stu-id="b8abf-102">EDI Interchange Structural Element</span></span>
<span data-ttu-id="b8abf-103">インターチェンジは、EDI メッセージの最上位レベルの構造体要素です。</span><span class="sxs-lookup"><span data-stu-id="b8abf-103">The interchange is the highest-level structural element of an EDI message.</span></span> <span data-ttu-id="b8abf-104">2 つのパートナーによって交換される 1 つまたは複数のグループのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8abf-104">It contains a collection of one or more groups exchanged by two partners.</span></span> <span data-ttu-id="b8abf-105">インターチェンジの送信先は、1 つの取引先パートナーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8abf-105">The destination of an interchange must be a single trading partner.</span></span> <span data-ttu-id="b8abf-106">インターチェンジが 1 つまたは複数のトランザクション セット/メッセージを含めることができますの種類。</span><span class="sxs-lookup"><span data-stu-id="b8abf-106">Interchanges may contain transaction sets/message of one or more than one type.</span></span>  
  
 <span data-ttu-id="b8abf-107">インターチェンジをインターチェンジ自体とグループとトランザクション セット/メッセージ内には、ヘッダーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="b8abf-107">With an interchange, the interchange itself and the groups and transaction sets/messages within it are defined by headers.</span></span> <span data-ttu-id="b8abf-108">セグメント、データ要素、およびサブ要素は、区切り記号で区切られます。</span><span class="sxs-lookup"><span data-stu-id="b8abf-108">Segments, data elements, and sub-elements are delimited by separators.</span></span> <span data-ttu-id="b8abf-109">各区切り記号は、既定値を持つが、パーティの別の文字として定義することがあります。</span><span class="sxs-lookup"><span data-stu-id="b8abf-109">Each separator has a default value, but may be defined as a different character for the party.</span></span> <span data-ttu-id="b8abf-110">EDIFACT インターチェンジの場合で、インターチェンジの区切り記号として使用される文字は、独立した UNA インターチェンジ ヘッダーで定義されます。</span><span class="sxs-lookup"><span data-stu-id="b8abf-110">In EDIFACT interchanges, the characters selected for use as separators in the interchange are defined in a separate UNA Interchange Header.</span></span> <span data-ttu-id="b8abf-111">X12 インターチェンジの場合、区切り記号が ISA インターチェンジ ヘッダーで定義されます。</span><span class="sxs-lookup"><span data-stu-id="b8abf-111">In X12 interchanges, separators are defined in the ISA Interchange Header.</span></span> <span data-ttu-id="b8abf-112">X12 で、データ要素区切り記号は、4 番目の文字位置の文字およびデータのセグメント終端記号は最後の文字位置の文字です。</span><span class="sxs-lookup"><span data-stu-id="b8abf-112">Note that in X12, the data element separator is the character in the fourth character position, and the data segment terminator is the character in the last character position.</span></span> <span data-ttu-id="b8abf-113">その他の X12 区切り記号およびすべての EDIFACT 区切り記号が X12 などのフィールドで定義されている ISA16 フィールドと、EDIFACT データ要素区切り記号は UNA2 フィールドによって、コンポーネントの区切り記号。</span><span class="sxs-lookup"><span data-stu-id="b8abf-113">The other X12 separators and all the EDIFACT separators are defined by fields, such as the X12 component separator by the ISA16 field and the EDIFACT data element separator by the UNA2 field.</span></span>  
  
 <span data-ttu-id="b8abf-114">インターチェンジには、EDI メッセージを定義するエンベロープが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8abf-114">The interchange includes an envelope that defines the EDI message.</span></span> <span data-ttu-id="b8abf-115">エンベロープはインターチェンジ ヘッダー (x12 ISA) または edifact の場合、UNA または UNB で開始する必要があり、インターチェンジ トレーラー (IEA/UNZ) で終わらなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b8abf-115">The envelope must start with an Interchange Header (ISA in X12 or UNA/UNB in EDIFACT), and it must end with an Interchange Trailer (IEA/UNZ).</span></span> <span data-ttu-id="b8abf-116">インターチェンジ ヘッダーには、送信者と受信者、日付と時間、バージョン番号、ヘッダーとトレーラー、およびその他の情報に一致する制御番号を定義する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8abf-116">The Interchange Header includes elements defining the sender and receiver, a date and time, a version number, a control number that matches the header and the trailer, and other information.</span></span>  
  
 <span data-ttu-id="b8abf-117">ISA12 と GS8 フィールド (X12 インターチェンジの場合) の UNH2 フィールド (EDIFACT インターチェンジの場合) を含むスキーマの検出に必要なバージョン情報とします。</span><span class="sxs-lookup"><span data-stu-id="b8abf-117">The ISA12 and GS8 fields (for X12 interchanges) and the UNH2 field (for EDIFACT interchanges) contain version information that is required for schema discovery.</span></span>  
  
 <span data-ttu-id="b8abf-118">インターチェンジ トレーラーには、インターチェンジ内のグループの数を示す要素があります。</span><span class="sxs-lookup"><span data-stu-id="b8abf-118">The Interchange Trailer has an element that indicates the number of groups within the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8abf-119">機能セキュリティ ヘッダー、機能保証ヘッダー、機能セキュリティ値セグメント、および機能セキュリティ トレーラー セグメントは、の範囲を超えている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI および AS2 します。</span><span class="sxs-lookup"><span data-stu-id="b8abf-119">The functional security header, functional assurance header, functional security value segment, and functional security trailer segments are beyond the scope of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2.</span></span> <span data-ttu-id="b8abf-120">これらのセグメントを持つインターチェンジを受信すると、これらが認識されないセグメントであることを示すエラー ログで中断されます。</span><span class="sxs-lookup"><span data-stu-id="b8abf-120">If an interchange with these segments is received, it will be suspended with an error log indicating that these are unidentified segments.</span></span>
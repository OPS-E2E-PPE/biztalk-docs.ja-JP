---
title: EDI ドキュメント スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc3a30b8-0686-4c06-985b-13f2c95f8e99
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac5830f12351bd5441411fe54598e55894216fa6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998627"
---
# <a name="edi-document-schemas"></a><span data-ttu-id="05648-102">EDI ドキュメント スキーマ</span><span class="sxs-lookup"><span data-stu-id="05648-102">EDI Document Schemas</span></span>
<span data-ttu-id="05648-103">ドキュメント スキーマは、EDI トランザクション ドキュメントの種類のボディを定義します。</span><span class="sxs-lookup"><span data-stu-id="05648-103">Document schemas define the body of an EDI transaction document type.</span></span>  
  
## <a name="schema-delivery-and-setup"></a><span data-ttu-id="05648-104">スキーマの配信と設定</span><span class="sxs-lookup"><span data-stu-id="05648-104">Schema Delivery and Setup</span></span>  
 <span data-ttu-id="05648-105">EDI ドキュメント スキーマは、自己解凍実行可能ファイルに圧縮された状態で配信される[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe します。</span><span class="sxs-lookup"><span data-stu-id="05648-105">EDI document schemas are delivered in a compressed state in a self-extracting executable, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe.</span></span> <span data-ttu-id="05648-106">自己解凍形式の実行可能ファイルによって、確実に、適切なフォルダ構造が作成されることになります (エンコードの種類ごと、およびバージョン/リリースのサブタイプごと)。</span><span class="sxs-lookup"><span data-stu-id="05648-106">The self-extracting executable ensures that an appropriate folder structure is created (per the encoding type and version/release sub types).</span></span> <span data-ttu-id="05648-107">実行すると、この実行可能ファイルと同じディレクトリ内のサブフォルダーに、EANCOM、EDIFACT、HIPAA、および X12 のスキーマが展開されます。</span><span class="sxs-lookup"><span data-stu-id="05648-107">When executed, the executable deposits EANCOM, EDIFACT, HIPAA, and X12 schemas into subfolders in the same directory as the executable.</span></span>  
  
 <span data-ttu-id="05648-108">既定のスキーマの名前空間は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="05648-108">The default schema namespaces are:</span></span>  
  
-   <span data-ttu-id="05648-109">X12 の場合 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`</span><span class="sxs-lookup"><span data-stu-id="05648-109">For X12 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`</span></span>  
  
-   <span data-ttu-id="05648-110">EDIFACT の場合 – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`</span><span class="sxs-lookup"><span data-stu-id="05648-110">For EDIFACT – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`</span></span>  
  
## <a name="schema-naming-convention"></a><span data-ttu-id="05648-111">スキーマの名前付け規則</span><span class="sxs-lookup"><span data-stu-id="05648-111">Schema Naming Convention</span></span>  
 <span data-ttu-id="05648-112">X12 および EDIFACT エンコードの種類の名前付け規則は\<エンコード\>*\<バージョン\>\<リリース\>\\*  \<Doctype\>します。</span><span class="sxs-lookup"><span data-stu-id="05648-112">The naming convention for the X12 and EDIFACT encoding type is \<Encoding\>*\<Version\>\<Release\>\\*\<Doctype\>.</span></span> <span data-ttu-id="05648-113">たとえば、X12 864 ドキュメントの種類 (バージョン 004、リリース 01) の場合は X12_00401_864.xsd スキーマ、EDIFACT AUTHOR ドキュメントの種類 (バージョン D01、リリース C) の場合は EDIFACT_D01C_AUTHOR.xsd スキーマのようになります。</span><span class="sxs-lookup"><span data-stu-id="05648-113">Examples are the X12_00401_864.xsd schema for the X12 864 document type (version 004, release 01) and the EDIFACT_D01C_AUTHOR.xsd schema for the EDIFACT AUTHOR document type (version D01, release C).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05648-114">EDIFACT スキーマのスキーマ名では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="05648-114">The schema name of an EDIFACT schema is case-sensitive.</span></span> <span data-ttu-id="05648-115">たとえば、EFACT_D98B_ORDERS と EFACT_d98B_Orders は 2 つの異なるスキーマです。</span><span class="sxs-lookup"><span data-stu-id="05648-115">For example, EFACT_D98B_ORDERS and EFACT_d98B_Orders would be two different schemas.</span></span>  
  
## <a name="schema-contents"></a><span data-ttu-id="05648-116">スキーマ コンテンツ</span><span class="sxs-lookup"><span data-stu-id="05648-116">Schema Contents</span></span>  
 <span data-ttu-id="05648-117">ドキュメント スキーマは、X12 エンコード ドキュメントの場合、ST トランザクション セット ヘッダーで開始し、ST トランザクション セット トレーラーで終了します。</span><span class="sxs-lookup"><span data-stu-id="05648-117">A document schema starts with the ST transaction set header and ends with the SE transaction set trailer for an X12-encoded document.</span></span> <span data-ttu-id="05648-118">EDIFACT エンコード ドキュメントの場合は、UNH メッセージ ヘッダーで開始し、UNT メッセージ トレーラーで終了します。</span><span class="sxs-lookup"><span data-stu-id="05648-118">It starts with the UNH message header and ends with the UNT message trailer for an EDIFACT-encoded document.</span></span> <span data-ttu-id="05648-119">スキーマは、これらのヘッダーとトレーラーのデータ要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="05648-119">The schema defines each data element of these headers and trailers.</span></span>  
  
 <span data-ttu-id="05648-120">ドキュメント スキーマは、次に、トランザクション セット/メッセージ内の各セグメント、およびこれらのセグメント内のデータ要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="05648-120">A document schema then defines each segment within the transaction set/message and the data elements within those segments.</span></span> <span data-ttu-id="05648-121">たとえば、X12_00401_864.xsd スキーマは、BMG セグメントの BMG01、BMG02、および BMG03 要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="05648-121">For example, the X12_00401_864.xsd schema defines the BMG01, BMG02, and BMG03 elements of the BMG segments.</span></span> <span data-ttu-id="05648-122">スキーマは、フィールドの順序、区切り記号の種類、名前空間など、セグメントの複合データ型の特性を指定します。</span><span class="sxs-lookup"><span data-stu-id="05648-122">The schema specifies the characteristics of the segment's complex data type, such as the field order, delimiter type, and namespace.</span></span> <span data-ttu-id="05648-123">スキーマのクロス フィールド検証がある場合は、スキーマがそのルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="05648-123">If there are cross-field validation rules for the segment, the schema defines the rules.</span></span> <span data-ttu-id="05648-124">詳細については、次を参照してください。[クロス フィールド/セグメント検証](../core/cross-field-segment-validation.md)です。</span><span class="sxs-lookup"><span data-stu-id="05648-124">For more information, see [Cross Field-Segment Validation](../core/cross-field-segment-validation.md).</span></span>  
  
 <span data-ttu-id="05648-125">スキーマは、単純データ型、最小出現回数、最小長、および最大長など、セグメント内の各データ要素の特性を指定します。</span><span class="sxs-lookup"><span data-stu-id="05648-125">The schema specifies the characteristics of each data element within the segment, such as the simple data type, minimum occurrences, minimum length, and maximum length.</span></span>  
  
 <span data-ttu-id="05648-126">ループを含むメッセージの種類である場合、スキーマは、各ループ内のデータ要素、ループの最小出現回数と最大出現回数、ループでの境界の有無などを定義します。</span><span class="sxs-lookup"><span data-stu-id="05648-126">If there is a loop in the message type, the schema defines the data elements within each loop, the minimum and maximum occurrences of the loop, and whether the loop is bounded or unbounded.</span></span> <span data-ttu-id="05648-127">また、セグメントの入れ子や、ループが明示的であるか暗黙的であるかについても、スキーマによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="05648-127">The schema also defines nesting of a segment, and whether the loop is explicit or implicit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05648-128">参照</span><span class="sxs-lookup"><span data-stu-id="05648-128">See Also</span></span>  
 <span data-ttu-id="05648-129">[EDI メッセージの構造](../core/edi-message-structure.md) </span><span class="sxs-lookup"><span data-stu-id="05648-129">[EDI Message Structure](../core/edi-message-structure.md) </span></span>  
 [<span data-ttu-id="05648-130">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="05648-130">EDI Message Validation</span></span>](../core/edi-message-validation.md)
---
title: "カスタムの日付/時刻形式 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5efbec4-3138-44d7-bc76-f9c21547e1d5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1496f1f506df06a4d5569c065cba3bf4f8cbdad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="custom-date-time-formats"></a><span data-ttu-id="483d5-102">カスタムの日付/時刻書式</span><span class="sxs-lookup"><span data-stu-id="483d5-102">Custom Date-Time Formats</span></span>

## <a name="overview"></a><span data-ttu-id="483d5-103">概要</span><span class="sxs-lookup"><span data-stu-id="483d5-103">Overview</span></span>
<span data-ttu-id="483d5-104">基になるファイルが古いために、フラット ファイル スキーマを作成するフラット ファイル形式で、ISO 8601 形式に準拠しない日付/時刻書式が使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="483d5-104">Due to their legacy origins, the flat file formats for which you create flat file schemas are bound to use date and time formats that do not conform to ISO 8601 formats.</span></span> <span data-ttu-id="483d5-105">そのため、フラット ファイル スキーマを作成して、設定する、**データ型**のプロパティ、**フィールド要素**または**フィールド属性**XML スキーマ定義 (のいずれかのノードXSD) 言語プリミティブ データ型、 **xs:dateTime**、 **xs:time**、または**xs:date**、使用することができます、**カスタム日付/時刻書式**プロパティを別の形式の日付または時刻の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="483d5-105">Therefore, when you are creating a flat file schema and you set the **Data Type** property of a **Field Element** or **Field Attribute** node to one of the XML Schema definition (XSD) language primitive data types, **xs:dateTime**, **xs:time**, or **xs:date**, you can use the **Custom Date/Time Format** property to specify an alternative format for date or time values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="483d5-106">メッセージ ボックスに記憶域の時刻値を切り捨てます。 **xs:dateTime**と**xs:time**ミリ秒レベル下にある要素。</span><span class="sxs-lookup"><span data-stu-id="483d5-106">Storage in the message box truncates time values in **xs:dateTime** and **xs:time** elements below the millisecond level.</span></span> <span data-ttu-id="483d5-107">同様の精度の低下は、.NET の日付/時刻データ型に変換する場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="483d5-107">A similar loss of precision may occur when converting to .NET date/time data types.</span></span>  
  
 <span data-ttu-id="483d5-108">フラット ファイル逆アセンブラーは、このようなフィールドを対応する XML が変換されるときの値の書式、**カスタム日付/時刻書式**ISO 8601 準拠に変換するフラット ファイルの日付/時刻形式を許可するプロパティが使用されます等価です。</span><span class="sxs-lookup"><span data-stu-id="483d5-108">When the flat file disassembler translates such a field to its equivalent XML format, the value of the **Custom Date/Time Format** property will be used to allow the flat file date/time format to be converted to its ISO 8601 compliant equivalent.</span></span> <span data-ttu-id="483d5-109">同様に、フラット ファイル アセンブラーでは、等価なフラット ファイルへの ISO 8601 準拠の日付/時刻値を変換、されるときに、書式指定文字列で指定、**カスタム日付/時刻書式**プロパティが使用されます、適切な日付を構築/フラット ファイルの予期される時刻形式。</span><span class="sxs-lookup"><span data-stu-id="483d5-109">Likewise, when the flat file assembler translates an ISO 8601 compliant date/time value to its flat file equivalent, the format string specified in the **Custom Date/Time Format** property will be used construct the appropriate date/time format expected in the flat file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="483d5-110">既定では、XSD 日付/時刻データ型に対応する値は、複数ある形式のうち、ISO 8601 形式に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="483d5-110">By default, values that correspond to XSD date and time data types, of which there are several, must conform to ISO 8601 formats.</span></span> <span data-ttu-id="483d5-111">として日付を表現する、簡単に言えば**YYYY MM DD**で表される時間と**hh:mm:ss** 24 時間表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="483d5-111">In brief, dates are expressed as **YYYY-MM-DD** and hours are expressed as **hh:mm:ss** using 24-hour notation.</span></span> <span data-ttu-id="483d5-112">日付と時刻の値が"T"文字で区切られた発生すると同時に、: **YYYY:MM:DDThh:mm:ss**です。</span><span class="sxs-lookup"><span data-stu-id="483d5-112">When they occur together, date and time values are separated by the "T" character: **YYYY:MM:DDThh:mm:ss**.</span></span>  
  
 <span data-ttu-id="483d5-113">構成することができます、**カスタム日付/時刻書式**ユリウス暦を除くほとんどの日付と時刻の形式を持つプロパティです。</span><span class="sxs-lookup"><span data-stu-id="483d5-113">You can configure the **Custom Date/Time Format** property with almost any time and date format, except for Julian dates.</span></span> <span data-ttu-id="483d5-114">ドロップダウン リストにさまざまな選択肢が用意されていますが、別の書式を入力して選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="483d5-114">The drop-down list provides various choices, but you can also type a different format of your choosing.</span></span> <span data-ttu-id="483d5-115">日付と時刻の形式は、共通言語ランタイム (CLR) を使用して**DateTime**機能します。</span><span class="sxs-lookup"><span data-stu-id="483d5-115">The date and time formats use the Common Language Runtime (CLR) **DateTime** facilities.</span></span> <span data-ttu-id="483d5-116">例外的に、d、m または M が 1 文字だけの場合は、前に自動的にパーセント記号 (%) が付加され、DataTime 値の対応する要素の 1 つが生成されます。</span><span class="sxs-lookup"><span data-stu-id="483d5-116">The exception is that a single character d, m, or M is automatically prepended with a percent sign (%) to yield the corresponding single element of the DateTime value.</span></span> <span data-ttu-id="483d5-117">カスタム日付/時刻書式で使用できる区切り記号は、ダッシュ (-)、スラッシュ (/) およびピリオド (.) です。</span><span class="sxs-lookup"><span data-stu-id="483d5-117">The allowable separators for custom date/time formats are dash (-), slash (/), and period (.).</span></span> <span data-ttu-id="483d5-118">詳細については**DateTime**形式が Visual Studio ドキュメント コレクション内で検索 datetimeformatinfo」を参照します。</span><span class="sxs-lookup"><span data-stu-id="483d5-118">For more information about **DateTime** formats, search on "DateTimeFormatInfo" in the Visual Studio document collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483d5-119">参照</span><span class="sxs-lookup"><span data-stu-id="483d5-119">See Also</span></span>  
-  [<span data-ttu-id="483d5-120">フィールドに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="483d5-120">Field Considerations</span></span>](../core/field-considerations.md)   
-  <span data-ttu-id="483d5-121">**データ型 (すべてのスキーマのノード プロパティ)**と**カスタム日時書式指定 (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="483d5-121">**Data Type (Node Property of All Schemas)** and **Custom Date-Time Format (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
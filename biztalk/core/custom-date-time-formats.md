---
title: カスタムの日付/時刻書式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5efbec4-3138-44d7-bc76-f9c21547e1d5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e1c456170170859ffd81d0963b85fb6db60f955
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353367"
---
# <a name="custom-date-time-formats"></a><span data-ttu-id="578e9-102">カスタムの日付と時刻の形式</span><span class="sxs-lookup"><span data-stu-id="578e9-102">Custom Date-Time Formats</span></span>

## <a name="overview"></a><span data-ttu-id="578e9-103">概要</span><span class="sxs-lookup"><span data-stu-id="578e9-103">Overview</span></span>
<span data-ttu-id="578e9-104">により、従来のオリジンは、フラット ファイル スキーマを作成するフラット ファイル形式は ISO 8601 形式に準拠していない日付と時刻の形式を使用するバインドされます。</span><span class="sxs-lookup"><span data-stu-id="578e9-104">Due to their legacy origins, the flat file formats for which you create flat file schemas are bound to use date and time formats that do not conform to ISO 8601 formats.</span></span> <span data-ttu-id="578e9-105">そのため、フラット ファイル スキーマを作成して、設定する、**データ型**のプロパティを**フィールド要素**または**フィールド属性**XML スキーマ定義 (のいずれかのノードXSD) 言語のプリミティブ データ型、 **xs:dateTime**、 **xs:time**、または**xs:date**、使用することができます、**カスタム日付/時刻書式**プロパティを日付または時刻の値の代替形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="578e9-105">Therefore, when you are creating a flat file schema and you set the **Data Type** property of a **Field Element** or **Field Attribute** node to one of the XML Schema definition (XSD) language primitive data types, **xs:dateTime**, **xs:time**, or **xs:date**, you can use the **Custom Date/Time Format** property to specify an alternative format for date or time values.</span></span>  

> [!NOTE]
>  <span data-ttu-id="578e9-106">メッセージ ボックスにストレージで時間の値は切り捨てられます**xs:dateTime**と**xs:time**ミリ秒レベルの下の要素。</span><span class="sxs-lookup"><span data-stu-id="578e9-106">Storage in the message box truncates time values in **xs:dateTime** and **xs:time** elements below the millisecond level.</span></span> <span data-ttu-id="578e9-107">.NET の日付/時刻データ型に変換するときのような精度の損失があります。</span><span class="sxs-lookup"><span data-stu-id="578e9-107">A similar loss of precision may occur when converting to .NET date/time data types.</span></span>  

 <span data-ttu-id="578e9-108">フラット ファイル逆アセンブラーは、このようなフィールドを等価の XML が変換されるときの値の書式、**カスタム日付/時刻書式**準拠している ISO 8601 形式に変換するフラット ファイルの日付/時刻形式を許可するプロパティが使用されます等価です。</span><span class="sxs-lookup"><span data-stu-id="578e9-108">When the flat file disassembler translates such a field to its equivalent XML format, the value of the **Custom Date/Time Format** property will be used to allow the flat file date/time format to be converted to its ISO 8601 compliant equivalent.</span></span> <span data-ttu-id="578e9-109">同様に、フラット ファイル アセンブラーでは、等価なフラット ファイルへの ISO 8601 準拠の日付/時刻値を変換、されるときに、書式指定文字列はで指定された、**カスタム日付/時刻書式**プロパティが使用する、適切な日付の構築/時刻の形式は、フラット ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="578e9-109">Likewise, when the flat file assembler translates an ISO 8601 compliant date/time value to its flat file equivalent, the format string specified in the **Custom Date/Time Format** property will be used construct the appropriate date/time format expected in the flat file.</span></span>  

> [!NOTE]
>  <span data-ttu-id="578e9-110">既定では、XSD 日付と時刻データ型にするは、いくつか、対応する値は、ISO 8601 形式に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="578e9-110">By default, values that correspond to XSD date and time data types, of which there are several, must conform to ISO 8601 formats.</span></span> <span data-ttu-id="578e9-111">として日付を表現する簡単に言うと **- YYYY-MM-DD**で表される時間と**hh:mm:ss** 24 時間表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="578e9-111">In brief, dates are expressed as **YYYY-MM-DD** and hours are expressed as **hh:mm:ss** using 24-hour notation.</span></span> <span data-ttu-id="578e9-112">化が発生したときの日付と時刻の値は"T"の文字で区切られます。**YYYY:MM:DDThh:mm:ss**します。</span><span class="sxs-lookup"><span data-stu-id="578e9-112">When they occur together, date and time values are separated by the "T" character: **YYYY:MM:DDThh:mm:ss**.</span></span>  

 <span data-ttu-id="578e9-113">構成することができます、**カスタム日付/時刻書式**ユリウス暦を除くほとんどの日付と時刻の形式を持つプロパティです。</span><span class="sxs-lookup"><span data-stu-id="578e9-113">You can configure the **Custom Date/Time Format** property with almost any time and date format, except for Julian dates.</span></span> <span data-ttu-id="578e9-114">ドロップダウン リストがさまざまな選択肢を提供しますが、独自の別の形式を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="578e9-114">The drop-down list provides various choices, but you can also type a different format of your choosing.</span></span> <span data-ttu-id="578e9-115">日付と時刻の形式を使用して、共通言語ランタイム (CLR) **DateTime**機能します。</span><span class="sxs-lookup"><span data-stu-id="578e9-115">The date and time formats use the Common Language Runtime (CLR) **DateTime** facilities.</span></span> <span data-ttu-id="578e9-116">例外は、ことの 1 文字 d、m または M が自動的に付きます。 パーセント記号 (%)DateTime 値の 1 つの対応する要素を生成します。</span><span class="sxs-lookup"><span data-stu-id="578e9-116">The exception is that a single character d, m, or M is automatically prepended with a percent sign (%) to yield the corresponding single element of the DateTime value.</span></span> <span data-ttu-id="578e9-117">カスタム日付/時刻形式を使用できる区切り記号は、ダッシュ (-)、スラッシュ (/)、およびピリオド (.) です。</span><span class="sxs-lookup"><span data-stu-id="578e9-117">The allowable separators for custom date/time formats are dash (-), slash (/), and period (.).</span></span> <span data-ttu-id="578e9-118">詳細については**DateTime**形式が Visual Studio ドキュメント コレクション内の「DateTimeFormatInfo」で検索します。</span><span class="sxs-lookup"><span data-stu-id="578e9-118">For more information about **DateTime** formats, search on "DateTimeFormatInfo" in the Visual Studio document collection.</span></span>  

## <a name="see-also"></a><span data-ttu-id="578e9-119">参照</span><span class="sxs-lookup"><span data-stu-id="578e9-119">See Also</span></span>  
- [<span data-ttu-id="578e9-120">フィールドに関する注意</span><span class="sxs-lookup"><span data-stu-id="578e9-120">Field Considerations</span></span>](../core/field-considerations.md)   
- <span data-ttu-id="578e9-121">**データ型 (すべてのスキーマのノード プロパティ)** と**カスタム日付/時刻形式 (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="578e9-121">**Data Type (Node Property of All Schemas)** and **Custom Date-Time Format (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

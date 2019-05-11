---
title: ファイル メッセージ スキーマをフラットを作成する際の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52271b17-4f0b-4286-a462-cd5951ae49aa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ea131abf4f506ad8f396d7da895b44d8c24536e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354689"
---
# <a name="considerations-when-creating-flat-file-message-schemas"></a><span data-ttu-id="012f0-102">ファイル メッセージ スキーマをフラットを作成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="012f0-102">Considerations When Creating Flat File Message Schemas</span></span>
<span data-ttu-id="012f0-103">フラット ファイル メッセージ スキーマを使用する場合は、多くの注意事項にがあります。</span><span class="sxs-lookup"><span data-stu-id="012f0-103">There are a number of considerations when working with flat file message schemas.</span></span> <span data-ttu-id="012f0-104">これには、すべてのフラット ファイル スキーマに適用される考慮事項の位置指定レコード、区切り記号付きレコード、位置指定のフィールドまたは区切られたフィールドに適用される考慮事項も含まれます。</span><span class="sxs-lookup"><span data-stu-id="012f0-104">This includes considerations that apply to all flat file schemas, as well as considerations that apply specifically to positional records, delimited records, positional fields, or delimited fields.</span></span> <span data-ttu-id="012f0-105">考慮事項がありますそれ以外の場合を解釈する方法について特別な文字を通常のデータ。</span><span class="sxs-lookup"><span data-stu-id="012f0-105">There are also considerations about how to interpret otherwise special characters as regular data.</span></span> <span data-ttu-id="012f0-106">このセクションでは、これらの考慮事項についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="012f0-106">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="012f0-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="012f0-107">In This Section</span></span>  
  
-   [<span data-ttu-id="012f0-108">フラット ファイル スキーマに使用されるコード ページの仕様</span><span class="sxs-lookup"><span data-stu-id="012f0-108">Code Page Specification for Flat File Schemas</span></span>](../core/code-page-specification-for-flat-file-schemas.md)  
  
-   [<span data-ttu-id="012f0-109">フラット ファイル スキーマにおける大文字と小文字の扱い</span><span class="sxs-lookup"><span data-stu-id="012f0-109">Case Handling in Flat File Schemas</span></span>](../core/case-handling-in-flat-file-schemas.md)  
  
-   [<span data-ttu-id="012f0-110">文字範囲の制限</span><span class="sxs-lookup"><span data-stu-id="012f0-110">Restricted Character Ranges</span></span>](../core/restricted-character-ranges.md)  
  
-   [<span data-ttu-id="012f0-111">入れ子になった位置指定レコードおよび区切り記号付きレコード</span><span class="sxs-lookup"><span data-stu-id="012f0-111">Nested Positional and Delimited Records</span></span>](../core/nested-positional-and-delimited-records.md)  
  
-   [<span data-ttu-id="012f0-112">位置指定レコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="012f0-112">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)  
  
-   [<span data-ttu-id="012f0-113">区切り記号付きレコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="012f0-113">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)  
  
-   [<span data-ttu-id="012f0-114">フィールドに関する注意</span><span class="sxs-lookup"><span data-stu-id="012f0-114">Field Considerations</span></span>](../core/field-considerations.md)  
  
-   [<span data-ttu-id="012f0-115">特殊文字をフィールド値の一部として解釈させる方法</span><span class="sxs-lookup"><span data-stu-id="012f0-115">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)
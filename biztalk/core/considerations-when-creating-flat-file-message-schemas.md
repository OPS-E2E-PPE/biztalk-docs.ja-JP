---
title: ファイル メッセージ スキーマをフラットを作成する際の考慮事項 |Microsoft ドキュメント
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
ms.openlocfilehash: 3d0cbe19b85fc65c492f1e0ae377da94dad75baf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237898"
---
# <a name="considerations-when-creating-flat-file-message-schemas"></a><span data-ttu-id="3467a-102">ファイル メッセージ スキーマをフラットを作成する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="3467a-102">Considerations When Creating Flat File Message Schemas</span></span>
<span data-ttu-id="3467a-103">フラット ファイル メッセージのスキーマの扱いには、さまざまな注意点があります。</span><span class="sxs-lookup"><span data-stu-id="3467a-103">There are a number of considerations when working with flat file message schemas.</span></span> <span data-ttu-id="3467a-104">フラット ファイルのスキーマ全般に当てはまる注意点のほか、位置指定ベースまたは区切り文字ベースのレコード/フィールドに固有の注意点などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3467a-104">This includes considerations that apply to all flat file schemas, as well as considerations that apply specifically to positional records, delimited records, positional fields, or delimited fields.</span></span> <span data-ttu-id="3467a-105">また、特殊文字を通常のデータとして解釈させる方法も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3467a-105">There are also considerations about how to interpret otherwise special characters as regular data.</span></span> <span data-ttu-id="3467a-106">このセクションでは、これらの注意事項に関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="3467a-106">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3467a-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3467a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="3467a-108">フラット ファイル スキーマのコード ページ仕様</span><span class="sxs-lookup"><span data-stu-id="3467a-108">Code Page Specification for Flat File Schemas</span></span>](../core/code-page-specification-for-flat-file-schemas.md)  
  
-   [<span data-ttu-id="3467a-109">フラット ファイル スキーマでの処理の場合</span><span class="sxs-lookup"><span data-stu-id="3467a-109">Case Handling in Flat File Schemas</span></span>](../core/case-handling-in-flat-file-schemas.md)  
  
-   [<span data-ttu-id="3467a-110">文字範囲の制限</span><span class="sxs-lookup"><span data-stu-id="3467a-110">Restricted Character Ranges</span></span>](../core/restricted-character-ranges.md)  
  
-   [<span data-ttu-id="3467a-111">入れ子になった位置指定レコードおよび区切り記号付きレコード</span><span class="sxs-lookup"><span data-stu-id="3467a-111">Nested Positional and Delimited Records</span></span>](../core/nested-positional-and-delimited-records.md)  
  
-   [<span data-ttu-id="3467a-112">位置指定レコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="3467a-112">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)  
  
-   [<span data-ttu-id="3467a-113">区切り記号付きレコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="3467a-113">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)  
  
-   [<span data-ttu-id="3467a-114">フィールドに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3467a-114">Field Considerations</span></span>](../core/field-considerations.md)  
  
-   [<span data-ttu-id="3467a-115">フィールドの値の一部として特殊文字を解釈する方法</span><span class="sxs-lookup"><span data-stu-id="3467a-115">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)
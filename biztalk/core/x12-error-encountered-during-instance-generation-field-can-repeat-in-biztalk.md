---
title: インスタンスの生成中に発生したエラーは、フィールドを繰り返すことができますが、繰り返し区切り記号が定義されていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7a6783c-cb35-4ce8-9164-ec34ae500de1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c589c4abfe957b2b6515a1508bdf2da3cadd75a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394771"
---
# <a name="error-encountered-during-instance-generation--field-can-repeat-but-repetition-delimiter-has-not-been-defined"></a><span data-ttu-id="822ee-102">インスタンスの生成中に発生したエラー フィールドが繰り返すことができますが、繰り返し区切り記号が定義されていません</span><span class="sxs-lookup"><span data-stu-id="822ee-102">Error encountered during instance generation--field can repeat but repetition delimiter has not been defined</span></span>
## <a name="details"></a><span data-ttu-id="822ee-103">詳細</span><span class="sxs-lookup"><span data-stu-id="822ee-103">Details</span></span>  
  
|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="822ee-104">製品名</span><span class="sxs-lookup"><span data-stu-id="822ee-104">Product Name</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                   |
| <span data-ttu-id="822ee-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="822ee-105">Product Version</span></span> |                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                               |
|    <span data-ttu-id="822ee-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="822ee-106">Event ID</span></span>     |                                                           -                                                           |
|  <span data-ttu-id="822ee-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="822ee-107">Event Source</span></span>   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="822ee-108">EDI</span><span class="sxs-lookup"><span data-stu-id="822ee-108">EDI</span></span>                 |
|    <span data-ttu-id="822ee-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="822ee-109">Component</span></span>    |                                                      <span data-ttu-id="822ee-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="822ee-110">EDI Engine</span></span>                                                       |
|  <span data-ttu-id="822ee-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="822ee-111">Symbolic Name</span></span>  |                                                           -                                                           |
|  <span data-ttu-id="822ee-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="822ee-112">Message Text</span></span>   | <span data-ttu-id="822ee-113">インスタンスの生成中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="822ee-113">Error encountered during instance generation.</span></span> <span data-ttu-id="822ee-114">フィールド{0}繰り返すことができますが、繰り返し区切り記号が定義されていません。</span><span class="sxs-lookup"><span data-stu-id="822ee-114">The field {0} can repeat but repetition delimiter has not been defined.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="822ee-115">説明</span><span class="sxs-lookup"><span data-stu-id="822ee-115">Explanation</span></span>  
 <span data-ttu-id="822ee-116">このエラー/警告/情報イベントは、スキーマの指定どおり、表示されたフィールドを繰り返すことができますが、繰り返し区切り記号が定義されていないため、BizTalk Server が X12 メッセージ インスタンスを生成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="822ee-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an X12 message instance because the indicated field can repeat (as specified by the schema), but no repetition separator has been defined.</span></span> <span data-ttu-id="822ee-117">このイベントは、スキーマのフィールドに 1 を超えるのと同等な minOccurs が設定されているが、繰り返し区切り記号ではなく、標準識別子が定義されている場合に発生します </span><span class="sxs-lookup"><span data-stu-id="822ee-117">This occurs when a field in the schema has minOccurs equal to more than 1, but a Standard identifier has been defined, rather than a Repetition separator.</span></span> <span data-ttu-id="822ee-118">(EDIFACT インターチェンジの場合、既定で繰り返し区切り記号が定義されます)。</span><span class="sxs-lookup"><span data-stu-id="822ee-118">(For EDIFACT interchanges, a repetition separator is defined by default.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="822ee-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="822ee-119">User Action</span></span>  
 <span data-ttu-id="822ee-120">このエラーを解決するには、インターチェンジ受信者のパーティの [ISA セグメントの定義] ページの ISA11 で、標準識別子ではなく繰り返し区切り記号を選択し、区切り記号の文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="822ee-120">To resolve this error, select Repetition separator rather than Standard identifier for ISA11 in the ISA Segment Definition page for the party as interchange receiver, and enter a character for the separator.</span></span> <span data-ttu-id="822ee-121">インターチェンジにパーティが解決されていない場合は、グローバル プロパティの [ISA セグメントの定義] ページで繰り返し区切り記号を定義します (X12 インターチェンジの場合)。</span><span class="sxs-lookup"><span data-stu-id="822ee-121">If no party has been resolved for the interchange, define the repetition separator in the ISA Segment Definition page of the global properties (for X12 interchanges).</span></span>
---
title: "1 つまたは複数のエラー セグメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 340c722bc96ec8efdf2f48e6b40260aa5323e675
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="one-or-more-segments-in-error"></a><span data-ttu-id="ded02-102">エラーに 1 つ以上のセグメントが含まれています</span><span class="sxs-lookup"><span data-stu-id="ded02-102">One or more segments in error</span></span>
## <a name="details"></a><span data-ttu-id="ded02-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ded02-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ded02-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ded02-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ded02-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ded02-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ded02-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ded02-106">Event ID</span></span>|-|  
|<span data-ttu-id="ded02-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ded02-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ded02-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ded02-108"> EDI</span></span>|  
|<span data-ttu-id="ded02-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ded02-109">Component</span></span>|<span data-ttu-id="ded02-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ded02-110">EDI Engine</span></span>|  
|<span data-ttu-id="ded02-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ded02-111">Symbolic Name</span></span>|<span data-ttu-id="ded02-112">X12TsOneOrMoreSegmentsInErrorDescription</span><span class="sxs-lookup"><span data-stu-id="ded02-112">X12TsOneOrMoreSegmentsInErrorDescription</span></span>|  
|<span data-ttu-id="ded02-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ded02-113">Message Text</span></span>|<span data-ttu-id="ded02-114">エラーに 1 つ以上のセグメントが含まれています</span><span class="sxs-lookup"><span data-stu-id="ded02-114">One or more segments in error</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ded02-115">説明</span><span class="sxs-lookup"><span data-stu-id="ded02-115">Explanation</span></span>  
 <span data-ttu-id="ded02-116">このエラー/警告/情報イベントは、インターチェンジの 1 つ以上のセグメントが、それらのセグメントを管理するスキーマに準拠していなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ded02-116">This Error/Warning/Information event indicates that one or more segments in the interchange did not conform to the schema governing them.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ded02-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ded02-117">User Action</span></span>  
 <span data-ttu-id="ded02-118">このエラーを解決するには、どのセグメントがエラーになっているかを特定し、そのセグメントを管理するスキーマを開きます。その後、セグメントがエラーになっている理由をそのスキーマから判断します。</span><span class="sxs-lookup"><span data-stu-id="ded02-118">To resolve this error, determine which segment is in error, open the schema governing that segment, and determine from that schema why the segment is in error.</span></span>
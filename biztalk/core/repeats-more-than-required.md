---
title: 必要な複数の繰り返し |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fec52b5b-e95f-479e-8922-dcf17dcefee7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cb8f9e324c9d09e09649719c98e3f684b0d81f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268226"
---
# <a name="repeats-more-than-required"></a><span data-ttu-id="94333-102">繰り返しが必要な回数を上回っています</span><span class="sxs-lookup"><span data-stu-id="94333-102">Repeats more than required</span></span>
## <a name="details"></a><span data-ttu-id="94333-103">詳細</span><span class="sxs-lookup"><span data-stu-id="94333-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="94333-104">製品名</span><span class="sxs-lookup"><span data-stu-id="94333-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="94333-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="94333-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="94333-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="94333-106">Event ID</span></span>|-|  
|<span data-ttu-id="94333-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="94333-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="94333-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="94333-108"> EDI</span></span>|  
|<span data-ttu-id="94333-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="94333-109">Component</span></span>|<span data-ttu-id="94333-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="94333-110">EDI Engine</span></span>|  
|<span data-ttu-id="94333-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="94333-111">Symbolic Name</span></span>|<span data-ttu-id="94333-112">X12FeRepeatsMoreThanRequiredDescription</span><span class="sxs-lookup"><span data-stu-id="94333-112">X12FeRepeatsMoreThanRequiredDescription</span></span>|  
|<span data-ttu-id="94333-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="94333-113">Message Text</span></span>|<span data-ttu-id="94333-114">繰り返しが必要な回数を上回っています</span><span class="sxs-lookup"><span data-stu-id="94333-114">Repeats more than required</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="94333-115">説明</span><span class="sxs-lookup"><span data-stu-id="94333-115">Explanation</span></span>  
 <span data-ttu-id="94333-116">このエラー/警告/情報イベントは、X12 インターチェンジのループ内またはループ外にあるセグメントの繰り返しが、ドキュメント スキーマで必要な回数を上回っていたことを示します。</span><span class="sxs-lookup"><span data-stu-id="94333-116">This Error/Warning/Information event indicates that segments in an X12 interchange that are either inside or outside of a loop repeated more times than required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="94333-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="94333-117">User Action</span></span>  
 <span data-ttu-id="94333-118">このエラーを解決するには、インターチェンジのループの内側または外側にあるセグメントがスキーマで指定された回数繰り返されることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="94333-118">To resolve this error, make sure that the segments that are either inside or outside of a loop in the interchange repeat the numbers of times specified in the schema, and then resend the interchange.</span></span>
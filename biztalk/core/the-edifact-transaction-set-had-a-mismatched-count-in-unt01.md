---
title: "Edifact トランザクション セットが UNT01 に一致しないカウントが |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2859274-78e8-4e16-92b7-c143da6da421
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 180abe338441917afa6691400a02a42e88026052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a><span data-ttu-id="3682e-102">EDIFACT トランザクション セットの UNT01 に一致しないカウントがあります</span><span class="sxs-lookup"><span data-stu-id="3682e-102">The Edifact Transaction set had a mismatched count in UNT01</span></span>
## <a name="details"></a><span data-ttu-id="3682e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3682e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3682e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3682e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3682e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3682e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3682e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3682e-106">Event ID</span></span>|-|  
|<span data-ttu-id="3682e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3682e-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3682e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3682e-108"> EDI</span></span>|  
|<span data-ttu-id="3682e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3682e-109">Component</span></span>|<span data-ttu-id="3682e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="3682e-110">EDI Engine</span></span>|  
|<span data-ttu-id="3682e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3682e-111">Symbolic Name</span></span>|<span data-ttu-id="3682e-112">EfactUnhUntCountMismatch</span><span class="sxs-lookup"><span data-stu-id="3682e-112">EfactUnhUntCountMismatch</span></span>|  
|<span data-ttu-id="3682e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3682e-113">Message Text</span></span>|<span data-ttu-id="3682e-114">EDIFACT トランザクション セットの UNT01 に一致しないカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="3682e-114">The Edifact Transaction set had a mismatched count in UNT01.</span></span> <span data-ttu-id="3682e-115">UNT01 {0} でした、一方 {1} されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3682e-115">UNT01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="3682e-116">問題の修正が完了しました。</span><span class="sxs-lookup"><span data-stu-id="3682e-116">It has been corrected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3682e-117">説明</span><span class="sxs-lookup"><span data-stu-id="3682e-117">Explanation</span></span>  
 <span data-ttu-id="3682e-118">この警告は、セグメント カウントである UNT01 フィールドが、トランザクション セットのセグメント数に一致しなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3682e-118">This Warning indicates that the UNT01 field, which is the segment count, did not match the number of segments in the transaction set.</span></span> <span data-ttu-id="3682e-119">UNT01 の値が変更されたか壊れている、またはカウントの決定後にセグメントが追加あるいは削除されました。</span><span class="sxs-lookup"><span data-stu-id="3682e-119">Either the value of UNT01 was changed or corrupted, or segments were added or deleted after the count was determined.</span></span> <span data-ttu-id="3682e-120">送信パイプラインが UNT01 フィールドを正しいセグメント数にリセットし、インターチェンジを送信しました。</span><span class="sxs-lookup"><span data-stu-id="3682e-120">The send pipeline reset the UNT01 field to the correct number of segments, and then sent the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3682e-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3682e-121">User Action</span></span>  
 <span data-ttu-id="3682e-122">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3682e-122">No user action is necessary.</span></span>
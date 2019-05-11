---
title: Edifact トランザクション セットが UNT01 に一致しないカウントが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2859274-78e8-4e16-92b7-c143da6da421
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 428704c78c3d6b615f0272927b03fb57aa66d91b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298789"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a><span data-ttu-id="f2767-102">UNT01 に一致しないカウントがあります、Edifact トランザクション セット</span><span class="sxs-lookup"><span data-stu-id="f2767-102">The Edifact Transaction set had a mismatched count in UNT01</span></span>
## <a name="details"></a><span data-ttu-id="f2767-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f2767-103">Details</span></span>  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f2767-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f2767-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="f2767-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f2767-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    <span data-ttu-id="f2767-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f2767-106">Event ID</span></span>     |                                                                  -                                                                  |
|  <span data-ttu-id="f2767-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f2767-107">Event Source</span></span>   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f2767-108">EDI</span><span class="sxs-lookup"><span data-stu-id="f2767-108">EDI</span></span>                        |
|    <span data-ttu-id="f2767-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f2767-109">Component</span></span>    |                                                             <span data-ttu-id="f2767-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f2767-110">EDI Engine</span></span>                                                              |
|  <span data-ttu-id="f2767-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f2767-111">Symbolic Name</span></span>  |                                                      <span data-ttu-id="f2767-112">EfactUnhUntCountMismatch</span><span class="sxs-lookup"><span data-stu-id="f2767-112">EfactUnhUntCountMismatch</span></span>                                                       |
|  <span data-ttu-id="f2767-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f2767-113">Message Text</span></span>   | <span data-ttu-id="f2767-114">Edifact トランザクション セット UNT01 に一致しないカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="f2767-114">The Edifact Transaction set had a mismatched count in UNT01.</span></span> <span data-ttu-id="f2767-115">UNT01 が{0}されている一方、{1}します。</span><span class="sxs-lookup"><span data-stu-id="f2767-115">UNT01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="f2767-116">修正されています。</span><span class="sxs-lookup"><span data-stu-id="f2767-116">It has been corrected.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f2767-117">説明</span><span class="sxs-lookup"><span data-stu-id="f2767-117">Explanation</span></span>  
 <span data-ttu-id="f2767-118">この警告は、セグメントの数をある UNT01 フィールドが、トランザクション セットのセグメントの数と一致しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="f2767-118">This Warning indicates that the UNT01 field, which is the segment count, did not match the number of segments in the transaction set.</span></span> <span data-ttu-id="f2767-119">UNT01 の値が変更されたか壊れているか、またはセグメントの追加または数が決定された後に削除されました。</span><span class="sxs-lookup"><span data-stu-id="f2767-119">Either the value of UNT01 was changed or corrupted, or segments were added or deleted after the count was determined.</span></span> <span data-ttu-id="f2767-120">送信パイプラインでは、UNT01 フィールドを正しいセグメント数にリセットされ、インターチェンジが送信されます。</span><span class="sxs-lookup"><span data-stu-id="f2767-120">The send pipeline reset the UNT01 field to the correct number of segments, and then sent the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f2767-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f2767-121">User Action</span></span>  
 <span data-ttu-id="f2767-122">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f2767-122">No user action is necessary.</span></span>
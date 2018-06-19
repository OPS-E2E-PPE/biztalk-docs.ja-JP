---
title: X12 トランザクション セットの SE01 に一致しないカウントが |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a90079f5-5939-40b6-9756-d7943240c125
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41539f0492f90d3f7276b0d80af28c568593ef4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278706"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a><span data-ttu-id="ccf1f-102">X12 トランザクション セットの SE01 に一致しないカウントがあります</span><span class="sxs-lookup"><span data-stu-id="ccf1f-102">The X12 Transaction set had a mismatched count in SE01</span></span>
## <a name="details"></a><span data-ttu-id="ccf1f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ccf1f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ccf1f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ccf1f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ccf1f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ccf1f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ccf1f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ccf1f-106">Event ID</span></span>|-|  
|<span data-ttu-id="ccf1f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ccf1f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ccf1f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ccf1f-108"> EDI</span></span>|  
|<span data-ttu-id="ccf1f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ccf1f-109">Component</span></span>|<span data-ttu-id="ccf1f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ccf1f-110">EDI Engine</span></span>|  
|<span data-ttu-id="ccf1f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ccf1f-111">Symbolic Name</span></span>|<span data-ttu-id="ccf1f-112">X12StSeCountMismatch</span><span class="sxs-lookup"><span data-stu-id="ccf1f-112">X12StSeCountMismatch</span></span>|  
|<span data-ttu-id="ccf1f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ccf1f-113">Message Text</span></span>|<span data-ttu-id="ccf1f-114">X12 トランザクション セットの SE01 に一致しないカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="ccf1f-114">The X12 Transaction set had a mismatched count in SE01.</span></span> <span data-ttu-id="ccf1f-115">SE01 {0} でした、一方 {1} されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf1f-115">SE01 was {0}, whereas it should have been {1}.</span></span> <span data-ttu-id="ccf1f-116">問題の修正が完了しました。</span><span class="sxs-lookup"><span data-stu-id="ccf1f-116">It has been corrected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ccf1f-117">説明</span><span class="sxs-lookup"><span data-stu-id="ccf1f-117">Explanation</span></span>  
 <span data-ttu-id="ccf1f-118">この警告は、トランザクション セット トレーラー (SE01 フィールド) の数値が、インターチェンジのトランザクション セットのセグメント数と一致しなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ccf1f-118">This Warning indicates that the number in the transaction set trailer (SE01 field) did not match the number of segments in the transaction set of the interchange.</span></span> <span data-ttu-id="ccf1f-119">送信パイプラインは、SE01 フィールドのカウントを修正し、警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="ccf1f-119">The send pipeline corrects the count in the SE01 field and posts the warning.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ccf1f-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ccf1f-120">User Action</span></span>  
 <span data-ttu-id="ccf1f-121">必要なアクションはありません。</span><span class="sxs-lookup"><span data-stu-id="ccf1f-121">No action is necessary.</span></span>
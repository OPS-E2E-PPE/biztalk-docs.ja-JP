---
title: "含まれているセグメントの数が一致しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c868de02-fda7-4d84-be50-2c08cde0450c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01878c11c8464968b31a7f34ff75b5b494309f90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-included-segments-do-not-match"></a><span data-ttu-id="205a5-102">含まれているセグメントの数が一致しません</span><span class="sxs-lookup"><span data-stu-id="205a5-102">Number of included segments do not match</span></span>
## <a name="details"></a><span data-ttu-id="205a5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="205a5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="205a5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="205a5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="205a5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="205a5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="205a5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="205a5-106">Event ID</span></span>|-|  
|<span data-ttu-id="205a5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="205a5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="205a5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="205a5-108"> EDI</span></span>|  
|<span data-ttu-id="205a5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="205a5-109">Component</span></span>|<span data-ttu-id="205a5-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="205a5-110">EDI Engine</span></span>|  
|<span data-ttu-id="205a5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="205a5-111">Symbolic Name</span></span>|<span data-ttu-id="205a5-112">X12TsIncludedSegCountMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="205a5-112">X12TsIncludedSegCountMismatchDescription</span></span>|  
|<span data-ttu-id="205a5-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="205a5-113">Message Text</span></span>|<span data-ttu-id="205a5-114">含まれているセグメントの数が一致しません</span><span class="sxs-lookup"><span data-stu-id="205a5-114">Number of included segments do not match</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="205a5-115">説明</span><span class="sxs-lookup"><span data-stu-id="205a5-115">Explanation</span></span>  
 <span data-ttu-id="205a5-116">このエラー/警告/情報イベントは、X12 インターチェンジのトランザクション セットのセグメント数が、トランザクション セット トレーラー (SE01 フィールド) の数と等しくないことを示します。</span><span class="sxs-lookup"><span data-stu-id="205a5-116">This Error/Warning/Information event indicates that the number of segments in the transaction set of the X12 interchange does not equal the number in the transaction set trailer (SE01 field).</span></span> <span data-ttu-id="205a5-117">これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="205a5-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="205a5-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="205a5-118">User Action</span></span>  
 <span data-ttu-id="205a5-119">このエラーを解決するには、インターチェンジ トレーラーの SE01 フィールドの数が、トランザクション セットのセグメント数と同じであることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="205a5-119">To resolve this error, make sure that the number in the SE01 field of the interchange trailer is the same as the number of segments in the transaction set, and then resend the interchange.</span></span>
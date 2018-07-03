---
title: セグメントの繰り返し回数が許容される最小より小さい |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8ca6c3d-f923-49bc-b5d9-65dc2d7adab1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29df069fefbf6e47b711d37884c00a40318e96b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008835"
---
# <a name="segment-repeats-less-than-the-minimum-allowed-number-of-times"></a><span data-ttu-id="8a550-102">セグメントの繰り返し回数が許容される最小値を下回っています</span><span class="sxs-lookup"><span data-stu-id="8a550-102">Segment repeats less than the minimum allowed number of times</span></span>
## <a name="details"></a><span data-ttu-id="8a550-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8a550-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8a550-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8a550-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8a550-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8a550-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8a550-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8a550-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8a550-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8a550-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8a550-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8a550-108"> EDI</span></span> |
|    <span data-ttu-id="8a550-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8a550-109">Component</span></span>    |                                       <span data-ttu-id="8a550-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8a550-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="8a550-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8a550-111">Symbolic Name</span></span>  |                        <span data-ttu-id="8a550-112">X12SeSegmentRepeatsLessTimesDescription</span><span class="sxs-lookup"><span data-stu-id="8a550-112">X12SeSegmentRepeatsLessTimesDescription</span></span>                         |
|  <span data-ttu-id="8a550-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8a550-113">Message Text</span></span>   |             <span data-ttu-id="8a550-114">セグメントの繰り返し回数が許容される最小値を下回っています</span><span class="sxs-lookup"><span data-stu-id="8a550-114">Segment repeats less than the minimum allowed number of times</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="8a550-115">説明</span><span class="sxs-lookup"><span data-stu-id="8a550-115">Explanation</span></span>  
 <span data-ttu-id="8a550-116">このエラー/警告/情報イベントは、インターチェンジのセグメントの繰り返しが、ドキュメント スキーマで必要とされる最小回数を下回っているため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8a550-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because a segment in the interchange does not repeat the minimum number of times required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a550-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8a550-117">User Action</span></span>  
 <span data-ttu-id="8a550-118">このエラーを解決するには、インターチェンジの送信者に対して、セグメントの繰り返しが少なくともドキュメント スキーマで必要とされる最小回数となるよう依頼し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="8a550-118">To resolve this error, have the sender of the interchange as repetition of the segment so that it repeats at least the minimum number of times required by the document schema, and then resend the interchange.</span></span>
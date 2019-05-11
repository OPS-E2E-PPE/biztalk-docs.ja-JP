---
title: 未満の最小回数の許容回数をループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0be21d1d-86da-456b-83e6-c91f1dc9fb48
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27188ecbf45cb147d718a7349c123ce195c4a1a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380499"
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a><span data-ttu-id="5b23a-102">ループの繰り返し回数が許容される最小値を下回っています</span><span class="sxs-lookup"><span data-stu-id="5b23a-102">Loop repeats less than the minimum allowed number of times</span></span>
## <a name="details"></a><span data-ttu-id="5b23a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5b23a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5b23a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5b23a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5b23a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5b23a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5b23a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5b23a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5b23a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5b23a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5b23a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="5b23a-108">EDI</span></span> |
|    <span data-ttu-id="5b23a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5b23a-109">Component</span></span>    |                                       <span data-ttu-id="5b23a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="5b23a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="5b23a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5b23a-111">Symbolic Name</span></span>  |                          <span data-ttu-id="5b23a-112">X12SeLoopRepeatsLessTimesDescription</span><span class="sxs-lookup"><span data-stu-id="5b23a-112">X12SeLoopRepeatsLessTimesDescription</span></span>                          |
|  <span data-ttu-id="5b23a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5b23a-113">Message Text</span></span>   |               <span data-ttu-id="5b23a-114">ループの繰り返し回数が許容される最小値を下回っています</span><span class="sxs-lookup"><span data-stu-id="5b23a-114">Loop repeats less than the minimum allowed number of times</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="5b23a-115">説明</span><span class="sxs-lookup"><span data-stu-id="5b23a-115">Explanation</span></span>  
 <span data-ttu-id="5b23a-116">このエラー/警告/情報イベントは、メッセージのスキーマで規定された最小回数に満たない繰り返し回数を持つループがインターチェンジに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="5b23a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated fewer times than the minimum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b23a-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5b23a-117">User Action</span></span>  
 <span data-ttu-id="5b23a-118">このエラーを解決するには、インターチェンジのループの繰り返し回数がメッセージのスキーマで指定されたループの minOccurs プロパティの回数以上であることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="5b23a-118">To resolve this error, make sure that the loop repeats in the interchange at least the number of times in the minOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>
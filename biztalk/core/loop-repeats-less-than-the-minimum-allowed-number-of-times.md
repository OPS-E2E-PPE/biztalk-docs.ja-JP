---
title: "小さい値の回数が許容される最小の繰り返しをループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0be21d1d-86da-456b-83e6-c91f1dc9fb48
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00d9b38712d8b8336daa9357bd20eb34148691b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a><span data-ttu-id="3f721-102">ループの繰り返し回数が許容される最小値を下回っています</span><span class="sxs-lookup"><span data-stu-id="3f721-102">Loop repeats less than the minimum allowed number of times</span></span>
## <a name="details"></a><span data-ttu-id="3f721-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3f721-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f721-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3f721-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3f721-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3f721-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3f721-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3f721-106">Event ID</span></span>|-|  
|<span data-ttu-id="3f721-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3f721-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3f721-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3f721-108"> EDI</span></span>|  
|<span data-ttu-id="3f721-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3f721-109">Component</span></span>|<span data-ttu-id="3f721-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="3f721-110">EDI Engine</span></span>|  
|<span data-ttu-id="3f721-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3f721-111">Symbolic Name</span></span>|<span data-ttu-id="3f721-112">X12SeLoopRepeatsLessTimesDescription</span><span class="sxs-lookup"><span data-stu-id="3f721-112">X12SeLoopRepeatsLessTimesDescription</span></span>|  
|<span data-ttu-id="3f721-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3f721-113">Message Text</span></span>|<span data-ttu-id="3f721-114">ループの繰り返し回数が許容される最小値を下回っています</span><span class="sxs-lookup"><span data-stu-id="3f721-114">Loop repeats less than the minimum allowed number of times</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f721-115">説明</span><span class="sxs-lookup"><span data-stu-id="3f721-115">Explanation</span></span>  
 <span data-ttu-id="3f721-116">このエラー/警告/情報イベントは、メッセージのスキーマで規定された最小回数に満たない繰り返し回数を持つループがインターチェンジに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3f721-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated fewer times than the minimum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f721-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3f721-117">User Action</span></span>  
 <span data-ttu-id="3f721-118">このエラーを解決するには、インターチェンジのループの繰り返し回数がメッセージのスキーマで指定されたループの minOccurs プロパティの回数以上であることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="3f721-118">To resolve this error, make sure that the loop repeats in the interchange at least the number of times in the minOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>
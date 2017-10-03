---
title: "最大回数を超えてループが発生した |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 827ab88a2676cd052ee1ea3ba3a4bd7bd80f1912
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="loop-occurs-over-maximum-times"></a><span data-ttu-id="77354-102">最大回数を超えてループが発生します</span><span class="sxs-lookup"><span data-stu-id="77354-102">Loop Occurs Over Maximum Times</span></span>
## <a name="details"></a><span data-ttu-id="77354-103">詳細</span><span class="sxs-lookup"><span data-stu-id="77354-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77354-104">製品名</span><span class="sxs-lookup"><span data-stu-id="77354-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="77354-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="77354-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="77354-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77354-106">Event ID</span></span>|-|  
|<span data-ttu-id="77354-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="77354-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="77354-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="77354-108"> EDI</span></span>|  
|<span data-ttu-id="77354-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77354-109">Component</span></span>|<span data-ttu-id="77354-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="77354-110">EDI Engine</span></span>|  
|<span data-ttu-id="77354-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="77354-111">Symbolic Name</span></span>|<span data-ttu-id="77354-112">X12LoopOccursOverMaximumTimesDescription</span><span class="sxs-lookup"><span data-stu-id="77354-112">X12LoopOccursOverMaximumTimesDescription</span></span>|  
|<span data-ttu-id="77354-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="77354-113">Message Text</span></span>|<span data-ttu-id="77354-114">最大回数を超えてループが発生します。</span><span class="sxs-lookup"><span data-stu-id="77354-114">Loops Occurs Over Maximum Times</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77354-115">説明</span><span class="sxs-lookup"><span data-stu-id="77354-115">Explanation</span></span>  
 <span data-ttu-id="77354-116">このエラー/警告/情報イベントは、メッセージのスキーマで規定された最大回数を超える繰り返し回数を持つループがインターチェンジに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="77354-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated more times than the maximum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77354-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="77354-117">User Action</span></span>  
 <span data-ttu-id="77354-118">このエラーを解決するには、インターチェンジのループの繰り返し回数がメッセージのスキーマで指定されたループの maxOccurs プロパティの回数以下であることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="77354-118">To resolve this error, make sure that the loop repeats in the interchange no more than the number of times in the maxOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>
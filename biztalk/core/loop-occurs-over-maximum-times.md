---
title: 最大回数を超えてループが発生します |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6587e5b5dcef641f37f24005fe594a084e5de12d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979603"
---
# <a name="loop-occurs-over-maximum-times"></a><span data-ttu-id="f1005-102">最大回数を超えてループが発生します</span><span class="sxs-lookup"><span data-stu-id="f1005-102">Loop Occurs Over Maximum Times</span></span>
## <a name="details"></a><span data-ttu-id="f1005-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f1005-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f1005-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f1005-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f1005-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f1005-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f1005-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f1005-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f1005-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f1005-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f1005-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f1005-108"> EDI</span></span> |
|    <span data-ttu-id="f1005-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f1005-109">Component</span></span>    |                                       <span data-ttu-id="f1005-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="f1005-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f1005-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f1005-111">Symbolic Name</span></span>  |                        <span data-ttu-id="f1005-112">X12LoopOccursOverMaximumTimesDescription</span><span class="sxs-lookup"><span data-stu-id="f1005-112">X12LoopOccursOverMaximumTimesDescription</span></span>                        |
|  <span data-ttu-id="f1005-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f1005-113">Message Text</span></span>   |                            <span data-ttu-id="f1005-114">最大回数を超えてループが発生します</span><span class="sxs-lookup"><span data-stu-id="f1005-114">Loops Occurs Over Maximum Times</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="f1005-115">説明</span><span class="sxs-lookup"><span data-stu-id="f1005-115">Explanation</span></span>  
 <span data-ttu-id="f1005-116">このエラー/警告/情報イベントは、メッセージのスキーマで規定された最大回数を超える繰り返し回数を持つループがインターチェンジに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f1005-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated more times than the maximum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f1005-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f1005-117">User Action</span></span>  
 <span data-ttu-id="f1005-118">このエラーを解決するには、インターチェンジのループの繰り返し回数がメッセージのスキーマで指定されたループの maxOccurs プロパティの回数以下であることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="f1005-118">To resolve this error, make sure that the loop repeats in the interchange no more than the number of times in the maxOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>